FROM jenkins/inbound-agent:4.3-4

# TODO: instead of running as root, allow jenkins user to install packages i guess ¯\_(ツ)_/¯
USER root

RUN apt-get update && apt-get install -y python3 python3-pip

RUN pip3 install --no-cache --upgrade pip setuptools pylint flake8 pydocstyle black mypy
RUN curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
RUN install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

ENTRYPOINT ["/usr/local/bin/jenkins-agent"]
