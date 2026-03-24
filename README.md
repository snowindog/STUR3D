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
    <td align="center"><img src="./figs/headfig.png" width="400px"/><br><b>(b) Motivation/Overall Concept</b></td>
  </tr>
</table>

---

## 1. 整体框架图
<p align="center">
  <img src="./figs/mainfig.png" width="95%"><br>
  <i>Figure 2: The overall architecture of STUR3D, featuring STOPP, STGE, and OQG modules.</i>
</p>

---

## 2. 核心亮点
- **<font color="#d9534f">STOPP (Spatio-Temporal Object-centric Point Prompting):</font>** 针对遮挡问题，通过引入时空目标中心点提示，增强了模型在复杂场景下的目标召回能力。
- **<font color="#5bc0de">STGE (Spatio-Temporal Geometric Encoding):</font>** 统一了时空几何表示，解决了 2D 图像特征与 3D 空间推理之间的几何不一致性。
- **<font color="#5cb85c">OQG (Object-centric Query Generation):</font>** 利用深度信息引导初始化高质量的 3D Query。

---

## 3. 性能表现
<table align="center">
  <thead>
    <tr style="border-bottom: 2px solid black;">
      <th align="left">Method</th>
      <th align="center">Backbone</th>
      <th align="center">Image Size</th>
      <th align="center">mAP↑</th>
      <th align="center">NDS↑</th>
      <th align="center">mATE↓</th>
      <th align="center">mASE↓</th>
      <th align="center">mAOE↓</th>
      <th align="center">mAVE↓</th>
      <th align="center">mAAE↓</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="left">StreamPETR</td>
      <td align="center">ResNet50</td>
      <td align="center">704×256</td>
      <td align="center">43.2</td>
      <td align="center">54.0</td>
      <td align="center">0.581</td>
      <td align="center">0.272</td>
      <td align="center">0.413</td>
      <td align="center">0.295</td>
      <td align="center">0.196</td>
    </tr>
    <tr>
      <td align="left">FreqPDE</td>
      <td align="center">ResNet50</td>
      <td align="center">704×256</td>
      <td align="center">43.5</td>
      <td align="center">54.3</td>
      <td align="center">0.577</td>
      <td align="center">0.270</td>
      <td align="center">0.442</td>
      <td align="center">0.257</td>
      <td align="center">0.199</td>
    </tr>
    <tr bgcolor="#f2f2f2">
      <td align="left"><strong>STUR3D (Ours)</strong></td>
      <td align="center">ResNet50</td>
      <td align="center">704×256</td>
      <td align="center"><strong>44.8</strong></td>
      <td align="center"><strong>55.0</strong></td>
      <td align="center">0.558</td>
      <td align="center">0.275</td>
      <td align="center">0.431</td>
      <td align="center">0.257</td>
      <td align="center">0.208</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;"><td colspan="10"></td></tr>
    <tr>
      <td align="left">QAF2D†</td>
      <td align="center">ResNet50</td>
      <td align="center">704×256</td>
      <td align="center">46.0</td>
      <td align="center">56.1</td>
      <td align="center">0.573</td>
      <td align="center">0.263</td>
      <td align="center">0.387</td>
      <td align="center">0.276</td>
      <td align="center">0.191</td>
    </tr>
    <tr>
      <td align="left">DySS†</td>
      <td align="center">ResNet50</td>
      <td align="center">704×256</td>
      <td align="center">46.2</td>
      <td align="center">56.2</td>
      <td align="center">0.537</td>
      <td align="center">0.268</td>
      <td align="center">0.338</td>
      <td align="center">0.239</td>
      <td align="center">0.177</td>
    </tr>
    <tr>
      <td align="left">GeoBEV*†</td>
      <td align="center">ResNet50</td>
      <td align="center">704×256</td>
      <td align="center">43.0</td>
      <td align="center">54.6</td>
      <td align="center">0.533</td>
      <td align="center">0.275</td>
      <td align="center">0.419</td>
      <td align="center">0.298</td>
      <td align="center">0.214</td>
    </tr>
    <tr>
      <td align="left">OPEN†</td>
      <td align="center">ResNet50</td>
      <td align="center">704×256</td>
      <td align="center">47.0</td>
      <td align="center">56.5</td>
      <td align="center">0.573</td>
      <td align="center">0.275</td>
      <td align="center">0.413</td>
      <td align="center">0.235</td>
      <td align="center">0.193</td>
    </tr>
    <tr bgcolor="#f2f2f2">
      <td align="left"><strong>STUR3D (Ours)†</strong></td>
      <td align="center">ResNet50</td>
      <td align="center">704×256</td>
      <td align="center"><strong>48.6</strong></td>
      <td align="center"><strong>57.9</strong></td>
      <td align="center">0.562</td>
      <td align="center">0.269</td>
      <td align="center">0.362</td>
      <td align="center">0.237</td>
      <td align="center">0.202</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;"><td colspan="10"></td></tr>
    <tr>
      <td align="left">QAF2D</td>
      <td align="center">V2-99</td>
      <td align="center">320×800</td>
      <td align="center">50.0</td>
      <td align="center">58.6</td>
      <td align="center">0.561</td>
      <td align="center">0.261</td>
      <td align="center">0.369</td>
      <td align="center">0.251</td>
      <td align="center">0.196</td>
    </tr>
    <tr>
      <td align="left">tgGBC</td>
      <td align="center">V2-99</td>
      <td align="center">320×800</td>
      <td align="center">52.1</td>
      <td align="center">60.3</td>
      <td align="center">0.533</td>
      <td align="center">0.268</td>
      <td align="center">0.344</td>
      <td align="center">0.210</td>
      <td align="center">0.192</td>
    </tr>
    <tr bgcolor="#f2f2f2">
      <td align="left"><strong>STUR3D (Ours)</strong></td>
      <td align="center">V2-99</td>
      <td align="center">320×800</td>
      <td align="center"><strong>53.0</strong></td>
      <td align="center"><strong>61.2</strong></td>
      <td align="center">0.478</td>
      <td align="center">0.270</td>
      <td align="center">0.307</td>
      <td align="center">0.241</td>
      <td align="center">0.194</td>
    </tr>
    <tr style="border-bottom: 1px solid #ddd;"><td colspan="10"></td></tr>
    <tr>
      <td align="left">MV2D-T†</td>
      <td align="center">ResNet101</td>
      <td align="center">1600×900</td>
      <td align="center">47.1</td>
      <td align="center">56.1</td>
      <td align="center">0.593</td>
      <td align="center">0.262</td>
      <td align="center">0.340</td>
      <td align="center">0.368</td>
      <td align="center">0.184</td>
    </tr>
    <tr>
      <td align="left">StreamPETR†</td>
      <td align="center">ResNet101</td>
      <td align="center">1408×512</td>
      <td align="center">50.4</td>
      <td align="center">59.2</td>
      <td align="center">0.569</td>
      <td align="center">0.262</td>
      <td align="center">0.315</td>
      <td align="center">0.257</td>
      <td align="center">0.199</td>
    </tr>
    <tr>
      <td align="left">Sparse4Dv2†§</td>
      <td align="center">ResNet101</td>
      <td align="center">1408×512</td>
      <td align="center">52.1</td>
      <td align="center">60.8</td>
      <td align="center">0.519</td>
      <td align="center">0.265</td>
      <td align="center">0.364</td>
      <td align="center">0.199</td>
      <td align="center">0.180</td>
    </tr>
    <tr>
      <td align="left">DVPE†</td>
      <td align="center">ResNet101</td>
      <td align="center">1408×512</td>
      <td align="center">52.1</td>
      <td align="center">60.3</td>
      <td align="center">0.544</td>
      <td align="center">0.262</td>
      <td align="center">0.318</td>
      <td align="center">0.248</td>
      <td align="center">0.200</td>
    </tr>
    <tr>
      <td align="left">OPEN†</td>
      <td align="center">ResNet101</td>
      <td align="center">1408×512</td>
      <td align="center">51.9</td>
      <td align="center">60.6</td>
      <td align="center">0.528</td>
      <td align="center">0.266</td>
      <td align="center">0.312</td>
      <td align="center">0.222</td>
      <td align="center">0.190</td>
    </tr>
    <tr bgcolor="#f2f2f2">
      <td align="left"><strong>STUR3D (Ours)†</strong></td>
      <td align="center">ResNet101</td>
      <td align="center">1408×512</td>
      <td align="center"><strong>53.1</strong></td>
      <td align="center"><strong>61.3</strong></td>
      <td align="center">0.509</td>
      <td align="center">0.267</td>
      <td align="center">0.310</td>
      <td align="center">0.224</td>
      <td align="center">0.199</td>
    </tr>
  </tbody>
