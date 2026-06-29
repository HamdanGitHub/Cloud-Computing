# Infrastructure in Google Cloud - Commands

---

## Lab 1 - Cloud Storage

### Check authenticated account

```bash
gcloud auth list
```

### Check active project

```bash
gcloud config list project
```

### Set default compute region

```bash
gcloud config set compute/region us-west1
```

### Create a Cloud Storage bucket

```bash
gcloud storage buckets create gs://bucket-name
```

### Download a file from the internet

```bash
curl IMAGE_URL --output filename.jpg
```

### Upload a file to Cloud Storage

```bash
gcloud storage cp filename.jpg gs://bucket-name
```

### Download a file from Cloud Storage

```bash
gcloud storage cp gs://bucket-name/filename.jpg .
```

### Copy an object to another folder

```bash
gcloud storage cp gs://bucket-name/filename.jpg gs://bucket-name/folder-name/
```

### List bucket contents

```bash
gcloud storage ls gs://bucket-name
```

### View object details

```bash
gcloud storage ls -l gs://bucket-name/filename.jpg
```

### Make an object publicly readable

```bash
gcloud storage objects update gs://bucket-name/filename.jpg \
--add-acl-grant=entity=allUsers,role=READER
```

### Remove public access

```bash
gcloud storage objects update gs://bucket-name/filename.jpg \
--remove-acl-grant=allUsers
```


---

## Lab 2 - Cloud SQL for MySQL

### Connect to a Cloud SQL instance

```bash
gcloud sql connect myinstance --user=root
```

### Create a database

```sql
CREATE DATABASE guestbook;
```

### Use the database

```sql
USE guestbook;
```

### Create a table

```sql
CREATE TABLE entries (
    guestName VARCHAR(255),
    content VARCHAR(255),
    entryID INT NOT NULL AUTO_INCREMENT,
    PRIMARY KEY(entryID)
);
```

### Insert records

```sql
INSERT INTO entries (guestName, content)
VALUES ("first guest", "I got here!");

INSERT INTO entries (guestName, content)
VALUES ("second guest", "Me too!");
```

### Query records

```sql
SELECT * FROM entries;
```

### Delete an object

```bash
gcloud storage rm gs://bucket-name/filename.jpg
```

---

## Lab 3 - Introduction to APIs in Google Cloud

### Set the default region

```bash
gcloud config set compute/region europe-west4
```

### Create a JSON configuration file

```bash
nano values.json
```

### View files

```bash
ls
```

### Set OAuth token

```bash
export OAUTH2_TOKEN=<YOUR_TOKEN>
```

### Get Project ID

```bash
export PROJECT_ID=$(gcloud config get-value project)
```

### Create a Cloud Storage bucket using REST API

```bash
curl -X POST --data-binary @values.json \
-H "Authorization: Bearer $OAUTH2_TOKEN" \
-H "Content-Type: application/json" \
"https://www.googleapis.com/storage/v1/b?project=$PROJECT_ID"
```

### Get the image path

```bash
realpath demo-image.png
```

### Set image path

```bash
export OBJECT=/home/<username>/demo-image.png
```

### Set bucket name

```bash
export BUCKET_NAME=<PROJECT_ID>-bucket
```

### Upload an image using the Cloud Storage REST API

```bash
curl -X POST --data-binary @$OBJECT \
-H "Authorization: Bearer $OAUTH2_TOKEN" \
-H "Content-Type: image/png" \
"https://www.googleapis.com/upload/storage/v1/b/$BUCKET_NAME/o?uploadType=media&name=demo-image"
```

---

## Lab 4 - Pub/Sub: Qwik Start (Python)

### Install Virtual Environment

```bash
sudo apt-get install -y virtualenv
```

### Create a Virtual Environment

```bash
python3 -m venv venv
```

### Activate the Virtual Environment

```bash
source venv/bin/activate
```

### Install Pub/Sub Python Library

```bash
pip install --upgrade google-cloud-pubsub
```

### Clone the Sample Repository

```bash
git clone https://github.com/googleapis/python-pubsub.git
```

### Navigate to the Sample Directory

```bash
cd python-pubsub/samples/snippets
```

### Verify the Project ID

```bash
echo $GOOGLE_CLOUD_PROJECT
```

### View the Publisher Script

```bash
cat publisher.py
```

### Display Publisher Help

```bash
python publisher.py -h
```

### Create a Pub/Sub Topic

```bash
python publisher.py $GOOGLE_CLOUD_PROJECT create MyTopic
```

### List Topics

```bash
python publisher.py $GOOGLE_CLOUD_PROJECT list
```

### Create a Subscription

```bash
python subscriber.py $GOOGLE_CLOUD_PROJECT create MyTopic MySub
```

### List Subscriptions

```bash
python subscriber.py $GOOGLE_CLOUD_PROJECT list-in-project
```

### Display Subscriber Help

```bash
python subscriber.py -h
```

### Publish Messages

```bash
gcloud pubsub topics publish MyTopic --message "Hello"

gcloud pubsub topics publish MyTopic --message "Publisher's name is Hamdan"

gcloud pubsub topics publish MyTopic --message "Publisher likes to eat Nasi Lemak"

gcloud pubsub topics publish MyTopic --message "Publisher thinks Pub/Sub is awesome"
```

### Receive Messages

```bash
python subscriber.py $GOOGLE_CLOUD_PROJECT receive MySub
```
