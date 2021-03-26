FROM centos:latest

MAINTAINER raghav1674 ragaws1674@gmail.com


# INSTALLING SOME PACKAGES

RUN yum install -y wget \
	           git \
                   net-tools \
		   vim \
		   openssh-server \
		   sudo \
		   shadow-utils \
		   ncurses 

# CREATING WORK DIRECTORY AND INSTALLING JAVA AND MVN AND SETTING THE PATH 

RUN  mkdir /java_workspace

COPY jdk-8u171-linux-x64.rpm  /java_workspace/

ADD apache-maven-3.6.3-bin.tar.gz /java_workspace/

RUN yum install -y /java_workspace/jdk-8u171-linux-x64.rpm

# CREATING jenkins user

RUN ssh-keygen -A

RUN useradd jenkins

RUN echo jenkins:jenkins | chpasswd

RUN echo 'jenkins ALL=(ALL) NOPASSWD: ALL' >>  /etc/sudoers.d/jenkins

RUN rm -f /run/nologin

# SETTING THE ENV VARIABLES

ENV M2_HOME "/java_workspace/apache-maven-3.6.3"

ENV PATH    "${PATH}:${M2_HOME}/bin"


RUN mkdir /home/jenkins/work_space

# RUNNING sshd DEAMON.............


CMD ["/usr/sbin/sshd","-D"] 


EXPOSE 22 

