---
title: "Parallel WaveGAN: A fast waveform generation model based on generative adversarial networks with multi-resolution spectrogram"
date: 2019-10-21T20:18:27+09:00
draft: false
type: "project"
categories: ["TTS"]
tags: ["icassp"]
---

Preprint: [arXiv:1910.11480](https://arxiv.org/abs/1910.11480) (submitted to [ICASSP 2020](https://2020.ieeeicassp.org/))

TBA: We will publish English samples using the [LJSpeech dataset](https://keithito.com/LJ-Speech-Dataset/) soon.

- [Audio samples (Japanese)](#audio-samples-japanese)
- [Audio samples (English)](#audio-samples-english)

*Japanese samples were used in the subjective evaluations reported in our paper.*

## Authors

- Ryuichi Yamamoto (LINE Corp.)
- Eunwoo Song (NAVER Corp.)
- Jae-Min Kim (NAVER Corp.)

## Abstract

We propose Parallel WaveGAN[^1], a distillation-free, fast, and small-footprint waveform generation method using a generative adversarial network. In the proposed method, a non-autoregressive WaveNet is trained by jointly optimizing multi-resolution spectrogram and adversarial loss functions, which can effectively capture the time-frequency distribution of the realistic speech waveform. As our method does not require density distillation used in the conventional teacher-student framework, the entire model can be easily trained even with a small number of parameters. In particular, the proposed Parallel WaveGAN has only 1.44 M parameters and can generate 24 kHz speech waveform 28.68 times faster than real-time on a single GPU environment. Perceptual listening test results verify that our proposed method achieves 4.16 mean opinion score within a Transformer-based text-to-speech framework, which is comparative to the best distillation-based Parallel WaveNet system.

[^1]: Note that our work is not closely related to an unsupervised waveform synthesis model, [WaveGAN](https://arxiv.org/abs/1802.04208).

<div align="center"><img src="/images/icassp2020_fig.png" width="60%" /></div>

### Systems used for comparision

- **Ground truth**: Recorded speech.
- **WaveNet**: Gaussian WaveNet [\[1\]](https://arxiv.org/abs/1807.07281)
- **ClariNet-$L^{(1)}$**: ClariNet [\[1\]](https://arxiv.org/abs/1807.07281) with the single STFT auxiliary loss
- **ClariNet-$L^{(1,2,3)}$**: ClariNet with the multi-resolution STFT loss
- **ClariNet-GAN-$L^{(1,2,3)}$**: ClariNet with the multi-resolution STFT and adversarial losses [\[2\]](https://arxiv.org/abs/1807.07281)
- **Parallel WaveGAN-$L^{(1)}$**: Parallel WaveGAN with th single STFT loss
- **Parallel WaveGAN-$L^{(1,2,3)}$**: Parallel WaveGAN with the multi-resolution STFT loss

## Audio samples (Japanese)

1. Analysis/synthesis
2. Text-to-speech (Transformer TTS + vocoder models)

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

## Audio samples (English)

1. Analysis/synthesis
2. Text-to-speech ([ESPnet-TTS](https://arxiv.org/abs/1910.10909) + Our Parallel WaveGAN)

[LJSpeech dataset](https://keithito.com/LJ-Speech-Dataset/) is used for the test. Mel-spectrograms (with the range of 70 - 7600 Hz[^2]) were used for local conditioning.

[^2]: Audio quaility can be improved by using the full-band frequency range, but it may suffer from the over-smoothing problem in TTS.

*Please note that the English samples were not used in the subjective evaluations reported in our paper.*

### Analysis/synthesis

<p>That is reflected in definite and comprehensive operating procedures.</p>
<table><thead>
<tr><th>Ground truth</th><th>WaveNet</th><th>ClariNet-$L^{(1)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample01]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample01]-2-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="audio/dummy.wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>ClariNet-$L^{(1,2,3)}$</th><th>ClariNet-GAN-$L^{(1,2,3)}$</th><th>Parallel WaveGAN-$L^{(1)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="audio/dummy.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="audio/dummy.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample01]-6-Parallel WaveGAN (1spec).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Parallel WaveGAN-$L^{(1,2,3)}$ <font color="#0000cd">(ours)</font></th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample01]-7-Parallel WaveGAN (3spec) (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>The commission also recommends.</p>
<table><thead>
<tr><th>Ground truth</th><th>WaveNet</th><th>ClariNet-$L^{(1)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample02]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample02]-2-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="audio/dummy.wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>ClariNet-$L^{(1,2,3)}$</th><th>ClariNet-GAN-$L^{(1,2,3)}$</th><th>Parallel WaveGAN-$L^{(1)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="audio/dummy.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="audio/dummy.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample02]-6-Parallel WaveGAN (1spec).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Parallel WaveGAN-$L^{(1,2,3)}$ <font color="#0000cd">(ours)</font></th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample02]-7-Parallel WaveGAN (3spec) (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>That the secret service consciously set about the task of inculcating and maintaining the highest standard of excellence and esprit, for all of its personnel.</p>
<table><thead>
<tr><th>Ground truth</th><th>WaveNet</th><th>ClariNet-$L^{(1)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample03]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample03]-2-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="audio/dummy.wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>ClariNet-$L^{(1,2,3)}$</th><th>ClariNet-GAN-$L^{(1,2,3)}$</th><th>Parallel WaveGAN-$L^{(1)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="audio/dummy.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="audio/dummy.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample03]-6-Parallel WaveGAN (1spec).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Parallel WaveGAN-$L^{(1,2,3)}$ <font color="#0000cd">(ours)</font></th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample03]-7-Parallel WaveGAN (3spec) (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>This involves tight and unswerving discipline as well as the promotion of an outstanding degree of dedication and loyalty to duty.</p>
<table><thead>
<tr><th>Ground truth</th><th>WaveNet</th><th>ClariNet-$L^{(1)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample04]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample04]-2-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="audio/dummy.wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>ClariNet-$L^{(1,2,3)}$</th><th>ClariNet-GAN-$L^{(1,2,3)}$</th><th>Parallel WaveGAN-$L^{(1)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="audio/dummy.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="audio/dummy.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample04]-6-Parallel WaveGAN (1spec).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Parallel WaveGAN-$L^{(1,2,3)}$ <font color="#0000cd">(ours)</font></th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample04]-7-Parallel WaveGAN (3spec) (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>The commission emphasizes that it finds no causal connection between the assassination.</p>
<table><thead>
<tr><th>Ground truth</th><th>WaveNet</th><th>ClariNet-$L^{(1)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample05]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample05]-2-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="audio/dummy.wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>ClariNet-$L^{(1,2,3)}$</th><th>ClariNet-GAN-$L^{(1,2,3)}$</th><th>Parallel WaveGAN-$L^{(1)}$</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="audio/dummy.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="audio/dummy.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample05]-6-Parallel WaveGAN (1spec).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>Parallel WaveGAN-$L^{(1,2,3)}$ <font color="#0000cd">(ours)</font></th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample05]-7-Parallel WaveGAN (3spec) (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table>

### Text-to-speech

We combined our Parallel WaveGAN with [ESPnet-TTS](https://arxiv.org/abs/1910.10909). The systems used here are as follows:

- **Transformer.v3**: Transformer.v3 presented in [ESPnet-TTS](https://arxiv.org/abs/1910.10909).
- **MoL WaveNet**: WaveNet with mixture of logistics output distribution (shipped with ESPnet). Pre-emphasis/de-emphasis were applied to reduce perceptual noise (similar to [LPCNet](https://arxiv.org/abs/1810.11846)).
- **Parallel WaveGAN**: Our Parallel WaveGAN with multi-resolution spectrogram loss.

Note that **Transformer.v3 + MoL WaveNet** is the same as used in https://espnet.github.io/icassp2020-tts/.
Mel-spectrograms (with the range of 70 - 11025 Hz) were used for local conditioning.

<p>That is reflected in definite and comprehensive operating procedures.</p>
<table><thead>
<tr><th>Ground truth</th><th>Transformer.v3 + MoL WaveNet</th><th>Transformer.v3 + Parallel WaveGAN</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample01]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/LJSpeech/TTS/[LJ-Sample01]-1-MoL-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/LJSpeech/TTS/[LJ-Sample01]-2-Parallel WaveGAN.wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>The commission also recommends.</p>
<table><thead>
<tr><th>Ground truth</th><th>Transformer.v3 + MoL WaveNet</th><th>Transformer.v3 + Parallel WaveGAN</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample02]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/LJSpeech/TTS/[LJ-Sample02]-1-MoL-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/LJSpeech/TTS/[LJ-Sample02]-2-Parallel WaveGAN.wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>That the secret service consciously set about the task of inculcating and maintaining the highest standard of excellence and esprit, for all of its personnel.</p>
<table><thead>
<tr><th>Ground truth</th><th>Transformer.v3 + MoL WaveNet</th><th>Transformer.v3 + Parallel WaveGAN</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample03]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/LJSpeech/TTS/[LJ-Sample03]-1-MoL-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/LJSpeech/TTS/[LJ-Sample03]-2-Parallel WaveGAN.wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>This involves tight and unswerving discipline as well as the promotion of an outstanding degree of dedication and loyalty to duty.</p>
<table><thead>
<tr><th>Ground truth</th><th>Transformer.v3 + MoL WaveNet</th><th>Transformer.v3 + Parallel WaveGAN</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample04]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/LJSpeech/TTS/[LJ-Sample04]-1-MoL-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/LJSpeech/TTS/[LJ-Sample04]-2-Parallel WaveGAN.wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>The commission emphasizes that it finds no causal connection between the assassination.</p>
<table><thead>
<tr><th>Ground truth</th><th>Transformer.v3 + MoL WaveNet</th><th>Transformer.v3 + Parallel WaveGAN</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/icassp2020/LJSpeech/AnaSyn/[LJ-Sample05]-1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/LJSpeech/TTS/[LJ-Sample05]-1-MoL-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/icassp2020/LJSpeech/TTS/[LJ-Sample05]-2-Parallel WaveGAN.wav" type="audio/wav"></audio></td>
</tr></tbody></table>

## References

- W. Ping, K. Peng, and J. Chen, “ClariNet: Parallel wave generation in end-to-end text-to-speech,” in Proc. ICLR, 2019 ([arXiv](https://arxiv.org/abs/1807.07281)).
- R. Yamamoto, E. Song, and J.-M. Kim, “Probability density distillation with generative adversarial networks for high-quality parallel waveform generation,” in Proc. INTERSPEECH, 2019, pp. 699–703. ([ISCA archive](https://www.isca-speech.org/archive/Interspeech_2019/abstracts/1965.html))

## Acknowledgements

Work performed with nVoice, Clova Voice, Naver Corp.

## Citation

```
@misc{yamamoto2019parallel,
    title={Parallel WaveGAN: A fast waveform generation model based on generative adversarial networks with multi-resolution spectrogram},
    author={Ryuichi Yamamoto and Eunwoo Song and Jae-Min Kim},
    year={2019},
    eprint={1910.11480},
    archivePrefix={arXiv},
    primaryClass={eess.AS}
}
```
