---
layout: post
title: Ubuntu安装TensorFlow
---

最近好多人都在说TensorFlow，搞得我也想弄一个玩一玩。
安装其实很简单，按照[这里](https://www.tensorflow.org/install/install_linux)的教程安装就可以了。
以下过程基于Ubuntu16.04LTS 和 Python27
```
$ wget https://ci.tensorflow.org/view/Nightly/job/nightly-matrix-cpu/TF_BUILD_IS_OPT=OPT,TF_BUILD_IS_PIP=PIP,TF_BUILD_PYTHON_VERSION=PYTHON2,label=cpu-slave/lastSuccessfulBuild/artifact/pip_test/whl/tensorflow-1.2.0-cp27-none-linux_x86_64.whl
$ pip install tensorflow-1.2.0-cp27-none-linux_x86_64.whl
```

但是这需要CUDA的库才能用。
到[CUDA的官网](https://developer.nvidia.com/cuda-downloads)下载安装之后，就可以用了。

附上测试代码
```
$ python
>> import tensorflow as tf
>> hello = tf.constant("Hello, TensorFlow.")
>> sess = tf.Session()
>> print(sess.run(hello))
Hello, TensorFlow.
```
一般来说，如果import那行没报错，就没什么问题了。