# Commands Used

## Set region and zone

```bash
gcloud config set compute/region us-west1
gcloud config set compute/zone us-west1-b
```

## Create a Cloud Storage bucket

```bash
export PROJECT_ID=$(gcloud config get-value project)

gcloud storage buckets create gs://$PROJECT_ID-bucket --location=US
```

## Create a Compute Engine VM

```bash
gcloud compute instances create my-instance \
    --zone=us-west1-b \
    --machine-type=e2-medium \
    --image-family=debian-12 \
    --image-project=debian-cloud \
    --boot-disk-type=pd-balanced \
    --boot-disk-size=10GB \
    --tags=http-server
```

## Create a persistent disk

```bash
gcloud compute disks create mydisk \
    --size=200GB \
    --zone=us-west1-b
```

## Attach the persistent disk

```bash
gcloud compute instances attach-disk my-instance \
    --disk=mydisk \
    --zone=us-west1-b
```

## SSH into the VM

```bash
gcloud compute ssh my-instance
```

## Update the operating system

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

## Enable NGINX

```bash
sudo systemctl enable nginx
```

## Check NGINX status

```bash
sudo systemctl status nginx
```

## View VM information

```bash
gcloud compute instances list
```
