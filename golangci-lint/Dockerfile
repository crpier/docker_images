from "golang:alpine"

USER root
ENV PYTHONUNBUFFERED=1
ENV DOCKER_HOST=tcp://172.17.0.1:50000

RUN apk add --update --no-cache bash curl

RUN curl -fsSLO https://get.docker.com/builds/Linux/x86_64/docker-17.04.0-ce.tgz \
    && tar xzvf docker-17.04.0-ce.tgz \
    && mv docker/docker /usr/local/bin \
    && rm -r docker docker-17.04.0-ce.tgz

RUN addgroup docker
RUN addgroup jenkins docker
RUN wget -O- -nv https://raw.githubusercontent.com/golangci/golangci-lint/master/install.sh | sh -s v1.41.1

CMD ""
