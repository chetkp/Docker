# The Conventional method of Integrated Development Environment (IDE) Setup

> The below explanation covers everything best for both the questions. Due to the time constraint I haven’t written this paper in Markdown, but I have very good knowledge of Html, Javascript, C, C++, Java, CSS, and Markdown. I understand the base of syntax required for different programming languages. Being BCA, MCA from the University of Pune I am able to grasp the technical concepts quite easily.
>

Let’s recall the conventional method of setting up an Integrated Development Environment (IDE) for creating the applications. To setup the IDE means to iterate through number of documents and follow the processes to make the application ready for development. There may be number of dependencies and sequences that may be required to be followed to get the application environment ready for development.

For sake of simplicity, let me take an example of readying the IDE JCreator for creating java applications.

The prerequisite for the JCreator installation is to install java. Typically, the location where Java is placed on your computer would be: C:\Program Files\Java\jdk1.5.0_01

Now that you have installed java, run the **JCreator exe** file to complete the installation process. During the installation process, follow the steps to configure the  **JDK Profiles**, setup the **environment variable** and make it ready for development.

But wait, this is not as easy as it seems. The application may encounter number of hurdles if there is a version mismatch (…jdk1.5.0_01) with what JCreator version supports, misconfigured JDK Profiles or if the project location changes, or there may need to re-configure the environment variable.

In some cases, we may need to uninstall the current version of Java and install the compatible version of Java. This is something you can never find during installation because the Operating System doesn’t know which version of JCreator  would be used and unless you configure the JDK Profiles, setup the environment variable and run your first programme.

The problems with conventional methods are:

1. To develop applications, one may need to remember the prerequisite to setup the development environment.

2. The sequence is important to install the dependencies.

3. All the dependencies should be present to setup the IDE for working successfully.

4. The version mismatch may need you to setup the application again to match the system compatibilities and re-configure a few things.

5. Consider the case where you need to install a complex application which demands matching .Net Framework(s), etc. or the OS level things where latest version of .Net Framework doesn’t come pre-installed.

6. Sometimes one may need to look for the down-graded version of the .Net for backward compatibility either for setting up the application or support the app development versions.

Let’s take another example of readying **ABP Framework** which is a complete open-source infrastructure to create modern web applications. ABP Framework supports configuring the Documentation Module named ABP VoloDocs. It means configuring a whole Documentation Module with the application to make it ready for documentation.

To configure the documentation module in ABP Framework, one may encounter the underlying issues:
1. Number of sequences and prerequisites are required to be followed.

2. If there is version mis-match for any of these prerequsites, the framework wouldn’t work entirely.

3. The underlying issues may need number of services to be stopped and run to make the framework work.

4.  The process itself is not just tedious but also time-consuming.

5. That’s why most developers haven’t even heard about it or have no experience working with ABP Framework.

6. It has no popularity just because of the tedious setup and time-consumption just to setup IDE for the applications development.

## **What is Docker**

Docker is an innovative technology that has transformed the way web-developers can build, ship, and run the applications. Docker provides a complete new experience to the web developers for creating the projects. With the help of Dockers, the developers need not to be worried about setting up the IDE and will have the ready environment to develop the applications.

**What Docker Offers and how it enhances productivity**

Docker lets developers build, test, and deploy applications quickly. Using Docker, one can quickly deploy and scale applications into any environment and know that code will run. Running Docker on AWS provides developers and admins a highly reliable, low-cost way to build, ship, and run distributed applications at any scale.

Docker speeds up the software development processes, supporting micro services architecture, simplifies application deployment in cloud environments, and even enhancing reproducibility.

**The benefits of Docker**

The key benefit of Docker is that it allows users to package an application with all of its dependencies into a standardized unit for software development. In other words, to develop an application the Docker will provide all the dependencies and prerequisites to develop an application inside the containers.

You may have encountered the problems where the code runs perfectly on developer’s machine but it stops working on other machine.

The probable causes are:

1. The other machine may be missing one or more dependencies as part of deployment to run the code successfully.

2. Software version mismatch, the target machine may be running different version of the software that an application needs, for e.g., the application being developed needs Node version 14 but the target machine has Node version 9.
1. The environment variable set are different at the developer application and the target machine.

This is where Docker plays an important role to ensure that the code will run successfully on any machine as it works on developer’s machine.

With Docker we package our application with everything it needs to run the code. The Docker downloads and installs all the dependencies required inside an isolated environment named **Containers**. For example:

DEVELOPER’S MACHINE (RUNNING DOCKER):

Package 1 Requirement (It will run inside Container 1) :
- Node 14
- Mongo 4
- App

Package 2 Requirement (It will run inside Container 2) :
- Node 9
- Mongo 4
- App

QUALITY ASSURANCE MACHINE (RUNNING DOCKER):

Package 1 Requirement (It will run inside Container 1) :

- Node 14
- Mongo 4
- App

Package 2 Requirement (It will run inside Container 2) :
- Node 9
- Mongo 4
- App

The output for running the code would be same at both the machines and wherever the application is running inside the Docker.

**Benefits:**

