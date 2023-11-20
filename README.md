# Automated Incremental Updates for Machine Learning Models

In this repository, we demonstrate a comprehensive approach to incrementally incorporate new data into a machine learning model in an automated manner, with a focus on minimizing the associated overhead. The process involves updating the model while it is actively serving predictions in a production environment.

## Tools Utilized

This project relies on three powerful tools:

1. **Apache Kafka:** A distributed messaging platform that facilitates sequential logging of streaming data into topic-specific feeds. Other applications can then tap into these feeds.

2. **Apache Airflow:** A task scheduling platform enabling the creation, orchestration, and monitoring of data workflows.

3. **MLFlow:** An open-source tool that assists in tracking machine learning experiments, including logging parameters, results, models, and data for each trial.

## Workflow Overview

The workflow can be broken down into the following steps:

1. **Setting up the Environment and Training an Initial Model:**
   - Establish the necessary environment using Docker containers.
   - Train an initial machine learning model.

2. **Simulating Streaming Data:**
   - Use Kafka to simulate streaming data by pushing data to a Kafka feed.

3. **Periodically Updating the Model:**
   - Extract data from the Kafka feed at regular intervals.
   - Utilize the extracted data to update the machine learning model.
   - Evaluate the updated model's performance relative to the current version.
   - If the updated model outperforms the current version, deploy it for use.

4. **Logging Results with MLFlow:**
   - Log the results, model parameters, and sample characteristics of each update run using MLFlow.

## Project Structure

The project is structured as follows:


Certainly! Below is the content you can use for your README.md file:

markdown
Copy code
# Automated Incremental Updates for Machine Learning Models

In this repository, we demonstrate a comprehensive approach to incrementally incorporate new data into a machine learning model in an automated manner, with a focus on minimizing the associated overhead. The process involves updating the model while it is actively serving predictions in a production environment.

## Tools Utilized

This project relies on three powerful tools:

1. **Apache Kafka:** A distributed messaging platform that facilitates sequential logging of streaming data into topic-specific feeds. Other applications can then tap into these feeds.

2. **Apache Airflow:** A task scheduling platform enabling the creation, orchestration, and monitoring of data workflows.

3. **MLFlow:** An open-source tool that assists in tracking machine learning experiments, including logging parameters, results, models, and data for each trial.

## Workflow Overview

The workflow can be broken down into the following steps:

1. **Setting up the Environment and Training an Initial Model:**
   - Establish the necessary environment using Docker containers.
   - Train an initial machine learning model.

2. **Simulating Streaming Data:**
   - Use Kafka to simulate streaming data by pushing data to a Kafka feed.

3. **Periodically Updating the Model:**
   - Extract data from the Kafka feed at regular intervals.
   - Utilize the extracted data to update the machine learning model.
   - Evaluate the updated model's performance relative to the current version.
   - If the updated model outperforms the current version, deploy it for use.

4. **Logging Results with MLFlow:**
   - Log the results, model parameters, and sample characteristics of each update run using MLFlow.

## Project Structure

The project is structured as follows:

project_folder
├── dags
│ └── src
│ ├── data
│ ├── models
│ └── preprocessing
├── data
│ ├── to_use_for_training
│ ├── used_for_training
├── models
│ ├── current_model
│ └── archive
├── airflow_docker
├── mlflow_docker
└── docker_compose.yml

# Instructions for Running the Project

1. Use Docker Compose to set up multi-container applications by running the following commands:

docker compose -f docker-compose-project.yml build
docker compose -f docker-compose-project.yml up


2. Access the Airflow and MLFlow dashboards in your browser through `localhost:8080` and `localhost:5000`, respectively.

3. Activate each DAG on the Airflow dashboard to train the initial model, push streaming data to Kafka, and update the model at regular intervals.

## Acknowledgments

This project leverages the capabilities of Kafka, Airflow, and MLFlow to automate the process of incorporating new data into a machine learning model. .

