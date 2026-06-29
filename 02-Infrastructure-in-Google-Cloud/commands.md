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
