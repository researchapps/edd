Bootstrap: docker
From: ubuntu:14.04

%runscript

    exec /usr/local/anaconda2/bin/edd "$@"


% post

    sudo apt-get update && apt-get install -y \
    build-essential \
    libz-dev \
    wget \
    git \
    vim

    mkdir /data

    # Install anaconda 3
    wget https://repo.continuum.io/archive/Anaconda2-4.3.0-Linux-x86_64.sh
    bash Anaconda2-4.3.0-Linux-x86_64.sh -b -p /usr/local/anaconda2
    export PATH=/usr/local/anaconda2/bin:$PATH
    /usr/local/anaconda2/bin/conda install -y scipy pandas patsy statsmodel cython
    git clone https://github.com/daler/pybedtools && cd pybedtools && /usr/local/anaconda2/bin/python setup.py install
    /usr/local/anaconda2/bin/pip install --upgrade pysam
    /usr/local/anaconda2/bin/pip install edd

    # Make some default locations for Stanford clusters
    mkdir -p /share/PI
    mkdir -p /scratch
    mkdir -p /local-scratch

    echo "" >> /environment
    echo "export PATH=/usr/local/anaconda2/bin:$PATH" >> /environment
