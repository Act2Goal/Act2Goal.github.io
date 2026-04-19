<div align="center">

# Act2Goal

## From World Model to General Goal-conditioned Policy

<p>
  Pengfei Zhou<sup>1*</sup>, Liliang Chen<sup>1*</sup>, Shengcong Chen<sup>1</sup>, Di Chen<sup>1</sup><br>
  Wenzhi Zhao<sup>1</sup>, Rongjun Jin<sup>1</sup>, Guanghui Ren<sup>1</sup>, Jianlan Luo<sup>1†</sup>
</p>

<p><sup>1</sup> Agibot Research</p>

<p>
  <a href="http://arxiv.org/abs/2512.23541"><strong>Arxiv</strong></a>
  &nbsp;|&nbsp;
  <a href="https://www.agibot.com/research/"><strong>About Us</strong></a>
</p>

</div>

<p align="center">
  <video src="./web_videos/PR_video.mp4" controls muted playsinline poster="./figures/cover.png" width="100%"></video>
</p>

<p align="center">
  <img src="./figures/fig1.png" alt="System overview of Act2Goal" width="100%" />
</p>

<p align="center"><em>System overview of Act2Goal</em></p>

---

# Generalization

<p align="center"><em>Real-world scenarios that are difficult to specify precisely via language and require fine-grained control for successful execution.</em></p>

## In-Domain

<table>
  <tr>
    <td align="center" valign="top" width="33.33%">
      <strong>Write</strong><br><br>
      <video src="./web_videos/WRITE_ID.mp4" controls muted playsinline width="100%"></video><br>
      <sub>The robot writes the English word shown in the goal image on a whiteboard using a marker pen.</sub>
    </td>
    <td align="center" valign="top" width="33.33%">
      <strong>Dessert</strong><br><br>
      <video src="./web_videos/DESSERT_ID.mp4" controls muted playsinline width="100%"></video><br>
      <sub>The robot performs dessert plating with reference to a given goal image.</sub>
    </td>
    <td align="center" valign="top" width="33.33%">
      <strong>Plug-In</strong><br><br>
      <video src="./web_videos/Plug_ID.mp4" controls muted playsinline width="100%"></video><br>
      <sub>Following the goal image's guidance, the robot picks up bearing workpieces and inserts them into small holes one by one.</sub>
    </td>
  </tr>
</table>

## Out of Domain

<table>
  <tr>
    <td align="center" valign="top" width="33.33%">
      <strong>Write</strong><br><br>
      <video src="./web_videos/WRITE_OOD.mp4" controls muted playsinline width="100%"></video><br>
      <sub>The robot writes words unseen during training on a whiteboard using a marker pen.</sub>
    </td>
    <td align="center" valign="top" width="33.33%">
      <strong>Dessert</strong><br><br>
      <video src="./web_videos/DESSERT_OOD.mp4" controls muted playsinline width="100%"></video><br>
      <sub>The robot performs dessert plating with reference to a given goal image, using a plate and dessert types unseen in the training data.</sub>
    </td>
    <td align="center" valign="top" width="33.33%">
      <strong>Plug-In</strong><br><br>
      <video src="./web_videos/Plug_OOD.mp4" controls muted playsinline width="100%"></video><br>
      <sub>The robot completes a plug-in task unseen in training: inserting a cylindrical drink bottle into a cup holder.</sub>
    </td>
  </tr>
</table>

## Real-World Tasks Results

