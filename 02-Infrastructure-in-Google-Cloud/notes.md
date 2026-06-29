# Infrastructure in Google Cloud - Notes

## Lab 1 - Cloud Storage

### What I Learned
- Configured the default compute region.
- Created a Cloud Storage bucket.
- Uploaded and downloaded files.
- Managed object permissions.
- Deleted objects from a bucket.

### Key Concepts
- Cloud Storage stores data as objects inside buckets.
- Bucket names must be globally unique.


---

## Lab 2 - Cloud SQL for MySQL

### What I Learned

- Created a Cloud SQL for MySQL instance.
- Connected to the instance using Cloud Shell.
- Created a MySQL database called `guestbook`.
- Created a table and inserted sample records.
- Queried data using SQL statements.
- Learned how Cloud SQL provides managed relational database services on Google Cloud.

### Key Concepts

- Cloud SQL is a fully managed relational database service.
- MySQL databases can be created and managed through Google Cloud.
- Cloud Shell can connect directly to Cloud SQL instances.
- SQL commands can be used to create databases, tables, insert data, and retrieve records.

---

## Lab 3 - Introduction to APIs in Google Cloud

### What I Learned

- Learned the basics of APIs and how applications communicate.
- Explored the Google API Library.
- Enabled the Google Fitness API.
- Used OAuth 2.0 to authenticate API requests.
- Created a Cloud Storage bucket using the Cloud Storage JSON/REST API.
- Uploaded an image to the bucket using a REST API request with `curl`.

### Key Concepts

- APIs allow applications to communicate with each other.
- REST APIs use HTTP methods such as GET, POST, PUT, and DELETE.
- JSON is commonly used to exchange data between clients and servers.
- OAuth 2.0 provides secure authentication for accessing Google APIs.
- Cloud Storage REST API can create buckets and upload objects without using the Cloud Console.

- ---

## Lab 4 - Pub/Sub: Qwik Start (Python)

### What I Learned

- Learned the basics of Google Cloud Pub/Sub messaging.
- Created a Python virtual environment.
- Installed the Google Cloud Pub/Sub Python client library.
- Created a Pub/Sub topic and subscription.
- Published multiple messages to a topic.
- Received messages using a Python subscriber.

### Key Concepts

- Pub/Sub is a fully managed messaging service for asynchronous communication.
- A **topic** receives messages from publishers.
- A **subscription** allows subscribers to receive messages from a topic.
- Publishers send messages to topics, while subscribers pull or receive those messages.
- Python client libraries simplify interaction with Google Cloud services.
