# 🎤 Hindi Voice Cloning - Source Code

Welcome to the `src` directory! This folder contains all the core Python source code for the Hindi Voice Cloning project. Below is a summary of what each script does and its role in the cloning pipeline.

---

## 📂 File Descriptions

### `preprocess.py`
* **What it does:** This script handles all the necessary **audio preprocessing**. It prepares your raw audio files, making them suitable for training the neural network. 🎧
* **How it works:** It likely loads audio files from your dataset, converts them to a standard format (like Mel spectrograms), normalizes their volume, and segments them into smaller, usable chunks for the model to process.

### `model.py`
* **What it does:** This file defines the **neural network architecture**. It contains the blueprint for the voice cloning model itself, specifying all the layers, dimensions, and operations. 🧠
* **How it works:** It uses a deep learning framework like PyTorch or TensorFlow to build the model. The code likely defines classes for the **Encoder** (which captures the voice identity from an audio sample) and the **Synthesizer/Vocoder** (which generates new speech).

### `train.py`
* **What it does:** This is the script used to **train the voice cloning model**. It feeds the preprocessed data into the model architecture and teaches it how to clone voices. 🚀
* **How it works:** It sets up the training loop, which involves loading data batches, performing forward and backward passes, calculating the loss, and updating the model's weights using an optimizer. It also handles saving model checkpoints periodically.

### `eval.py`
* **What it does:** This script is for **evaluating the performance** of your trained model. It helps you understand how well the model can clone a voice from a new, unseen audio sample. 📈
* **How it works:** It loads a saved model checkpoint and a reference audio clip. It then generates a new audio clip by cloning the voice from the reference and synthesizes a target text. This allows you to listen to the output and objectively measure its quality.

### `main.py`
* **What it does:** This is the **main entry point** for running the application. It likely ties all the other scripts together, allowing you to easily train, evaluate, or run inference with simple commands. 🎬
* **How it works:** This script typically parses command-line arguments to decide which action to perform (e.g., `python main.py --train` or `python main.py --clone --text "नमस्ते"`). It then calls the appropriate functions from the other modules to execute the task.

### `utils.py`
* **What it does:** A collection of **utility functions** and helper code used by the other scripts. This keeps the main scripts clean and organized. 🛠️
* **How it works:** This file might contain functions for loading configurations from a file, logging progress, plotting results, or performing common audio manipulations. It prevents code duplication by storing reusable logic in one place.

---

## 🚀 How to Use

The scripts are designed to be run from the command line. The primary way to interact with the project is likely through `main.py`.

1.  **Preprocessing Data:**
    ```bash
    python preprocess.py --dataset_path /path/to/your/audio
    ```
2.  **Training the Model:**
    ```bash
    python train.py --config config.yaml
    ```
3.  **Cloning a Voice (Inference):**
    ```bash
    python main.py --clone --ref_audio /path/to/sample.wav --text "आप कैसे हैं?"
    ```

*Note: The exact commands may vary as per device.*
