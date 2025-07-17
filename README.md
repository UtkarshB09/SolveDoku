# 🧠 Sudoku Solver (Real-Time via Webcam)

This project captures a real-time webcam feed, detects and extracts Sudoku puzzles from the video frames, solves them instantly using a highly efficient algorithm, and overlays the solution on the video stream.

---

## 📌 Overview

- **Live Detection**: Uses OpenCV to identify Sudoku puzzles from real-time webcam frames.
- **Instant Solving**: Solves puzzles in under **0.01 seconds** using Peter Norvig's constraint propagation + search algorithm.  
  ([Read more](https://norvig.com/sudoku.html))
- **Digit Recognition**: A custom-trained CNN model based on a LeNet-inspired architecture accurately detects digits.
- **End-to-End Pipeline**: From camera feed → grid detection → digit recognition → puzzle solving → overlay display.

---

## 📂 Project Structure

sudoku-solver/
├── sudoku_solver.py # Main script: real-time Sudoku detection and solving
├── model/ # (Not included) Trained digit recognition model
├── dataset/ # (Not included) Custom dataset for training
├── utils/
│ ├── image_utils.py # Image preprocessing and grid extraction helpers
│ └── solver.py # Peter Norvig’s Sudoku solver implementation
├── README.md # This file


---

## 🧠 Digit Recognition Model

- Trained on a **curated subset** of the [Char74K Dataset](https://www.ee.surrey.ac.uk/CVSSP/demos/chars74k/)
- Focused on digits that visually resemble those used in standard printed Sudoku puzzles.
- The CNN architecture is inspired by **LeNet-5**, originally used for the MNIST dataset.

> ⚠️ **Note**: The dataset and trained model are **not included** in this repository.  
> To replicate:
> 1. Download and curate your own digit samples from Char74K.
> 2. Train a CNN on your custom dataset.
> 3. Save and use the trained model in `sudoku_solver.py`.

---

## 💻 Requirements

Install the dependencies using pip:

```bash
pip install -r requirements.txt
