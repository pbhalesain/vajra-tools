FROM centos:7

RUN yum -y install "@Development tools" python-devel libpcap-devel
RUN curl "https://bootstrap.pypa.io/get-pip.py" -o "get-pip.py" && python get-pip.py
RUN pip install libpcap confluent-kafka pcapy argparse
ADD scripts /scripts
WORKDIR /scripts/
RUN pip install -r requirements.txt && python setup.py install

CMD ["/scripts/start-pycapa.sh"]
