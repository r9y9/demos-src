---
title: "Parallel WaveGAN: A fast waveform generation model based on generative adversarial networks with multi-resolution spectrogram"
date: 2019-10-21T20:18:27+09:00
draft: false
type: "project"
categories: ["TTS"]
tags: ["icassp"]
---

Preprint: [TBD](https://arxiv.org/abs/1904.04472) (submitted to [ICASSP 2020](https://2020.ieeeicassp.org/))

TBA: We will publish English samples using the [LJSpeech dataset](https://keithito.com/LJ-Speech-Dataset/) soon.

## Authors

- Ryuichi Yamamoto (LINE Corp.)
- Eunwoo Song (NAVER Corp.)
- Jae-Min Kim (NAVER Corp.)

## Abstract

We propose Parallel WaveGAN[^1], a distillation-free, fast, and small-footprint waveform generation method using a generative adversarial network. In the proposed method, a non-autoregressive WaveNet is trained by jointly optimizing multi-resolution spectrogram and adversarial loss functions, which can effectively capture the time-frequency distribution of the realistic speech waveform. As our method does not require density distillation used in the conventional teacher-student framework, the entire model can be easily trained even with a small number of parameters. In particular, the proposed Parallel WaveGAN has only 1.44 M parameters and can generate 24 kHz speech waveform 28.68 times faster than real-time on a single GPU environment. Perceptual listening test results verify that our proposed method achieves 4.16 mean opinion score within a Transformer-based text-to-speech framework, which is comparative to the best distillation-based Parallel WaveNet system.

[^1]: Note that our work is not closely related to an unsupervised waveform synthesis model, [WaveGAN](https://arxiv.org/abs/1802.04208).

<div align="center"><img src="/images/icassp2020_fig.png" width="60%" /></div>

## Audio samples (Japanese)

1. Analysis/synthesis
2. Text-to-speech (Transformer TTS + vocoder models)

The following samples are used in our subjective evaluations.

### Systems used for comparision

- **Ground truth**: Recorded speech.
- **WaveNet**: Gaussian WaveNet [\[1\]](https://arxiv.org/abs/1807.07281)
- **ClariNet-$L^{(1)}$**: ClariNet [\[1\]](https://arxiv.org/abs/1807.07281) with the single STFT auxiliary loss
- **ClariNet-$L^{(1,2,3)}$**: ClariNet with the multi-resolution STFT loss
- **ClariNet-GAN-$L^{(1,2,3)}$**: ClariNet with the multi-resolution STFT and adversarial losses [\[2\]](https://arxiv.org/abs/1807.07281)
- **Parallel WaveGAN-$L^{(1)}$**: Parallel WaveGAN with th single STFT loss
- **Parallel WaveGAN-$L^{(1,2,3)}$**: Parallel WaveGAN with the multi-resolution STFT loss

### Analysis/synthesis

<p>Sample 1</p>
<table><thead>
<tr><th>Ground truth</th><th>WaveNet</th><th>ClariNet-$L^{(1)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample01]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample01]-2-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample01]-3-ClariNet (1spec).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>ClariNet-$L^{(1,2,3)}$</th><th>ClariNet-GAN-$L^{(1,2,3)}$</th><th>Parallel WaveGAN-$L^{(1)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample01]-4-ClariNet (3spec).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample01]-5-ClariNet-GAN (3spec).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample01]-6-Parallel WaveGAN (1spec).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Parallel WaveGAN-$L^{(1,2,3)}$ <font color="#0000cd">(ours)</font></th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample01]-7-Parallel WaveGAN (3spec) (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 2</p>
<table><thead>
<tr><th>Ground truth</th><th>WaveNet</th><th>ClariNet-$L^{(1)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample02]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample02]-2-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample02]-3-ClariNet (1spec).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>ClariNet-$L^{(1,2,3)}$</th><th>ClariNet-GAN-$L^{(1,2,3)}$</th><th>Parallel WaveGAN-$L^{(1)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample02]-4-ClariNet (3spec).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample02]-5-ClariNet-GAN (3spec).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample02]-6-Parallel WaveGAN (1spec).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Parallel WaveGAN-$L^{(1,2,3)}$ <font color="#0000cd">(ours)</font></th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample02]-7-Parallel WaveGAN (3spec) (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 3</p>
<table><thead>
<tr><th>Ground truth</th><th>WaveNet</th><th>ClariNet-$L^{(1)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample03]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample03]-2-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample03]-3-ClariNet (1spec).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>ClariNet-$L^{(1,2,3)}$</th><th>ClariNet-GAN-$L^{(1,2,3)}$</th><th>Parallel WaveGAN-$L^{(1)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample03]-4-ClariNet (3spec).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample03]-5-ClariNet-GAN (3spec).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample03]-6-Parallel WaveGAN (1spec).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Parallel WaveGAN-$L^{(1,2,3)}$ <font color="#0000cd">(ours)</font></th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample03]-7-Parallel WaveGAN (3spec) (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 4</p>
<table><thead>
<tr><th>Ground truth</th><th>WaveNet</th><th>ClariNet-$L^{(1)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample04]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample04]-2-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample04]-3-ClariNet (1spec).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>ClariNet-$L^{(1,2,3)}$</th><th>ClariNet-GAN-$L^{(1,2,3)}$</th><th>Parallel WaveGAN-$L^{(1)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample04]-4-ClariNet (3spec).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample04]-5-ClariNet-GAN (3spec).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample04]-6-Parallel WaveGAN (1spec).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Parallel WaveGAN-$L^{(1,2,3)}$ <font color="#0000cd">(ours)</font></th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample04]-7-Parallel WaveGAN (3spec) (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 5</p>
<table><thead>
<tr><th>Ground truth</th><th>WaveNet</th><th>ClariNet-$L^{(1)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample05]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample05]-2-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample05]-3-ClariNet (1spec).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>ClariNet-$L^{(1,2,3)}$</th><th>ClariNet-GAN-$L^{(1,2,3)}$</th><th>Parallel WaveGAN-$L^{(1)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample05]-4-ClariNet (3spec).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample05]-5-ClariNet-GAN (3spec).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample05]-6-Parallel WaveGAN (1spec).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Parallel WaveGAN-$L^{(1,2,3)}$ <font color="#0000cd">(ours)</font></th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample05]-7-Parallel WaveGAN (3spec) (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table>

### Text-to-speech

<p>Sample 1</p>
<table><thead>
<tr><th>Ground truth</th><th>Transformer + WaveNet</th><th>Transformer + ClariNet-$L^{(1,2,3)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample01]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/TTS/[Sample01]-2-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/TTS/[Sample01]-4-ClariNet (3spec).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Transformer + ClariNet-GAN-$L^{(1,2,3)}$</th><th>Transformer + Parallel WaveGAN--$L^{(1,2,3)}$ <font color="#0000cd">(ours)</font></th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/TTS/[Sample01]-5-ClariNet-GAN (3spec).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/TTS/[Sample01]-7-Parallel WaveGAN (3spec) (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 2</p>
<table><thead>
<tr><th>Ground truth</th><th>Transformer + WaveNet</th><th>Transformer + ClariNet-$L^{(1,2,3)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample02]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/TTS/[Sample02]-2-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/TTS/[Sample02]-4-ClariNet (3spec).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Transformer + ClariNet-GAN-$L^{(1,2,3)}$</th><th>Transformer + Parallel WaveGAN--$L^{(1,2,3)}$ <font color="#0000cd">(ours)</font></th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/TTS/[Sample02]-5-ClariNet-GAN (3spec).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/TTS/[Sample02]-7-Parallel WaveGAN (3spec) (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 3</p>
<table><thead>
<tr><th>Ground truth</th><th>Transformer + WaveNet</th><th>Transformer + ClariNet-$L^{(1,2,3)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample03]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/TTS/[Sample03]-2-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/TTS/[Sample03]-4-ClariNet (3spec).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Transformer + ClariNet-GAN-$L^{(1,2,3)}$</th><th>Transformer + Parallel WaveGAN--$L^{(1,2,3)}$ <font color="#0000cd">(ours)</font></th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/TTS/[Sample03]-5-ClariNet-GAN (3spec).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/TTS/[Sample03]-7-Parallel WaveGAN (3spec) (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 4</p>
<table><thead>
<tr><th>Ground truth</th><th>Transformer + WaveNet</th><th>Transformer + ClariNet-$L^{(1,2,3)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample04]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/TTS/[Sample04]-2-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/TTS/[Sample04]-4-ClariNet (3spec).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Transformer + ClariNet-GAN-$L^{(1,2,3)}$</th><th>Transformer + Parallel WaveGAN--$L^{(1,2,3)}$ <font color="#0000cd">(ours)</font></th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/TTS/[Sample04]-5-ClariNet-GAN (3spec).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/TTS/[Sample04]-7-Parallel WaveGAN (3spec) (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 5</p>
<table><thead>
<tr><th>Ground truth</th><th>Transformer + WaveNet</th><th>Transformer + ClariNet-$L^{(1,2,3)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/AnaSyn/[Sample05]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/TTS/[Sample05]-2-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/TTS/[Sample05]-4-ClariNet (3spec).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Transformer + ClariNet-GAN-$L^{(1,2,3)}$</th><th>Transformer + Parallel WaveGAN--$L^{(1,2,3)}$ <font color="#0000cd">(ours)</font></th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/TTS/[Sample05]-5-ClariNet-GAN (3spec).wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/TTS/[Sample05]-7-Parallel WaveGAN (3spec) (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table>

## References

- [1]: W. Ping, K. Peng, and J. Chen, “ClariNet: Parallel wave generation in end-to-end text-to-speech,” in Proc. ICLR, 2019 ([arXiv](https://arxiv.org/abs/1807.07281)).
- [2]: R. Yamamoto, E. Song, and J.-M. Kim, “Probability density distillation with generative adversarial networks for high-quality parallel waveform generation,” in Proc. INTERSPEECH, 2019, pp. 699–703. ([ISCA archive](https://www.isca-speech.org/archive/Interspeech_2019/abstracts/1965.html))

## Acknowledgements

Work performed with nVoice, Clova Voice, Naver Corp.
