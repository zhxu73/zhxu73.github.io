---
title: 'Install CCTools Ubuntu 18.04LTS'
date: 2019-11-23
permalink: /posts/2019/08/blog-post-4/
tags:
  - ubuntu
  - cctools
---

sudo apt-get -y update

sudo apt-get -y install build-essential zlib1g-dev libpcre3-dev

sudo apt-get -y install libpython-dev

sudo apt-get -y install libpython3-dev 2to3 python3-distutils

sudo ln /usr/bin/x86_64-linux-gnu-python3-config /usr/bin/python3-config


# Download SWIG

wget https://iweb.dl.sourceforge.net/project/swig/swig/swig-4.0.1/swig-4.0.1.tar.gz

tar -xzvf swig-4.0.1.tar.gz

cd swig-4.0.1

./configure

make

sudo make install


# Download CCTOOLS

wget http://ccl.cse.nd.edu/software/files/cctools-7.0.21-source.tar.gz

tar -xzvf cctools-7.0.21-source.tar.gz

cd cctools-release-7.0.21

./configure --prefix /usr

make

sudo make install


#Python2 binding is installed at /usr/lib/python2.7/site-packages/

# Python3 binding is installed at /usr/lib/python3.6/site-packages/


# Added path file

sudo echo "../site-packages" > /usr/lib/python2.7/dist-packages/site-packages.pth

sudo echo "/usr/lib/python3.6/site-packages" > /usr/local/lib/python3.6/dist-packages/site-packages.pth
