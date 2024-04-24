---
weight: 40
date: "2022-09-30T"
draft: false
author: "SWHL"
title: "YOLOv5 YAML → COCO"
icon: "circle"
toc: true
description: ""
publishdate: "2022-09-30T"
---

#### 简介
将以yaml文件给出的YOLOv5格式数据集转换为COCO格式

支持标注格式为矩形框和多边形框。

#### YOLOv5 yaml结构如下：

{{< alert text="具体结构示例文件，可移步：[yolov5_yaml_dataset](https://github.com/RapidAI/LabelConvert/tree/main/tests/test_files/yolov5_yaml_dataset)" />}}

```text {linenos=table}
yolov5_yaml_dataset
├── images
│   ├── train
│   │   ├── images(13).jpg
│   │   └── images(3).jpg
│   └── val
│       ├── images(13).jpg
│       └── images(3).jpg
├── labels
│   ├── train
│   │   ├── images(13).txt
│   │   └── images(3).txt
│   └── val
│       ├── images(13).txt
│       └── images(3).txt
└── sample.yaml
```

#### 转换
```bash {linenos=table}
yolov5_yaml_to_coco --yaml_path dataset/yolov5_yaml_dataset/sample.yaml
```
- `--yaml_path`: yaml文件路径
- `--save_dir`: 保存转换后的数据集目录。默认为`dataset/yolov5_yaml_dataset_coco`


#### 转换后结构如下：

{{< alert text="具体结构示例文件，可移步：[COCO_dataset](https://github.com/RapidAI/LabelConvert/tree/main/tests/test_files/COCO_dataset)" />}}

```text {linenos=table}
COCO_dataset
├── annotations
│   ├── instances_train2017.json
│   └── instances_val2017.json
├── train2017
│   ├── 000000000001.jpg
│   └── 000000000002.jpg
└── val2017
    └── 000000000001.jpg
```

<script src="https://giscus.app/client.js"
        data-repo="RapidAI/LabelConvert"
        data-repo-id="MDEwOlJlcG9zaXRvcnkzODkwNDExMDY="
        data-category="Q&A"
        data-category-id="DIC_kwDOFzBL0s4CYoY-"
        data-mapping="title"
        data-strict="0"
        data-reactions-enabled="1"
        data-emit-metadata="0"
        data-input-position="top"
        data-theme="preferred_color_scheme"
        data-lang="zh-CN"
        data-loading="lazy"
        crossorigin="anonymous"
        async>
</script>