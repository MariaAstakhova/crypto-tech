# Marketplace

Application allowing to view and book attendence to upcoming learn-tech showcases and workshops.

### Using Marketplace Slack App

Executing /Show command in any channel will display upcoming workhops and showcases.

Clicking "Attend" button on the right of the workhop will log your attendance.

Clicking "Unattend" button will remove your attendance.


### Development Notes
Marketplace is using Airtable Marketplace table with a NOTOUCHY view as the database. 
The application is running on AWS ECS. Amazon resources are created with terraform.

Env variables for airtable and Amazon AWS are stored in CircleCI. CircleCI automatically updates the application on AWS upon every push to master branch.
To clone the application to a different AWS account:

  - Set Env variables in CircleCI 
  - Terraform init and apply terraform code to build S3 bucket resource
  - Add a dynamodb resource in tf file, init and apply
  - Run terraform code that refers to dynamodb in S3 backend 
  - Use .CircleCI config.yml to build the rest of the environment using CircleCI

Refer to https://docs.google.com/document/d/10LaLHCNbx6u4RvodIXD8MH892vNoFfmqGBGVzdcAtQU/edit?usp=sharing for more info.

