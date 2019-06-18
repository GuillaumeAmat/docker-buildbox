ARG NODE_VERSION
# FROM node:12-alpine
FROM node:$NODE_VERSION-alpine
LABEL maintainer="Thomas Rabaix <rabaix@ekino.com>"

ARG CI_HELPER_VERSION



RUN apk add --update --upgrade \
    bzip2 \
    curl \
    git \
    grep \
    make \
    ncurses \
    openssh && \
    \
    # echo "Install AWS" && \
    # apk add --update --upgrade -q --no-cache bash ca-certificates curl git jq make openssh-client python py-pip rsync zip && \
    # pip install pip==${PYTHON_PIP_VERSION} && \
    # pip -q install pipenv==${PIPENV_VERSION} awscli boto3 awsebcli PyYAML==${PY_YAML_VERSION} && \
    # echo "Done install AWS" && \
    \
    echo "Install CI Helper" && \
    curl -sSL https://github.com/rande/gitlab-ci-helper/releases/download/${CI_HELPER_VERSION}/alpine-amd64-gitlab-ci-helper -o /usr/bin/ci-helper && \
    chmod 755 /usr/bin/ci-helper && \
    echo "Done install CI Helper" && \
    \
    echo "Adding an up to date mime-types definition file" && \
    curl -sSL https://salsa.debian.org/debian/mime-support/raw/master/mime.types -o /etc/mime.types && \
    \
    rm -rf /tmp/* /var/cache/apk/* \
    \
    echo "Done!"
