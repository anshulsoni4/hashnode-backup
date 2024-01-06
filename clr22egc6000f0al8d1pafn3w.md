---
title: "Docker for Beginners: About Image and Containers, create and publish your first Image,"
seoTitle: "Docker for beginners"
datePublished: Sat Jan 06 2024 12:52:15 GMT+0000 (Coordinated Universal Time)
cuid: clr22egc6000f0al8d1pafn3w
slug: dockers-for-beginners
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704543954707/fcabc44d-b56a-460e-ba43-b862e891c416.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1704545515562/a1bd7bd1-50ef-4d6b-b58a-8fcf2792a03a.png
tags: docker, technology, opensource, technical-writing-1

---

---

# Introduction to Docker:

* The docker is like a lunch box, where we add not only the food (code), but also sweets and other side stuff (other dependencies) to taste right.
    
* it doesn’t matter where we eat this lunch box office desk, garden, etc, everything is set up just like we thought while making it.
    
* Docker is an application where we encapsulate the development, packaging, and execution in one place, that to in a unified environment.
    

* In docker, there is an independent system of its own where we just add our files and dependencies, and it has its run time environment and operating system.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704544428279/d0066aeb-f1db-4e1d-8bf2-64e418208912.png align="center")
    

---

### Why do we need docker, what is the use?

* **Consistency across the environment** - It ensures that the application or web app runs the same on any device, either my computer or your computer, etc, everyone is using the same command to run the app.
    
* **Isolation** - maintains clear boundaries in our app and dependencies, no more clashes, more like a compartment and bifurcation.
    
* **Portability** - It makes it very easy to move our app to any condition, like we can move to the development stage easily, and then to testing with the same files. no more hassle, docker containers are used in deployment also, and reduces load.
    
* **Version Control** - just like we can track our version of apps using git, we can do that in docker as well, we can return to the previous version easily
    
* **Scalable** - We create copies of the same app so that it can be used among various platforms at the same time. it's like making multiple copies of the same menu in the restaurant.
    
* **DevOps Integration** - the gap between development and operation is now gone, one software takes care of development, testing, and deployment at the same time.
    

---

## How does Docker work?

It works on 2 main concepts, IMAGES and CONTAINERS.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704544548083/a6ac78d5-2c0b-49ac-a971-c612636c84d8.png align="center")

* **Images** - it is a lightweight, executable package, which is needed to run a piece of software. It is like a recipe of a dish, it provides us with code, libraries (things needed) and runtime to execute them, and system tools (instructions on how to use them).
    

* **Container** - We will have to run this image somewhere right, so we will run this in a container, which is a runnable instance for executing the images. Provides an execution environment. The image is a menu and the final baked dish is the docker container, the final instance made using an image, sets the Environment for running applications like downloading resources and dependencies, etc.
    
* We can run multiple containers using a single image, with
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704544603061/854bf3cc-5274-4cac-bca5-79f7ee06f372.png align="center")
    

* **Network** - Creates a connection between containers, or with any external server, allowing to share resources among the containers, take the example of cooking stations where every station has different meal cooking but there is one particular host administrating them. And they share info without any problem.
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704544642806/10e32ad0-5956-488a-aff2-5f768bd08148.png align="center")
    

---

## Docker workflow

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704544686787/8a9db953-3fa9-4706-a9a9-c583316bbaa4.png align="center")

* **Docker Client** - It is the user interface that is used for interacting with docker, its the tool we use to command things we want to get executed, it is like the chef of the kitchen giving instructions to the cooks.
    
* **Docker Host (Docker Daemon)** - Background process for managing client, it gets the command from the client and manages images and containers, handles other docker-related tasks. It is like a master chef who does not cook but overviews all the tasks that are being carried away.
    
* **Docket Registry (Docker Hub)** - It is nothing but a centralized repository of Docker images. This is like what Git is to Git Hub. This contains all the information about things required for building containers, etc. It is like a cookbook or recipe library, where we find different.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704544722936/e03244b1-b1de-4134-92cb-d06abe736411.png align="center")
    

