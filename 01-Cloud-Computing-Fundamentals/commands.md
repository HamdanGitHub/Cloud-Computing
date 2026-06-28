# Google Cloud Computing Foundations - Useful Commands

This file contains commonly used Google Cloud and Kubernetes commands from the hands-on labs.

---

# Project Information

## View active project

```bash
gcloud config get-value project
```

## List configurations

```bash
gcloud config list
```

## List authenticated accounts

```bash
gcloud auth list
```

---

# Cloud Storage

## Create a bucket

```bash
gcloud storage buckets create gs://PROJECT_ID-bucket --location=US
```

## List buckets

```bash
gcloud storage buckets list
```

## Upload a file

```bash
gcloud storage cp filename.txt gs://PROJECT_ID-bucket
```

## List bucket contents

```bash
gcloud storage ls gs://PROJECT_ID-bucket
```

---

# Compute Engine

## Create a virtual machine

```bash
gcloud compute instances create my-instance \
    --machine-type=e2-medium \
    --image-family=debian-12 \
    --image-project=debian-cloud
```

## List VM instances

```bash
gcloud compute instances list
```

## SSH into a VM

```bash
gcloud compute ssh my-instance --zone=ZONE
```

---

# Persistent Disk

## Create a persistent disk

```bash
gcloud compute disks create mydisk \
    --size=200GB \
    --zone=ZONE
```

## Attach the disk

```bash
gcloud compute instances attach-disk my-instance \
    --disk=mydisk \
    --zone=ZONE
```

---

# NGINX

## Update packages

```bash
sudo apt update
```

## Install NGINX

```bash
sudo apt install nginx -y
```

## Start NGINX

```bash
sudo systemctl start nginx
```

## Enable NGINX on boot

```bash
sudo systemctl enable nginx
```

## Check NGINX status

```bash
sudo systemctl status nginx
```

---

# App Engine

## Deploy application

```bash
gcloud app deploy
```

## Open deployed application

```bash
gcloud app browse
```

---

# Cloud Functions

## Deploy a Cloud Function

```bash
gcloud functions deploy FUNCTION_NAME \
    --gen2 \
    --runtime=nodejs22 \
    --region=REGION \
    --source=. \
    --entry-point=ENTRY_POINT
```

## Describe a function

```bash
gcloud functions describe FUNCTION_NAME --region=REGION
```

---

# Kubernetes Engine (GKE)

## Get cluster credentials

```bash
gcloud container clusters get-credentials CLUSTER_NAME --zone=ZONE
```

## Create a deployment

```bash
kubectl create deployment hello-server \
    --image=gcr.io/google-samples/hello-app:1.0
```

## View deployments

```bash
kubectl get deployments
```

## View pods

```bash
kubectl get pods
```

## Expose deployment

```bash
kubectl expose deployment hello-server \
    --type=LoadBalancer \
    --port=8080
```

## View services

```bash
kubectl get service
```

## Delete deployment

```bash
kubectl delete deployment hello-server
```

---

# General Kubernetes

## View cluster information

```bash
kubectl cluster-info
```

## View nodes

```bash
kubectl get nodes
```

---

# Helpful Commands

## Display current directory

```bash
pwd
```

## List files

```bash
ls
```

## Change directory

```bash
cd folder-name
```

## Create directory

```bash
mkdir folder-name
```

## Clear terminal

```bash
clear
```

---

# Notes

- Replace `PROJECT_ID` with your Google Cloud project ID.
- Replace `ZONE` with the zone provided in the lab.
- Replace `REGION` with the region provided in the lab.
- Replace `FUNCTION_NAME`, `ENTRY_POINT`, and `CLUSTER_NAME` with the appropriate names for your lab.
