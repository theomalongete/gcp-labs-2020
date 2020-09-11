Google Cloud Computing via Qwiklabs (2020)
================================================

**Website: [Qwiklabs](https://theguestlistapp.co.za/)**

Labs
------------------------------
**The following labs that exist in the Qwiklabs:**

### Associate Cloud Engineer: Learning Phase 1 Main Track Channel (2020) ### 

Google Cloud Platform Fundamentals - Core Infrastructure
------------------------------

  i. ~~GCP Fundamentals: Getting Started with Cloud Marketplace~~
  ii. ~~GCP Fundamentals: Getting Started with Compute Engine~~
  . ~~GCP Fundamentals: Getting Started with Cloud Storage and Cloud SQL~~
  4. ~~GCP Fundamentals: Getting Started with GKE~~
  5. ~~GCP Fundamentals: Getting Started with App Engine~~
  6. ~~GCP Fundamentals: Getting Started with Deployment Manager and Cloud Monitoring~~
  7. ~~GCP Fundamentals: Getting Started with BigQuery~~

Essential Google Cloud Infrastructure: Foundation
------------------------------

  1. ~~Console and Cloud Shell~~
  2. Infrastructure Preview
  3. VPC Networking
  4. Implement Private Google Access and Cloud NAT
  5. Creating Virtual Machines
  6. Working with Virtual Machines

Essential Google Cloud Infrastructure: Core Services
------------------------------

  1. ~~Cloud IAM~~
  2. ~~Implementing Cloud SQL~~
  3. ~~Examining Billing data with BigQuery~~
  4. ~~Error Reporting and Debugging~~

Elastic Google Cloud Infrastructure: Scaling and Automation
------------------------------

  1. Virtual Private Networks (VPN)
  2. Configuring an HTTP Load Balancer with Autoscaling
  3. Automating the Deployment of Infrastructure Using Terraform


Labs: Translaion to Code
------------------------------
**The following labs that exist in the Qwiklabs:**

### Associate Cloud Engineer: Learning Phase 1 Main Track Channel (2020) ### 

LAB: GCP Fundamentals: Getting Started with Cloud Storage and Cloud SQL
------------------------------
***Objectives***

In this lab, you learn how to perform the following tasks:
	- Create a Cloud Storage bucket and place an image into it.
	- Create a Cloud SQL instance and configure it.
	- Connect to the Cloud SQL instance from a web server.
	- Use the image in the Cloud Storage bucket on a web page.

***STEPS***

1. Create a Cloud Storage bucket and place an image into it.
	-  gsutil mb gs://theo-bucket
	- gsutil mb cp Documents/theo.png gs://theo-bucket

2. Create a Cloud SQL instance and configure it
	- gcloud sql instance create theo-db --instance-id 'theo-sql' --region 'asia-east1' --machine-type 'n1-standard-1'  --storage-type 'HDD'

3. Connect to the Cloud SQL instance from a web server.
	- mysql--host=192.162.3.1 --user=theo --password [Enter password]

4. Use the image in the Cloud Storage bucket on a web page.
	- gsutil cp gs://theo-bucket/theo.png Documents/theo1.png

LAB: GCP Fundamentals: Getting Started with Cloud Storage and Cloud SQL
------------------------------

***Objectives***

In this lab, you learn how to perform the following tasks:
	- Initialize App Engine.
	- Preview an App Engine application running locally in Cloud Shell.
	- Deploy an App Engine application, so that others can reach it.
	- Disable an App Engine application, when you no longer want it to be visible.

***STEPS***

1. Initialize App Engine.
	- $PROJECT=theo-test
	- gcloud config set project $PROJECT
	- git clone https://github.com/GoogleCloudPlatform/python-docs-sample
	- cd python-docs-samples/appengine/standard_python3/hello_world

2. Preview an App Engine application running locally in Cloud Shell.
	- sudo apt-get update
	- sudo apt-get install virtualenv
	- virtualenv -p python3 venv
	- source venv/bin/activate
	- pip install  -r requirements.txt
	- python main.py
	- gcloud app browse

3. Deploy an App Engine application, so that others can reach it.
	- cd ~/python-docs-samples/appengine/standard_python3/hello_world
	- gcloud app deploy ./index.yaml ./app.yaml --version='1.1'

4. Disable an App Engine application, when you no longer want it to be visible.
	- gcloud app versions stop 1.1