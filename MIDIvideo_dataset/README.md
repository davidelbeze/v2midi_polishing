# MIDI2ParseqDeforum

## Overview

This folder contains the main scripts for converting MIDI files into Parseq and Deforum configurations, which is a critical part of the V2MIDI project. These configurations allow us to create synchronized videos that combine musical content with visual effects, bridging the gap between sound and sight.

## Contents

- **`MIDI_to_parseq.py`**: Converts MIDI files into Parseq configurations.
- **`parseq_to_rendered.py`**: Transforms the Parseq configurations into a format compatible with Deforum.
- **`dataset_creation.py`**: Automates the process of generating a dataset by running all MIDI files through the pipeline.

## How It Works

1. **MIDI Processing** (`MIDI_to_parseq.py`):
   - Reads each MIDI file and extracts events frame by frame.
   - Maps specific MIDI notes to corresponding visual effects, like rotation or translation.
   - Generates a Parseq configuration for each MIDI file, including randomized visual effects.

2. **Converting to Deforum** (`parseq_to_rendered.py`):
   - Takes the Parseq configurations and converts them into Deforum's format.
   - Calculates keyframe values and transitions for smooth visual effects.
   - Adds visual prompts for AI-generated content in the final video.

3. **Automated Dataset Creation** (`dataset_creation.py`):
   - Processes all MIDI files in a folder.
   - Creates both Parseq and Deforum configurations for each MIDI file.
   - Organizes everything into a structured dataset.

## Key Features

- Focuses on drum patterns from house music.
- Maps five key drum instruments to specific visual effects:
  - **Hi-Hat Open** (MIDI Note 46) → `rotation_3d_x`
  - **Pedal Hi-Hat** (MIDI Note 44) → `rotation_3d_y`
  - **Kick Drum** (MIDI Note 36) → `strength`
  - **Snare Drum** (MIDI Note 38) → `translation_z`
  - **Closed Hi-Hat** (MIDI Note 42) → `rotation_3d_z`
- Randomizes visual prompts to ensure diversity in the generated content.
- Works with 16-second MIDI sequences at 24 frames per second (creating 384 frames).

## Usage

1. Place your MIDI files in a folder (for example, `House_MIDI_16s_2`).
2. Set up a directory for visual prompts (for example, `video2midi_prompts`).
3. Make sure the paths are correctly set in `dataset_creation.py`.
4. Run `dataset_creation.py` to generate the Parseq and Deforum configurations for all your MIDI files.

## Customization

You can adjust many aspects of the configuration generation to suit your needs:

- **In `MIDI_to_parseq.py`**:
  - Change how MIDI notes are mapped to visual effects.
  - Add new visual effects or fine-tune existing ones.
  - Modify the duration of specific effects (e.g., how long the kick drum effect lasts).

- **In `dataset_creation.py`**:
  - Adjust the frame rate (default is 24 fps).
  - Modify the randomization for parameters like visual effects.

## Output Structure

For each MIDI file, the script generates a dataset with:

- The original MIDI file.
- A Parseq configuration (`.json` format).
- A Deforum-rendered configuration (`.json` format).

The files are organized like this:

```plaintext
midi_parseq_dataset/
    midi_parseq_rendered_1/
        midi_1.mid
        midi_1_parseq_config.json
        midi_1_parseq_rendered.json
    midi_parseq_rendered_2/
        midi_2.mid
        midi_2_parseq_config.json
        midi_2_parseq_rendered.json
    ...
```

This dataset is ready for the next step in the V2MIDI workflow: video generation!