---

## Creating Docker Images

* We create the image by first using the docker file, it is a set of instructions telling docker how to build your own image, take it as a docker lang, or docker’s diff syntax, here are some commands :
    
* **FROM** - specifies the base image to use from the New image, picking an image from the already built image, like picking a kitchen that has already some of the ingredients.
    
* **WORKDIR** - sets the working directory for following instructions. Specifies the path., and decides where in the kitchen you want to do the cooking.
    
* **COPY** - Copies the files or directory from the built context to the image, it is like bringing your favorite tools to your side of the kitchen.
    
* **RUN** - executes the commands in the shell.
    
* **EXPOSE** - tells docker that the container will listen to specified network ports at run time, it is like saying out loud - I am going to use this part of the kitchen.
    
* **ENV** - they set the environment variables during the build process, setting the mood.
    
* **ARG** - defines the build time variables, having a note that can be changed before cooking.
    
* **VOLUME** - creates mount point for external points, creates a space if something external needs to be added.
    
* **CMD** - provides a command to when the container should be started.
    
* **ENTRYPOINT** - it is like the menu dish that people will see and order, and after that, you will make it.
    

---

## Docker Demo:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704544879864/57e9613c-e0ca-447c-91fd-aea7ba34d0b2.png align="center")

* first, we used an Ubuntu image from the docker hub (explore)
    
* after that, we added a folder, opened vs code, and added this command docker pull ubuntu.
    
* following that we saw in the docker desktop an image was created
    
* now to run that we used the docker run command.
    
* now a new container has been made using a Ubuntu image.
    
* We are using Ubuntu commands on Windows, wowowo
    

```docker
PS D:\\docker-demo> docker run -it ubuntu
root@67312dac8f3d:/# cd home
root@67312dac8f3d:/home# mkdir hello
root@67312dac8f3d:/home# ls
hello
root@67312dac8f3d:/home# cd hello 
root@67312dac8f3d:/home/hello# touch hello-ubuntu.txt
root@67312dac8f3d:/home/hello# ls
hello-ubuntu.txt
root@67312dac8f3d:/home/hello#
```

---

### Creating our own Docker Images

* we have created a folder, and files, now inside the dockerfile we will write the docker code.
    

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704544892738/bb6acc7d-78e0-482a-9d62-9c5180c86ea0.png align="center")

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704544905418/fb526ddc-bf65-4395-b6ab-1555dfdcb69a.png align="center")

---

* Image is created
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704544922052/3cc8e599-1b0e-47a6-a49a-84bde5e140fe.png align="center")

---

* Now let's run/containerize it :
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704544961951/f38fbef2-e913-4a81-b420-b34d212f1c8e.png align="center")
    

---

* if you go to the docker desktop, we see :
    
* ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704544995310/c6d057ce-29c6-42cf-9b59-921694eaea9a.png align="center")
    

so many files and an app file that we created, that has our files inside it.

---

## Dockerize React app

* First, we create a react app using vite, but we do not install the dependencies using npm install, we will do it using images.
    
* so we create an image :
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704545045081/82425c9d-a7d3-44f7-bc64-29643656317c.png align="center")
    

* and this creates an image, you can see this on the docker desktop.
    
* after this we have to host this, so we map the local host and create the app with safety so that no external source can access it.
    
* now we run the image, also we will map the directory that is in our system to the directory present in the container.
    
* so we use it, and now our local code is linked to the container.
    

```docker
docker run -p 5173:5173
```

* the pwd, tells the current working directory path, -v creates a volume where we can store our data, which keeps track of changes that are happening.
    
* another -v is for node modules and creating a new volume is imp for ensuring volume mount is available in the container, the changes will be linked to this module, and we will now need to run again and again.
    

```docker
-v "$(pwd):/app" -v /app/node_modules react-with-docker
```

