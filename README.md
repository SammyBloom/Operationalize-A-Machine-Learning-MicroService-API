[![SammyBloom](https://circleci.com/gh/SammyBloom/Operationalize-A-Machine-Learning-MicroService-API.svg?style=svg)](https://circleci.com/gh/SammyBloom/Operationalize-A-Machine-Learning-MicroService-API)

## Project Summary

This project applies the skills acquired in the Udacity Cloud DevOps Engineering Nanodegree course to operationalize a Machine Learning Microservice API. 

It includes a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project shows my ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

Your project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project you will:
* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

You can find a detailed [project rubric, here](https://review.udacity.com/#!/rubrics/2576/view).

**The implementation of this project showcases my abilities to operationalize production microservices.**

---

## Setup the Environment

* Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/Scripts/activate
```
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Other Files
1. Make Predictions: `./make_prediction.sh`
2. Docker Output file `./outout_txt_files/docker_out.txt`
3. Kubernetes Output file `./outout_txt_files/kubernetes_out.txt`
4. Requirements file states the requirements for dependency installations `./requirements.txt`
5. File that contains commands to upload docker images `./upload_docker.sh`
6. Create working directory and install dependencies `./Dockerfile` 
7. File for linting and tests `./Makefile`

### Kubernetes Steps

* Setup and Configure Docker locally `docker build --tag=latest .`
* Setup and Configure Kubernetes locally `minikube start`
* Create Flask app in Container `docker run -p 8080:80 latest`
* Run via kubectl `kubectl run app1 --image=$dockerpath --port=80`
* Check pod status `kubectl get pod`
* Stop Kubernetes Cluster `minikube close`
* Delete Kubernetes Cluster `minikube delete`
