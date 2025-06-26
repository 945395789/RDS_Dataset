# RDS Dataset: A Reinforced Concrete Damage Segmentation Dataset

![GitHub commit activity](https://img.shields.io/github/commit-activity/w/945395789/RDS_Dataset?style=for-the-badge) ![GitHub last commit](https://img.shields.io/github/last-commit/945395789/RDS_Dataset?style=for-the-badge) ![GitHub repo size](https://img.shields.io/github/repo-size/945395789/RDS_Dataset?style=for-the-badge)

The **RDS (Reinforced-concrete Damage Segmentation) Dataset** is a high-quality image dataset designed for the semantic segmentation of damage in reinforced concrete (RC) structures. This dataset focuses on common structural defects arising from rebar corrosion, providing a valuable resource for developing and evaluating computer vision models.

All images were captured in real-world underground parking garages and have been meticulously annotated manually at the pixel level.

<br>

<details>
<summary><strong>🇨🇳 中文版本 (Click to Expand)</strong></summary>

---

# RDS 数据集：一个钢筋混凝土损伤分割数据集

![GitHub commit activity](https://img.shields.io/github/commit-activity/w/945395789/RDS_Dataset?style=for-the-badge) ![GitHub last commit](https://img.shields.io/github/last-commit/945395789/RDS_Dataset?style=for-the-badge) ![GitHub repo size](https://img.shields.io/github/repo-size/945395789/RDS_Dataset?style=for-the-badge)

**RDS (Reinforced-concrete Damage Segmentation) Dataset** 是一个专为钢筋混凝土（RC）结构损伤语义分割任务设计的高质量图像数据集。该数据集专注于由钢筋腐蚀引起的常见结构缺陷，为开发和评估计算机 vision 模型提供了宝贵的资源。

所有图像均在真实世界的地下停车场环境中采集，并经过精细的像素级手动标注。

---
</details>

## 🌟 Features

* **🏢 Real-world Scenarios**: Images were collected from various underground parking garages in Zhejiang, China, reflecting real degradation of concrete structures in humid coastal environments.
* **🎯 Focus on Core Defects**: Primarily targets two core damage types caused by rebar corrosion: **Bump** and **Spalling**.
* **📊 Fine-grained Annotations**: Provides 5 pixel-level annotation classes, offering more detail than similar public datasets and enabling more advanced multi-class segmentation research.
* **💡 Diverse Acquisition Conditions**: Images were captured under varied lighting (bright and dim) and with multiple camera devices to enhance model robustness and generalization.
* **🖼️ High-Resolution Images**: The original images have a high resolution (generally ranging from 707×1039 to 779×1145 pixels), meeting the input requirements of modern CV models.
* **📦 Augmented Dataset**: Includes an augmented dataset of 3,336 images to support more robust model training.

<br>

<details>
<summary><strong>🇨🇳 数据集特色</strong></summary>

---

* **🏢 真实世界场景**: 图像采集自中国浙江省多个住宅区的地下停车场，真实反映了潮湿沿海环境下混凝土结构的退化情况。
* **🎯 专注核心损伤**: 主要针对由钢筋腐ission引起的两种核心损伤类型：**隆起 (Bump)** 和 **剥落 (Spalling)**。
* **📊 精细化标注**: 提供了5个像素级标注类别，远超同类公开数据集，有助于进行更深入的多类别分割研究。
* **💡 多样化采集条件**: 图像在不同光照条件（明亮与昏暗）下、使用多种相机设备拍摄，旨在提升模型的鲁棒性和泛化能力。
* **🖼️ 高分辨率图像**: 原始图像分辨率较高（普遍在 707×1039 到 779×1145 像素之间），满足现代计算机视觉模型的输入要求。
* **📦 数据增强**: 提供了包含3336张图像的增强数据集，以支持更稳健的模型训练。

---
</details>

## 📂 Directory Structure

```
RDS_Dataset/
├── ann_dir/            # Annotation files (JSON format from LabelMe)
│   ├── image_001.json
│   ├── image_002.json
│   └── ...
├── img_dir/            # Original images
│   ├── image_001.jpg
│   ├── image_002.jpg
│   └── ...
├── LICENSE             # License file
└── README.md           # This README file
```

<br>

<details>
<summary><strong>🇨🇳 目录结构</strong></summary>

---

```
RDS_Dataset/
├── ann_dir/            # 标注文件目录 (JSON格式, from LabelMe)
│   ├── image_001.json
│   ├── image_002.json
│   └── ...
├── img_dir/            # 原始图像目录
│   ├── image_001.jpg
│   ├── image_002.jpg
│   └── ...
├── LICENSE             # 许可证文件
└── README.md           # 本说明文件
```

---
</details>

## 📖 Dataset Details

### 1. Image Source and Acquisition

The image dataset was compiled from surveys in underground parking garages in Zhejiang Province, China. These structures are frequently exposed to a humid coastal environment, resulting in extensive concrete degradation. Images were captured from various RC elements, including beams, slabs, columns, and walls. To enhance model robustness, data was deliberately collected under diverse lighting conditions and with multiple imaging devices.

### 2. Annotation Classes

All images were manually annotated at the pixel level using LabelMe 5.3.1. Compared to datasets like `φ-Net` which only offer "Background" and "Damaged Area," RDS provides a more detailed classification:

1.  **Background**
2.  **Structure surface**
3.  **Spalling**
4.  **Exposed Rebar**
5.  **Bump**

### 3. Dataset Scale and Composition

* **Original Images**: 576
* **Augmented Images**: 3,336
* **Resolution**: Mainly ranges from 707×1039 to 779×1145 pixels.

While smaller in image count than large-scale datasets like Cityscapes, the scale of RDS is considered adequate and appropriate for its specialized vertical domain.

### 4. Class Distribution

Even the least frequent class (**Exposed Rebar**) accounts for approximately 2% of the total annotated pixels. This is above the threshold where classes are often disregarded in other datasets (e.g., <0.9% in Cityscapes). Therefore, all annotated classes are considered valid and sufficiently represented for model training.

### 5. Data Augmentation

To enhance model robustness and generalization, the 576 original images were systematically augmented to create the final training set of 3,336 images. The techniques used include:

* Random Cropping
* Brightness Adjustments
* Horizontal Flipping
* Random Noise Injection

<br>

<details>
<summary><strong>🇨🇳 数据集详细说明</strong></summary>

---

### 1. 图像来源与采集

本数据集的图像源于对中国浙江省住宅区地下停车场的实地勘测。这些结构长期处于潮湿的沿海环境中，导致混凝土普遍存在退化。图像捕捉对象涵盖了梁、板、柱、墙等多种RC结构构件。为增强模型鲁棒性，我们特意在多样化的光照和设备条件下进行采集。

### 2. 标注类别

所有图像均使用 LabelMe 5.3.1 工具进行像素级手动标注。与仅提供“背景”和“损伤区域”的 `φ-Net` 等数据集相比，RDS数据集提供了更详细的分类：

1.  **Background (背景)**
2.  **Structure surface (结构表面)**
3.  **Spalling (剥落)**
4.  **Exposed Rebar (外露钢筋)**
5.  **Bump (隆起)**

### 3. 数据集规模与构成

* **原始图像数量**: 576 张
* **增强后图像数量**: 3336 张
* **图像分辨率**: 主要介于 707×1039 ~ 779×1145 像素之间。

虽然图像总数少于 Cityscapes 等大型数据集，但RDS的规模对于其高度垂直的专业领域是充足且合理的。

### 4. 类别分布

在数据集中，即使是像素占比最小的类别（**Exposed Rebar**），其占比也达到了约2%，高于许多研究中被忽略的类别阈值（如Cityscapes中的0.9%）。因此，所有标注的损伤类别均被认为是有效且充分的，并全部用于模型训练。

### 5. 数据增强

为了提升模型的鲁棒性和泛化能力，我们对576张原始图像系统地应用了数据增强技术，最终生成了包含3336张图像的训练集。采用的增强方法包括：

* 随机裁剪 (Random Cropping)
* 亮度调整 (Brightness Adjustments)
* 水平翻转 (Horizontal Flipping)
* 注入随机噪声 (Random Noise Injection)

---
</details>

## 🚀 Getting Started

Here is a simple Python snippet to load an image and its corresponding annotation.

```python
import os
import json
from PIL import Image
import matplotlib.pyplot as plt

# --- English: Set data paths ---
# --- 中文: 设置数据路径 ---
base_dir = '.' # or '/path/to/RDS_Dataset'
img_dir = os.path.join(base_dir, 'img_dir')
ann_dir = os.path.join(base_dir, 'ann_dir')

# --- English: Get all image filenames ---
# --- 中文: 获取所有图像文件名 ---
image_files = [f for f in os.listdir(img_dir) if f.endswith(('.jpg', '.png'))]

# --- English: Load and display a sample ---
# --- 中文: 加载并显示一个样本 ---
sample_image_name = image_files[0]
image_path = os.path.join(img_dir, sample_image_name)
json_path = os.path.join(ann_dir, os.path.splitext(sample_image_name)[0] + '.json')

# --- English: Open image ---
# --- 中文: 打开图像 ---
image = Image.open(image_path)

# --- English: Load annotation data ---
# --- 中文: 加载标注信息 ---
with open(json_path, 'r', encoding='utf-8') as f:
    annotation = json.load(f)

print(f"Successfully loaded image: {sample_image_name}")
print(f"Image dimensions: {image.size}")
print(f"Annotation file contains {len(annotation['shapes'])} shapes.")

# --- English: Display the image ---
# --- 中文: 显示图像 ---
plt.imshow(image)
plt.title(sample_image_name)
plt.axis('off')
plt.show()

# --- English: Print the label of the first annotation ---
# --- 中文: 打印第一个标注的标签 ---
if annotation['shapes']:
    print(f"Label of the first annotation: {annotation['shapes'][0]['label']}")

```

## 🖼️ Visualization

Below are some representative examples from the RDS dataset and an illustration of the annotation process.

**Sample 1: Well-lit**
![Sample Image 1](https://user-images.githubusercontent.com/24237865/178283995-3b32879a-8c36-4734-95b8-0d195a633195.png)

**Sample 2: Dimly-lit**
![Sample Image 2](https://user-images.githubusercontent.com/24237865/178283999-31733225-28e4-4d89-94ad-38a421257917.png)

**Annotation Example**
![Annotation Example](https://user-images.githubusercontent.com/24237865/178284003-888975b2-3543-466d-88a4-3580d85a1112.png)


## 📜 Citation

If you use the RDS dataset in your research, please cite our paper.

```bibtex
@article{YourLastName_2025_RDS,
  title={A Title for Your Paper Describing the Dataset and Model},
  author={Author, First A. and Author, Second B. and ...},
  journal={Journal or Conference Name},
  year={2025},
  volume={XX},
  pages={XX-XX}
}
```

<br>

<details>
<summary><strong>🇨🇳 如何引用</strong></summary>

---
如果您在您的研究中使用了RDS数据集，请引用我们的论文。

```bibtex
@article{YourLastName_2025_RDS,
  title={A Title for Your Paper Describing the Dataset and Model},
  author={作者, A. and 作者, B. and ...},
  journal={期刊或会议名称},
  year={2025},
  volume={XX},
  pages={XX-XX}
}
```

---
</details>

## ⚖️ License

This project is licensed under the terms specified in the [LICENSE](LICENSE) file.

<br>

<details>
<summary><strong>🇨🇳 许可证</strong></summary>

---
该项目采用 [LICENSE](LICENSE) 文件中指定的许可证。

---
</details>

![sample](https://github.com/user-attachments/assets/5cf67b63-769c-4aef-b8af-b3267fd46f86)

