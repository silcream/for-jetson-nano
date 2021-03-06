# for-jetson-nano
jetson nano 

## download opencv
sudo apt update
sudo apt install python3-opencv

sudo apt install build-essential cmake git pkg-config libgtk-3-dev \
    libavcodec-dev libavformat-dev libswscale-dev libv4l-dev \
    libxvidcore-dev libx264-dev libjpeg-dev libpng-dev libtiff-dev \
    gfortran openexr libatlas-base-dev python3-dev python3-numpy \
    libtbb2 libtbb-dev libdc1394-22-dev
    
mkdir ~/opencv_build && cd ~/opencv_build
git clone https://github.com/opencv/opencv.git
git clone https://github.com/opencv/opencv_contrib.git

cd ~/opencv_build/opencv
mkdir build && cd build

cmake -D CMAKE_BUILD_TYPE=RELEASE \
    -D CMAKE_INSTALL_PREFIX=/usr/local \
    -D INSTALL_C_EXAMPLES=ON \
    -D INSTALL_PYTHON_EXAMPLES=ON \
    -D OPENCV_GENERATE_PKGCONFIG=ON \
    -D OPENCV_EXTRA_MODULES_PATH=~/opencv_build/opencv_contrib/modules \
    -D BUILD_EXAMPLES=ON ..
    
make -j8

sudo make install
## download jetpack
https://docs.nvidia.com/deeplearning/frameworks/install-tf-jetson-platform/index.html

## download tensorflow
sudo apt install python3-venv

mkdir my_tensorflow
cd my_tensorflow

python3 -m venv venv

source venv/bin/activate

pip install --upgrade pip

pip install --upgrade tensorflow

## install numpy
sudo pip install numpy

## download jupyter notebook
sudo apt-get update
sudo apt-get upgrade

sudo apt-get install jupyter-notebook

jupyter notebook


