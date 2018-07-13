# Single Data Science VM #

This project demonstrates launching the Microsoft Azure Data Science VM as a standalone node.
The Data Science VM may be used as the base image in most CycleCloud clusters.



## Pre-Requisites ##


This sample requires the following:

  1. CycleCloud must be installed and running.

     a. If this is not the case, see the CycleCloud QuickStart Guide for
        assistance.

  2. The CycleCloud CLI must be installed and configured for use.

  3. You must have access to log in to CycleCloud.

  4. You must have access to upload data and launch instances in your chosen
     Cloud Provider account.

  5. You must have access to a configured CycleCloud "Locker" for Project Storage
     (Cluster-Init and Chef).

  6. Optional: To use the `cyclecloud project upload <locker>` command, you must
     have a Pogo configuration file set up with write-access to your locker.

     a. You may use your preferred tool to interact with your storage "Locker"
        instead.


## Configuring the Project ##


The first step is to configure the project for use with your storage locker:

  1. Open a terminal session with the CycleCloud CLI enabled.

  2. Switch to the data-science-vm project directory.


## Deploying the Project ##


To upload the project (including any local changes) to your target locker, run the
`cyclecloud project upload` command from the project directory.  The expected output looks like
this:

``` bash

   $ cyclecloud project upload my_locker
   Sync completed!

```


**IMPORTANT**

For the upload to succeed, you must have a valid Pogo configuration for your target Locker.


## Importing the Cluster Template ##


To import the cluster:

 1. Open a terminal session with the CycleCloud CLI enabled.

 2. Switch to the data-science-vm project directory.

 3. Run ``cyclecloud import_template Data-Science-VM -f templates/data-science-vm.txt``.
    The expected output looks like this:
    
    ``` bash
    
    $ cyclecloud import_template Data-Science-VM -f templates/data-science-vm.txt --force
    Importing template Data-Science-VM....
    ----------------------------
    Data-Science-VM : *template*
    ----------------------------
    Keypair:
    Cluster nodes:
	dsvm: off
    Total nodes: 1
    ```


