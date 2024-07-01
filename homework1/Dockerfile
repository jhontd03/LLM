# Usa una imagen base de Elasticsearch
FROM docker.elastic.co/elasticsearch/elasticsearch:8.4.3

# Reduce la memoria asignada a JVM
RUN echo "-Xms512m" >> /usr/share/elasticsearch/config/jvm.options && \
    echo "-Xmx512m" >> /usr/share/elasticsearch/config/jvm.options

# Configura Elasticsearch para un uso reducido de recursos
RUN echo "xpack.ml.enabled: false" >> /usr/share/elasticsearch/config/elasticsearch.yml && \
    echo "xpack.monitoring.collection.enabled: false" >> /usr/share/elasticsearch/config/elasticsearch.yml

# Exponer el puerto necesario
EXPOSE 9200 9300

# Comando para iniciar Elasticsearch
CMD ["/usr/share/elasticsearch/bin/elasticsearch"]

# winpty docker run -it -p 9200:9200 -p 9300:9300 -e "xpack.security.enabled=false" -e "discovery.type=single-node" --name es-optimized elasticsearch
