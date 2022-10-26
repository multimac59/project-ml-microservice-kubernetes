[![CircleCI](https://dl.circleci.com/status-badge/img/gh/multimac59/project-ml-microservice-kubernetes/tree/master.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/multimac59/project-ml-microservice-kubernetes/tree/master)

## Project Overview

In this project, we will apply the skills we have acquired in this course to operationalize a Machine Learning Microservice API. 

Here we have pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). 

This project tests our ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

Project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. This Project:
* tests project code using linting
* uses dockerfile to containerize this application
* deploys containerized application using Docker and make a prediction
* improves the log statements in the source code for this application
* configures Kubernetes and creates a Kubernetes cluster
* deploys a container using Kubernetes and make a prediction
* uploads a complete Github repo with CircleCI to indicate that your code has been tested

---

## Setup the Environment

* Create a virtualenv with Python 3.7 and activate it.  
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```
* Run `make install` to install the necessary dependencies. It uses command pip install -r requirements.txt for installing all the necessary python packages.

### Running python script app.py

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`


### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl

## Project Structure

* .circleci: This is the directory for CICD pipeline with the help of circleci. This directory contains config.yml having workflow, jobs and instructions require for running pipeline.
* evidences: this directory contains screenshots: 
    * circle_ci_passed.png: shows CICD pipeline successfully completed and passed.
    * image_upload_docker_hub.png: shows docker image is uploaded successfully to docker hub.
* model_data: It contains trained machine learning model for predicting housing prices.
* output_txt_files: It contains following files:
    * docker_out.txt: having output when applicaiton runs in docker
    * kubernetes_out.txt: having output when app runs in Kubernetes
    * upload_image_log.txt: having output shows docker image is uploaded successfully to docker hub.
* app.py: python application script
* Dockerfile: uses this file to deploy an image for the application to be run in docker container.
* make_redictions.sh: shell script which provides input for housing price prediction.
* Makefile: having useful commands to setup, install environment and lint the application code.
requirements.txt: having all the packages and their versions need to be installed for running the application.
run_docker.sh: shell script to build and run application in docker container.
run_kubernetes.sh: shell script to build and run application in kubernetes.
upload_docker.sh: shell script having commands to upload image to docker hub.