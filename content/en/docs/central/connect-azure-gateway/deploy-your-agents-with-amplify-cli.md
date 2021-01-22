---
title: Deploy your agents with AMPLIFY CLI
linkTitle: Deploy your agents with AMPLIFY CLI
draft: false
weight: 10
description: Learn how to deploy your agents using AMPLIFY CLI so that you can
  manage your Azure Gateway environment within AMPLIFY Central.
---
## Before you start

* Read [AMPLIFY Central Azure Gateway connected overview](/docs/central/connect-azure-gateway/)
* You will need information on Azure

    * The region that the Azure Gateway resources are hosted in
    * The bucket that the Resources will be uploaded to
    * The logging configuration setup on Azure Gateway
    * The configuration of Azure Config Service
* It is recommended that you have access to the Azure CLI command line to run the necessary setup commands

## Objectives

Learn how to quickly install and run your Discovery and Traceability agents with basic configuration using AMPLIFY Central CLI.

## AMPLIFY Central CLI prerequisites

* Node.js 8 LTS or later
* Access to npm package (for installing AMPLIFY cli)
* Access to login.axway.com on port 443
* Minimum AMPLIFY Central CLI version: 0.5.0 (check version using `amplify central --version`)

For more information, see [Install AMPLIFY Central CLI](/docs/central/cli_central/cli_install/).

## Installing the agents

### Step 1: Folder preparation

Create an empty directory where AMPLIFY CLI will generate files. Run all AMPLIFY Central CLI from this directory.

### Step 2: Identify yourself to AMPLIFY Platform with AMPLIFY CLI

To use Central CLI to log in with your AMPLIFY Platform credentials, run the following command:

```shell
amplify auth login
```

A browser automatically opens.
Enter your valid credentials (email address and password). Once the “Authorization Successful” message is displayed, go back to AMPLIFY CLI. The browser may be closed at this point.

If you are a member of multiple AMPLIFY organizations, you may have to choose an organization.

{{< alert title="Note" color="primary" >}}If you do not have a graphical environment, forward the display to an X11 server (Xming or similar tools) using the `export DISPLAY=myLaptop:0.0` command.{{< /alert >}}

### Step 3: Run the agents' install procedure

Azure agents are delivered in a Docker image provided by Axway. You can run them from any Docker container that can access the AMPLIFY Platform and Azure Gateway.
The AMPLIFY Central CLI will guide you through the configuration of the agents. Cloud formation templates are provided to help you setup either an EC2 architecture or an ECS-fargate architecture. You can also decide to not use any of them and deploy the Docker images in your own Docker container architecture.