</table>
<p align="center">
  <small>
    <b>Comparison with previous State-of-the-art multi-view 3D detectors on the nuScenes val set.<br>
    † benefited from the perspective-view pre-training of nuImages. * indicates methods with CBGS training. § means to use a future frame.</b>
  </small>
</p>

<table align="center">
  <thead>
    <tr style="border-bottom: 2px solid black;">
      <th align="left">Method</th>
      <th align="center">Backbone</th>
      <th align="center">Image Size</th>
      <th align="center">mAP↑</th>
      <th align="center">NDS↑</th>
      <th align="center">mATE↓</th>
      <th align="center">mASE↓</th>
      <th align="center">mAOE↓</th>
      <th align="center">mAVE↓</th>
      <th align="center">mAAE↓</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="left">StreamPETR</td>
      <td align="center">V2-99</td>
      <td align="center">640×1600</td>
      <td align="center">55.0</td>
      <td align="center">63.6</td>
      <td align="center">0.479</td>
      <td align="center">0.239</td>
      <td align="center">0.317</td>
      <td align="center">0.241</td>
      <td align="center">0.119</td>
    </tr>
    <tr>
      <td align="left">QAF2D</td>
      <td align="center">V2-99</td>
      <td align="center">640×1600</td>
      <td align="center">55.5</td>
      <td align="center">63.6</td>
      <td align="center">0.471</td>
      <td align="center">0.237</td>
      <td align="center">0.322</td>
      <td align="center">0.268</td>
      <td align="center">0.118</td>
    </tr>
    <tr>
      <td align="left">DVPE</td>
      <td align="center">V2-99</td>
      <td align="center">640×1600</td>
      <td align="center">57.2</td>
      <td align="center">64.4</td>
      <td align="center">0.466</td>
      <td align="center">0.240</td>
      <td align="center">0.319</td>
      <td align="center">0.266</td>
      <td align="center">0.126</td>
    </tr>
    <tr>
      <td align="left">RayDN</td>
      <td align="center">V2-99</td>
      <td align="center">640×1600</td>
      <td align="center">56.5</td>
      <td align="center">64.5</td>
      <td align="center">0.461</td>
      <td align="center">0.241</td>
      <td align="center">0.322</td>
      <td align="center">0.239</td>
      <td align="center">0.114</td>
    </tr>
    <tr>
      <td align="left">FreqPDE</td>
      <td align="center">V2-99</td>
      <td align="center">640×1600</td>
      <td align="center">56.0</td>
      <td align="center">64.2</td>
      <td align="center">0.468</td>
      <td align="center">0.241</td>
      <td align="center">0.315</td>
      <td align="center">0.242</td>
      <td align="center">0.115</td>
    </tr>
    <tr bgcolor="#f2f2f2">
      <td align="left"><strong>STUR3D (Ours)</strong></td>
      <td align="center">V2-99</td>
      <td align="center">640×1600</td>
      <td align="center"><strong>57.9</strong></td>
      <td align="center"><strong>64.6</strong></td>
      <td align="center">0.449</td>
      <td align="center">0.259</td>
      <td align="center">0.355</td>
      <td align="center">0.243</td>
      <td align="center">0.124</td>
    </tr>
  </tbody>
</table>

<p align="center">
  <small>
    <b>Comparison on the nuScenes test set. No other tricks (e.g., CBGS, test time augmentation) are used during training and testing.</b>
  </small>
</p>

<p align="center">
  <img src="./figs/compare.png" width="95%"><br>
  <b>Comparison with state-of-the-art methods on nuScenes dataset.</b>
</p>

## 4. 最新动态 (Latest Updates)

- **[2026-03]** 🚀 **STUR3D** 被 **CVPR 2026** 正式接收！
- **[Coming Soon]** 🛠️ 训练代码与预训练模型正在清理中，即将发布。
- **[Coming Soon]** 📝 Arxiv --------

---

## 引用 (Citation)

```bibtex
@inproceedings{fan2026stur3d,
  title={STUR3D: Spatio-Temporal Unified Representation Learning for 3D Object Detection},
  author={Fan, Huijie and Huang, Pengrui and Wang, Qiang and Fan, Baojie and Dong, Jiahua and Qu, Liangqiong},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2026}
}
