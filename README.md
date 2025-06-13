🎵 Music Generation with Neural Networks
This project demonstrates how to train a neural network model to generate music using MIDI files. The generated music is served via a Flask web interface, allowing users to input desired duration and download AI-generated piano compositions in MP3 format.

🔗 GitHub Repository: CodeAlpha_MusicGenProject

🚀 Project Overview
The aim is to build a Long Short-Term Memory (LSTM) neural network that learns from classical piano MIDI files and generates new music sequences based on learned patterns. A web interface built with Flask enables real-time user interaction and audio generation.

🧠 Key Features
Trains an LSTM-based neural network on MIDI files.

Generates original piano music sequences.

Converts MIDI output to MP3 format using FluidSynth and FFmpeg.

Interactive Flask-based web interface for music generation and download.

🛠️ Technologies Used
Category	Tools/Technologies
Backend	Python, Flask
ML/DL	TensorFlow, Keras
Music Processing	Music21, FluidSynth
Audio Conversion	pydub, FFmpeg
Web Interface	HTML (Jinja2 templates)

📁 Project Structure
php
Copy
Edit
CodeAlpha_MusicGenProject/
├── data/                   # MIDI data and extracted notes
├── soundfont/              # FluidR3_GM.sf2 soundfont file
├── static/                 # Static assets (CSS/JS)
├── templates/              # HTML templates for web UI
├── app.py                  # Flask application
├── play.py                 # Music playback script
├── train_notebook.py       # Script to train the LSTM model
├── weights.best.music3.keras # Trained model weights
├── requirements.txt        # Python dependencies
└── README.md               # Project documentation
⚙️ How It Works
1. Model Training
Preprocessing: MIDI files are parsed using music21 to extract notes and chords, which are encoded into sequences for training.

Model Architecture: Two LSTM layers followed by Dense layers are used to predict the next note in a sequence.

Training: The model is trained on sequences of notes and saved as weights.best.music3.keras.

2. Music Generation (via Flask)
Input: User provides music duration via the web interface.

Sequence Generation: Trained model predicts a new note sequence.

MIDI Conversion: Notes are converted to a .mid file using music21.

Audio Conversion: .mid → .wav via FluidSynth → .mp3 via FFmpeg.

Output: The generated MP3 file is provided for playback or download.

🌐 Web Interface
Accessible at http://127.0.0.1:5000/ (after running app.py).
Users can:

Input desired duration in seconds

Generate new music

Download or play the output MP3

✅ Requirements
Ensure the following are installed:

Python 3.6+

Flask

TensorFlow 2.x

Keras

Music21

pydub

FluidSynth

FFmpeg

Additional Setup
🔉 SoundFont (FluidR3_GM.sf2)
Download from official sources or MuseScore.

Place it in the soundfont/ directory.

Update the path in app.py accordingly:

python
Copy
Edit
soundfont_path = "soundfont/FluidR3_GM.sf2"
🧪 How to Run
Clone the Repository
bash
Copy
Edit
git clone https://github.com/ChiragAvasthi/CodeAlpha_MusicGenProject.git
cd CodeAlpha_MusicGenProject
Install Dependencies
bash
Copy
Edit
pip install -r requirements.txt
Train the Model (Optional)
bash
Copy
Edit
python train_notebook.py
Skip if weights.best.music3.keras already exists.

Start the Flask App
bash
Copy
Edit
python app.py
Navigate to: http://127.0.0.1:5000/

🎼 Generate Music
Enter desired music duration in the interface.

Model generates and saves a MIDI → WAV → MP3.

Resulting MP3 is available to stream or download.

📌 Notes
This project generates only piano-based music.

Ensure FFmpeg and FluidSynth are properly installed and in your system path.

Performance and output quality depend on training data and epochs.

📜 License
This project is licensed under the MIT License.
