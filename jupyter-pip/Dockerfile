FROM python:3.9-slim-bullseye

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

COPY requirements.txt .
RUN pip install --upgrade pip \
 && pip install -r requirements.txt

# Configure jupyter
COPY jupyter_notebook_config.py /root/.jupyter/jupyter_lab_config.py
RUN jupyter nbextension enable --py widgetsnbextension

EXPOSE 8888

CMD [ "jupyter-lab" ]
