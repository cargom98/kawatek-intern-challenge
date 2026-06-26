# Challenge A: Physical AI & Robotics

## Context

At Kawatek, we develop the RYO® bionic hand — a robotic prosthetic that uses EMG (electromyography) signals from a user's muscles to control finger movements. A critical part of our system is the **signal processing pipeline** that converts raw sensor data into motor commands.

## The Problem

You are given a simulated EMG signal dataset (`data/emg_signals.csv`) representing sensor readings from 4 channels over time. Your task is to build a **signal classification pipeline** that:

1. **Reads and preprocesses** the raw EMG data (noise filtering, normalization)
2. **Extracts features** from the signal windows (e.g., RMS, zero crossings, mean absolute value)
3. **Classifies** the signal into one of 5 grip patterns:
   - `rest` — hand open, no movement
   - `power_grip` — full hand close (grabbing a bottle)
   - `pinch` — thumb + index finger (picking up a coin)
   - `lateral` — thumb against side of index finger (holding a key)
   - `point` — index finger extended

4. **Outputs** a real-time-style prediction for each time window

## Provided Files

```
challenge-a/
├── README.md          (this file)
├── data/
│   ├── emg_signals.csv       (raw signal data: timestamp, ch1, ch2, ch3, ch4, label)
│   └── test_signals.csv      (unlabeled test data for your classifier)
├── src/
│   └── placeholder.py        (start here)
├── requirements.txt
└── SOLUTION.md               (write your explanation here)
```

## Requirements

- **Language:** Python (preferred) or C++ 
- **Output:** A script that, given `test_signals.csv`, prints predicted grip labels per window
- **Minimum accuracy:** Your classifier should achieve ≥ 70% accuracy on the labeled data (using train/test split)

## Tasks

### Task 1: Signal Preprocessing (Required)
- Load the CSV data
- Apply a bandpass filter (20–450 Hz) to remove noise
- Segment data into windows of 200ms with 50ms overlap

### Task 2: Feature Extraction (Required)
- For each window, extract at least 4 features per channel:
  - Root Mean Square (RMS)
  - Mean Absolute Value (MAV)
  - Zero Crossing Rate (ZCR)
  - Waveform Length (WL)

### Task 3: Classification (Required)
- Train a classifier on the labeled data
- Evaluate accuracy with a train/test split
- Predict labels for `test_signals.csv`

### Task 4: Visualization (Bonus)
- Plot the raw vs filtered signals
- Show a confusion matrix of your classifier
- Visualize feature distributions per grip type

### Task 5: Real-time Simulation (Bonus)
- Simulate a real-time prediction loop that processes one window at a time
- Print predictions with latency metrics

## Evaluation Focus

- Signal processing fundamentals
- Understanding of classification pipelines
- Code structure and documentation
- Ability to work with sensor data (relevant to our embedded systems)

## Hints

- `scipy.signal` is your friend for filtering
- `sklearn` works great for the classification step
- Think about what a real prosthetic system would need: low latency, reliability
