FROM amazon/aws-cli:2.17.0

LABEL org.opencontainers.image.source="https://github.com/jessetbh/dockerfile-inventory-test"

RUN yum install -y jq gzip && yum clean all
COPY export.sh /usr/local/bin/export.sh
ENTRYPOINT ["/usr/local/bin/export.sh"]
