# Audio Transcriber

A powerful and efficient Python script for transcribing audio files using the high-speed Groq API with OpenAI's Whisper model. This tool automatically converts various audio formats to MP3 using FFmpeg and provides fast, accurate transcriptions.

## Features

- **Multi-Format Support**: Transcribes various audio formats, including `.ogg`, `.wav`, `.flac`, `.m4a`, `.aac`, `.mp3`, and more.
- **Automatic Conversion**: Seamlessly converts non-MP3 audio files to the required format using FFmpeg.
- **High-Speed Transcription**: Leverages the Groq API with the `whisper-large-v3` model for incredibly fast processing.
- **Secure Configuration**: Manages API keys and settings through a `.env` file for better security.
- **Organized Output**: Saves the converted MP3 file and the final transcription to a designated output folder.
- **Dependency Check**: Includes a built-in verification to ensure FFmpeg is installed and accessible.

## Prerequisites

Before you begin, ensure you have the following installed and configured:

- **Python 3.7+**
- **FFmpeg**: A cross-platform framework for audio and video processing.
- **Groq API Key**: You can obtain one from [GroqCloud](https://console.groq.com/keys).

## Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/SakibAhmedShuva/OGG-Transcriber.git
   cd OGG-Transcriber
   ```

2. **Install the required Python dependencies:**
   ```bash
   pip install python-dotenv groq pydub
   ```

3. **Install FFmpeg:**

   - **Windows:** Download from the [official FFmpeg website](https://ffmpeg.org/download.html) and add the `bin` directory to your system's PATH.
   - **macOS (using Homebrew):**
     ```bash
     brew install ffmpeg
     ```
   - **Linux (using APT):**
     ```bash
     sudo apt update && sudo apt install ffmpeg
     ```

## Usage

### 1. Create a Configuration File

Create a file named `.env` in the root of the project directory. Add your Groq API key and specify an output folder:

```env
# .env file
GROQ_API_KEY="your_groq_api_key_here"
OUTPUT_FOLDER="transcriptions"
```

### 2. Set the Input File Path

Open the `transcriber.ipynb` notebook and update the `INPUT_FILE` variable to the path of the audio file you want to transcribe:

```python
# --- SET YOUR INPUT FILE HERE ---
INPUT_FILE = "path/to/your/audio_file.wav"  # <--- REPLACE WITH THE PATH TO YOUR AUDIO FILE
```

### 3. Run the Script

Open and execute the cells in `transcriber.ipynb` using a Jupyter environment (like Jupyter Lab, VS Code, or Google Colab). The script will:

- Verify that FFmpeg is installed.
- Load your configuration from the `.env` file.
- Convert your audio file to MP3 format (if it isn't already).
- Transcribe the audio using the Groq API.
- Print the transcription directly in the notebook.
- Save the results to the output folder.

### 4. Access the Results

The converted `.mp3` file and the corresponding `_transcription.txt` file will be saved in the folder you specified in the `OUTPUT_FOLDER` variable (e.g., `transcriptions/`).

## How It Works

The transcription process follows this simple workflow:

```
Audio File → FFmpeg Conversion → MP3 File → Groq API (Whisper) → Transcription Text
```

1. **Initialize**: The script starts by verifying FFmpeg's availability and loading your environment variables.
2. **Convert**: The input audio file is converted to a 192k bitrate MP3 using FFmpeg (this step is skipped if the file is already an MP3).
3. **Transcribe**: The MP3 file is sent to the Groq API, which processes it with the `whisper-large-v3` model.
4. **Save**: The final transcription is saved as a `.txt` file in the specified output folder.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Acknowledgements

- **Groq**: For their incredibly fast API service.
- **OpenAI**: For developing the powerful Whisper ASR model.
- **FFmpeg Community**: For their essential and versatile multimedia framework.

## Contributing

Contributions are welcome! If you have suggestions or improvements, please feel free to fork the repository and submit a pull request.

## Support

If you encounter any issues or have questions, please open an issue on the [GitHub repository](https://github.com/SakibAhmedShuva/OGG-Transcriber).
