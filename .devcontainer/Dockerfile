# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.245.2/containers/ubuntu/.devcontainer/base.Dockerfile
FROM mcr.microsoft.com/vscode/devcontainers/base:0-ubuntu-22.04

# Select desired TAG from https://github.com/argoproj/argo-cd/releases
ENV ARGOCD_VERSION=v2.8.4
RUN curl -sSL -o /usr/local/bin/argocd "https://github.com/argoproj/argo-cd/releases/download/${ARGOCD_VERSION}/argocd-linux-amd64" \
    && chmod +x /usr/local/bin/argocd

ENV AKUITY_VERSION=v0.9.3
RUN curl -sSL -o /usr/local/bin/akuity "https://dl.akuity.io/akuity-cli/${AKUITY_VERSION}/linux/amd64/akuity" \
    && chmod +x /usr/local/bin/akuity

ENV KIND_VERSION=v0.20.0
RUN curl -Lo /usr/local/bin/kind https://kind.sigs.k8s.io/dl/${KIND_VERSION}/kind-linux-amd64 \
    && chmod +x /usr/local/bin/kind

ENV KUSTOMIZE_VERSION=v5.3.0
RUN curl -Lo /tmp/kustomize.tar.gz https://github.com/kubernetes-sigs/kustomize/releases/download/kustomize%2F${KUSTOMIZE_VERSION}/kustomize_${KUSTOMIZE_VERSION}_linux_amd64.tar.gz \
    && tar -xvf /tmp/kustomize.tar.gz -C /tmp \
    && mv /tmp/kustomize /usr/local/bin/kustomize \
    && chmod +x /usr/local/bin/kustomize

# Install k9s
ENV K9S_VERSION=v0.32.4
RUN curl -sSL -o /tmp/k9s.tar.gz https://github.com/derailed/k9s/releases/download/${K9S_VERSION}/k9s_Linux_amd64.tar.gz \
    && tar -xzf /tmp/k9s.tar.gz -C /tmp \
    && mv /tmp/k9s /usr/local/bin/k9s \
    && chmod +x /usr/local/bin/k9s