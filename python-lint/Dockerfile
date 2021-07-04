from jenkins/agent:alpine

USER root
ENV PYTHONUNBUFFERED=1
ENV DOCKER_HOST=tcp://172.17.0.1:50000

RUN apk add --update --no-cache python3 bash curl && ln -sf python3 /usr/bin/python
RUN python3 -m ensurepip
RUN pip3 install --no-cache --upgrade pip setuptools pylint flake8 pydocstyle # prospector[with_pyroma]

RUN curl -fsSLO https://get.docker.com/builds/Linux/x86_64/docker-17.04.0-ce.tgz \
    && tar xzvf docker-17.04.0-ce.tgz \
    && mv docker/docker /usr/local/bin \
    && rm -r docker docker-17.04.0-ce.tgz

RUN addgroup docker
RUN addgroup jenkins docker

USER jenkins
CMD ""
