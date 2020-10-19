---
title: "Probability Density Distillation with Generative Adversarial Networks for High-Quality Parallel Waveform Generation"
date: 2019-06-25T17:20:29+09:00
draft: false
categories: ["TTS"]
tags: ["interspeech"]
---

Preprint: [arXiv:1904.04472](https://arxiv.org/abs/1904.04472), Published version: [ISCA Archive Interspeech 2019](https://www.isca-speech.org/archive/Interspeech_2019/abstracts/1965.html)

## Authors

- Ryuichi Yamamoto (LINE Corp.)
- Eunwoo Song (NAVER Corp.)
- Jae-Min Kim (NAVER Corp.)

## Abstract

This paper proposes an effective probability density distillation (PDD) algorithm for WaveNet-based parallel waveform generation (PWG) systems. Recently proposed teacher-student frameworks in the PWG system have successfully achieved a real-time generation of speech signals. However, the difficulties optimizing the PDD criteria without auxiliary losses result in quality degradation of synthesized speech. To generate more natural speech signals within the teacher-student framework, we propose a novel optimization criterion based on generative adversarial networks (GANs). In the proposed method, the inverse autoregressive flow-based student model is incorporated as a generator in the GAN framework, and jointly optimized by the PDD mechanism with the proposed adversarial learning method. As this process encourages the student to model the distribution of realistic speech waveform, the perceptual quality of the synthesized speech becomes much more natural. Our experimental results verify that the PWG systems with the proposed method outperform both those using conventional approaches, and also autoregressive generation systems with a well-trained teacher WaveNet.

<div align="center"><img src="/images/interspeech2019_fig.png" width="90%" /></div>

## Audio samples

There are 8 different systems, that include 6 parallel waveform generation systems (Student-*) trained by different optimization criteria as follows:

1. **Ground truth**: Recorded speech.
2. **Teacher**: Teacher Gaussian WaveNet [[1]](https://arxiv.org/abs/1807.07281).
3. **Student-AX**: STFT auxiliary loss.
4. **Student-AXAD**: STFT and adversarial losses.
5. **Student-KL**: KLD loss (Ablation study; not used for subjective evaluations).
6. **Student-KLAX**: KLD and STFT auxiliary losses.
7. **Student-KLAXAD**: KLD, STFT, and adversarial losses (proposed).
8. **Student-KLAXAD***: Weights optimized version of the above (proposed).

### Copy-synthesis

#### Japanese female speaker

<p>Sample 1</p>
<table><thead>
<tr><th>Ground truth</th><th>Teacher</th><th>Student-AX</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/interspeech2019/[Sample01]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample01]-2-Teacher.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample01]-3-Student-AX (AuxLoss).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Student-AXAV</th><th>Student-KL</th><th>Student-KLAX</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/interspeech2019/[Sample01]-4-Student-AXAV (AuxLoss + AdvLoss).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample01]-5-Student-KL (KLD only; ablation study).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample01]-6-Student-KLAX (KLD + AuxLoss).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Student-KLAXAD</th><th>Student-KLAXAD\*</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/interspeech2019/[Sample01]-7-Student-KLAXAD (Proposed; KLD + AuxLoss + AdvLoss).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample01]-8-Student-KLAXAD (Proposed; weights optimized version).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 2</p>
<table><thead>
<tr><th>Ground truth</th><th>Teacher</th><th>Student-AX</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/interspeech2019/[Sample02]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample02]-2-Teacher.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample02]-3-Student-AX (AuxLoss).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Student-AXAV</th><th>Student-KL</th><th>Student-KLAX</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/interspeech2019/[Sample02]-4-Student-AXAV (AuxLoss + AdvLoss).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample02]-5-Student-KL (KLD only; ablation study).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample02]-6-Student-KLAX (KLD + AuxLoss).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Student-KLAXAD</th><th>Student-KLAXAD\*</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/interspeech2019/[Sample02]-7-Student-KLAXAD (Proposed; KLD + AuxLoss + AdvLoss).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample02]-8-Student-KLAXAD (Proposed; weights optimized version).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 3</p>
<table><thead>
<tr><th>Ground truth</th><th>Teacher</th><th>Student-AX</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/interspeech2019/[Sample03]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample03]-2-Teacher.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample03]-3-Student-AX (AuxLoss).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Student-AXAV</th><th>Student-KL</th><th>Student-KLAX</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/interspeech2019/[Sample03]-4-Student-AXAV (AuxLoss + AdvLoss).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample03]-5-Student-KL (KLD only; ablation study).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample03]-6-Student-KLAX (KLD + AuxLoss).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Student-KLAXAD</th><th>Student-KLAXAD\*</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/interspeech2019/[Sample03]-7-Student-KLAXAD (Proposed; KLD + AuxLoss + AdvLoss).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample03]-8-Student-KLAXAD (Proposed; weights optimized version).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 4</p>
<table><thead>
<tr><th>Ground truth</th><th>Teacher</th><th>Student-AX</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/interspeech2019/[Sample04]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample04]-2-Teacher.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample04]-3-Student-AX (AuxLoss).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Student-AXAV</th><th>Student-KL</th><th>Student-KLAX</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/interspeech2019/[Sample04]-4-Student-AXAV (AuxLoss + AdvLoss).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample04]-5-Student-KL (KLD only; ablation study).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample04]-6-Student-KLAX (KLD + AuxLoss).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Student-KLAXAD</th><th>Student-KLAXAD\*</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/interspeech2019/[Sample04]-7-Student-KLAXAD (Proposed; KLD + AuxLoss + AdvLoss).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample04]-8-Student-KLAXAD (Proposed; weights optimized version).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 5</p>
<table><thead>
<tr><th>Ground truth</th><th>Teacher</th><th>Student-AX</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/interspeech2019/[Sample05]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample05]-2-Teacher.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample05]-3-Student-AX (AuxLoss).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Student-AXAV</th><th>Student-KL</th><th>Student-KLAX</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/interspeech2019/[Sample05]-4-Student-AXAV (AuxLoss + AdvLoss).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample05]-5-Student-KL (KLD only; ablation study).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample05]-6-Student-KLAX (KLD + AuxLoss).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Student-KLAXAD</th><th>Student-KLAXAD\*</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/interspeech2019/[Sample05]-7-Student-KLAXAD (Proposed; KLD + AuxLoss + AdvLoss).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/interspeech2019/[Sample05]-8-Student-KLAXAD (Proposed; weights optimized version).wav" type="audio/wav"></audio></td>
</tr></tbody></table>

## References

- [1]: W. Ping, K. Peng, and J. Chen, “ClariNet: Parallel wave generation in end-to-end text-to-speech,” in Proc. ICLR, 2019 ([arXiv](https://arxiv.org/abs/1807.07281)).

## Acknowledgements

Work performed with nVoice, Clova Voice, Naver Corp.

## Citation

```
@inproceedings{Yamamoto2019,
  author={Ryuichi Yamamoto and Eunwoo Song and Jae-Min Kim},
  title={{Probability Density Distillation with Generative Adversarial Networks for High-Quality Parallel Waveform Generation}},
  year=2019,
  booktitle={Proc. Interspeech 2019},
  pages={699--703},
  doi={10.21437/Interspeech.2019-1965},
  url={http://dx.doi.org/10.21437/Interspeech.2019-1965}
}
```
