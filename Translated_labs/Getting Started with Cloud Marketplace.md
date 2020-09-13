# Lab: Google Cloud Fundamentals: Getting Started with Cloud Marketplace

## Overview

In this lab, you will replicate the operation of using Cloud Marketplace on the Cloud Shell to deploy a LAMP stack on a Compute Engine instance.
### Steps
1. Sign in to google cloud platform using your qwiklabs credentials
2. Click on the cloud shell icon to activate the web command line

3. Create an instance in the region and zone of your choice e.g :us-central1 and us-central1-c using the following commands:
gcloud compute instances create lampstack-1 --zone=us-central1-a --machine-type=f1-micro \
--subnet=default --network-tier=PREMIUM --tags=http-server --image=debian-10-buster-v20200902 \
--image-project=debian-cloud --boot-disk-size=10GB --boot-disk-type=pd-standard \
--boot-disk-device-name=lampstack-1

4. Connect to your instance through SSH:
glcoud compute ssh lampstack-1 --zone=us-central1-c

5. Install Apache2 on your instance:
sudo apt-get update
sudo apt-get install apache2
6. Test the installed Apache2 by copying the external IP address from your previously created instance
http://[YOUR_EXTERNAL_IP_ADDRESS]