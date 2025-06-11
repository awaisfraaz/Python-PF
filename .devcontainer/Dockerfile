FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu

# Set up Miniconda installation variables
ENV MINICONDA_VERSION latest
ENV MINICONDA_ARCH x86_64
ENV MINICONDA_ROOT /opt/miniconda

# Install dependencies and Miniconda
RUN apt-get update && apt-get install -y curl bzip2 && \
    curl -L https://repo.anaconda.com/miniconda/Miniconda3-${MINICONDA_VERSION}-Linux-${MINICONDA_ARCH}.sh -o miniconda.sh && \
    bash miniconda.sh -b -p ${MINICONDA_ROOT} && \
    rm miniconda.sh && \
    ${MINICONDA_ROOT}/bin/conda clean -tipsy && \
    ln -s ${MINICONDA_ROOT}/etc/profile.d/conda.sh /etc/profile.d/conda.sh

# Update PATH so conda is available
ENV PATH="${MINICONDA_ROOT}/bin:${PATH}"