# terraform-web-server
Deploys a simple Apache web server instance in AWS using terraform

One command builds the infrastructure.
* terraform apply

One command tears down the infrastructure.
* terraform destroy

One command runs the tests
* pytest --driver PhantomJS

One command handles installing the required build environment
* bash install-preqs.sh


# Setup and prerequisites

There are a number of dev ops tools which are required in the build environment.

## Linux Version
* Fedora 25.  Other versions may work.  But testing has only been done on Fedora 25.

* dnf and git must already be installed.

Clone using https protocol
*  git clone https://github.com/dokadon/terraform-web-server.git

Your build system should be up to date with the latest packages installed

The included install script installs all tools needed if they do not already exist.

You will need sudo access to install them
* terraform
* python
* python-pip
* wget
* unzip
* nodejs

To install the prerequisites execute
* bash install-preqs.sh

An AWS user account with awscli access priveleges is needed
You can get one here https://aws.amazon.com

Export your AWS user crendentials into the env using
* export AWS_ACCESS_KEY_ID=[AWS_ACCESS_KEY_ID]
* export AWS_SECRET_ACCESS_KEY=[AWS_SECRET_ACCESS_KEY]

# Building the web server infrastructure

After you have set up your dev ops env

To build the web server
* cd web-server
* terraform apply

# Running the tests

The test framework uses
* pytest
* Selenium
* PhantomJS

To run the tests from within the web-server directory execute
* pytest --driver PhantomJS

# Removing the web server infrastructure

When you are ready to remove your infrastructure execute
* terraform destroy
