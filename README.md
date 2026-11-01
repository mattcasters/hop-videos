# Apache Hop getting-started videos

Narration, stills, clips, and the renderer for the Apache Hop YouTube getting-started series. The series was drafted for [Hop issue 7931](https://github.com/apache/hop/issues/7931).

Each episode is a folder under `docs/video-series/` with a `manifest.yaml`, PNG stills, and short muted clips. `tools/video-series/render.py` synthesizes the voice-over with the xAI text-to-speech API, holds every scene for the longest language, and writes a 1080p MP4 plus WebVTT captions. Generated audio and video stay in `output/` and are not committed.

Series notes, languages, capture rules, and the render commands are in [docs/video-series/SERIES.md](docs/video-series/SERIES.md).

## Setup

`ffmpeg` and `ffprobe` need to be on `PATH`. Python packages are listed in `tools/video-series/requirements.txt`.

```bash
python3 -m pip install -r tools/video-series/requirements.txt
python3 tools/video-series/render.py self-test
python3 tools/video-series/render.py validate 01-orientation
```

A real voice-over needs `XAI_API_KEY` in the environment. `render.py render <episode> --silence` builds the picture with timed silence and does not call the speech service.

This project is licensed under the Apache License 2.0. See `LICENSE`.
