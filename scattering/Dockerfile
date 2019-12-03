FROM continuumio/miniconda3


RUN apt-get upgrade -y \
    && apt-get update -y \
    && apt-get install gcc g++ -y \ 
    && apt-get update -y \
    && apt-get clean -y

RUN git clone https://github.com/mattwthompson/mdtraj \
    && git clone https://github.com/mattwthompson/scattering \
    && cd mdtraj \
    && git checkout van-hove \
    && pip install numpy cython \
    && python setup.py develop \
    && cd ../scattering \
    && pip install scipy \
    && python setup.py develop \
    && cd ..

CMD [ "/bin/bash" ]
