# Deployment Files Collection

Currently contains:
- ClickHouse
- Apache Kafka
- PostgreSQL
- ELK
- RabbitMQ

This repository contains Docker Compose files for deploying various services. Below is the structure of the repository:

- **clickhouse**
  - *config*
    - `users.xml`: Configuration file for ClickHouse users.
  - `docker-compose.yml`: Docker Compose file for ClickHouse deployment.

- **kafka**
  - `docker-compose.yml`: Docker Compose file for Kafka deployment.

- **postgresql**
  - `docker-compose.yml`: Docker Compose file for PostgreSQL deployment.

- **ELK**
  - *config*
    - *logstash*
        - `Logstash.conf`: Can be used to read logs from .json file
        - `Logstash_from_http.conf`: Can be used to send logs via http API
        - `Logstash.yml`: Standart logstash config with hosts settings
    - *elasticsearch*
        - `elasticsearch.yml`: Elasticsearch main configuration file
    - *kibana*
        - `kibana.yml`: Kibana main configuration file
  - `docker-compose.complete.yml`: Docker Compose file for ELK deployment.

- **rabbitmq**
  - `docker-compose.yml`: Compose file for RabbitMQ deployment

- **mongodb**
  - `docker-compose.yml`: Compose file for MongoDB deployment

## Usage

### ClickHouse

1. Navigate to the `clickhouse` directory:
    ```bash
    cd clickhouse
    ```

2. Start ClickHouse service:
    ```bash
    docker-compose up --build -d
    ```

### Kafka

1. Navigate to the `kafka` directory:
    ```bash
    cd kafka
    ```

2. Start Kafka service:
    ```bash
    docker-compose up --build -d
    ```

### PostgreSQL

1. Navigate to the `postgresql` directory:
    ```bash
    cd postgresql
    ```

2. Start PostgreSQL service:
    ```bash
    docker-compose up --build -d
    ```


### RabbitMQ

1. Navigate to the `rabbitmq` directory:
    ```bash
    cd rabbitmq
    ```

2. Start rabbitmq service:
    ```bash
    docker-compose up --build -d
    ```

### MongoDB

1. Navigate to the `mongodb` directory:
    ```bash
    cd mongodb
    ```

2. Start rabbitmq service:
    ```bash
    docker-compose up --build -d
    ```

### ELK

#### Before deploy

1. Choose type of logs input u need (.json or http API) and reconfigure config in docker-compose file

2. If i choose .json file config, u should specify path to shared folder, where ur logs will be located


#### Deploy

1. Navigate to the `ELK` directory:
    ```bash
    cd ELK
    ```

2. Start ELK services:
    ```bash
    docker-compose up --build -d
    ```

3. Set passwords in elasticsearch container (by default, for local development set "localpassword")
    ```bash
    docker container exec -it elasticsearch /bin/bash

    /usr/share/elasticsearch/bin/elasticsearch-setup-passwords interactive
    ```

## Notes

- Make sure you have Docker and Docker Compose installed on your system.
- Customize configuration files according to your requirements.
- Feel free to explore each service's directory for additional configuration details.
