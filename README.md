# jupyter-docker

Minimal example to user Jupyter with Docker using either pip or Miniconda with Mamba.

# Usage

To run Jupyter using Docker and pip, type:

    docker-compose \
      -f docker-compose.pip.yml up --build

To run Jupyter using Docker, [Miniconda](https://docs.conda.io/en/latest/miniconda.html) and [Mamba](https://github.com/mamba-org/mamba), type:

    docker-compose \
      -f docker-compose.miniconda.yml up --build

# Resources

- [Docker Python](https://hub.docker.com/_/python)
- [Docker Miniconda](https://hub.docker.com/r/continuumio/miniconda3/)
- [Miniconda](https://docs.conda.io/en/latest/miniconda.html)
- [Mamba](https://github.com/mamba-org/mamba) Mamba is a reimplementation of the conda package manager in C++

# License

This project is licensed under the MIT license. See the [LICENSE](LICENSE) for details.
