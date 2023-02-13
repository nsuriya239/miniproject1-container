FROM ubuntu:18.04
RUN apt update; apt install -y gnupg2
RUN apt install -y python3-pip

ADD . /web

WORKDIR /web

RUN pip3 install -r requirements.txt

CMD ["python3","run.py"]

