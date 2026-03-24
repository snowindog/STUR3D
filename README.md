<div align="center">

# <font color="#2e6da4"> STUR3D: Spatio-Temporal Unified Representation Learning for 3D Object Detection </font>

<p align="center">
  [Huijie Fan](mailto:fanhuijie@sia.cn) <sup>1,†</sup>, 
  [Pengrui Huang](mailto:huangpengrui@sia.cn) <sup>1,2,†</sup>, 
  [Qiang Wang](mailto:wangqiang@sia.cn) <sup>3,*</sup>, 
  [Baojie Fan](mailto:jobfbj@gmail.com) <sup>4</sup>, 
  [Jiahua Dong](mailto:dongjiahua1995@gmail.com) <sup>5</sup>, 
  [Liangqiong Qu](mailto:liangqqu@hku.hk) <sup>6</sup>
</p>

<p align="center">
  <sup>1</sup> State Key Laboratory of Robotics and Intelligent Systems, <br>
  Shenyang Institute of Automation, Chinese Academy of Sciences <br>
  <sup>2</sup> Shenyang University of Chemical Technology <br>
  <sup>3</sup> Key Laboratory of Manufacturing Industrial Integrated Automation, Shenyang University <br>
  <sup>4</sup> Nanjing University of Posts and Telecommunications <br>
  <sup>5</sup> Mohamed bin Zayed University of Artificial Intelligence &nbsp;&nbsp;
  <sup>6</sup> The University of Hong Kong
</p>

<p align="center">
  <code>{fanhuijie, huangpengrui, wangqiang}@sia.cn</code>, 
  <code>{jobfbj, dongjiahua1995}@gmail.com</code>, 
  <code>liangqqu@hku.hk</code>
</p>

<p align="center">
  <strong>CVPR 2026</strong> <br>
  <small><sup>†</sup> Equal contribution. &nbsp; <sup>*</sup> Corresponding author.</small>
</p>

