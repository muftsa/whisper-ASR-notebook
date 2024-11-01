# whisper-ASR-notebook
Jupyter Notebook for Automatic Speech Recognition

A Jupyter notebook code that sets up and uses OpenAI's Whisper model for Automatic Speech Recognition (ASR) locally. It uses the [Whisper package](https://github.com/openai/whisper), which you can install and run on your machine if you have compatible hardware and dependencies.

### Requirements:
1. Install `whisper` package:
   ```bash
   pip install -U openai-whisper
   ```
   
2. Install `ffmpeg` for audio processing:
   - On MacOS:
     ```bash
     brew install ffmpeg
     ```
   - On Ubuntu:
     ```bash
     sudo apt update && sudo apt install ffmpeg
     ```

### Notebook Code

Below is a complete Jupyter notebook with code cells for setting up and running Whisper locally.

```python
# Whisper ASR with Jupyter Notebook

# Install required packages
!pip install openai-whisper
!apt install ffmpeg  # For Linux-based systems. If on Mac, use 'brew install ffmpeg'

# Import Whisper
import whisper

# Load the Whisper model (base model is faster; large model is more accurate but slower)
# Available models: 'tiny', 'base', 'small', 'medium', 'large'
model = whisper.load_model("base")

# Load and transcribe audio file
# Upload your audio file to the notebook environment, then specify the file path here
audio_path = "path_to_your_audio_file.mp3"  # Replace with the path to your audio file

# Transcribe the audio
result = model.transcribe(audio_path)

# Display the transcription
print("Transcription:")
print(result["text"])
```

### Step-by-Step Instructions:

1. **Set Up the Environment**: Run the first code cell to install `whisper` and `ffmpeg`.
2. **Load the Model**: Choose a model size depending on your hardware and accuracy needs.
3. **Specify Your Audio File Path**: Replace `"path_to_your_audio_file.mp3"` with the path to your audio file.
4. **Run Transcription**: Execute the transcription cell, and the output text will display.

This notebook transcribes audio files into text using OpenAI's Whisper locally on your machine.
