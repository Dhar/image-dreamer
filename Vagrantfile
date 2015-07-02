# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "data-science-toolbox/dst"
  config.vm.network "forwarded_port", guest: 8888, host: 8888

  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y git bc wget
    sudo apt-get install -y libprotobuf-dev libleveldb-dev libsnappy-dev libopencv-dev libboost-all-dev libhdf5-serial-dev
    sudo apt-get install -y libgflags-dev libgoogle-glog-dev liblmdb-dev protobuf-compiler
    sudo apt-get install -y libopenblas-base libopenblas-dev
    git clone https://github.com/BVLC/caffe.git
    cd caffe
    cp Makefile.config.example Makefile.config
    sed -i "s/# CPU_ONLY := 1/CPU_ONLY := 1/" Makefile.config
    sed -i "s/BLAS := atlas/BLAS := open/" Makefile.config
    make all

    # Uncomment the below if you're feeling paranoid.  We're not running in production or anything, here.
    # make test
    # make runtest

    make pycaffe
    for req in $(cat python/requirements.txt); do sudo pip install $req; done
    echo 'export PYTHONPATH=/home/vagrant/caffe/python:$PYTHONPATH' >> /home/vagrant/.profile
    if [ ! -f "/home/vagrant/caffe/models/bvlc_googlenet/bvlc_googlenet.caffemodel" ]; then
        wget -q http://dl.caffe.berkeleyvision.org/bvlc_googlenet.caffemodel -O /home/vagrant/caffe/models/bvlc_googlenet/bvlc_googlenet.caffemodel
    fi
  SHELL
end