Just the Docker is needed and it eliminates the need to setup the machines with the number of dependencies to be installed separately, Node 14, Mongo 4, App or Node 14, Mongo 4, App respectively for setting up two or more different machines.

The IDE needed to start developing the application just need the Docker. There is no point worrying about the version mismatch or missing dependencies needed to be deployed on test machines.

**How Container Works**

The containers allow running multiple applications versions inside isolated environment. No two containers can see each other’s processes that are running and there is no point of interference of the application with each other.

In such a way:

On a one single machine, two different versions of the applications can run side by side without harming other application or its resources that are needed. For e.g.,

![Alt](https://github.com/chetkp/Docker/blob/main/Image1.jpg)

*In usual application development environment, there would be unnecessary clutter while installing and uninstalling the number of dependencies that are needed to develop another version of the application. It might also result in slowdown the process or sometimes important dependencies may accidently get uninstalled while uninstalling the software application and it may result in application to stop responding.*

But with the help of Docker container, we can immediately drop the container that is not needed and setup another container to develop the application. See the below figure:

![Alt](https://github.com/chetkp/Docker/blob/main/Image2.jpg)

**What is Virtual Machine then? And what’s the problem with using the virtual machines for different application versions**

The virtual machines need a complete setup of the Operating System and all the dependencies to be installed as required one by one for developing each version of the application.

The development is not as fast as it is with the help of containers as one single machine can run multiple applications side by side.

The virtual machines are resource intensives and utilises the physical resources of the single machine and it slows down the process. Whereas the Docker runs on the top of the OS it is installed and it uses only the OS kernel of the host machine or in other words, CPU core.

**Docker Development Environment (Docker Image and Docker File)**

We add Docker file to the Docker which is a plain text file containing instructions that Docker uses to package this application into an image.

 ![Alt](https://github.com/chetkp/Docker/blob/main/Image3.jpg)

The above image has everything that an applications needs to run.

Let’s take a look at what this image contains:
- A cut-down OS
- A runtime environment (e.g., Node)
- Application files
- Third-party libraries
- Environment variables

**Setting up and running the Docker Container**

The Docker Engine is an open source containerization technology for building and containerizing your applications. Docker Engine acts as a client-server application with: A server with a long-running daemon process dockerd. APIs which specify interfaces that programs can use to talk to and instruct the Docker daemon.

The below diagram shows how the Docker Works:

 ![Alt](https://github.com/chetkp/Docker/blob/main/Image4.jpg)

**Docker Images and Docker Hub (Registry)**

Docker Hub is a Docker registry, which is a system for storing, versioning, and distributing Docker images:

 ![Alt](https://github.com/chetkp/Docker/blob/main/Image5.jpg)

**Docker Hub**

Docker's official cloud-based registry is used by default when installing Docker. It's a public registry that anyone can use, and it's built for developers and open source contributors. Developers can host public repos for free, or private repos for teams and enterprises.

**Docker Registry**

A general term for a system that stores and distributes Docker images. There are many other Docker registries available, including Amazon Elastic Container Registry (ECR), Azure Container Registry (ACR), and Google Container Registry (GCR). You can also run your own private registry on your local system or inside your organization.

**Difference between working of Docker-run and Docker Compose and its use cases**

The key difference between docker-run versus docker-compose is that docker run is entirely command line based, while docker-compose reads configuration data from a YAML file.

The second major difference is that docker run can only start one container at a time, while docker-compose will configure and run multiple.

Docker Compose is a tool for defining and running multi-container applications. It is the key to unlocking a streamlined and _efficient development and deployment experience._

# Analogy

 ![Alt](https://github.com/chetkp/Docker/blob/main/Image6.jpg)

There are two chefs in Master Chef Australia Kitchen and both the Chef enters in their kitchen. Both have been provided the necessary items to cook pizza. They can’t see each other for what they have been provided with. They have no way to criticize each other. This is how Master Chef Australia has provided everything to two different chefs in their kitchens.

The same way Docker bundles all the dependencies, Docker file (Instructions to cook) for each container (Kitchen with necessary items). Each container is isolated from the outside environment and the applications would know what operations are to be performed based upon what is provided inside the containers.

![Alt](https://github.com/chetkp/Docker/blob/main/Image7.jpg)

**Docker Registry** would be like arrangement of different items in a **RACK** by the chefs for public. It would also mean that items are available for public to eat. They can have their versions of the food like removing the toppings, eating only a particular item from the chef or choose what they like as per their taste buds.

# Let’s talk Developer’s way

Basically, Docker provides everything on the top of OS and it is similar to the snapshots (Images in Docker) as in Hyper-V. We simply select the snapshots in Hyper-v and revert to the state of the system as required.

In case of Hyper-v we need to switch to virtual machine which is resource intensive and can’t even provide the simultaneous apps running experience.

In case of Docker we create Docker Image on the top of OS and it simply runs like a normal application. We are simply choosing Docker images as a snapshot or blueprint of the libraries and dependencies right from the already up operating system and need not to transit between different states, leaving the main operating system and rebooting as it requires in case of virtual machines to revert to the state of another OS.

In such a way, the Docker is quick, easy to setup and is always a ready to work Production Environment.

Thanks - *Chet* 
