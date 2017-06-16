#Standalone Machine Agent for Docker Visibility

The following example shows how to build and run the Standalone Machine Agent in a container with Docker Visibility enabled. This is provided as a guide only, and you may freely modify it to suit your needs.  Docker Container monitoring requires a Server Visibility license and version 4.3.3 or higher of both the Controller and the Standalone Machine Agent.
 

To build and run this example, you should be running Docker API version 1.27 or higher (to find out your version, run: `docker version`).  This example uses a Ubuntu 14.04 base image and packages the standalone Machine Agent (with bundled JRE) and a simple Bash shell script that starts the Machine Agent with the correct system properties to connect to your Controller: you supply these values as environment variables via the docker-compose.yml file.  

To build and run the project:

1. Clone this repo and `cd docker-machine-agent`
2. Edit the docker-compose.yml file and replace the text in italic with the host, port, account name, access key and SSL connection details for your Controller.  Please see the [product documentation](https://docs.appdynamics.com/display/PRO43/Standalone+Machine+Agent+Configuration+Property+Reference) for details of how to configure these properties, which allow the Machine Agent to connect to your Controller instance.
3. Run `docker-compose up`

The first time you run this command, you will see a lot of console output as the Docker image is built, followed by output similar to this:

```
Starting docker-machine-agent ... 
Starting docker-machine-agent ... done
Attaching to docker-machine-agent
docker-machine-agent    | Using Java Version [1.8.0_111] for Agent
docker-machine-agent    | Using Agent Version [Machine Agent v4.3.3.0 GA Build Date 2017-06-06 19:28:14]
docker-machine-agent    | [INFO] Agent logging directory set to: [/opt/appdynamics/machine-agent]
docker-machine-agent    | Machine Agent Install Directory :/opt/appdynamics/machine-agent
docker-machine-agent    | Machine Agent Temp Directory :/opt/appdynamics/machine-agent/tmp
docker-machine-agent    | Tasks Root Directory :/opt/appdynamics/machine-agent/controlchannel
docker-machine-agent    | [INFO] Agent logging directory set to: [/opt/appdynamics/machine-agent]
docker-machine-agent    | Redirecting all logging statements to the configured logger
docker-machine-agent    | Started AppDynamics Machine Agent Successfully.
```
