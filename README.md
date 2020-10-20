# Supplemental material for Intro to Kubernetes study group

## Create a Docker image and upload it to GCR

To build the image, go to app directory and run:
`docker build -t simpleapp:2.0 .`

To run container locally use this command:
`docker run -d -p 8888:8888 simpleapp:2.0`

Tag your image and push it to GCR:
`docker tag simpleapp:2.0 gcr.io/containers-studygroup/simpleapp:2.0`
`docker push gcr.io/containers-studygroup/simpleapp:2.0`

## Create a cluster in GKE and connect to the cluster:
`gcloud container clusters get-credentials <cluster-name> --zone <us-east1-b> --project <containers-studygroup>`

## Create deployment
Go to k8s_resources folder and run:
`kubectl apply -f deployment.yaml`

## Create load balancer service
`kubectl apply -f service.yaml`