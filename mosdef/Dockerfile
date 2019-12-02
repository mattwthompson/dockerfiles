FROM continuumio/miniconda3:4.7.12-alpine

ENV LANG=C.UTF-8 LC_ALL=C.UTF-8
ENV PATH /opt/conda/bin:$PATH
ENV MOSDEF https://github.com/mosdef-hub
ENV PY_VER 3.7

USER anaconda

RUN conda config --set always_yes yes --set changeps1 no

RUN conda config --add channels omnia \
    && conda config --add channels mosdef \
    && conda config --add channels conda-forge \
    && conda update --all -y \
    && conda update --all -y

RUN conda install -y python=3 conda conda-build pip mbuild foyer \
    && conda clean -ya

CMD [ "/bin/bash" ]
