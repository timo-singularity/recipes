#Bootstrap: library
#From: centos:8
Bootstrap: docker
From: centos:8

%help

  Base container with Rivet

%environment
  
  . /usr/local/rivetenv.sh

%post
  
  yum -y update
  yum -y install python3 python3-devel python3-pip
  ln -fs /usr/bin/python3 /usr/bin/python
  yum -y install wget zlib-devel
  yum -y groupinstall 'Development Tools'
  yum -y install gcc-gfortran cmake

  wget https://gitlab.com/hepcedar/rivetbootstrap/raw/3.1.0/rivet-bootstrap
  chmod +x rivet-bootstrap
  INSTALL_PREFIX=/usr/local ./rivet-bootstrap

  ldconfig
  yum clean all
