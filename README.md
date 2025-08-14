# OGG-Transcriber

A powerful and efficient Python script for transcribing audio files using Groq API with OpenAI's Whisper model. This tool automatically converts various audio formats to MP3 using FFmpeg and provides fast, accurate transcriptions.

## Features

- **Multi-Format Support**: Transcribes various audio formats including `.ogg`, `.wav`, `.flac`, `.m4a`, `.aac`, and more
- **Automatic Conversion**: Uses FFmpeg to seamlessly convert audio files to MP3 format
- **High-Speed Transcription**: Leverages Groq API with the `whisper-large-v3` model for fast processing
- **Batch Processing**: Process entire folders of audio files at once
- **Single File Mode**: Option to transcribe individual audio files
- **Organized Output**: Saves converted MP3 files and transcriptions in a designated output folder
- **Dependency Check**: Built-in verification to ensure FFmpeg is installed and accessible

## Prerequisites

Before you begin, ensure you have:

- **Python 3.7+**
- **FFmpeg**: Cross-platform multimedia framework for audio/video processing
- **Groq API Key**: Obtain from [GroqCloud](https://groq.com)

## Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/SakibAhmedShuva/OGG-Transcriber.git
   cd OGG-Transcriber
   ```

2. **Install Python dependencies:**
   ```bash
   pip install groq
   ```

3. **Install FFmpeg:**
   
   **Windows:** Download from the [official FFmpeg website](https://ffmpeg.org/download.html) and add the `bin` directory to your system's PATH.
   
   **macOS (using Homebrew):**
   ```bash
   brew install ffmpeg
   ```
   
   **Linux (using APT):**
   ```bash
   sudo apt update && sudo apt install ffmpeg
   ```

## Usage

### 1. Configure the Script

Open `transcriber.ipynb` and set your Groq API key:

```python
# Configuration
GROQ_API_KEY = "your_groq_api_key_here"  # Replace with your actual API key
```

### 2. Prepare Your Audio Files

Create an `audio_files` folder in the project root and place your audio files inside:

```
OGG-Transcriber/
├── audio_files/
│   ├── recording1.ogg
│   └── meeting_audio.wav
├── transcriber.ipynb
└── README.md
```

### 3. Run the Script

Open and execute the cells in `transcriber.ipynb` using a Jupyter environment (Jupyter Lab, VS Code, etc.). The script will:

- Verify FFmpeg installation
- Convert audio files to MP3 format
- Transcribe MP3 files using Groq API
- Save results to the output folder

### 4. Access Results

Converted `.mp3` files and corresponding `.txt` transcriptions will be saved in the `converted_mp3` folder.

## Configuration Options

Customize the following variables in `transcriber.ipynb`:

- `GROQ_API_KEY`: (Required) Your Groq API access key
- `INPUT_FOLDER`: Source directory for audio files (default: `"audio_files"`)
- `OUTPUT_FOLDER`: Destination for converted files and transcriptions (default: `"converted_mp3"`)

## How It Works

The transcription process follows this workflow:

```
Audio File → FFmpeg Conversion → MP3 File → Groq API (Whisper) → Transcription
```

1. **Initialize**: Verify FFmpeg availability
2. **Scan**: Detect all supported audio files in the input folder
3. **Convert**: Convert files to 192k bitrate MP3 using FFmpeg (skip if already MP3)
4. **Transcribe**: Process MP3 files through Groq API with `whisper-large-v3` model
5. **Save**: Store transcription text in corresponding `.txt` files

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

- **Groq**: For their incredibly fast API service
- **OpenAI**: For developing the powerful Whisper model
- **FFmpeg Community**: For their essential multimedia framework

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Support

If you encounter any issues or have questions, please open an issue on the GitHub repository.