<table>
  <thead>
    <tr>
      <th></th>
      <th>Model/Task</th>
      <th>Whiteboard Word Writing</th>
      <th>Dessert Plating</th>
      <th>Plug-In Operation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center" rowspan="4"><strong>ID</strong></td>
      <td>DP-GC</td>
      <td align="center">0.00</td>
      <td align="center">0.10</td>
      <td align="center">0.00</td>
    </tr>
    <tr>
      <td>π<sub>0.5</sub>-GC</td>
      <td align="center">0.23</td>
      <td align="center">0.18</td>
      <td align="center">0.00</td>
    </tr>
    <tr>
      <td>HyperGoalNet</td>
      <td align="center">0.00</td>
      <td align="center">0.08</td>
      <td align="center">0.00</td>
    </tr>
    <tr>
      <td><strong>Act2Goal</strong></td>
      <td align="center"><strong>0.93</strong></td>
      <td align="center"><strong>0.75</strong></td>
      <td align="center"><strong>0.45</strong></td>
    </tr>
    <tr>
      <td align="center" rowspan="4"><strong>OOD</strong></td>
      <td>DP-GC</td>
      <td align="center">0.00</td>
      <td align="center">0.00</td>
      <td align="center">0.00</td>
    </tr>
    <tr>
      <td>π<sub>0.5</sub>-GC</td>
      <td align="center">0.20</td>
      <td align="center">0.05</td>
      <td align="center">0.00</td>
    </tr>
    <tr>
      <td>HyperGoalNet</td>
      <td align="center">0.00</td>
      <td align="center">0.00</td>
      <td align="center">0.00</td>
    </tr>
    <tr>
      <td><strong>Act2Goal</strong></td>
      <td align="center"><strong>0.90</strong></td>
      <td align="center"><strong>0.48</strong></td>
      <td align="center"><strong>0.30</strong></td>
    </tr>
  </tbody>
</table>

## Simulated Benchmarks

<p align="center"><em>Four tasks from the RoboTwin 2.0 benchmark with both easy (no noise) and hard (with noise) environment settings.</em></p>

<table>
  <thead>
    <tr>
      <th></th>
      <th>Model/Task</th>
      <th>Move Can</th>
      <th>Pick Bottles</th>
      <th>Place Cup</th>
      <th>Place Shoe</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center" rowspan="4"><strong>Easy</strong></td>
      <td>DP-GC</td>
      <td align="center">0.18</td>
      <td align="center">0.04</td>
      <td align="center">0.03</td>
      <td align="center">0.04</td>
    </tr>
    <tr>
      <td>π<sub>0.5</sub>-GC</td>
      <td align="center">0.54</td>
      <td align="center">0.13</td>
      <td align="center">0.16</td>
      <td align="center">0.30</td>
    </tr>
    <tr>
      <td>HyperGoalNet</td>
      <td align="center">0.11</td>
      <td align="center">0.08</td>
      <td align="center">0.08</td>
      <td align="center">0.01</td>
    </tr>
    <tr>
      <td><strong>Act2Goal</strong></td>
      <td align="center"><strong>0.62</strong></td>
      <td align="center"><strong>0.80</strong></td>
      <td align="center"><strong>0.64</strong></td>
      <td align="center"><strong>0.52</strong></td>
    </tr>
    <tr>
      <td align="center" rowspan="4"><strong>Hard</strong></td>
      <td>DP-GC</td>
      <td align="center">0.00</td>
      <td align="center">0.00</td>
      <td align="center">0.00</td>
      <td align="center">0.00</td>
    </tr>
    <tr>
      <td>π<sub>0.5</sub>-GC</td>
      <td align="center"><strong>0.42</strong></td>
      <td align="center">0.06</td>
      <td align="center">0.04</td>
      <td align="center">0.06</td>
    </tr>
    <tr>
      <td>HyperGoalNet</td>
      <td align="center">0.00</td>
      <td align="center">0.00</td>
      <td align="center">0.00</td>
      <td align="center">0.00</td>
    </tr>
    <tr>
      <td>Act2Goal</td>
      <td align="center">0.13</td>
      <td align="center"><strong>0.43</strong></td>
      <td align="center"><strong>0.13</strong></td>
      <td align="center"><strong>0.15</strong></td>
    </tr>
  </tbody>
</table>

---

# Autonomous Improvement

<p align="center"><em>Rapid improvement of success rate by Online-training.</em></p>

## Real-World Examples

