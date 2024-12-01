# Big Data Architecture with Docker Compose

This repository contains a Docker Compose configuration to set up a Big Data Lambda architecture using the following technologies:  
- **Hadoop**: For distributed storage and processing.  
- **Kafka**: For real-time data streaming.  
- **Spark**: For batch and real-time data processing.  
- **PostgreSQL**: For relational database storage.  
- **TimescaleDB**: For time-series data storage and analysis.  

## Prerequisites  
Before running this setup, ensure you have the following installed on your system:  
- [Docker](https://docs.docker.com/get-docker/)  
- [Docker Compose](https://docs.docker.com/compose/install/)  

## Setup  

### 1. Clone the Repository  
Clone this repository to your local machine:  
```bash  
git clone https://github.com/HamzaMAIDINE/mini_prjt_docker.git
cd <repository-folder>  
```  

### 2. Start the Services  
Run the following command to start the entire stack:  
```bash  
docker-compose up -d  
```  

This will launch all services in detached mode.  

### 3. Verify Services  
Once the services are running, you can access the following:  
- **Hadoop Namenode UI**: [http://localhost:9870](http://localhost:9870)  
- **Spark Master UI**: [http://localhost:8080](http://localhost:8080)  
- **PostgreSQL**: Accessible at `localhost:5432`  
- **TimescaleDB**: Accessible at `localhost:5433`  

### 4. Stop the Services  
To stop and remove the containers, run:  
```bash  
docker-compose down  
```  

## Configuration  

### Environment Variables  
You can modify environment variables for each service directly in the `docker-compose.yml` file to suit your needs.  

### Data Persistence  
- Hadoop data is persisted in the `namenode-data` and `datanode-data` volumes.  
- PostgreSQL data is stored in the `pgdata` volume.  
- TimescaleDB data is stored in the `timescale-data` volume.  

### Accessing PostgreSQL and TimescaleDB  
Use a database client like `psql`, DBeaver, or pgAdmin to connect to the databases:  
- **PostgreSQL**  
  - Host: `localhost`  
  - Port: `5432`  
  - User: `admin`  
  - Password: `admin`  
  - Database: `bigdata`  
- **TimescaleDB**  
  - Host: `localhost`  
  - Port: `5433`  
  - User: `admin`  
  - Password: `admin`  
  - Database: `timeseries`  

## Troubleshooting  

### Check Logs  
To debug any issues, view the logs of a specific container:  
```bash  
docker logs <container_name>  
```  

### Restart a Service  
If a service fails, restart it:  
```bash  
docker-compose restart <service_name>  
```  

