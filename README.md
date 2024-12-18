# Audio Transcription Tool «TranscriboZH»
**Transcribe any audio or video file. Edit and view your transcripts in a standalone HTML editor.**

![GitHub License](https://img.shields.io/github/license/machinelearningzh/audio-transcription)
[![PyPI - Python](https://img.shields.io/badge/python-v3.10+-blue.svg)](https://github.com/machinelearningZH/audio-transcription)
[![GitHub Stars](https://img.shields.io/github/stars/machinelearningZH/audio-transcription.svg)](https://github.com/machinelearningZH/audio-transcription/stargazers)
[![GitHub Issues](https://img.shields.io/github/issues/machinelearningZH/audio-transcription.svg)](https://github.com/machinelearningZH/audio-transcription/issues)
[![GitHub Issues](https://img.shields.io/github/issues-pr/machinelearningZH/audio-transcription.svg)](https://img.shields.io/github/issues-pr/machinelearningZH/audio-transcription) 
[![Current Version](https://img.shields.io/badge/version-1.0-green.svg)](https://github.com/machinelearningZH/audio-transcription)
<a href="https://github.com/astral-sh/ruff"><img alt="linting - Ruff" class="off-glb" loading="lazy" src="https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/ruff/main/assets/badge/v2.json"></a>


<img src="_img/ui1.PNG" alt="editor" width="1000"/>

<details>

<summary>Contents</summary>

- [Setup Instructions](#setup-instructions)
    - [Hardware requirements](#hardware-requirements)
    - [Installation](#installation)
    - [Running the Application](#running-the-application)
    - [Configuration](#configuration)
- [Project Information](#project-information)
    - [What does the application do?](#what-does-the-application-do)
- [Project team](#project-team)
- [Feedback and Contributions](#feedback-and-contributions)
- [Disclaimer](#disclaimer)

</details>

## Fork

This is a fork of the original work done by machinelearningZH. <https://github.com/machinelearningZH/audio-transcription>. Thank you for open sourcing the code.

Things changed:

- Added docker support
- Split frontend and backend
- Fixed minor bugs
- Changed branding

## Setup Instructions
### Hardware requirements
- We strongly recommend using a CUDA-compatible graphics card, as transcription on a CPU is extremely slow.
    - https://developer.nvidia.com/cuda-gpus
- If you are using a graphics card, you need at least 8GB VRAM. Performance is better with 16GB VRAM.
- 8GB RAM

### Installation
- Docker (on Windows use WSL2 backend)
- Create a Huggingface access token
    - Accept [pyannote/segmentation](https://huggingface.co/pyannote/segmentation)) user conditions
    - Accept [pyannote/speaker-diarization-3.0](https://huggingface.co/pyannote/speaker-diarization) user conditions
    - Create access token at [hf.co/settings/tokens](https://hf.co/settings/tokens) with read permissions.
- Create a `.env` file for both api and add your access token at api/.env. See the file `api/.env_example`.
```
    HF_AUTH_TOKEN = ...
```
- Edit all the variables of `.env_example` in your `.env` file for your specific configuration. Make sure that your `.env` file is in your `.gitignore`.

### Running the Application
- docker-compose up -d --build

### Configuration
|   | Description |
|---|---|
| STORAGE_SECRET | String. Secret key for cookie-based identification of users |
| ROOT | String. path to main.py and worker.py |
| DEVICE | String. 'cuda' if you are using a GPU. 'cpu' otherwise. |
| ADDITIONAL_SPEAKERS | Integer. Number of additional speakers provied in the editor |
| BATCH_SIZE | Integer. Batch size for Whisper inference. Recommended batch size is 4 with 8GB VRAM and 32 with 16GB VRAM. |


## Project Information
This application provides advanced transcription capabilities for confidential audio and video files using the state-of-the-art Whisper v3 large model (non-quantized). It offers top-tier transcription quality without licensing or usage fees, even for Swiss German.

### What does the application do?
- State-of-the-Art Transcription: Powered by Whisper v3 large model, ensuring high accuracy and reliability.
- Cost-Free: No license or usage-related costs, making it an affordable solution for everyone.
- High Performance: Transcribe up to 15 times faster than real-time, ensuring efficient processing.
- High-Quality Transcriptions: Exceptional transcription quality for English and local languages, with substantial accuracy for Swiss German.
- Speaker Diarisation: Automatic identification and differentiation of speakers within the audio.
- Multi-File Upload: Easily upload and manage multiple files for transcription.
- Predefined vocabulary: Define the spelling of ambiguous words and names.
- Transcript Export Options: Export transcriptions in various formats:
    - Text file
    - SRT file (for video subtitles)
    - Synchronized viewer with integrated audio or video
- Integrated Editing: Edit transcriptions directly within the application, synchronously linked with the source video or audio. The editor is open-source and requires no installation.
    - General Text Editing Functions: Standard text editing features for ease of use.
    - Segments: Add or remove speech segments.
    - Speaker Naming: Assign names to identified speakers for clarity.
    - Power User Shortcuts: Keyboard shortcuts for enhanced navigation and control (start, stop, forward, backward, etc.).




## Project team
This project is a collaborative effort of these people of the cantonal administration of Zurich:

- **Stephan Walder** - [Leiter Digitale Transformation, Oberstaatsanwaltschaft Kanton Zürich](https://www.zh.ch/de/direktion-der-justiz-und-des-innern/staatsanwaltschaft/Oberstaatsanwaltschaft-des-Kantons-Zuerich.html)
- **Dominik Frefel** - [Team Data, Statistisches Amt](https://www.zh.ch/de/direktion-der-justiz-und-des-innern/statistisches-amt/data.html)
- **Patrick Arnecke** - [Team Data, Statistisches Amt](https://www.zh.ch/de/direktion-der-justiz-und-des-innern/statistisches-amt/data.html)
  
## Feedback and Contributions
Please share your feedback and let us know how you use the app in your institution. You can [write an email](mailto:datashop@statistik.zh.ch) or share your ideas by opening an issue or a pull requests.

Please note, we use [Ruff](https://docs.astral.sh/ruff/) for linting and code formatting with default settings.

## Disclaimer
This transcription software (the Software) incorporates the open-source model Whisper Large v3 (the Model) and has been developed according to and with the intent to be used under Swiss law. Please be aware that the EU Artificial Intelligence Act (EU AI Act) may, under certain circumstances, be applicable to your use of the Software. You are solely responsible for ensuring that your use of the Software as well as of the underlying Model complies with all applicable local, national and international laws and regulations. By using this Software, you acknowledge and agree (a) that it is your responsibility to assess which laws and regulations, in particular regarding the use of AI technologies, are applicable to your intended use and to comply therewith, and (b) that you will hold us harmless from any action, claims, liability or loss in respect of your use of the Software.