* you can now see that this is running on local host 5173, and the changes will be reflected easily.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704545089982/4831c1c6-0e72-4a96-8ff8-3ee5249de5c1.png align="center")
    

---

## How to publish Docker Image :

* First we cd to the folder where we have published image
    
* after that we login by saying
    

```docker
docker login
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704545134379/d2fe5dc9-2118-4e91-ae98-f6d07d4ce94d.png align="center")

* Now for publishing it, we use
    

```docker
docker tag react-with-docker anshulsondocker/react-with-docker
```

* Now push the image to Docker Hub, and it will look like this :
    

```docker
docker push anshulsondocker/react-with-docker
```

![](https://file.notion.so/f/f/de3e78e5-331f-467a-a96b-9b68e74fee36/0585be6b-2836-4ed8-b867-1632586227f0/Untitled.png?id=70b9735d-b9d0-400b-a83a-fa43cd36cde0&table=block&spaceId=de3e78e5-331f-467a-a96b-9b68e74fee36&expirationTimestamp=1704636000000&signature=MURrMEbMAllao1H4PXZMVbkjWQc3Sc1F6roC_tFYXPA&downloadName=Untitled.png align="left")

Now see the Docker desktop and you can see in the images section :

![](https://file.notion.so/f/f/de3e78e5-331f-467a-a96b-9b68e74fee36/560f7e7a-928d-4831-a229-4ec1182c2e03/Untitled.png?id=f9a82e64-db6a-46a7-93f4-88d66daafb7e&table=block&spaceId=de3e78e5-331f-467a-a96b-9b68e74fee36&expirationTimestamp=1704636000000&signature=I6iL9jDk9Yi7Rm-35iaCY_ZWuQNiOiWbj3cDr3Dzi6Q&downloadName=Untitled.png align="left")

See in the hub section as well, you can see the image :

![](https://file.notion.so/f/f/de3e78e5-331f-467a-a96b-9b68e74fee36/28543afb-69d6-4f71-987c-ee8d3a63a2b0/Untitled.png?id=cb6b1f95-1165-462c-8dad-51d7ee7f7706&table=block&spaceId=de3e78e5-331f-467a-a96b-9b68e74fee36&expirationTimestamp=1704636000000&signature=EsYTsat1A8r3KPmtpYr_u6SlB31VjwSUHnKpywd8Br8&downloadName=Untitled.png align="left")

You can also view this on the Docker hub website : (Published)

![](https://file.notion.so/f/f/de3e78e5-331f-467a-a96b-9b68e74fee36/e325d5ff-ac65-4b92-81b2-e228476a495a/Untitled.png?id=e5ab45f3-9c50-4186-ac03-e8d871d09dca&table=block&spaceId=de3e78e5-331f-467a-a96b-9b68e74fee36&expirationTimestamp=1704636000000&signature=Es3RAqsDmuqxhE21AJDp2lZdGTQyTwQeZ5SPgaM2Fsw&downloadName=Untitled.png align="left")

You can also update according to your preference.

![](https://file.notion.so/f/f/de3e78e5-331f-467a-a96b-9b68e74fee36/2240e348-d9a2-4d5f-b68a-b0ab21d051a2/Untitled.png?id=de2d0a75-8380-46b9-8fd7-a3b6b2b2b21d&table=block&spaceId=de3e78e5-331f-467a-a96b-9b68e74fee36&expirationTimestamp=1704636000000&signature=bQfHnLjCkFJoFHkGzW103G3hNPp4b8D3IurkT9fU0ok&downloadName=Untitled.png align="left")

---

## What if I tell you that, you don't need to create an image again and again, but use a single command?

## This can be automated using DOCKER COMPOSE :

* It is a tool that defines and manages multiple containers at once for our purpose. It uses a YML file to configure the network, volumes, and services for our application.
    
* Before this, we needed to run 10 different commands for 10 containers or files. Now all we need is a single command.
    
* We can list our requirements in a single file and make the execution easy.
    

---

### Using Docker INIT :

* create a react vite project and open the terminal
    
* now type docker init
    
    ![](https://file.notion.so/f/f/de3e78e5-331f-467a-a96b-9b68e74fee36/35e93958-442b-4b75-b902-72cb307bf924/Untitled.png?id=397f0bcf-3093-474f-b91c-aa24b9936996&table=block&spaceId=de3e78e5-331f-467a-a96b-9b68e74fee36&expirationTimestamp=1704636000000&signature=QOlvGFO-jANiNX3QGcy8mvvYDqSRgM_w1yELYFaFvfk&downloadName=Untitled.png align="left")
    

* Now answer the questions and it will create a YML file for you automatically.
    
* it will ask you questions like, the node’s version, etc just see the image and you will understand
    
    ![](https://file.notion.so/f/f/de3e78e5-331f-467a-a96b-9b68e74fee36/15d39d1f-484e-40da-8e6e-1b72e8a9bb89/Untitled.png?id=d2b65192-de11-4ba7-8390-6cfd397da646&table=block&spaceId=de3e78e5-331f-467a-a96b-9b68e74fee36&expirationTimestamp=1704636000000&signature=g3qr54zwrolbAeHXQZ9d5EUQOzN7OLX4rO3AQOGYqf4&downloadName=Untitled.png align="left")
    

It has created a Docker file for you :

![](https://file.notion.so/f/f/de3e78e5-331f-467a-a96b-9b68e74fee36/45fda877-d6c4-40c4-8bfd-2591576943ab/Untitled.png?id=6a9e5516-8321-4f20-83f3-fcd67b6b2210&table=block&spaceId=de3e78e5-331f-467a-a96b-9b68e74fee36&expirationTimestamp=1704636000000&signature=4hhqt5YBTGdkmETrdH-BZ5OI-_nEzL_qPh4S_xm2Yvo&downloadName=Untitled.png align="left")

The YML file :

![](https://file.notion.so/f/f/de3e78e5-331f-467a-a96b-9b68e74fee36/98fd2d92-cc7e-4838-8809-b071e35edc0f/Untitled.png?id=bcab53c7-d13c-42cc-a82a-8f7015b2378f&table=block&spaceId=de3e78e5-331f-467a-a96b-9b68e74fee36&expirationTimestamp=1704636000000&signature=HhVx5XTsHGv4ksZvOm1HIZUFYFjnMcI252VmJpw8Tmw&downloadName=Untitled.png align="left")

This is how we have reduced the -v coding part that we added previously

![](https://file.notion.so/f/f/de3e78e5-331f-467a-a96b-9b68e74fee36/fb93f852-2998-4f5c-a61e-a064027a1023/Untitled.png?id=4a0b89aa-1ddd-485b-818d-d9be173b8db4&table=block&spaceId=de3e78e5-331f-467a-a96b-9b68e74fee36&expirationTimestamp=1704636000000&signature=tj5VDDV3nGcDYiL8UefFFox9JdoroV8esiuaGi_yQY0&downloadName=Untitled.png align="left")

Now write docker compose up :

![](https://file.notion.so/f/f/de3e78e5-331f-467a-a96b-9b68e74fee36/42378260-52db-42f8-a6ab-04d350166fc2/Untitled.png?id=5994a365-daf6-404e-9400-e1ef10c33e89&table=block&spaceId=de3e78e5-331f-467a-a96b-9b68e74fee36&expirationTimestamp=1704636000000&signature=1YTERo3IBri6cqvoO-b0fwTZKTDqVxDnIZNsW9jqNpY&downloadName=Untitled.png align="left")

the process started ……..

**<mark>and then you can simply see the local host :)</mark>**

---

Follow for more tech-related blogs.  
Follow my socials - [https://bento.me/anshul-soni](https://bento.me/anshul-soni)