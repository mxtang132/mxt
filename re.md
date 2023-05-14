摘要：目标检测技术是计算机视觉技术的一个热点研究方向，该技术广泛应用于车辆导航、航空及其他重要领域，发展
前景广阔。 将深度学习应用到图像目标检测中能够学习到图像的高级特征，弥补传统算法的不足。 首先，重点介绍了基于深
度学习的单阶段目标检测算法；分析了多种算法的结构和优缺点，然后对各算法做了归纳总结；最后，结合目标检测算法提
出未来发展的方向与趋势。
关键词：目标检测；计算机视觉；深度学习；单阶段
Abstract: Object detection technology is a hot research direction of computer vision technology. This technology is
widely used in vehicle navigation, aviation and other important fields, and has broad development prospects. Applying deep
learning to image target detection can learn advanced features of images and make up for the shortcomings of traditional
algorithms. First, it focus on the single-stage object detection algorithm based on deep learning, and analyzes the structure
and advantages and disadvantages of various algorithms, and then each algorithm is summarized in this paper. Finally,
combined with the target detection algorithm, the direction and trend of future development are proposed.
Keywords: object detection, computer vision, deep learning, single-stage
目标检测是从图像区域中判断是否存在来自预设类别的对象实例，如果存在，则标注每个对象的位置和类别 ［1］。 目标检测是许多视觉任务的基础， 现已应用到了我们生活的各个方面，如：自动驾驶、医学检测和人脸识别等，因此目标检测算法显得尤为重要。 深度学习是一种直接从图像数据中学习特征表示的强有力策略 ［2］，使目标检测技术成了前所未有的研究热点。 目前目标检测可分为传统的检测技术和基于深度学习的检测算法，而后者又可分为单阶段和两阶段检测算法， 单阶段模型直接将目标检测问题转化为回归问题，能大大提升模型的计算速度。 本文主要对单阶段算法进行归纳总结， 并展望目标检测算法的未
来发展。单阶段目标检测算法通过卷积网络提取图像的高级特征，再对特征图进行融合处理，然后完成对目标的定位。 目前单阶段检测算法主要包括 YOLO 系列 、SSD ［3］和 RefineDet ［4］算法 ，在检测领域具有很高的应用价值。
1 YOLO 系列算法
1.1 YOLO
2015 年，Redmon J 等 ［5］提出 YOLO 算法，其整体思想是将一整张图像分成 S*S 个网格，如果这个网格存在着预测物体的中心位置 ，就由这个网格进行预测， 并且每个网格会产生多个边界框， 但在训练期间每个边界框只能选择一个对象预测， 这就导致一个网格内有多个物体时难以检测，使目标的检测精度受到限制，但大大提高了检测速度。
1.2 YOLOv2
2017 年， 考虑到 YOLO 算法定位不够准确等问题 ，Redmon J 又提出了 YOLOv2［6］，该算法采用 Darknet-19 网络，采用了一系列设计决策提高速度和精度， 主要包括： 批量标准化（BN 层）稳定模型训练、设计高分辨分类器，让网络更好地适应高分辨输入、引入多尺度训练以提升检测精度；采用 K-Means对目标框进行聚类，使模型更好地训练学习。 YOLOv2 提供了更好的模型选择灵活性，将检测对象延伸到了 9000 个，因此称之
为 YOLO9000。
1.3 YOLOv3
2018 年 ，Redmon J 又 提 出 了 YOLOv3 ［7］， 该 算 法 采 用Darknet-53 为特征提取 网络 ， 如图 1 所 示 ， 在 网 络 中 加 入ResNet［8］残差网络连接，降低了网络带来的梯度负面影响；并结合 FPN［9］的思想将深浅尺度的特征图融合，以提取更丰富的特征；采用 K-Means 聚类先验框，利用三个不同尺度的特征图来预测边界框，由于多尺度预测的优势，可以更多地检测小物体，但在中大型物体上的性能相对较差。
