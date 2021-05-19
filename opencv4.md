# Install OpenCv 4

## Prerequistites 

You need install some dep:

``` bash
sudo apt install build-essential cmake git pkg-config libgtk-3-dev \
    libavcodec-dev libavformat-dev libswscale-dev libv4l-dev \
    libxvidcore-dev libx264-dev libjpeg-dev libpng-dev libtiff-dev \
    gfortran openexr libatlas-base-dev python3-dev python3-numpy \
    libtbb2 libtbb-dev libdc1394-22-dev
```

## Install OpenCv 4

Go where you need to install opencv 4 lib

``` bash
mkdir -p ~/dev/libs && cd ~/dev/libs/
git clone https://github.com/opencv/opencv.git -b 4.3.0
git clone https://github.com/opencv/opencv_contrib.git -b 4.3.0
mkdir opencv/build && cd opencv/build
cmake -DOPENCV_EXTRA_MODULES_PATH=../../opencv_contrib/modules ..
make -j$(nproc --all) && sudo make install 
```

## If you need to test 

Let's imagin you have your code opencv files, go inside the folder.

``` bash
mkdir build 
cd build 
cmake ..
make 
```