FROM jupyter/minimal-notebook

LABEL maintainer="rpersee <gh:rpersee>"

# Fix: https://github.com/hadolint/hadolint/wiki/DL4006
# Fix: https://github.com/koalaman/shellcheck/wiki/SC3014
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

USER ${NB_UID}

# Install Graphviz
RUN mamba install --quiet --yes \
    'graphviz' \
    'python-graphviz' && \
    mamba clean --all -f -y && \
    fix-permissions "${CONDA_DIR}" && \
    fix-permissions "/home/${NB_USER}"

USER root

# Install Jupyter-RDFify which does not have a conda package
WORKDIR /tmp
RUN pip install jupyter-rdfify && \
    fix-permissions "${CONDA_DIR}" && \
    fix-permissions "/home/${NB_USER}"

USER ${NB_UID}

WORKDIR "${HOME}"
