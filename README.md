# Trajectory Prediction for Pedestrians and Cyclists using nuScenes Dataset

This project implements a trajectory prediction model for pedestrians and cyclists using the nuScenes `v1.0-mini` dataset. The goal is to predict future positions of these agents based on their past movement history.

## Project Overview

We developed an LSTM-based neural network model to predict the `x`, `y`, and `z` coordinates of pedestrian and cyclist trajectories. The model takes a sequence of historical positions, velocities, and speeds as input and outputs a sequence of future positions.

## Dataset

The project utilizes the `v1.0-mini` subset of the nuScenes dataset, a large-scale dataset for autonomous driving research. The data includes 3D bounding box annotations for various object categories, which we use to extract pedestrian and cyclist trajectories.

## Features & Model

*   **Feature Engineering:** Velocity (`vx`, `vy`, `vz`, `speed`) and acceleration (`ax`, `ay`, `az`, `acceleration`) were calculated from raw `x, y, z` coordinates for each instance.
*   **Sequence Generation:** Trajectories were segmented into sequences of 10 historical steps (2 seconds) as input and 10 future steps (2 seconds) as target outputs. Input features include `x, y, z, vx, vy, speed`.
*   **Model Architecture:** An LSTM neural network with a Dense output layer was used, built with TensorFlow/Keras.

## Setup and Running the Code

### 1. Google Colab (Recommended)

The easiest way to explore and run this project is through the provided Google Colab notebook. This notebook contains all the code, execution steps, and visualizations:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1e13clxFx-X_FZYwuuoG27EVY8l3n7m3g?usp=sharing)

### 2. Local Setup

To run this project locally, follow these steps:

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/sanjanapstech-ui/AI-in-mobility.git
    cd AI-IN-MOBILITY
    ```

2.  **Create a Virtual Environment (Optional but Recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scriptsctivate`
    ```

3.  **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Download nuScenes `v1.0-mini` Dataset:**
    You will need to download the `v1.0-mini.tgz` dataset from the official nuScenes website (requires registration) and place it in a known location. For this project, it's assumed to be accessible at `/content/drive/MyDrive/v1.0-mini.tgz` if running in Colab, or adjust the `file_path` variable in the code accordingly.

5.  **Run the Notebook:**
    Open the Jupyter Notebook (`AI in mobility.ipynb` or equivalent) and run all cells sequentially. The code will handle data extraction, processing, model training, and evaluation.

## Results

The model was evaluated on a test set, yielding the following performance metrics:

*   **Test Loss (Mean Squared Error - MSE):** 78.2580
*   **Average Displacement Error (ADE):** 12.8910
*   **Final Displacement Error (FDE):** 10.2079

Visualizations of predicted trajectories against ground truth are generated to qualitatively assess the model's performance.

## Key Files

*   `requirements.txt`: Lists all Python dependencies.
*   `README.md`: This file, providing project overview and instructions.
*   `AI in mobility.ipynb`: The main Colab notebook containing all project code and execution steps. (Replace with your actual notebook file name)


<>:40: SyntaxWarning: invalid escape sequence '\S'
<>:40: SyntaxWarning: invalid escape sequence '\S'
/tmp/ipykernel_10180/320039741.py:40: SyntaxWarning: invalid escape sequence '\S'
  source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
