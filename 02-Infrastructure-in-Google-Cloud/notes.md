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

- # Lab 5 – User Authentication: Identity-Aware Proxy (GSP499)

## Objective
Learn how to protect a Cloud Run application using Identity-Aware Proxy (IAP), retrieve authenticated user information, and verify the identity using cryptographic JWT verification.

## Concepts Learned

### Identity-Aware Proxy (IAP)
- Restricts access to web applications.
- Authenticates users using their Google account.
- Only authorized users can access the application.

### Cloud Run
- Serverless platform for deploying containerized applications.
- Hosts the sample Python Flask application.

### User Identity Headers
IAP automatically adds these request headers:
- X-Goog-Authenticated-User-Email
- X-Goog-Authenticated-User-ID

These headers allow the application to identify the authenticated user.

### JWT Verification
To prevent header spoofing, the application verifies:

- X-Goog-IAP-JWT-Assertion

using Google's public keys.

## Lab Flow

### Task 1
- Download the lab files.
- Deploy the HelloWorld application to Cloud Run.
- Enable Identity-Aware Proxy.
- Grant yourself the IAP-Secured Web App User role.
- Verify only authorized users can access the application.

### Task 2
- Deploy the HelloUser application.
- Read user email and user ID from IAP headers.
- Display authenticated user information.
- Disable IAP to demonstrate header spoofing.
- Test spoofing using curl.

### Task 3
- Deploy the HelloVerifiedUser application.
- Configure the IAP_AUDIENCE environment variable.
- Verify JWT tokens using Google's public keys.
- Enable IAP again.
- Grant the IAP service account the Cloud Run Invoker role.
- Confirm verified email and user ID are displayed.

## Key Learning

- IAP protects applications without modifying application logic.
- User identity can be retrieved from request headers.
- Request headers alone are not secure.
- JWT verification ensures identity information cannot be spoofed.
- Cloud Run integrates easily with Identity-Aware Proxy.

# Lab 6 – Cloud IAM: Qwik Start (GSP064)

## Objective
Learn how Google Cloud Identity and Access Management (IAM) controls user permissions by assigning, removing, and testing different roles.

## Concepts Learned

### Cloud IAM
Identity and Access Management (IAM) controls who can access Google Cloud resources and what actions they can perform.

### Basic IAM Roles

- Owner
  - Full control over project resources.
  - Can manage IAM permissions.

- Editor
  - Can create, modify and delete resources.

- Viewer
  - Read-only access.

- Browser
  - Can browse project resources but cannot access resource contents.

### Storage Object Viewer
A service-specific role that allows users to view Cloud Storage objects without granting access to the entire project.

## Lab Flow

### Task 1
- Sign in using two accounts.
- Username 1 is the Project Owner.
- Username 2 is the Project Viewer.
- Explore IAM roles and permissions.

### Task 2
- Create a Cloud Storage bucket.
- Upload sample.txt.
- Verify Username 2 can view the bucket.

### Task 3
- Remove Project Viewer role from Username 2.
- Confirm Username 2 loses project access.

### Task 4
- Grant Storage Object Viewer role to Username 2.
- Verify Username 2 can still access bucket objects using Cloud Shell.

## Key Learning

- IAM follows the Principle of Least Privilege.
- Project-level roles apply to all resources.
- Service-specific roles provide limited access.
- Removing a project role immediately revokes project permissions.
- Users should receive only the permissions necessary to perform their tasks.
