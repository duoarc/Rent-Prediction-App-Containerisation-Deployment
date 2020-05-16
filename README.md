[![CircleCI](https://circleci.com/gh/duoarc/Rent-Prediction-App-Containerisation-Deployment.svg?style=svg)](https://github.com/duoarc/Rent-Prediction-App-Containerisation-Deployment)

This project operationalizes a machine learning microservice using kubernetes, which is an open-source system for automating the management of containerized applications. A pre-trained sklearn model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on the data source site. This project operationalizes a Python flask app—in a provided file, app.py—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

## _Instructions_

1) Clone this repo
 `git clone https://github.com/duoarc/Rent-Prediction-App-Containerisation-Deployment.git`

2) Install [python](https://www.python.org/) if not already installed and run this command to create a virtual environment and activate it
`make setup`

3) Install the project dependencies
`make install`

4) Run this command to lint the project files
`make lint`

5) Run this script to build a docker image for the app and start the app in a docker container:
`./run_docker.sh`

6)Run this script to get a prediction from the app running in the Docker container:

`./make_prediction.sh`

7) Run this script to upload the docker image to your Docker hub account. Note you'll have to edit the script and change the Docker ID to yours:

`./upload_docker.sh`

8) Run this script to run the service in a kubernetes cluster. You'll be making use of my image repo. You can edit the script and change to your image repo on Docker hub if you've built and pushed your image. This script will be run twice to activate the port forwarding. Give some minutes after first run so that the pod can be up and running before attempting port forwarding:
`./run_kubernetes.sh`

9) Run this script to get a prediction from the app running in the Kubernetes Cluster after port forwarding is successful:
`./make_prediction.sh `
