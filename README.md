# mbaranowski.github.io

## 2/17/2017
[Tensorflow 1.0](https://research.googleblog.com/2017/02/announcing-tensorflow-10.html) was announced this Tuesday during the 2017 Dev Summit. I've been slowly watching [all the videos](https://www.youtube.com/playlist?list=PLOU2XLYxmsIKGc_NBoIhTn2Qhraji53cv) and getting excited about the new capabilities of Tensorflow like the ability to compile models to optimized ARM assembly for running on a mobile device using [XLA compiler](https://www.youtube.com/watch?v=kAOanJczHA0).

To celebrate the occasion I managed to install Tensorflow 1.0 on both my Mac Book Pro and on a AWS P2 instance running ubuntu. In both cases I just followed the Installation instruction. On macOS I had to upgrade to Cude SDK 8.0, and then debugg why Tensorflow couldn't find the cude libraries. The solution was to make sure that both `LD_LIBRARY_PATH` and `DYLD_LIBRARY_PATH` has the right cuda path (`/usr/local/cuda/lib` in my case). In some cases I as just getting a crash without any errors, so I had to learn how to run python in a debugger: `lldb -f python -- test.py`.

The AWS P2 instance was setup using the [setup_p2.sh](https://github.com/fastai/courses/blob/master/setup/setup_p2.sh) script from the [fast.ai course](http://course.fast.ai/lessons/aws.html). After that the installation was as simple as `pip install tensorflow_gpu` and my test code started running on an Nvidia K80 GPU right away.
