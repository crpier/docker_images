FROM jenkins/inbound-agent:4.3-4

# TODO: instead of running as root, allow jenkins user to install packages i guess ¯\_(ツ)_/¯
USER root

RUN apt-get update && apt-get install -y python3 python3-pip

RUN pip3 install --no-cache --upgrade pip setuptools pylint flake8 pydocstyle black

ENTRYPOINT ["/usr/local/bin/jenkins-agent"]
