---
title: "Parallel waveform synthesis based on generative adversarial networks with voicing-aware conditional discriminators"
date: 2020-10-21T23:38:48+09:00
draft: false
categories: ["TTS"]
tags: ["icassp"]
---

Preprint: [arXiv:2010.14151](https://arxiv.org/abs/2010.14151) (submitted to [ICASSP 2021](https://2021.ieeeicassp.org/))

## Table of contents

- [Analysis/synthesis samples (Japanese)](#analysis-synthesis)
- [Text-to-speech samples (Japanese)](#text-to-speech)
- [Bonus: analysis/synthesis samples for CMU ARCTIC (English)](#bonus-analysis-synthesis-english)


## Authors

- Ryuichi Yamamoto (LINE Corp.)
- Eunwoo Song (NAVER Corp.)
- Min-Jae Hwang (Search Solutions Inc.)
- Jae-Min Kim (NAVER Corp.)

## Abstract

This paper proposes voicing-aware conditional discriminators for Parallel WaveGAN-based waveform synthesis systems. In this framework, we adopt a projection-based conditioning method that can significantly improve the discriminator’s performance. Furthermore, the conventional discriminator is separated into two waveform discriminators for modeling voiced and unvoiced speech. As each discriminator learns the distinctive characteristics of the harmonic and noise components, respectively, the adversarial training process becomes more efficient, allowing the generator to produce more realistic speech waveforms. Subjective test results demonstrate the superiority of the proposed method over the conventional Parallel WaveGAN and WaveNet systems. In particular, our speaker-independently trained model within a FastSpeech 2 based text-to-speech framework achieves the mean opinion scores of 4.20, 4.18, 4.21, and 4.31 for four Japanese speakers, respectively.

<div align="center"><img src="/images/icassp2021_fig.png" width="50%" /></div>

## Systems for comparision

| System                       | Voiced segments | Unvoiced segments | Discriminator conditioning|
|------------------------------|----------------------|------------------------|-------------------|
| S1-WaveNet [\[1\]](https://arxiv.org/abs/1807.07281)               | -                    | -                      | -                 |
| S2-PWG [\[2\]](https://arxiv.org/abs/1910.11480)                   | -                    | -                      | -                 |
| S3-PWG-cGAN-D            | -                    | -                      | Yes               |
| S4-PWG-V/UV-D            | $D^{\mathrm{{v}}}$                | $D^{\mathrm{{v}}}$                  | Yes               |
| S5-PWG-V/UV-D            | $D^{\mathrm{{uv}}}$                | $D^{\mathrm{{v}}}$                  | Yes               |
| S6-PWG-V/UV-D            | $D^{\mathrm{{uv}}}$                | $D^{\mathrm{{uv}}}$                  | Yes               |
| S7-PWG-V/UV-D (proposed) | $D^{\mathrm{{v}}}$                | $D^{\mathrm{{uv}}}$                  | Yes               |
| Recordings               | -                    | -                      | -                 |

- $D^{\mathrm{{v}}}$: 1-D dilated CNN discrimiantor with the reseptive field size of 127.
- $D^{\mathrm{{uv}}}$: 1-D CNN discrimiantor with the reseptive field size of 13.

PWG denotes Parallel WaveGAN for short. Systems S2-PWG and S3-PWG-cGAN-D used $D^{\mathrm{{v}}}$  as the primary discriminator. **Note that all the Parallel WaveGAN systems used the same generator architecture and training configurations; they only differed in the discriminator settings.**

## Analysis/synthesis

### F1 (female)

<p>Sample 1</p><table><thead>
<tr><th>Recording</th><th>S1-WaveNet</th><th>S2-PWG</th><th><font color="#0000cd">S7-PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/AnaSyn/[Test01]-R1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/AnaSyn/[Test01]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/AnaSyn/[Test01]-S2-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/AnaSyn/[Test01]-S7-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>S3-PWG-cGAN-D</th><th>S4-PWG-V/UV-D</th><th>S5-PWG-V/UV-D</th><th>S6-PWG-V/UV-D</th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/AnaSyn/[Test01]-S3-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/AnaSyn/[Test01]-S4-PWG-VUV-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/AnaSyn/[Test01]-S5-PWG-VUV-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/AnaSyn/[Test01]-S6-PWG-VUV-D.wav" type="audio/wav"></audio></td>
</tr></tbody></table>

### F2 (female)

<p>Sample 1</p><table><thead>
<tr><th>Recording</th><th>S1-WaveNet</th><th>S2-PWG</th><th><font color="#0000cd">S7-PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/AnaSyn/[Test01]-R1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/AnaSyn/[Test01]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/AnaSyn/[Test01]-S2-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/AnaSyn/[Test01]-S7-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>S3-PWG-cGAN-D</th><th>S4-PWG-V/UV-D</th><th>S5-PWG-V/UV-D</th><th>S6-PWG-V/UV-D</th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/AnaSyn/[Test01]-S3-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/AnaSyn/[Test01]-S4-PWG-VUV-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/AnaSyn/[Test01]-S5-PWG-VUV-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/AnaSyn/[Test01]-S6-PWG-VUV-D.wav" type="audio/wav"></audio></td>
</tr></tbody></table>

### M1 (male)

<p>Sample 1</p><table><thead>
<tr><th>Recording</th><th>S1-WaveNet</th><th>S2-PWG</th><th><font color="#0000cd">S7-PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/AnaSyn/[Test01]-R1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/AnaSyn/[Test01]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/AnaSyn/[Test01]-S2-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/AnaSyn/[Test01]-S7-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>S3-PWG-cGAN-D</th><th>S4-PWG-V/UV-D</th><th>S5-PWG-V/UV-D</th><th>S6-PWG-V/UV-D</th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/AnaSyn/[Test01]-S3-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/AnaSyn/[Test01]-S4-PWG-VUV-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/AnaSyn/[Test01]-S5-PWG-VUV-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/AnaSyn/[Test01]-S6-PWG-VUV-D.wav" type="audio/wav"></audio></td>
</tr></tbody></table>

### M2 (male)

<p>Sample 1</p><table><thead>
<tr><th>Recording</th><th>S1-WaveNet</th><th>S2-PWG</th><th><font color="#0000cd">S7-PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/AnaSyn/[Test01]-R1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/AnaSyn/[Test01]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/AnaSyn/[Test01]-S2-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/AnaSyn/[Test01]-S7-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>S3-PWG-cGAN-D</th><th>S4-PWG-V/UV-D</th><th>S5-PWG-V/UV-D</th><th>S6-PWG-V/UV-D</th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/AnaSyn/[Test01]-S3-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/AnaSyn/[Test01]-S4-PWG-VUV-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/AnaSyn/[Test01]-S5-PWG-VUV-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/AnaSyn/[Test01]-S6-PWG-VUV-D.wav" type="audio/wav"></audio></td>
</tr></tbody></table>

## Text-to-speech


FastSpeech 2 ([\[3\]](https://arxiv.org/abs/2006.04558)) based acoustic models were used for text-to-speech experiments.

### F1 (female)

<p>Sample 1</p><table><thead>
<tr><th>Recording</th><th>FastSpeech 2 + WaveNet</th><th>FastSpeech 2 + PWG</th><th><font color="#0000cd">FastSpeech 2 + PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/TTS/[Test01]-R1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/TTS/[Test01]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/TTS/[Test01]-S2-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/TTS/[Test01]-S7-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>FastSpeech 2 + PWG-cGAN-D</th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/TTS/[Test01]-S3-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 2</p><table><thead>
<tr><th>Recording</th><th>FastSpeech 2 + WaveNet</th><th>FastSpeech 2 + PWG</th><th><font color="#0000cd">FastSpeech 2 + PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/TTS/[Test02]-R1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/TTS/[Test02]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/TTS/[Test02]-S2-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/TTS/[Test02]-S7-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>FastSpeech 2 + PWG-cGAN-D</th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/TTS/[Test02]-S3-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 3</p><table><thead>
<tr><th>Recording</th><th>FastSpeech 2 + WaveNet</th><th>FastSpeech 2 + PWG</th><th><font color="#0000cd">FastSpeech 2 + PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/TTS/[Test03]-R1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/TTS/[Test03]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/TTS/[Test03]-S2-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/TTS/[Test03]-S7-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>FastSpeech 2 + PWG-cGAN-D</th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F1/TTS/[Test03]-S3-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
</tr></tbody></table>

### F2 (female)

<p>Sample 1</p><table><thead>
<tr><th>Recording</th><th>FastSpeech 2 + WaveNet</th><th>FastSpeech 2 + PWG</th><th><font color="#0000cd">FastSpeech 2 + PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/TTS/[Test01]-R1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/TTS/[Test01]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/TTS/[Test01]-S2-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/TTS/[Test01]-S7-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>FastSpeech 2 + PWG-cGAN-D</th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/TTS/[Test01]-S3-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 2</p><table><thead>
<tr><th>Recording</th><th>FastSpeech 2 + WaveNet</th><th>FastSpeech 2 + PWG</th><th><font color="#0000cd">FastSpeech 2 + PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/TTS/[Test02]-R1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/TTS/[Test02]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/TTS/[Test02]-S2-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/TTS/[Test02]-S7-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>FastSpeech 2 + PWG-cGAN-D</th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/TTS/[Test02]-S3-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 3</p><table><thead>
<tr><th>Recording</th><th>FastSpeech 2 + WaveNet</th><th>FastSpeech 2 + PWG</th><th><font color="#0000cd">FastSpeech 2 + PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/TTS/[Test03]-R1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/TTS/[Test03]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/TTS/[Test03]-S2-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/TTS/[Test03]-S7-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>FastSpeech 2 + PWG-cGAN-D</th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/F2/TTS/[Test03]-S3-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
</tr></tbody></table>

### M1 (male)

<p>Sample 1</p><table><thead>
<tr><th>Recording</th><th>FastSpeech 2 + WaveNet</th><th>FastSpeech 2 + PWG</th><th><font color="#0000cd">FastSpeech 2 + PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/TTS/[Test01]-R1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/TTS/[Test01]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/TTS/[Test01]-S2-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/TTS/[Test01]-S7-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>FastSpeech 2 + PWG-cGAN-D</th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/TTS/[Test01]-S3-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 2</p><table><thead>
<tr><th>Recording</th><th>FastSpeech 2 + WaveNet</th><th>FastSpeech 2 + PWG</th><th><font color="#0000cd">FastSpeech 2 + PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/TTS/[Test02]-R1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/TTS/[Test02]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/TTS/[Test02]-S2-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/TTS/[Test02]-S7-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>FastSpeech 2 + PWG-cGAN-D</th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/TTS/[Test02]-S3-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 3</p><table><thead>
<tr><th>Recording</th><th>FastSpeech 2 + WaveNet</th><th>FastSpeech 2 + PWG</th><th><font color="#0000cd">FastSpeech 2 + PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/TTS/[Test03]-R1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/TTS/[Test03]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/TTS/[Test03]-S2-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/TTS/[Test03]-S7-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>FastSpeech 2 + PWG-cGAN-D</th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M1/TTS/[Test03]-S3-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
</tr></tbody></table>

### M2 (male)

<p>Sample 1</p><table><thead>
<tr><th>Recording</th><th>FastSpeech 2 + WaveNet</th><th>FastSpeech 2 + PWG</th><th><font color="#0000cd">FastSpeech 2 + PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/TTS/[Test01]-R1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/TTS/[Test01]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/TTS/[Test01]-S2-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/TTS/[Test01]-S7-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>FastSpeech 2 + PWG-cGAN-D</th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/TTS/[Test01]-S3-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 2</p><table><thead>
<tr><th>Recording</th><th>FastSpeech 2 + WaveNet</th><th>FastSpeech 2 + PWG</th><th><font color="#0000cd">FastSpeech 2 + PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/TTS/[Test02]-R1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/TTS/[Test02]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/TTS/[Test02]-S2-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/TTS/[Test02]-S7-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>FastSpeech 2 + PWG-cGAN-D</th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/TTS/[Test02]-S3-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 3</p><table><thead>
<tr><th>Recording</th><th>FastSpeech 2 + WaveNet</th><th>FastSpeech 2 + PWG</th><th><font color="#0000cd">FastSpeech 2 + PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/TTS/[Test03]-R1-Ground truth.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/TTS/[Test03]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/TTS/[Test03]-S2-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/TTS/[Test03]-S7-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>FastSpeech 2 + PWG-cGAN-D</th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/M2/TTS/[Test03]-S3-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
</tr></tbody></table>


## Bonus: Analysis/synthesis (English)

Samples for [CMU ARCTIC database](http://www.festvox.org/cmu_arctic/) are provided as follows. The models were trained using total six speakers (clb, slt, bdl, rms, jmk, and ksp) in a speaker-independent way.
The models were similary configured as the above experiments.

### clb (female)

<p>Sample 1</p><table><thead>
<tr><th>Recording</th><th>PWG</th><th>PWG-cGAN-D</th><th><font color="#0000cd">PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/clb/AnaSyn/[Test01]-clb_arctic_b0490_ref-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/clb/AnaSyn/[Test01]-clb_arctic_b0490_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/clb/AnaSyn/[Test01]-clb_arctic_b0490_gen-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/clb/AnaSyn/[Test01]-clb_arctic_b0490_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 2</p><table><thead>
<tr><th>Recording</th><th>PWG</th><th>PWG-cGAN-D</th><th><font color="#0000cd">PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/clb/AnaSyn/[Test02]-clb_arctic_b0491_ref-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/clb/AnaSyn/[Test02]-clb_arctic_b0491_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/clb/AnaSyn/[Test02]-clb_arctic_b0491_gen-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/clb/AnaSyn/[Test02]-clb_arctic_b0491_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 3</p><table><thead>
<tr><th>Recording</th><th>PWG</th><th>PWG-cGAN-D</th><th><font color="#0000cd">PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/clb/AnaSyn/[Test03]-clb_arctic_b0492_ref-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/clb/AnaSyn/[Test03]-clb_arctic_b0492_gen-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/clb/AnaSyn/[Test03]-clb_arctic_b0492_gen-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/clb/AnaSyn/[Test03]-clb_arctic_b0492_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table>

### slt (female)

<p>Sample 1</p><table><thead>
<tr><th>Recording</th><th>PWG</th><th>PWG-cGAN-D</th><th><font color="#0000cd">PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/slt/AnaSyn/[Test01]-slt_arctic_b0490_ref-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/slt/AnaSyn/[Test01]-slt_arctic_b0490_gen-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/slt/AnaSyn/[Test01]-slt_arctic_b0490_gen-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/slt/AnaSyn/[Test01]-slt_arctic_b0490_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 2</p><table><thead>
<tr><th>Recording</th><th>PWG</th><th>PWG-cGAN-D</th><th><font color="#0000cd">PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/slt/AnaSyn/[Test02]-slt_arctic_b0491_ref-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/slt/AnaSyn/[Test02]-slt_arctic_b0491_gen-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/slt/AnaSyn/[Test02]-slt_arctic_b0491_gen-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/slt/AnaSyn/[Test02]-slt_arctic_b0491_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 3</p><table><thead>
<tr><th>Recording</th><th>PWG</th><th>PWG-cGAN-D</th><th><font color="#0000cd">PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/slt/AnaSyn/[Test03]-slt_arctic_b0492_ref-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/slt/AnaSyn/[Test03]-slt_arctic_b0492_gen-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/slt/AnaSyn/[Test03]-slt_arctic_b0492_gen-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/slt/AnaSyn/[Test03]-slt_arctic_b0492_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table>

### bdl (male)

<p>Sample 1</p><table><thead>
<tr><th>Recording</th><th>PWG</th><th>PWG-cGAN-D</th><th><font color="#0000cd">PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/bdl/AnaSyn/[Test01]-bdl_arctic_b0490_ref-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/bdl/AnaSyn/[Test01]-bdl_arctic_b0490_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/bdl/AnaSyn/[Test01]-bdl_arctic_b0490_gen-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/bdl/AnaSyn/[Test01]-bdl_arctic_b0490_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 2</p><table><thead>
<tr><th>Recording</th><th>PWG</th><th>PWG-cGAN-D</th><th><font color="#0000cd">PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/bdl/AnaSyn/[Test02]-bdl_arctic_b0491_ref-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/bdl/AnaSyn/[Test02]-bdl_arctic_b0491_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/bdl/AnaSyn/[Test02]-bdl_arctic_b0491_gen-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/bdl/AnaSyn/[Test02]-bdl_arctic_b0491_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 3</p><table><thead>
<tr><th>Recording</th><th>PWG</th><th>PWG-cGAN-D</th><th><font color="#0000cd">PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/bdl/AnaSyn/[Test03]-bdl_arctic_b0492_ref-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/bdl/AnaSyn/[Test03]-bdl_arctic_b0492_gen-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/bdl/AnaSyn/[Test03]-bdl_arctic_b0492_gen-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/bdl/AnaSyn/[Test03]-bdl_arctic_b0492_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table>

### rms (male)

<p>Sample 1</p><table><thead>
<tr><th>Recording</th><th>PWG</th><th>PWG-cGAN-D</th><th><font color="#0000cd">PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/rms/AnaSyn/[Test01]-rms_arctic_b0490_ref-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/rms/AnaSyn/[Test01]-rms_arctic_b0490_gen-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/rms/AnaSyn/[Test01]-rms_arctic_b0490_gen-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/rms/AnaSyn/[Test01]-rms_arctic_b0490_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 2</p><table><thead>
<tr><th>Recording</th><th>PWG</th><th>PWG-cGAN-D</th><th><font color="#0000cd">PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/rms/AnaSyn/[Test02]-rms_arctic_b0491_ref-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/rms/AnaSyn/[Test02]-rms_arctic_b0491_gen-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/rms/AnaSyn/[Test02]-rms_arctic_b0491_gen-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/rms/AnaSyn/[Test02]-rms_arctic_b0491_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 3</p><table><thead>
<tr><th>Recording</th><th>PWG</th><th>PWG-cGAN-D</th><th><font color="#0000cd">PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/rms/AnaSyn/[Test03]-rms_arctic_b0492_ref-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/rms/AnaSyn/[Test03]-rms_arctic_b0492_gen-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/rms/AnaSyn/[Test03]-rms_arctic_b0492_gen-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/rms/AnaSyn/[Test03]-rms_arctic_b0492_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table>

### jmk (male)

<p>Sample 1</p><table><thead>
<tr><th>Recording</th><th>PWG</th><th>PWG-cGAN-D</th><th><font color="#0000cd">PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/jmk/AnaSyn/[Test01]-jmk_arctic_b0490_ref-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/jmk/AnaSyn/[Test01]-jmk_arctic_b0490_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/jmk/AnaSyn/[Test01]-jmk_arctic_b0490_gen-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/jmk/AnaSyn/[Test01]-jmk_arctic_b0490_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 2</p><table><thead>
<tr><th>Recording</th><th>PWG</th><th>PWG-cGAN-D</th><th><font color="#0000cd">PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/jmk/AnaSyn/[Test02]-jmk_arctic_b0491_ref-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/jmk/AnaSyn/[Test02]-jmk_arctic_b0491_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/jmk/AnaSyn/[Test02]-jmk_arctic_b0491_gen-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/jmk/AnaSyn/[Test02]-jmk_arctic_b0491_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 3</p><table><thead>
<tr><th>Recording</th><th>PWG</th><th>PWG-cGAN-D</th><th><font color="#0000cd">PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/jmk/AnaSyn/[Test03]-jmk_arctic_b0492_ref-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/jmk/AnaSyn/[Test03]-jmk_arctic_b0492_gen-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/jmk/AnaSyn/[Test03]-jmk_arctic_b0492_gen-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/jmk/AnaSyn/[Test03]-jmk_arctic_b0492_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table>

### ksp (male)

<p>Sample 1</p><table><thead>
<tr><th>Recording</th><th>PWG</th><th>PWG-cGAN-D</th><th><font color="#0000cd">PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/ksp/AnaSyn/[Test01]-ksp_arctic_b0490_ref-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/ksp/AnaSyn/[Test01]-ksp_arctic_b0490_gen-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/ksp/AnaSyn/[Test01]-ksp_arctic_b0490_gen-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/ksp/AnaSyn/[Test01]-ksp_arctic_b0490_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 2</p><table><thead>
<tr><th>Recording</th><th>PWG</th><th>PWG-cGAN-D</th><th><font color="#0000cd">PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/ksp/AnaSyn/[Test02]-ksp_arctic_b0491_ref-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/ksp/AnaSyn/[Test02]-ksp_arctic_b0491_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/ksp/AnaSyn/[Test02]-ksp_arctic_b0491_gen-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/ksp/AnaSyn/[Test02]-ksp_arctic_b0491_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 3</p><table><thead>
<tr><th>Recording</th><th>PWG</th><th>PWG-cGAN-D</th><th><font color="#0000cd">PWG-V/UV-D (ours)</font></th></tr>
</thead><tbody><tr><td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/ksp/AnaSyn/[Test03]-ksp_arctic_b0492_ref-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/ksp/AnaSyn/[Test03]-ksp_arctic_b0492_gen-PWG.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/ksp/AnaSyn/[Test03]-ksp_arctic_b0492_gen-PWG-cGAN-D.wav" type="audio/wav"></audio></td>
<td><audio controls="" style="width: 250px;"><source src="/audio/icassp2021-pwg-vuvd/bonus/ksp/AnaSyn/[Test03]-ksp_arctic_b0492_gen-PWG-VUV-D (ours).wav" type="audio/wav"></audio></td>
</tr></tbody></table>


## References

- [1] W. Ping, K. Peng, and J. Chen, “ClariNet: Parallel wave generation in end-to-end text-to-speech,” in Proc. ICLR, 2019 [arXiv](https://arxiv.org/abs/1807.07281).
- [2] R Yamamoto, E Song, and J.-M Kim, “Parallel WaveGAN:A fast waveform generation model based on generative adversarial networks with multi-resolution spectrogram,”  in Proc. ICASSP, 2020, pp. 6199–6203. [arXiv](https://arxiv.org/abs/1910.11480).
- [3] Y Ren, C Hu, T Qin, S Zhao, Z Zhao, and T.-Y Liu, “Fast-speech 2: Fast and high-quality end-to-end text-to-speech,”arXiv preprint arXiv:2006.04558, 2020. [arXiv](https://arxiv.org/abs/2006.04558).

## Acknowledgements

Work performed with nVoice, Clova Voice, Naver Corp.

## Citation

```
@misc{yamamoto2020pwgvuvd,
    title={Parallel waveform synthesis based on generative adversarial networks with voicing-aware conditional discriminators},
    author={Ryuichi Yamamoto and Eunwoo Song and Min-Jae Hwang and Jae-Min Kim},
    year={2020},
    eprint={2010.14151},
    archivePrefix={arXiv},
    primaryClass={eess.AS}
```