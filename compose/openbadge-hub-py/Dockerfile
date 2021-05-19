# Based on - https://github.com/don41382/docker-rpi-python3-with-bluetooth
# Pull base image
FROM python:3
MAINTAINER Oren Lederman orenled@mit.edu

# Install dependencies
RUN apt-get update && apt-get install -y \
    bluez \
    --no-install-recommends && \
    rm -rf /var/lib/apt/lists/*

ENV DATA_DIR /data
RUN mkdir $DATA_DIR

ENV LOG_DIR /logs
RUN mkdir $LOG_DIR

ENV CONFIG_DIR /config
RUN mkdir $CONFIG_DIR

# Define working directory
WORKDIR /app

COPY ./src/requirements.txt requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

COPY ./src .

# Define default command
#CMD ["bash"]
#ENTRYPOINT ["./badge_hub.py"]
