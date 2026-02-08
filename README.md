# ava-speak

Convert text files to audio with Ava's voice (Microsoft Edge TTS).

## Installation

```bash
# 1. Install edge-tts
pip install edge-tts

# 2. Download the script
curl -fsSL https://raw.githubusercontent.com/amzqvc/ava-tts/main/ava-speak -o /usr/local/bin/ava-speak
chmod +x /usr/local/bin/ava-speak
```

Or clone the repo:
```bash
git clone https://github.com/amzqvc/ava-tts.git
cd ava-tts
./ava-speak --help
```

## Usage

```bash
# Convert a text file to MP3
ava-speak story.txt

# Custom output name
ava-speak script.md -o podcast.mp3

# Play after creating
ava-speak chapter1.txt --play

# Read from stdin
echo "Hello, this is Ava speaking" | ava-speak - -o hello.mp3
cat notes.md | ava-speak - -o notes.mp3
```

## Options

| Option | Description |
|--------|-------------|
| `-o, --output FILE` | Output filename (default: input.mp3) |
| `--play` | Play audio after creating |
| `-v, --voice VOICE` | Edge TTS voice (default: en-US-AvaNeural) |
| `-h, --help` | Show help |

## Supported Formats

- `.txt` - Plain text
- `.md` - Markdown (formatting stripped automatically)
- `-` - Read from stdin

## Requirements

- Python 3.8+
- `edge-tts` (`pip install edge-tts`)
- `ffprobe` (optional, for duration display - comes with ffmpeg)

## Voice

Uses Microsoft Edge TTS with the **en-US-AvaNeural** voice by default. This is a high-quality neural voice that sounds natural and warm.

Other voices available via `--voice`:
- `en-US-JennyNeural` - Another US female voice
- `en-GB-SoniaNeural` - British female
- `en-AU-NatashaNeural` - Australian female

List all voices: `edge-tts --list-voices`
