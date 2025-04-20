# Terraform

terraform state file maps resoucess from hte configuration to real words object.
state locking -- lock the state file while executing write operation to prevent concurrent modification and state cirruption.
backend - Thebackend in terraform determines how and where your state file is stored by defalut terraform stores them locally. 
.tfstate file track the current state of your infrastructure.
to download the statefile to your local machine-
    terraform state pull > terraform.tfstate


    we store our state file in consul whic is keyvalue storage system  . it is organised as a hierarchy key structure similar to file system.

    Below is the block-->

    terraform {
      backend "consul" {
        address      = "consul.mmt.mmt:8500"
        scheme       = "http"
        path         = "DEVOPS/terraform/Devops"
        access_token = "ac6361fa-19c1-c91b-69b0-24fcb63800ff"
        lock         = true
      gzip         = true
  }
}


