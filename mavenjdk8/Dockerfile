FROM java:openjdk-8
MAINTAINER Alexander Krieg


# Install a basic SSH server
RUN apt-get install -y openssh-server
RUN mkdir -p /var/run/sshd


# Install packages needed for the build
RUN apt-get install -y --no-install-recommends git maven

# Add user jenkins to the image
RUN adduser --quiet jenkins
# Set password for the jenkins user (you may want to alter this).
RUN echo "jenkins:jenkins" | chpasswd

# Standard SSH port
EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
