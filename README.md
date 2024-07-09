# elasticompose

## Objective:
Efficiently deploy and manage the ELK (Elasticsearch, Logstash, Kibana) stack using Docker Compose, enabling streamlined logging and monitoring solutions for various applications and environments.

## Components:
### 1. Elasticsearch
Serves as the search and analytics engine, storing and indexing log data for quick and efficient retrieval.
### 2. Logstash
Collects, processes, and transforms log data before sending it to Elasticsearch.
### 3. Kibana
Visualizes data stored in Elasticsearch through customizable dashboards and graphs.
### 4. Filebeat
Lightweight shipper for forwarding and centralizing log data to Logstash and Elasticsearch.
### 5. Docker
Containerizes the entire ELK stack, making it easy to deploy, manage, and scale.

## Pre-requisites:
- Ensure Docker is installed on your system.
- Docker Compose is required to manage multi-container Docker applications. Install Docker Compose to orchestrate the ELK stack services.
- At least 4GB of RAM is recommended to run the ELK stack smoothly.
- Ensure you have the necessary permissions to install software and manage Docker containers on your system.

## .env Configuration
Since there are some secret credentials that need to stay hidden they have been added inside the `.env` file. This is an example of the contents inside the file:
```shell
ELASTIC_VERSION=[string]
ELASTIC_PASSWORD=[string]
KIBANA_SYSTEM_PASSWORD=[string]
LOGSTASH_INTERNAL_PASSWORD=[string]
FILEBEAT_INTERNAL_PASSWORD=[string]
```

## Steps:
### 1. Set Up the Environment
Install Docker and Docker Compose on your system and ensure your system meets the memory, CPU, and storage requirements.

### 2. Prepare Configuration Files:
Create or obtain configuration files for Elasticsearch, Logstash, Kibana, and Filebeat and ensure these files are tailored to your specific needs, such as log paths and indices.

### 3. Create a Docker Compose File:
Define a docker-compose.yml file to orchestrate the ELK stack services. Include configurations for Elasticsearch, Logstash, Kibana, and Filebeat in the file.

### 4. Start the ELK Stack:
Navigate to the directory containing your docker-compose.yml file and run the `docker-compose up -d` command to start the ELK Stack services in detached mode.

### 5. Verify Service Availability:
Check the status of the ELK stack services using the `docker-compose ps` command. Use `curl` or a web browser to verify that Elasticsearch and Kibana are accessible.

### 6. Set Up User Authentication:
Access the Elasticsearch container using the `docker exec -it elasticsearch /bin/bash` command.

### 7. Configure Kibana:
Log in to Kibana using the `elastic` user credentials and set up index patterns and visualizations to monitor and analyze your data.

### 8. Test the Setup:
Send sample log data to ensure the entire pipeline (Filebeat -> Logstash -> Elasticsearch -> Kibana) is working correctly and verify that logs are being indexed in Elasticsearch and visualized in Kibana.

### Documentation
#### [Install Docker Engine](https://docs.docker.com/engine/install/) - This section describes how to install Docker Engine on Linux, also known as Docker CE.
#### [Overview of installing Docker Compose](https://docs.docker.com/compose/install/) - This page contains summary information about the available options for installing Docker Compose.
#### [Dockerfiles](https://github.com/elastic/dockerfiles) - Dockerfiles for the official Elastic Stack images.