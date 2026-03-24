# <p align="center"> <font color="#2e6da4"> STUR3D: Spatio-Temporal Unified Representation Learning <br> for 3D Object Detection </font> </p>

<p align="center">
  <a href="https://your-paper-link.pdf"><strong>[Paper]</strong></a> | 
  <a href="https://github.com/snowindog/STUR3D"><strong>[Project Page]</strong></a> |
  <a href="#maintenance"><strong>[Code Coming Soon]</strong></a>
</p>

---

## 0. 效果展示与核心架构图
<table align="center">
  <tr>
    <td align="center"><img src="URL_TO_YOUR_GIF" width="400px"/><br><b>(a) Inference Demo</b></td>
    <td align="center"><img figs="headfig" width="400px"/><br><b>(b) Motivation/Overall Concept</b></td>
  </tr>
</table>

---

## 1. 整体框架图 (Figure 2)
<p align="center">
  <img src="URL_TO_YOUR_FIG2" width="90%"><br>
  <i>Figure 2: The overall architecture of STUR3D, featuring STOPP, STGE, and OQG modules.</i>
</p>

---

## 2. 核心亮点 (Key Innovations)
- **<font color="#d9534f">STOPP (Spatio-Temporal Object-centric Point Prompting):</font>** 针对遮挡问题，通过引入时空目标中心点提示，增强了模型在复杂场景下的目标召回能力。
- **<font color="#5bc0de">STGE (Spatio-Temporal Geometric Encoding):</font>** 统一了时空几何表示，解决了 2D 图像特征与 3D 空间推理之间的几何不一致性。
- **<font color="#5cb85c">OQG (Object-centric Query Generation):</font>** 利用深度信息引导初始化高质量的3D Query。

---

## 3. 性能表现 (Benchmark Results)
| Method | Backbone | mAP ↑ | NDS ↑ | mATE ↓ | mASE ↓ |
| :--- | :---: | :---: | :---: | :---: | :---: |
| Baseline | ResNet-50 | 48.2 | 57.8 | 0.609 | 0.275 |
| **STUR3D (Ours)** | **ResNet-50** | **53.0** | **61.2** | **0.478** | **0.268** |
| *Improvement* | - | *+4.8* | *+3.4* | *-0.131* | *-0.007* |

---

## 4. 最新动态 (Latest Updates)

- **[2026-03]** 🚀 **STUR3D** 被 **CVPR 2026** 正式接收！
- **[Coming Soon]** 🛠️ 训练代码与预训练模型正在清理中，即将发布。
- **[Coming Soon]** 📝 Arxiv 论文链接即将更新。

---

## 引用 (Citation)

```bibtex
@inproceedings{fan2026stur3d,
  title={STUR3D: Spatio-Temporal Unified Representation Learning for 3D Object Detection},
  author={Fan, Huijie and Huang, Pengrui and Wang, Qiang and Fan, Baojie and Dong, Jiahua and Qu, Liangqiong},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2026}
}
