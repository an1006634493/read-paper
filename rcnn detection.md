R-CNN：先利用某种算法生成proposal region（如selective search算法），然后对图片中不同的proposal region利用卷积网络提取特征，特征作两用：1、用作分类，判断框选内的目标类别；2、用作位置回归，判断该怎么修正框的位置。

Fast R-CNN：先利用某种算法生成proposal region，然后对整张图片提取feature map，在最后一层feature map上确定原始图像中各个proposal region的位置，然后过全连接提取最终特征，做分类与位置回归。

（针对不同大小的region feature map，类似于重采样，横着分为W个格子，竖着分为H个格子，对这HxW个格子内做pooling，最后得到的pooling后的feature map就是HxW大小了。）

Faster R-CNN：先对整张图片生成feature map，在feature map上用RPN网络确定proposal region的位置，然后对各个region过全连接提取最终特征，做分类与位置回归。

优化：由feature map提取最终特征所经过的FC网络可以改成卷积网络以便加快速度。

参考：https://www.cnblogs.com/skyfsm/p/6806246.html
