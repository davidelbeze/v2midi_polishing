# Video Generation for V2MIDI

## Overview

This folder contains the code responsible for large-scale video generation in the V2MIDI project. It transforms MIDI files and their corresponding Parseq/Deforum configurations into synchronized, AI-generated videos.

## Contents

- **`v2midi_dataset.slurm`**: SLURM job script to run video generation on a supercomputer.
- **`main_video_generation.py`**: The main Python script that handles video generation.
- **`new_deforum_settings.txt`**: Default settings file for Deforum video generation.

## How It Works

1. **Job Scheduling** (`v2midi_dataset.slurm`):
   - Configures the environment and allocates necessary resources for running on a supercomputer.
   - Launches the video generation process by executing the main Python script with the appropriate settings.

2. **Video Generation** (`main_video_generation.py`):
   - Manages the distribution of video generation tasks across multiple GPUs.
   - Processes the Parseq configurations, creating videos using Stable Diffusion and Deforum.
   - Includes error handling and job recovery to ensure smooth execution.

3. **Deforum Settings** (`new_deforum_settings.txt`):
   - Provides default configuration parameters for generating videos.
   - Includes settings for resolution, animation modes, and various visual effects.

## Key Features

- Efficient parallel processing utilizing multiple GPUs.
- Robust error recovery system to handle any issues during video generation.
- Integration with Stable Diffusion and Deforum for producing high-quality, AI-driven videos.
- Customizable video generation settings to suit different artistic needs.

## Usage

1. Ensure you have access to a multi-GPU setup or a supercomputer with SLURM support.
2. Update the paths and settings in both `v2midi_dataset.slurm` and `main_video_generation.py`.
3. Submit the SLURM job script to begin the video generation process.

## Customization

- **SLURM Job Settings**: Modify GPU allocation and job arrays in `v2midi_dataset.slurm` to suit your computational setup.
- **Deforum Settings**: Adjust video parameters, such as resolution or animation style, by editing `new_deforum_settings.txt`.
- **Job Distribution**: Customize the error handling and task distribution logic in `main_video_generation.py` to fine-tune performance.

## Output

The script generates:

- MP4 video files that are synchronized with the input MIDI data.
- A neatly organized output directory that corresponds to the structure of the input dataset.

## Requirements

- A SLURM-enabled cluster or supercomputer.
- PyTorch with CUDA support for GPU acceleration.
- Installed versions of Stable Diffusion and Deforum.
- Access to a dataset of MIDI files paired with Parseq configurations.
