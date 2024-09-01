In Docker, Everything is based on Images. An Image is a combination of a file system and parameters. Images contains the binaries and dependencies.
Images contains the data which is required to run container.
Docker Images can be downloaded for Docker Hub.
Images can be commited with changes and have multiple versions.

Docker Images Differentiation:  
       Base Image: Images that have no parent image, usually images with an OS like ubuntu, busybox or debian
       Child Image: Images that build on base images and add additional functionality
       Official Images: Images that are officially maintained and supported by the Docker folks.
       User Images: Images created by users like us. user/image_name

Docker Image Layer
      docker history <Image_name>

Docker File Instructions:

FROM: The FROM instruction initializes a new build stage and sets the base Image for subsequent instructions
eg: FROM redhat/ubi9-minimal
A valid Docker file must start with a FROM instruction

LABEL: it is added to image to organize images by project, record licensing information. For each label, add a line beginning with label and with one or more key value pairs
eg: LABEL vendor1="ACME Incorporated"

RUN: This instruction will execute any commands in a new layer on top of the current image and commit results. The resulting committed image will be used for the next step in the Dockerfile.

CMD: This instruction should be used to run th software contained by your image along with any arguments.
eg: CMD ["mariadb"]

EXPOSE: EXPOSE instruction indicates the ports on which a container listens for connections.

ENV: THis instruction sets the environment variable to the value.

ADD: This instruction copies new files, directories or remote file URLs from <src> and adds them to the filesystem of the image at the path <dest>

COPY: This instruction copies files

VOLUME: Volume instruction should be used to expose any database storage area, configuration storage, or files/folders created by your docker container.

WORKDIR: WORKDIR instruction sets the working directory for any RUN , CMD , ADD instructions that follow it in the docker file.
