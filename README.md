# GoogleMT3



## Project Overview (Updating)

1. **Basic Pitch Prediction**:
   - Generate predictions using the Basic Pitch Temporal Convolutional Network (TCN) model.
   - Output includes MIDI files, NPZ model outputs, and CSV files containing note event labels.

2. **Label Processing**:
   - Extract framed Mel spectrograms from the raw audio files using note event timestamps from Basic Pitch predictions.
   - Create structured datasets for CNN training, aligning the spectrograms with corresponding note event labels.
   - Each Mel spectrogram is set to 2s long for now. This might change in the future.

3. **Simple CNN Training**:   
   - Train a simple CNN model to predict music transcription from the framed Mel spectrograms.
   - The model predicts note events, including ```start time```, ```end time```, ```pitch```, ```velocity```, and ```confidence```.

### Project Structure


```plaintext
GoogleMT3/
│
├── Models/
│   └── SimpleCNN.py       # CNN model training and prediction script
│
├── Preprocessor/
│   └── BASIC_Pitch_spectrogram_gen.py   # Basic Pitch prediction and spectrogram extraction
│
├── BasicPitchTCN_prediction/
│   ├── csv/               # Basic Pitch-generated CSV files
│   ├── midi/              # Basic Pitch-generated MIDI files
│   ├── npz/               # Basic Pitch model outputs (NPZ format)
│   └── spectrograms/      # Extracted framed Mel spectrograms
│
├── .gitignore             # Git ignore file
├── README.md              # Project readme file
└── requirements.txt       # Python dependencies
