FROM alpine:latest
ENV JAVA_HOME="/usr/lib/jvm/default-jvm/"
RUN apk update && apk add \
  openjdk11 \
  ttf-freefont \
  libudev-zero \
  openssh-keygen
ENV PATH=$PATH:${JAVA_HOME}/bin
RUN mkdir -p /opt/gitflicd
COPY gitflic.jar /opt/gitflic/
COPY default-config /opt/gitflic/default-config
WORKDIR /opt/gitflic/
RUN mkdir cert && cd cert && ssh-keygen -f key.pem -m pem -q -N ""
