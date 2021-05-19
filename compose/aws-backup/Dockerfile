FROM python:3
MAINTAINER Jordan Reedie jreedie@mit.edu
ENV DEBIAN_FRONTEND noninteractive

RUN RUN apt-get update && apt-get install -y \
    cron \
    --no-install-recommends && \
    rm -rf /var/lib/apt/lists/*

RUN pip install --no-cache-dir awscli

COPY ./compose/aws-backup/entrypoint.sh /
COPY ./compose/aws-backup/backup.sh /

RUN chmod +x /entrypoint.sh /backup.sh
