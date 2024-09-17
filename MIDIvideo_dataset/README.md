# MIDIvideo Dataset

## Overview

This folder contains essential components and examples for creating the MIDIvideo dataset, which is part of the V2MIDI project. The dataset pairs MIDI files with AI-generated videos, offering a unique resource for research into audio-visual synchronization using AI.

## Folder Structure

- **`MIDI2ParseqDeforum/`**: Code for converting MIDI files into Parseq/Deforum configurations.
- **`video_generation/`**: Scripts for large-scale video generation using these configurations.
- **`examples/`**: Sample videos and corresponding MIDI exports, showcasing various resolutions and styles.

## Key Components

1. **MIDI2ParseqDeforum**:
   - Converts MIDI files into Parseq/Deforum configurations.
   - Maps MIDI events to visual parameters for synchronization.
   - Includes randomized visual prompts to enhance diversity.

2. **video_generation**:
   - Generates synchronized videos using Stable Diffusion and Deforum.
   - Employs multi-GPU processing for efficiency.
   - Includes job scheduling and error recovery mechanisms.

3. **examples**:
   - Demonstrates different video outputs, ranging in resolution and visual styles.
   - Includes MP3 exports of MIDI files for quick reference and playback.

## Usage

1. Begin by using the **MIDI2ParseqDeforum** scripts to generate configurations.
2. Then, run the **video_generation** scripts to create synchronized video outputs.
3. Refer to the **examples** folder for inspiration and to see the outputs in action.

## Dataset Specifications

While the examples folder provides videos in various resolutions and styles, the final MIDIvideo dataset used for training the V2MIDI model is standardized at 256x256 resolution for consistency.

## Getting Started

For more detailed instructions on how each component works, check the README files located within the **MIDI2ParseqDeforum** and **video_generation** folders.

## Requirements

- Python 3.7 or higher
- PyTorch with CUDA support
- Installed versions of Stable Diffusion and Deforum
- Multi-GPU system or access to a supercomputer for large-scale processing

## Accessing the Full Dataset

The complete MIDIvideo dataset, containing all paired MIDI files and their synchronized video outputs, is too large for GitHub and is hosted on Hugging Face:

🔗 [V2MIDI Dataset on Hugging Face](https://huggingface.co/datasets/obvious-research/V2MIDI)

On the Hugging Face page, you can find:
- Detailed information about the dataset structure.
- Instructions on how to download and use the dataset.
- Guidelines for working with the dataset in your own projects.

The examples and scripts provided here demonstrate how the dataset is created and include sample outputs, but to access the full dataset, please visit the Hugging Face repository.
