# test3

##配置环境

1.安装conda，我是以前装的anaconda,其实miniconda也可以

2.创建conda环境，激活一个ultralytics虚拟环境

conda create -n yolov8 python=3.8

activate ultralytics

3.配一个国内pypi源

4.安装pytorch

因为题目要求是yolov8，可能比较老了，打开pytorch会安装最新的2.8版本，然而pytorch2.6以上版本引入了安全更改，会出问题，所以这里我降了pytorch版本
pip install torch==2.5.0 torchvision==0.20.0

5.在github上找到yolov8n.pt，下载到根目录下

6.vscode上终端改为cmd的ultralytics虚拟环境下

##运行程序说明

在vscode中运行check-1.py
如果摄像头亮度或者对比度之类导致画面不清请修改参数，
或者在系统设置里直接改，

##关于多个目标

在使用循环处理检测到的结果时，遍历所有检测结果，对每一个物体单独处理，绘制矩形框，（代码里我把数据集里80个物体类都放进去了，所以检测到的内容会有点多，可以根据需要把target_class里的内容去掉一些）

##关于三维空间中物体的方向

仅靠当前信息，不行，因为使用的是单目相机，不能获取物体的距离等信息无法计算空间中的位置方向
