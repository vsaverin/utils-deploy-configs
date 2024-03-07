# Deployment Files Collection

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
    - `logstash.conf`: Standart logstash config with logs settings
    - `logstash.yml`: Standart logstash config with hosts settings
  - `docker-compose.yml`: Docker Compose file for ClickHouse deployment.

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

### ELK

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
