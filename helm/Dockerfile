FROM jpapejr/command_runner:latest

ENV HELM_VERSION="2.14.3"

RUN apk add --update ca-certificates openssh-client \
  jq curl bash git gcc g++ make libffi-dev openssl-dev \
  && curl -o /tmp/helm.tar.gz https://get.helm.sh/helm-v${HELM_VERSION}-linux-amd64.tar.gz \
  && cd /tmp && tar xvfz helm.tar.gz \
  && ls -ltra /tmp \
  && mv /tmp/linux-amd64/helm /usr/local/bin/helm \
  && mv /tmp/linux-amd64/tiller /usr/local/bin/tiller \
  && chmod +x /usr/local/bin/helm \
  && chmod +x /usr/local/bin/tiller \
  && apk add python python-dev py-pip build-base \
  && rm /var/cache/apk/* \
  && pip install --upgrade pip \
  && pip install requests pytest pykube



CMD ["/usr/local/bin/helm"]
