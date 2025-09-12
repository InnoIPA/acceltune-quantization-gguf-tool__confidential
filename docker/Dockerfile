FROM python:3.10-slim

ENV DEBIAN_FRONTEND=noninteractive \
    TIMEZONE=Asia/Taipei

# Setting TimeZone
RUN apt -yq update && \
    apt -yq install tzdata && \
    ln -fs /usr/share/zoneinfo/${TIMEZONE} /etc/localtime && \
    dpkg-reconfigure -f noninteractive tzdata

WORKDIR /app

COPY . /opt/llama.cpp

RUN pip install --no-cache-dir -r /opt/llama.cpp/requirements.txt