[![Paper](https://img.shields.io/badge/Arxiv-2026.xxxxx-red?logo=arxiv&logoColor=red)](https://your-paper-link.pdf)
[![Project](https://img.shields.io/badge/Project-STUR3D-blue?logo=github&logoColor=white)](https://github.com/snowindog/STUR3D)
[![Maintenance](https://img.shields.io/badge/Code-Coming_Soon-yellow?logo=visual-studio-code&logoColor=white)](#)

</div>

**Abstract:** Existing surrounding-view 3D object detectors typically initialize queries using 2D information from the current frame, leading to spatial and temporal inconsistencies. We propose **STUR3D**, a unified framework featuring three key components: **STOPP**, **STGE**, and **OQG**. STOPP addresses occlusion by introducing spatio-temporal object-centric point prompting; STGE unifies spatio-temporal geometric representations to resolve inconsistencies; and OQG utilizes depth-informed initialization for high-quality 3D queries. STUR3D achieves state-of-the-art performance, notably **64.6% NDS** and **57.9% mAP** on the nuScenes test benchmark.

---

## 🚩 News
- **[2026.03]** 🚀 **STUR3D** has been accepted by **CVPR 2026**!
- **[Coming Soon]** 🛠️ Training code and pre-trained models are being cleaned up and will be released soon.

---

## 0. Demo & Motivation
<table align="center">
  <tr>
    <td align="center"><img src="URL_TO_YOUR_GIF" width="400px"/><br><b>(a) Inference Demo</b></td>
    <td align="center"><img src="./figs/headfig.png" width="400px"/><br><b>(b) Motivation/Overall Concept</b></td>
  </tr>
</table>

---

## 1. Overall Architecture
<p align="center">
  <img src="./figs/mainfig.png" width="95%"><br>
  <i>Figure 2: The overall architecture of STUR3D, featuring STOPP, STGE, and OQG modules.</i>
</p>

---

## 2. Core Highlights
- **<font color="#d9534f">STOPP (Spatio-Temporal Object-centric Point Prompting):</font>** Enhances object recall in complex scenes and occlusions via spatio-temporal prompting.
- **<font color="#5bc0de">STGE (Spatio-Temporal Geometric Encoding):</font>** Resolves inconsistencies between 2D features and 3D reasoning through unified geometric representations.
- **<font color="#5cb85c">OQG (Object-centric Query Generation):</font>** Produces high-quality 3D initial queries guided by precise depth information.

---

## 3. Performance Performance

### nuScenes Val Set
<table align="center">
  <thead>
    <tr style="border-bottom: 2px solid black;">
      <th align="left">Method</th>
      <th align="center">Backbone</th>
      <th align="center">Res.</th>
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
    <tr><td>StreamPETR</td><td>R50</td><td>704×256</td><td>43.2</td><td>54.0</td><td>0.581</td><td>0.272</td><td>0.413</td><td>0.295</td><td>0.196</td></tr>
    <tr><td>FreqPDE</td><td>R50</td><td>704×256</td><td>43.5</td><td>54.3</td><td>0.577</td><td>0.270</td><td>0.442</td><td>0.257</td><td>0.199</td></tr>
    <tr bgcolor="#f2f2f2"><td><strong>STUR3D (Ours)</strong></td><td>R50</td><td>704×256</td><td><strong>44.8</strong></td><td><strong>55.0</strong></td><td>0.558</td><td>0.275</td><td>0.431</td><td>0.257</td><td>0.208</td></tr>
    <tr style="border-bottom: 1px solid #ddd;"><td colspan="10"></td></tr>
    <tr><td>OPEN†</td><td>R50</td><td>704×256</td><td>47.0</td><td>56.5</td><td>0.573</td><td>0.275</td><td>0.413</td><td>0.235</td><td>0.193</td></tr>
    <tr bgcolor="#f2f2f2"><td><strong>STUR3D† (Ours)</strong></td><td>R50</td><td>704×256</td><td><strong>48.6</strong></td><td><strong>57.9</strong></td><td>0.562</td><td>0.269</td><td>0.362</td><td>0.237</td><td>0.202</td></tr>
    <tr style="border-bottom: 1px solid #ddd;"><td colspan="10"></td></tr>
    <tr><td>tgGBC</td><td>V2-99</td><td>320×800</td><td>52.1</td><td>60.3</td><td>0.533</td><td>0.268</td><td>0.344</td><td>0.210</td><td>0.192</td></tr>
    <tr bgcolor="#f2f2f2"><td><strong>STUR3D (Ours)</strong></td><td>V2-99</td><td>320×800</td><td><strong>53.0</strong></td><td><strong>61.2</strong></td><td>0.478</td><td>0.270</td><td>0.307</td><td>0.241</td><td>0.194</td></tr>
    <tr style="border-bottom: 1px solid #ddd;"><td colspan="10"></td></tr>
    <tr><td>Sparse4Dv2†§</td><td>R101</td><td>1408×512</td><td>52.1</td><td>60.8</td><td>0.519</td><td>0.265</td><td>0.364</td><td>0.199</td><td>0.180</td></tr>
    <tr bgcolor="#f2f2f2"><td><strong>STUR3D† (Ours)</strong></td><td>R101</td><td>1408×512</td><td><strong>53.1</strong></td><td><strong>61.3</strong></td><td>0.509</td><td>0.267</td><td>0.310</td><td>0.224</td><td>0.199</td></tr>
  </tbody>
</table>

### nuScenes Test Set
<table align="center">
  <thead>
    <tr style="border-bottom: 2px solid black;">
      <th align="left">Method</th>
      <th align="center">Backbone</th>
      <th align="center">Res.</th>
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
    <tr><td>RayDN</td><td>V2-99</td><td>640×1600</td><td>56.5</td><td>64.5</td><td>0.461</td><td>0.241</td><td>0.322</td><td>0.239</td><td>0.114</td></tr>
    <tr><td>FreqPDE</td><td>V2-99</td><td>640×1600</td><td>56.0</td><td>64.2</td><td>0.468</td><td>0.241</td><td>0.315</td><td>0.242</td><td>0.115</td></tr>
    <tr bgcolor="#f2f2f2"><td><strong>STUR3D (Ours)</strong></td><td>V2-99</td><td>640×1600</td><td><strong>57.9</strong></td><td><strong>64.6</strong></td><td>0.449</td><td>0.259</td><td>0.355</td><td>0.243</td><td>0.124</td></tr>
  </tbody>
</table>

<p align="center">
  <img src="./figs/compare.png" width="95%"><br>
  <i>Comparison with state-of-the-art methods on nuScenes dataset.</i>
</p>

---

## 📜 Citation
```bibtex
@inproceedings{fan2026stur3d,
  title={STUR3D: Spatio-Temporal Unified Representation Learning for 3D Object Detection},
  author={Fan, Huijie and Huang, Pengrui and Wang, Qiang and Fan, Baojie and Dong, Jiahua and Qu, Liangqiong},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2026}
}
