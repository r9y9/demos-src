---
title: "Parallel waveform synthesis based on generative adversarial networks with voicing-aware conditional discriminators"
date: 2020-10-18T23:38:48+09:00
draft: false
categories: ["TTS"]
tags: ["icassp"]
---

Submitted to [ICASSP 2021](https://2021.ieeeicassp.org/)

## Table of contents

- [Analysis/synthesis samples (Japanese)](#analysis-synthesis)
- [Text-to-speech samples (Japanese)](#text-to-speech)


## Authors

- Ryuichi Yamamoto (LINE Corp.)
- Eunwoo Song (NAVER Corp.)
- Min-jae Hwang (Search Solutions Inc.)
- Jae-Min Kim (NAVER Corp.)

## Abstract (TBD)

This paper proposes voicing-aware conditional discriminators for Parallel WaveGAN-based waveform synthesis systems. In the proposed method, two waveform discriminators independently operate according to the voicing information of input speech sig- nal. Because each discriminator learns distinctive characteristics of harmonic and noise components, respectively, the adversarial training efficiency can be significantly improved. Furthermore, by using the acoustic features as conditional input of discrimi- nator, it is easier for the discriminators to distinguish the input speech whether it is real or fake. As a result, the generator is able to generate more realistic speech waveforms. Subjective test results demonstrate the superiority of the proposed method over the conventional methods. In particular, our system within a FastSpeech 2-based text-to-speech framework achieves 4.21, 4.25, 4.28, and 4.42 mean opinion score for four Japanese speak- ers, respectively.


## Systems for comparision

| System                       | Voiced discriminator | Unvoiced discriminator | Discriminator conditioning|
|------------------------------|----------------------|------------------------|-------------------|
| S1-WaveNet [\[1\]](https://arxiv.org/abs/1807.07281)               | -                    | -                      | -                 |
| S2-PWG [\[2\]](https://arxiv.org/abs/1910.11480)                   | -                    | -                      | -                 |
| S3-PWG-cGAN-D            | -                    | -                      | Yes               |
| S4-PWG-V/UV-D            | $D_1$                | $D_1$                  | Yes               |
| S5-PWG-V/UV-D            | $D_2$                | $D_1$                  | Yes               |
| S6-PWG-V/UV-D            | $D_2$                | $D_2$                  | Yes               |
| S7-PWG-V/UV-D (proposed) | $D_1$                | $D_2$                  | Yes               |
| Recordings               | -                    | -                      | -                 |

- $D_1$: 1-D dilated CNN discrimiantor with the reseptive field size of 127.
- $D_2$: 1-D CNN discrimiantor with the reseptive field size of 13.

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


## References

- [1] W. Ping, K. Peng, and J. Chen, “ClariNet: Parallel wave generation in end-to-end text-to-speech,” in Proc. ICLR, 2019 [arXiv](https://arxiv.org/abs/1807.07281).
- [2] R Yamamoto, E Song, and J.-M Kim, “Parallel WaveGAN:A fast waveform generation model based on generative adversarial networks with multi-resolution spectrogram,”  in Proc. ICASSP, 2020, pp. 6199–6203. [arXiv](https://arxiv.org/abs/1910.11480).
- [3] Y Ren, C Hu, T Qin, S Zhao, Z Zhao, and T.-Y Liu, “Fast-speech 2: Fast and high-quality end-to-end text-to-speech,”arXiv preprint arXiv:2006.04558, 2020. [arXiv](https://arxiv.org/abs/2006.04558).

## Acknowledgements

Work performed with nVoice, Clova Voice, Naver Corp.