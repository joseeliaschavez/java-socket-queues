# Java IBM MQ Example

<img  alt="Spock Logo" src="https://open-logix.com/wp-content/uploads/2019/11/ibm-mq.png" width="100">
<img  alt="Spock Logo" src="https://spring.io/img/projects/spring-boot.svg" width="100">

An example SpringBoot application showcasing using a request/response queue pattern with a REST API.

## Getting Started

### IBM MQ Server

#### Install IBM MQ Queue Manager (Windows and Linux)

Follow [these instructions](https://developer.ibm.com/learningpaths/ibm-mq-badge/create-configure-queue-manager/) to run an IBM MQ Queue Manager locally using Docker.

#### For MacOS Apple Silicon

You'll first need to run the [following instructions](https://community.ibm.com/community/user/integration/blogs/richard-coppen/2023/06/30/ibm-mq-9330-container-image-now-available-for-appl) 
to build a custom Docker image for IBM MQ Server. This is necessary because the official IBM MQ Server image does not support MacOS Apple Silicon.

Essentially the commands are:
```shell
git clone https://github.com/ibm-messaging/mq-container.git

cd mq-container

make build-devserver
```

Once done, you should have an IBM MQ server image in your local Docker image repository.

#### Run IBM MQ Server

You can run the IBM MQ Server using Docker Compose:

```shell
docker-compose up
```

Or manually run the container using the following command:

```shell
docker run --volume qm1data:/mnt/mqm --publish 1414:1414 --publish 9443:9443 --detach --env LICENSE=accept --env MQ_QMGR_NAME=QM1 --env MQ_APP_PASSWORD=passw0rd --env MQ_ADMIN_PASSWORD=passw0rd --name QM1 ibm-mqadvanced-server-dev:9.3.5.0-arm64
```

### Reference Documentation
For further reference, please consider the following sections:

* [Official Gradle documentation](https://docs.gradle.org)
* [Spring Boot Gradle Plugin Reference Guide](https://docs.spring.io/spring-boot/docs/3.2.4/gradle-plugin/reference/html/)
* [Create an OCI image](https://docs.spring.io/spring-boot/docs/3.2.4/gradle-plugin/reference/html/#build-image)
* [Spring Web](https://docs.spring.io/spring-boot/docs/3.2.4/reference/htmlsingle/index.html#web)
* [WebSocket](https://docs.spring.io/spring-boot/docs/3.2.4/reference/htmlsingle/index.html#messaging.websockets)
* [Spring for Apache ActiveMQ Artemis](https://docs.spring.io/spring-boot/docs/3.2.4/reference/htmlsingle/index.html#messaging.jms.artemis)

### Guides
The following guides illustrate how to use some features concretely:

* [Building a RESTful Web Service](https://spring.io/guides/gs/rest-service/)
* [Serving Web Content with Spring MVC](https://spring.io/guides/gs/serving-web-content/)
* [Building REST services with Spring](https://spring.io/guides/tutorials/rest/)
* [Using WebSocket to build an interactive web application](https://spring.io/guides/gs/messaging-stomp-websocket/)
* [Messaging with JMS](https://spring.io/guides/gs/messaging-jms/)

### Additional Links
These additional references should also help you:

* [Gradle Build Scans – insights for your project's build](https://scans.gradle.com#gradle)