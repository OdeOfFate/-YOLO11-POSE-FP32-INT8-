# -YOLO11-POSE-FP32-INT8-
导出FP32格式的神经网络为INT8格式的一种方式，适配最新版本的OpenVino
1.登录OpenVINO官方网址
https://www.intel.cn/content/www/cn/zh/developer/tools/openvino-toolkit/download.html?PACKAGE=OPENVINO_BASE&VERSION=v_2026_0_0&OP_SYSTEM=WINDOWS&DISTRIBUTION=CONDA

<img width="865" height="486" alt="image" src="https://github.com/user-attachments/assets/8ad16039-06c7-46af-a681-8b34992c1de5" />

 
2.按照图片当中的选项选择，在Anaconda当中一个一个地运行这些命令，完成OpenVINO的下载
3.安装ultralytics
pip install -U ultralytics
4.在你的新安装的环境当中运行以下命令以量化模型
yolo export model=path\to\best.pt format=openvino int8=True imgsz=640 data=path\to\maps.yaml
# 务必指定具体的 imgsz，并关闭 dynamic
yolo export model=best.pt format=openvino int8=True imgsz=640 data=path\to\maps.yaml dynamic=False

转成FP16格式：
yolo export model= best.pt format=openvino half=True imgsz=640 data= path\to\maps.yaml dynamic=False
5.在netron网页当中可以查看你的模型
https://netron.app
