# How to set up Linux for Deep Learning, with NVIDIA GPU

## Verify version compatibility and note down
At this moment, the latest version of Tensorflow is compatible with python3.8, Cuda 11.0, cuDNN 8.0
(https://www.tensorflow.org/install/source#tested_build_configurations)

## Get and install NVIDIA Driver
(https://www.nvidia.com/en-us/drivers/unix/)

## Get and install Cuda Toolkit:
(https://developer.nvidia.com/cuda-downloads)

## Get and install libcudnn:
Will need to join NVIDIA Developer Program (it's free).
(https://developer.nvidia.com/rdp/cudnn-download)

## Get and install TensorRT:
(https://developer.nvidia.com/tensorrt)

## Get and install Python 3.8:
Since Debian Testing has moved to python 3.9 and this is incompatible with Tensorflow, we will need to get python3.8

(https://www.python.org/downloads/source/)

### Install Python 3.8
This will compile and install to /usr/local/bin, /usr/local/lib, etc...

```shell
./configure --enable-optimizations --enable-loadable-sqlite-extensions 

make
make test
su -
make altinstall 
```

## Upgrade pip and virtualenv
```shell
/usr/local/bin/python3.8 -m pip install --no-cache-dir --upgrade pip
/usr/local/bin/python3.8 -m pip install --no-cache-dir --upgrade virtualenv
```

## Create Virtual Environment:
```shell
/usr/local/bin/python3.8 -m virtualenv -p /usr/local/bin/python3.8 --always-copy --download env
```

## Activate Virtual Environment:
```shell
source ~/env/bin/activate
```

## Install the relevant python packages:
Feel free to add/remove package as you like.

```shell
for package in audioread beautifulsoup4 bottleneck face-recognition face-recognition-models fastparquet geopy hdbscan ipyparallel ipython jupyter jupyterlab keras Keras-Applications librosa lxml matplotlib nbconvert numba numexpr numpy opencv-contrib-python pandas pip pyarrow PyAudio rawpy requests scikit-learn scipy seaborn statsmodels tensorboard tensorflow tf-models-official virtualenv xgboost
do
    pip install --no-cache-dir --upgrade $package
done
```
