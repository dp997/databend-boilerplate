
# Databend Boilerplate Project
This project provides a boilerplate setup for the Databend platform with a MinIO backend.

## Overview
The project uses Docker Compose to create three main services:
* **MinIO**: provides S3-compatible storage
* **Storage Setup**: creates a MinIO bucket and inserts files into the bucket
* **Databend**: the Databend platform

## Prerequisites
To use this project, you will need to have Docker and Docker Compose installed on your machine.

## Environment Variables
The project uses the following environment variables:
* `MINIO_ROOT_USER`: the root user for MinIO
* `MINIO_ROOT_PASSWORD`: the root password for MinIO
* `MINIO_BUCKET`: the name of the MinIO bucket to create
* `DATABEND_USER`: the default user for Databend
* `DATABEND_PASSWORD`: the default password for Databend

## Usage
To start the services, run the following command in the project directory:
```bash
docker-compose up
```
This will create and start the MinIO, Storage Setup, and Databend containers.

## Services
### MinIO
The MinIO service is exposed on ports 9000 and 9001. You can access the MinIO console at `http://localhost:9000`.

### Storage Setup
The Storage Setup service creates a MinIO bucket and inserts files from the `source-data` directory into the bucket.

### Databend
The Databend service is exposed on ports 3307, 8000, 8124, 8900, and 8080. You can access the Databend web interface at `http://localhost:8000`.

## Notes
Make sure to set the environment variables before starting the services. You can do this by creating a `.env` file in the project directory with the following format:
```makefile
MINIO_ROOT_USER=<your_minio_root_user>
MINIO_ROOT_PASSWORD=<your_minio_root_password>
MINIO_BUCKET=<your_minio_bucket>
DATABEND_USER=<your_databend_user>
DATABEND_PASSWORD=<your_databend_password>
```
Replace `<your_minio_root_user>`, `<your_minio_root_password>`, `<your_minio_bucket>`, `<your_databend_user>`, and `<your_databend_password>` with your actual credentials.

To spin up the containers, use `docker compose up` command specifying your `.env` file, for example:
`docker compose --env-file .env up`
