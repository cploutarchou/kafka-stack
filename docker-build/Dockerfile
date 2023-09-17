# Use a specific version of the openjdk image
FROM openjdk:11.0.16-jre-slim-buster

# Update and install required packages
RUN apt-get update && \
    apt-get install -y curl && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Kafka and Scala versions
ENV KAFKA_VERSION 3.3.1
ENV SCALA_VERSION 2.13 

# Download Kafka and prepare directories
RUN mkdir -p /tmp-download/kafka /kafka-data/kraft-combined-logs /kafka && \
    curl "https://archive.apache.org/dist/kafka/${KAFKA_VERSION}/kafka_${SCALA_VERSION}-${KAFKA_VERSION}.tgz" \
    -o /tmp-download/kafka/kafka.tgz && \
    tar -xvzf /tmp-download/kafka/kafka.tgz -C /kafka --strip 1 && \
    rm -r /tmp-download

# Copy start script and make it executable
COPY start-kafka.sh /usr/bin
RUN chmod +x /usr/bin/start-kafka.sh


# Metadata as described above, adjust accordingly
LABEL maintainer="cploutarchou@gmail.com" \
      version="1.0" \
      description="Kafka ${KAFKA_VERSION} on OpenJDK 11"

CMD ["start-kafka.sh"]
