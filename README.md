# DeepSort_TensorRT
Use tensorrt to accelerate deepsort tracking.
使用tensorrt来加速deepsort的特征提取。
## Install
[REQUIRE] TensorRT 7</p>
[REQUIRE] OpenCV</p>
下载本库和deepsort的pytorch库
```
git clone git@github.com:ZQPei/deep_sort_pytorch.git
git clone https://github.com/RichardoMrMu/deepsort-tensorrt.git
```
配置好大佬的pytorch工程后，将exportOnnx.py复制到pytorch工程的项目目录下运行，将会生成deepsort.onnx。</p>
把deepsort.onnx移到本工程的resources目录下。然后回到工程的根目录</p>
```
mkdir build
cd build
cmake ..
make
./onnx2engine ../resources/deepsort.onnx ../resources/deepsort.engine
```
然后就可以运行demo测试了</p>
```
./demo ../resources/deepsort.engine ../resources/track.txt
```
然后就可以把自己TensorRT的目标检测工程进行对接。附上大佬TensorRT目标检测的工程</p>
```
git clone https://github.com/wang-xinyu/tensorrtx.git
```
注：视频文件太大了，所以只把检测结果保存成txt进行测试，因为图片全是黑的，所以demo只是demo，以实际使用为准哈。