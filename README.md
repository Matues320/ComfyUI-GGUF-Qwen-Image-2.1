# ComfyUI-GGUF — Qwen Image 2.1 Support

A compatibility fix for loading Qwen Image 2.1 GGUF models in ComfyUI-GGUF.

## Problem

When loading a Qwen Image 2.1 GGUF model, ComfyUI may raise the following error:

```text
ValueError: Unexpected architecture type in GGUF file: 'qwen_image21'
```

## Fixes

This version adds support for the `qwen_image21` architecture.

- **`loader.py`** — Adds `qwen_image21` to the supported image architecture list.
- **`tools/convert.py`** — Adds the `QwenImage21` model architecture definition for GGUF conversion.

These changes address the architecture compatibility issue encountered when using Qwen Image 2.1 GGUF models.

## Installation

### 1. Clone this repository

Open a terminal and navigate to your ComfyUI `custom_nodes` directory:

```bash
cd /path/to/ComfyUI/custom_nodes
```

Clone this repository:

```bash
git clone https://github.com/Matues320/ComfyUI-GGUF-Qwen-Image-2.1.git
```

This downloads the Qwen Image 2.1 compatibility version of ComfyUI-GGUF.

### 2. Install the required dependency

Install `gguf` using the Python environment associated with your ComfyUI installation:

```bash
python -m pip install -U gguf
```

**Important:** Make sure you use the Python environment that ComfyUI actually runs. Installing `gguf` into a different Python environment may not resolve the import error.

### 3. Restart ComfyUI

Restart ComfyUI and load your Qwen Image 2.1 GGUF model.

This version includes the `qwen_image21` architecture compatibility fix.

### 4. Verify the installation

If you still encounter:

```text
ValueError: Unexpected architecture type in GGUF file: 'qwen_image21'
```

make sure you are loading the custom node from this repository, rather than another existing ComfyUI-GGUF installation.


## Changes

- Added `qwen_image21` architecture support in `loader.py`.
- Added `QwenImage21` detection support in `tools/convert.py`.

The `tools/convert.py` change affects future GGUF conversions. It does not modify GGUF files that have already been converted.

## Upstream Project and Credits

This project is based on [city96/ComfyUI-GGUF](https://github.com/city96/ComfyUI-GGUF).

- Original project: https://github.com/city96/ComfyUI-GGUF
- Maintainer of this compatibility update: Matues320

Please retain the original project's license and copyright notices. Refer to the upstream repository for the applicable license terms.

## Disclaimer

This repository documents a compatibility fix for Qwen Image 2.1 architecture support. It is not an official release of the upstream ComfyUI-GGUF project.
