FROM continuumio/miniconda3:4.10.3

ENV DEBIAN_FRONTEND="noninteractive" TZ="Europe/Berlin"

# Update and upgrade
RUN apt-get update -qq && apt-get upgrade -y \
 && apt-get clean -y \
 && rm -rf /var/lib/apt/lists/*

# To install packages type instead:
#RUN apt-get update -qq && apt-get upgrade -y \
# && apt-get install -y --no-install-recommends \
#      tree net-tools \
# && apt-get clean -y \
# && rm -rf /var/lib/apt/lists/*

WORKDIR /workspace

# Install mamba
RUN conda install -y mamba -n base -c conda-forge

# Install base environment
COPY environment.yml /workspace/environment.yml
RUN mamba env update --file /workspace/environment.yml

# Configure jupyter
COPY jupyter_notebook_config.py /root/.jupyter/jupyter_lab_config.py
RUN jupyter nbextension enable --py widgetsnbextension

EXPOSE 8888

CMD [ "jupyter-lab" ]