<table>
  <tr>
    <td align="center" valign="top" width="33.33%">
      <strong>Drawing Unseen Pattern 1</strong><br><br>
      <video src="./web_videos/OA-drawing unseen_short.mp4" controls muted playsinline width="100%"></video><br>
      <sub>The robot learns to draw a cross (unseen pattern in training) through 27-min of online training.</sub>
    </td>
    <td align="center" valign="top" width="33.33%">
      <strong>Drawing Unseen Pattern 2</strong><br><br>
      <video src="./web_videos/OA-drawing unseen2.mp4" controls muted playsinline width="100%"></video><br>
      <sub>The robot learns to draw a paper clip (unseen pattern in training) through 20-min of online training.</sub>
    </td>
    <td align="center" valign="top" width="33.33%">
      <strong>Plug bottle into cup holder</strong><br><br>
      <video src="./web_videos/OA-plug bottle cup holder.mp4" controls muted playsinline width="100%"></video><br>
      <sub>The robot learns to accurately place beverages into cup holders through 17-min of online training.</sub>
    </td>
  </tr>
</table>

## Simulated Benchmarks

Online-training effectiveness test in the Robotwin Simulator.  
Figure on the left shows success rates improvement for all four challenging scenarios.  
Figure in the middle shows success rates improvement for different replay buffer settings.  
Video on the right demonstrates the progress of the robot's movements during online simulation learning.

<p align="center"><em>(A: Move Can Pot, B: Pick Bottles, C: Place Cup, D: Place Shoe)</em></p>

<p align="center">
  <img src="figures/robotwin_online_train.png" alt="Online training results comparison" width="100%" />
</p>

<p align="center">
  <video src="web_videos/OA-OOD sim tasks.mp4" controls muted playsinline width="100%"></video>
</p>

---

# Ablation Study for Multi-Scale Temporal Hashing

<p align="center"><em>The MSTH-based prediction strategy significantly outperforms the widely-used fixed-horizon action chunking approach in goal-conditioned tasks, particularly for long-horizon scenarios.</em></p>

<table>
  <thead>
    <tr>
      <th></th>
      <th>Model</th>
      <th>Short</th>
      <th>Medium</th>
      <th>Long</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center" rowspan="2"><strong>ID</strong></td>
      <td>w/o MSTH</td>
      <td align="center">0.95</td>
      <td align="center">0.35</td>
      <td align="center">0.10</td>
    </tr>
    <tr>
      <td>w/ MSTH</td>
      <td align="center"><strong>0.95</strong></td>
      <td align="center"><strong>0.90</strong></td>
      <td align="center"><strong>0.90</strong></td>
    </tr>
    <tr>
      <td align="center" rowspan="2"><strong>OOD</strong></td>
      <td>w/o MSTH</td>
      <td align="center">0.60</td>
      <td align="center">0.20</td>
      <td align="center">0.00</td>
    </tr>
    <tr>
      <td>w/ MSTH</td>
      <td align="center"><strong>0.93</strong></td>
      <td align="center"><strong>0.90</strong></td>
      <td align="center"><strong>0.88</strong></td>
    </tr>
  </tbody>
</table>

## Goal-conditioned Video generation via MSTH

The video is divided into two parts: a short-horizon proximal segment with densely and uniformly sampled future states for fine-grained dynamics, and a long-horizon distal segment with logarithmically spaced samples from the remaining path to the goal, enabling coarser, goal-directed planning.

<table>
  <tr>
    <td width="33.33%">
      <video src="web_videos/case3.mp4" controls muted playsinline width="100%"></video>
    </td>
    <td width="33.33%">
      <video src="web_videos/case4.mp4" controls muted playsinline width="100%"></video>
    </td>
    <td width="33.33%">
      <video src="web_videos/case5.mp4" controls muted playsinline width="100%"></video>
    </td>
  </tr>
</table>

---


## Citation

```bibtex
@misc{zhou2025act2goalworldmodelgeneral,
      title={Act2Goal: From World Model to General Goal-conditioned Policy},
      author={Pengfei Zhou and Liliang Chen and Shengcong Chen and Di Chen and Wenzhi Zhao and Rongjun Jin and Guanghui Ren and Jianlan Luo},
      year={2025},
      eprint={2512.23541},
      archivePrefix={arXiv},
      primaryClass={cs.RO},
      url={https://arxiv.org/abs/2512.23541},
}
```

<div align="center">© 2025 AgiBot Research.</div>
