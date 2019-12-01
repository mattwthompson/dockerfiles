FROM continuumio/miniconda3

RUN apt-get update -y \
    && apt-get clean -y

RUN conda config --set always_yes yes --set changeps1 no

RUN conda config --add channels omnia \
    && conda config --add channels mosdef \
    && conda config --add channels conda-forge \
    && conda update --all -y \
    && conda update --all -y

RUN conda install -y python=3 conda conda-build pip mbuild foyer \
    && conda clean -ya

CMD [ "/bin/bash" ]
