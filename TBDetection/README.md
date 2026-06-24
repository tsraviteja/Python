# TB Detection

Download the TB X-ray dataset from Kaggle and create the following folder structure in the project directory:

- `data/` folder with:
  - `train/` folder for training data
  - `validation/` folder for validation data

Split the downloaded data equally between the train and validation folders.

- In `data/` folder also include intents.json file that contains conversation patterns and responses for training the chatbot. This file defines different conversation intents (like greetings, medical queries, symptom detection) and their corresponding user patterns and bot responses, which enables the chatbot to understand and respond to user queries intelligently.

  **Example:**
  ```json
  {
    "tag": "greetings",
    "patterns": ["hello", "hi", "hey"],
    "responses": ["Hello!", "Hi there!", "What can I help you with?"]
  }
  ```
When a user types "hello" or "hi", the chatbot recognizes it as a "greetings" intent and responds with one of the predefined responses.

## System Setup

### Prerequisites
Before setting up the project, ensure you have Python 3.12 and required dependencies installed. Follow these steps:

### Step 1: Install Python 3.12
```bash
sudo add-apt-repository ppa:deadsnakes/ppa -y
sudo apt update
sudo apt install python3.12 python3.12-venv -y
```

### Step 2: Create Virtual Environment
```bash
cd ~/Desktop/Python/TBDetection
rm -rf .venv  # Remove existing .venv if any
python3.12 -m venv .venv
```

### Step 3: Activate Virtual Environment and Install Dependencies
```bash
source .venv/bin/activate
pip install -r requirements.txt
```

### Required Dependencies
The `requirements.txt` file includes:
- `tensorflow` - Deep learning framework for model training
- `keras` - Neural network API
- `numpy` - Numerical computing
- `pandas` - Data manipulation
- `matplotlib` - Data visualization
- `nltk` - Natural language processing for chatbot
- `opencv-python` - Computer vision for image processing
- `pyttsx3` - Text-to-speech functionality
- `SpeechRecognition` - Speech-to-text functionality

### Step 4: Configure Jupyter Kernel for Notebooks
To run the Jupyter notebooks with the virtual environment, install and configure the IPython kernel:

```bash
pip install ipykernel
python -m ipykernel install --user --name=venv --display-name "Python (.venv)"
```

This creates a Python kernel linked to your virtual environment. When opening notebooks in VS Code or Jupyter, select the "Python (.venv)" kernel to ensure the correct dependencies are used.

### Step 5: Install GUI and Additional Dependencies
```bash
sudo apt install python3.12-tk -y
pip install requests
pip install --upgrade --force-reinstall pillow
```

- `python3.12-tk` - Required for Tkinter GUI support (used by the interactive chatbot interface)
- `requests` - HTTP library for making web requests
- `pillow` - Image processing library for enhanced image handling
