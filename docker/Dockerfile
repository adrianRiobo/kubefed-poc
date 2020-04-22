FROM alpine@sha256:b276d875eeed9c7d3f1cfa7edb06b22ed22b14219a7d67c52c56612330348239

LABEL maintainer="adrian.riobo.lorenzo@gmail.com"

ENV KIND_VERSION=0.7.0 \
    K8S_VERSION=1.17.0 \
    KUBEFED_VERSION=0.2.0-alpha.1 \
    HELM_VERSION=2.16.6

RUN apk add docker curl bash \
    && wget https://dl.k8s.io/v${K8S_VERSION}/kubernetes-client-linux-amd64.tar.gz -P /tmp \
    && tar -xzvf /tmp/kubernetes-client-linux-amd64.tar.gz -C /tmp \
    && mv /tmp/kubernetes/client/bin/kubectl /usr/local/bin \
    && wget https://github.com/kubernetes-sigs/kubefed/releases/download/v$KUBEFED_VERSION/kubefedctl-$KUBEFED_VERSION-linux-amd64.tgz -P /tmp \
    && tar -xzvf /tmp/kubefedctl-$KUBEFED_VERSION-linux-amd64.tgz -C /tmp \
    && mv /tmp/kubefedctl /usr/local/bin \
    && wget https://github.com/kubernetes-sigs/kubefed/releases/download/v$KUBEFED_VERSION/kubefed-$KUBEFED_VERSION.tgz -P /tmp \
    && tar -xzvf /tmp/kubefed-$KUBEFED_VERSION.tgz -C /opt \
    && wget https://github.com/kubernetes-sigs/kubefed/archive/v$KUBEFED_VERSION.tar.gz -P /tmp \
    && tar -xzvf /tmp/v$KUBEFED_VERSION.tar.gz -C /opt \
    && wget https://get.helm.sh/helm-v$HELM_VERSION-linux-amd64.tar.gz -P /tmp \
    && tar -xzvf /tmp/helm-v$HELM_VERSION-linux-amd64.tar.gz -C /tmp \
    && mv /tmp/linux-amd64/helm /usr/local/bin \
    && curl -Lo ./kind https://github.com/kubernetes-sigs/kind/releases/download/v$KIND_VERSION/kind-$(uname)-amd64 \
    && chmod +x ./kind \
    && mv ./kind /usr/local/bin \
    && rm -rf /tmp/* 

