# Sign-Language-to-Text

Project converts American sign language to text in realtime. It uses CNN to train the required models for prediction. The dataset is custom made.

## Dataset
- train : https://drive.google.com/drive/u/1/folders/1-XTAjPPRPFeRqu3848z8dMXaolILWizn
- test : https://drive.google.com/drive/u/1/folders/18e1F1n1SWPF8lUF8pCKdUzSzKAbmSbVN

## Run in Terminal MacOS
cd Downloads/SignLanguage\ Project/Sign-Language-to-Text/Sign-Language-to-Text && /opt/homebrew/bin/python3.9 app.py

## Requirements
Install via pip:
```
pip install -r requirements_pip.txt
```
Or via conda:
```
conda create --name signlang --file requirements_conda.txt
```

## How to Run

### Step 1 - Collect Data
```
python collect-data.py
```

### Step 2 - Preprocess Data
```
python preprocessing.py
```

### Step 3 - Train the Model
```
python train.py
```

### Step 4 - Run the Application
```
python app.py
```

## Project Structure
| File | Description |
|------|-------------|
| `app.py` | Main tkinter GUI application |
| `train.py` | CNN model training script |
| `collect-data.py` | Dataset collection via webcam |
| `preprocessing.py` | Image preprocessing pipeline |
| `image_processing.py` | Gaussian blur & threshold functions |
| `requirements_pip.txt` | Pip dependencies |
| `requirements_conda.txt` | Conda dependencies |
| `signs.png` | ASL alphabet reference chart |

## Tech Stack
- Python 3.6
- Keras + TensorFlow (CNN)
- OpenCV (real-time video)
- Tkinter (GUI)
- Hunspell (autocorrect)

## Accuracy
- Layer 1 (27-class CNN): **95.8%**
- Layer 1 + Layer 2 (similar symbol classifier): **98.0%**

## How It Works
1. Webcam captures hand gesture in real-time
2. Gaussian blur + adaptive threshold applied for feature extraction
3. CNN model predicts the ASL letter (Layer 1)
4. A second classifier resolves similar-looking letters like D/R/U, I/T/K, M/N/S (Layer 2)
5. Letters build into words; Hunspell suggests corrections
6. Words form sentences displayed on screen
