# Emotion-Controlled Symbolic Music Generation via Prompt Tuning with Structured Constraints

Pavel Pomozov and Shlomo Dubnov, University of California, San Diego

This repository contains code and generated outputs for our ACL 2026 Student Research Workshop paper.

## Overview

We trained 12 learnable prompt tokens per emotion (sad, happy, calm) on a frozen SkyTNT model using 58 labeled jazz MIDI files. Only 36,864 parameters were trained. The learned prompt embeddings adjust tempo and rhythm, which then guide a structured generation layer that uses constraints like scales, chord progressions, and rhythm patterns. The generator produces three tracks (melody, chords, bass) as MIDI, creating 64-bar pieces lasting 32 to 148 seconds depending on emotion.

## Key Results

| Metric | Sad | Happy | Calm |
|---|---|---|---|
| Note Density (notes/sec) | 5.21 | 12.00 | 7.81 |
| Avg Duration (s) | 0.81 | 0.40 | 0.64 |
| Pitch Range (semitones) | 46 | 46 | 45 |
| Unique Pitches | 26 | 24 | 21 |
| Polyphony | 4.38 | 4.93 | 5.00 |
| Pitch Entropy | 4.53 | 4.40 | 4.19 |

## Listen to Generated Examples

Visit the [demo page](https://pavel-coder-2020.github.io/Emotion-Music-Generation/) to listen to audio examples of the generated music.

## Repository Structure

```
emotion-music-gen/
├── README.md
├── index.html
├── code/
│   ├── generate_music.py
│   └── evaluate_music.py
├── midi/
│   ├── sad_long.mid
│   ├── happy_long.mid
│   └── calm_long.mid
├── audio/
│   ├── sad_long.mp3
│   ├── happy_long.mp3
│   └── calm_long.mp3
├── results/
│   ├── evaluation_results.json
│   └── evaluation_comparison.png
└── paper/
    └── acl2026_paper.pdf
```

## Requirements

```
pip install transformers torch symusic music21 safetensors pretty_midi
```

## Citation

```
@inproceedings{pomozov2026emotion,
  title={Emotion-Controlled Symbolic Music Generation via Prompt Tuning with Structured Constraints},
  author={Pomozov, Pavel and Dubnov, Shlomo},
  booktitle={Proceedings of the ACL 2026 Student Research Workshop},
  year={2026}
}
```

## Acknowledgments

I thank Professor Shlomo Dubnov from UC San Diego for his guidance on this project.
