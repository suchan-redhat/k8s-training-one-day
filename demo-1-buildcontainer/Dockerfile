# This is a comment line (Lines that begin with a hash, or pound, sign (#) are comments.)

# The FROM instruction declares that the new container image extends the registry.access.redhat.com/ubi9/ubi:9.2 container base image.
FROM registry.access.redhat.com/ubi9/ubi:9.2


#The LABEL instruction is responsible for adding generic metadata to an image.
LABEL       description="This is a custom httpd container image"

# RUN executes commands in a new layer on top of the current image. The shell that is used to execute commands is /bin/sh.
RUN         yum install -y httpd

# EXPOSE indicates that the container listens on the specified network port at runtime. The EXPOSE instruction defines metadata only; it does not make ports accessible from the host.
EXPOSE      80

# ENV is responsible for defining environment variables that are available in the container.
ENV         LogLevel "info"

# The ADD instruction copies files or folders from a local or remote source and adds them to the container’s file system.
ADD         https://www.redhat.com/rhdc/managed-files/st-openshift-data-foundation-datasheet-158362pr-202211-en_0.pdf /var/www/html

# WORKDIR defines the default working path
WORKDIR /var/www/html/

# COPY copies files from the working directory and adds them to the container’s file system.
COPY        ./src/   /var/www/html/

# USER specifies the username or the UID to use when running the container image for the RUN, CMD, and ENTRYPOINT instructions
USER        0

# VOLUME defines the persistent storage location
VOLUME /var/www/html/

# ENTRYPOINT specifies the default command to execute when the image runs in a container.
ENTRYPOINT  ["/usr/bin/bash"]

# CMD provides the default arguments for the ENTRYPOINT instruction.
CMD         ["-c", "/usr/sbin/httpd", "-D", "FOREGROUND"]
