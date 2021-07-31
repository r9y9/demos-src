---
title: "Voicing-Aware Parallel WaveGAN for High-Quality Speech Synthesis"
date: 2021-07-30T12:11:03+09:00
draft: false
categories: ["TTS"]
tags: ["ieee-spl"]
---

Submitted to [IEEE signal processing letters](https://signalprocessingsociety.org/publications-resources/ieee-signal-processing-letters).

- [Authors](#authors)
- [Abstract](#abstract)
- [TTS samples](#tts-samples)
  - [M1 (male)](#m1-male)
  - [M2 (male)](#m2-male)
  - [F1 (female)](#f1-female)
  - [F2 (female)](#f2-female)
- [Acknowledgements](#acknowledgements)

## Authors

- Ryuichi Yamamoto (LINE Corp.)
- Min-Jae Hwang (Search Solutions Inc.)
- Eunwoo Song (NAVER Corp.)

## Abstract

This letter proposes a voicing-aware Parallel Wave- GAN (VA-PWG) vocoder for a neural text-to-speech (TTS) system. To generate a high-quality speech waveform, it is important to reflect the distinct characteristics of voiced and unvoiced speech signals well. However, it is difficult for the conventional PWG model to accurately represent this condition, since the single unified architectures of the generator and discriminator are insufficient to capture those characteristics. In the proposed method, both the generator and discriminator are divided into their subnetworks to individually model the voicing state-dependent characteristics of a speech signal. In particular, a VA-generator consisting of two sub-WaveNets generates the harmonic and noise components of a speech signal by inputting pitch-dependent sine wave and Gaussian noise sources, respectively. Likewise, a VA-discriminator consisting of two sub-discriminators learns the distinct characteristics of harmonic and noise components by feeding the voiced and unvoiced waveforms, respectively. Subjective evaluation results verified the effectiveness of the proposed VA-PWG vocoder by achieving a 4.25 mean opinion score from a speaker-independent training scenario that was 11% higher than that of a conventional PWG vocoder.

<div align="center"><img src="/images/va-pwg.png" width="60%" /></div>

## TTS samples

### M1 (male)

<p>Sample 1: “鹿児島県で最大震度三を観測しています。”</p>
<table><thead>
<tr><th>Recording</th><th>WaveNet</th><th>PWG</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/M1/TTS/[Test01]-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M1/TTS/[Test01]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M1/TTS/[Test01]-S2-PWG.wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>VA-PWG-G</th><th>VA-PWG-D</th><th>VA-PWG-GD (proposed)</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/M1/TTS/[Test01]-S3-VA-PWG-G.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M1/TTS/[Test01]-S4-VA-PWG-D.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M1/TTS/[Test01]-S5-VA-PWG-GD (proposed).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 2: “葉加瀬太郎の情熱大陸です。”</p>
<table><thead>
<tr><th>Recording</th><th>WaveNet</th><th>PWG</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/M1/TTS/[Test02]-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M1/TTS/[Test02]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M1/TTS/[Test02]-S2-PWG.wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>VA-PWG-G</th><th>VA-PWG-D</th><th>VA-PWG-GD (proposed)</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/M1/TTS/[Test02]-S3-VA-PWG-G.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M1/TTS/[Test02]-S4-VA-PWG-D.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M1/TTS/[Test02]-S5-VA-PWG-GD (proposed).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 3: “それでうちの部は半分に減らされる。”</p>
<table><thead>
<tr><th>Recording</th><th>WaveNet</th><th>PWG</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/M1/TTS/[Test03]-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M1/TTS/[Test03]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M1/TTS/[Test03]-S2-PWG.wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>VA-PWG-G</th><th>VA-PWG-D</th><th>VA-PWG-GD (proposed)</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/M1/TTS/[Test03]-S3-VA-PWG-G.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M1/TTS/[Test03]-S4-VA-PWG-D.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M1/TTS/[Test03]-S5-VA-PWG-GD (proposed).wav" type="audio/wav"></audio></td>
</tr></tbody></table>

### M2 (male)

<p>Sample 1: “ヨメの、レオンティーンさんですね。”</p>
<table><thead>
<tr><th>Recording</th><th>WaveNet</th><th>PWG</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/M2/TTS/[Test01]-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M2/TTS/[Test01]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M2/TTS/[Test01]-S2-PWG.wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>VA-PWG-G</th><th>VA-PWG-D</th><th>VA-PWG-GD (proposed)</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/M2/TTS/[Test01]-S3-VA-PWG-G.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M2/TTS/[Test01]-S4-VA-PWG-D.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M2/TTS/[Test01]-S5-VA-PWG-GD (proposed).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 2: “御予約は、二泊三日ですね。”</p>
<table><thead>
<tr><th>Recording</th><th>WaveNet</th><th>PWG</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/M2/TTS/[Test02]-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M2/TTS/[Test02]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M2/TTS/[Test02]-S2-PWG.wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>VA-PWG-G</th><th>VA-PWG-D</th><th>VA-PWG-GD (proposed)</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/M2/TTS/[Test02]-S3-VA-PWG-G.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M2/TTS/[Test02]-S4-VA-PWG-D.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M2/TTS/[Test02]-S5-VA-PWG-GD (proposed).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 3: “わたさちの、ローリーさんですね。”</p>
<table><thead>
<tr><th>Recording</th><th>WaveNet</th><th>PWG</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/M2/TTS/[Test03]-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M2/TTS/[Test03]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M2/TTS/[Test03]-S2-PWG.wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>VA-PWG-G</th><th>VA-PWG-D</th><th>VA-PWG-GD (proposed)</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/M2/TTS/[Test03]-S3-VA-PWG-G.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M2/TTS/[Test03]-S4-VA-PWG-D.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/M2/TTS/[Test03]-S5-VA-PWG-GD (proposed).wav" type="audio/wav"></audio></td>
</tr></tbody></table>

### F1 (female)

<p>Sample 1: “かわいそうに、助けてやらなくてはと、家に連れて帰りましたとさ。”</p>
<table><thead>
<tr><th>Recording</th><th>WaveNet</th><th>PWG</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/F1/TTS/[Test01]-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F1/TTS/[Test01]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F1/TTS/[Test01]-S2-PWG.wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>VA-PWG-G</th><th>VA-PWG-D</th><th>VA-PWG-GD (proposed)</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/F1/TTS/[Test01]-S3-VA-PWG-G.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F1/TTS/[Test01]-S4-VA-PWG-D.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F1/TTS/[Test01]-S5-VA-PWG-GD (proposed).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 2: “失礼のないよう、笑顔で挨拶して。”</p>
<table><thead>
<tr><th>Recording</th><th>WaveNet</th><th>PWG</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/F1/TTS/[Test02]-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F1/TTS/[Test02]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F1/TTS/[Test02]-S2-PWG.wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>VA-PWG-G</th><th>VA-PWG-D</th><th>VA-PWG-GD (proposed)</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/F1/TTS/[Test02]-S3-VA-PWG-G.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F1/TTS/[Test02]-S4-VA-PWG-D.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F1/TTS/[Test02]-S5-VA-PWG-GD (proposed).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 3: “照れていたので、ちょっと意外な気がしましたー。”</p>
<table><thead>
<tr><th>Recording</th><th>WaveNet</th><th>PWG</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/F1/TTS/[Test03]-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F1/TTS/[Test03]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F1/TTS/[Test03]-S2-PWG.wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>VA-PWG-G</th><th>VA-PWG-D</th><th>VA-PWG-GD (proposed)</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/F1/TTS/[Test03]-S3-VA-PWG-G.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F1/TTS/[Test03]-S4-VA-PWG-D.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F1/TTS/[Test03]-S5-VA-PWG-GD (proposed).wav" type="audio/wav"></audio></td>
</tr></tbody></table>

### F2 (female)

<p>Sample 1: “そして目に留まったのは、お気に入りの居酒屋の前にあるゴミの山。”</p>
<table><thead>
<tr><th>Recording</th><th>WaveNet</th><th>PWG</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/F2/TTS/[Test01]-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F2/TTS/[Test01]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F2/TTS/[Test01]-S2-PWG.wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>VA-PWG-G</th><th>VA-PWG-D</th><th>VA-PWG-GD (proposed)</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/F2/TTS/[Test01]-S3-VA-PWG-G.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F2/TTS/[Test01]-S4-VA-PWG-D.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F2/TTS/[Test01]-S5-VA-PWG-GD (proposed).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 2: “今ひとつ、時間が足りず。”</p>
<table><thead>
<tr><th>Recording</th><th>WaveNet</th><th>PWG</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/F2/TTS/[Test02]-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F2/TTS/[Test02]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F2/TTS/[Test02]-S2-PWG.wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>VA-PWG-G</th><th>VA-PWG-D</th><th>VA-PWG-GD (proposed)</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/F2/TTS/[Test02]-S3-VA-PWG-G.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F2/TTS/[Test02]-S4-VA-PWG-D.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F2/TTS/[Test02]-S5-VA-PWG-GD (proposed).wav" type="audio/wav"></audio></td>
</tr></tbody></table><p>Sample 3: “実はこの道の先に、高い山があってね。”</p>
<table><thead>
<tr><th>Recording</th><th>WaveNet</th><th>PWG</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/F2/TTS/[Test03]-Recording.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F2/TTS/[Test03]-S1-WaveNet.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F2/TTS/[Test03]-S2-PWG.wav" type="audio/wav"></audio></td>
</tr></tbody></table><table><thead>
<tr><th>VA-PWG-G</th><th>VA-PWG-D</th><th>VA-PWG-GD (proposed)</th></tr>
</thead><tbody><tr><td><audio controls=""><source src="/audio/va-pwg/F2/TTS/[Test03]-S3-VA-PWG-G.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F2/TTS/[Test03]-S4-VA-PWG-D.wav" type="audio/wav"></audio></td>
<td><audio controls=""><source src="/audio/va-pwg/F2/TTS/[Test03]-S5-VA-PWG-GD (proposed).wav" type="audio/wav"></audio></td>
</tr></tbody></table>



## Acknowledgements

Work performed with nVoice, Clova Voice, Naver Corp.

