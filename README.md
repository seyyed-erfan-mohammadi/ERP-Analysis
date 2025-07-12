# 🧠 ERP Analysis from EEG Data using MATLAB

Welcome to my course project on **Event-Related Potential (ERP)** analysis, created as part of my EEG signal processing coursework. This repository demonstrates how to preprocess EEG data, extract epochs based on event markers, perform baseline correction, compute ERPs, and visualize brain responses across time and space using MATLAB.

---

## 📂 Dataset

The EEG data used in this project is sourced from `eeglab_data.mat`, a sample dataset typically provided with the [EEGLAB toolbox](https://sccn.ucsd.edu/eeglab/index.php). The dataset contains multi-channel EEG recordings along with annotated events (`event`) and channel locations (`chanlocs`) for topographic plots.

---

## ⚙️ Pipeline Overview

### ✅ Step-by-Step Workflow

1. **Load EEG Data**
   - Load the `.mat` file and generate a time vector from **-200 ms to 1000 ms**, with 5 ms intervals.
  
2. **Average Re-Referencing**
   - Re-reference EEG signals by subtracting the average of all channels to reduce noise and global artifacts.

3. **Event Detection**
   - Extract event types and latencies.
   - Identify time points of interest for four specific event classes.

4. **Epoching**
   - Segment the EEG data from **-200 ms to 1000 ms** around each event.
   - Apply **baseline correction** using the pre-stimulus interval (-200 to 0 ms).

5. **ERP Calculation**
   - Average all epochs across trials for each event class to extract event-related potentials.

6. **Visualization**
   - **ERP waveform per channel**
   - **ERP image** (heatmap) for a selected channel and event
   - **All individual epochs** for a specific channel
   - **Overlayed ERP plots** across channels and events
   - **Global Field Power (GFP)** and **topographic variance**
   - **Topoplot** of brain activity across time

---

## 📊 Example Outputs

> 💡 Modify these variables to control the output:
- `which_stimulus = 1;` → Choose from 111, 112, 121, 122
- `which_channle = 30;` → Choose a channel index (1–32)

### ERP per Channel
Plots the averaged ERP waveform for each EEG channel.

### ERP Image
A heatmap showing signal fluctuations across epochs and time for one selected channel.

### All Epochs (Single Channel)
Line plot showing every single epoch overlaid to evaluate trial-by-trial variability.

### ERP Comparison Across Events
Overlayed ERP waveforms of a single channel across different event types.

### GFP & Variance Plot
Calculates and plots **Global Field Power** (standard deviation across all channels) and **variance** across time.

### Topoplots
Scalp topographies of ERP signals at different post-stimulus time points.
