# torchvision

torchvision是独立于pytorch的关于图像操作的一些方便工具库。

pytorch发布了torchvision0.3, 里面实现了Mask_RCNN, Keypoint_RCNN和DeepLabV3，可以直接用于语义分割，目标检测，实例分割和人体关键点检测4个任务。

在github上torch/vision/reference里面有classification, detection和segmentation三个文件夹，分别对应不同任务。直接运行detection的代码是MaskRCNN的实现，用于目标检测和实例分割任务。官网也有对应的[教程](https://pytorch.org/tutorials/intermediate/torchvision_tutorial.html])。可以轻松通过COCO2017数据集进行训练和测试。



