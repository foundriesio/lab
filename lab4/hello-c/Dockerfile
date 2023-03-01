# docker build --tag hello-c:latest .
#
# docker run -it --rm hello-c:latest
#

FROM debian:bullseye-20220316-slim

#Install packages
RUN apt-get update && \
    apt-get install -y --no-install-recommends build-essential && \
    rm -rf /var/lib/apt/lists/*

RUN mkdir -p /app/

COPY helloworld.c /app/
COPY start.sh /app/
RUN chmod +x /app/start.sh

WORKDIR /app/

RUN gcc helloworld.c -o helloworld

ENTRYPOINT ["/app/start.sh"]