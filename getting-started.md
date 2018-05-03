# Getting Started

### Overview

For this course, you only need to install two things on your computer: **Docker** and a **text editor**.

That's it! You won't need to install anything else to be able to run web servers, databases, or any other Linux applications, thanks to Docker.

You will also want to create a free account on both **Docker Hub** and **GitHub**, if you don't already have one. Docker Hub is used to discover, access and share Docker images on the Internet. GitHub is used to share source code, documentation, and issues.

We'll discuss each of these in the following sections.

### Downloading and Installing Docker CE

Docker is available for a large number of desktop, server, and cloud platforms. It is packaged as a free [Community Edition](https://www.docker.com/community-edition) \(**CE**\) and a commercially supported [Enterprise Edition](https://www.docker.com/enterprise-edition) \(**EE**\). There is a quarterly **stable** release for reliability and a monthly **edge** release that gives you access to the latest features.

For this course, we will use the **Community Edition**. It won't matter if you choose to install the latest stable or edge edition, which at the time of this writing are **18.03.1-ce** and **18.05.0-ce-rc1**, respectively. Docker's documentation doesn't always immediately reflect the latest version numbers, but you can always see the latest releases on [GitHub](https://github.com/docker/docker-ce/releases), if you're curious.

Unless you're planning to build Docker from source yourself, the recommended way to install Docker is from the [Docker Store](https://store.docker.com/). You can search for Docker at the Docker Store, but the _Get started with Docker_ section is normally prominently displayed right on the home page anyway. The [link](https://store.docker.com/search?offering=community&type=edition) takes you to a page where you can choose the edition you want to use for your environment.

For this course, we will assume that you are using either

* [Docker Community Edition for Mac](https://store.docker.com/editions/community/docker-ce-desktop-mac)
* [Docker Community Edition for Windows](https://store.docker.com/editions/community/docker-ce-desktop-windows).

These are the best ways to work with Docker on a Mac or Windows system. The installation should be smooth and straightforward, especially for newer machines, but if you need documentation for installing, you can follow the links under the _Resources_ tab on the store page.

#### Hello from Docker!

After installing Docker, you can quickly verify that things are working as expected by running the following command from the shell in a terminal window.

`docker run hello-world`

What the command will do is instruct Docker to run a container using the `hello-world` image. When you run this command for the first time, the image will not yet be present on your system, so Docker will pull it from the public Docker Hub. For now, you can think of the image as the binary you need to launch a container, similar to other binaries on your system used to launch applications.

```text
$ docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
9bb5a5d4561a: Pull complete
Digest: sha256:f5233545e43561214ca4891fd1157e1c3c563316ed8e237750d59bde73361e77
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/engine/userguide/

```

### Installing a Text Editor

Chances are that you may already have a good text editor that you like, such as Atom or Sublime. Perhaps, like me, you are already comfortable with editing using vi \(or vim\), which should be available in just about any terminal environment you find yourself in.

In any case, one editor I can strongly recommend for anyone is [Visual Studio Code](https://code.visualstudio.com/) from Microsoft. It's free and open source, starts up quickly, has an excellent user interface, and also has an active, thriving plugin community. It's nice as a lightweight text editor or as a full-fledged Interactive Development Environment \(IDE\). This has become my editor of choice for Go, Node, and occasional C/C++ programming.

Regardless of the editor you choose, the main thing to keep in mind is that a text editor is not the same thing as a word processing application. It won't insert "invisible" characters to provide rich formatting support and it won't add it's own extensions to files you create.



