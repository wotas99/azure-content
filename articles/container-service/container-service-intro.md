<properties
   pageTitle="Azure Container Service Introduction | Microsoft Azure"
   description="Azure Container Service provides a way to simplify the creation, configuration, and management of a cluster of virtual machines that are preconfigured to run containerized applications."
   services="container-service"
   documentationCenter=""
   authors="rgardler"
   manager="timlt"
   editor=""
   tags="acs, azure-container-service"
   keywords="Docker, Containers, Micro-services, Mesos, Azure"/>

<tags
   ms.service="container-service"
   ms.devlang="na"
   ms.topic="article"
   ms.tgt_pltfrm="na"
   ms.workload="na"
   ms.date="02/16/2016"
   ms.author="rogardle"/>

# Azure Container Service introduction

Azure Container Service makes it simpler for you to create,
configure, and manage a cluster of virtual machines that are
preconfigured to run containerized applications. It uses an optimized configuration of popular open-source scheduling and orchestration tools. This enables you to use your existing skills, or draw upon a large and growing body of community expertise, to deploy and manage container-based applications on Microsoft Azure.

<br />
![Azure Container Service provides a means to manage containerized applications on multiple hosts on Azure.](./media/acs-intro/acs-cluster.png)
<br /><br />

Azure Container Service leverages the Docker container format to ensure that your application containers are fully portable. It also supports your choice of Marathon and DC/OS or Docker Swarm so that you can scale these applications to thousands of containers, or even tens of thousands.

By using Azure Container Service, you can take advantage of the
enterprise-grade features of Azure, while still maintaining application portability--including portability at the orchestration layers.

Using Azure Container Service
-----------------------------

Our goal with Azure Container Service is to provide a container
hosting environment by using open-source tools and technologies that are popular among our customers today. To this end, we expose the standard API endpoints for your chosen orchestrator. By using these endpoints, you can leverage any software that is capable of talking to those endpoints. For example, in the case of the Docker Swarm endpoint, you might choose to use the Docker command-line interface (CLI). For DC/OS, you might choose to use the DCOS CLI.

Creating a Docker cluster by using Azure Container Service
-------------------------------------------------------

To begin using Azure Container Service, you deploy an Azure Container Service cluster by using an Azure Resource Manager template. You can configure this deployment with different size and availability options, by using either DC/OS or Docker Swarm. You can deploy Azure Resource Manager templates through the Azure portal by using the Azure CLI, or with PowerShell. The templates can also be modified to include additional or advanced Azure configuration. For more information on deploying an Azure Container Service cluster, see [Deploy an Azure Container Service cluster](container-service-deployment.md).

Deploying an application
------------------------

Azure Container Service provides a choice of either Docker Swarm or DC/OS for orchestration.

### Using DC/OS

DC/OS is an open-source project that is housed at the Apache Software
Foundation. It lists some of the [biggest names in
IT](http://mesos.apache.org/documentation/latest/powered-by-mesos/) as
users and contributors.

![Azure Container Service configured for Swarm showing agents and masters.](media/acs-intro/dcos.png)

DC/OS includes an impressive feature set:

-   Scalability to 10,000's of nodes

-   Fault-tolerant replicated master and slaves using Apache ZooKeeper

-   Support for Docker-formatted containers

-   Native isolation between tasks with Linux containers

-   Multiresource scheduling (memory, CPU, disk, and ports)

-   Java, Python, and C++ APIs for developing new parallel applications

-   A web UI for viewing cluster state

DC/OS supports a large number of
[frameworks](http://mesos.apache.org/documentation/latest/frameworks/)
that you can use for scheduling workloads on Azure Container
Service. By default, Azure Container Service includes the Marathon and Chronos frameworks.

#### Using Marathon and Chronos

Marathon is a cluster-wide init and control system for services in
cgroups--or, in the case of Azure Container Service, Docker-formatted containers. It is an ideal partner to Chronos, which is a fault-tolerant job scheduler for DC/OS that handles dependencies and time-based schedules.

Marathon and Chronos provide a web UI from which you can deploy your applications. You can access this at a URL that looks something like
`http://DNS_PREFIX.REGION.cloudapp.azure.com`
where DNS\_PREFIX and REGION are both defined at deployment time. Of course, you can also provide your own DNS name. For more information on running a container using the Marathon web UI, see [Container management through the web UI](container-service-mesos-marathon-ui.md).

You can also use the REST APIs for communicating with Marathon and
Chronos. There are a number of client libraries that are available for each tool. They cover a variety of languages--and, of course, you can use the HTTP protocol in any language. In addition, many popular DevOps tools provide support for these schedulers. This provides maximum flexibility for your operations team when you are working with an Azure Container Service cluster. For more information on running a container by using the Marathon REST API, see [Container management with the REST API](container-service-mesos-marathon-rest.md).

### Using Docker Swarm

Docker Swarm provides native clustering for Docker. Because Docker Swarm
serves the standard Docker API, any tool that already communicates with
a Docker daemon can use Swarm to transparently scale to multiple hosts
on Azure Container Service.

![Azure Container Service configured to use DC/OS--showing jumpbox, agents, and masters.](media/acs-intro/acs-swarm2.png)

Supported tools for managing containers on a Swarm cluster include, but are not limited
to, the following:

-   Dokku

-   Docker CLI and Docker Compose

-   Krane

-   Jenkins

Videos
------
AzureCon announcement:

> [AZURE.VIDEO azurecon-2015-deep-dive-on-the-azure-container-service-with-mesos]  

Getting started with Azure Container Service:  

> [AZURE.VIDEO connect-2015-getting-started-developing-with-docker-and-azure-container-service]

Building Applications Using the Azure Container Service

> [https://channel9.msdn.com/Events/Build/2016/B822]
