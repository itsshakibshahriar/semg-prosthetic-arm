# Resource-Efficient sEMG-Driven Prosthetic Arm with Edge-Deployed Deep Learning

Code, firmware and design files for a 3D-printed transradial prosthetic arm controlled by a
three-channel surface EMG (sEMG) array, with a deep neural network running on an ESP32-S3.

> Undergraduate thesis, Dept. of EEE, Jashore University of Science and Technology.
> Supervisor: Dr. Md. Moznuzzaman. Manuscript in preparation.

<!-- Add a hardware photo or demo GIF here: ![demo](figures/demo.gif) -->

## Overview
- **Sensing:** 3 sEMG channels
- **Data:** 20 participants, multi-session, posture-varied (supine and seated)
- **Models compared:** 1D-CNN, 1D-ResNet, LSTM, Hybrid CNN-LSTM
- **Deployment:** quantized model, bare-metal C++/Arduino firmware on ESP32-S3
- **Key results:** TODO (accuracy, macro-F1, on-device latency, model size)

## Dataset
The dataset is hosted separately: **DOI: TODO (Zenodo)**. See [`data/README.md`](data/README.md).
Filter processed data by `is_usable == 1` before training. Session IDs do not always follow the
S01/S02 convention; see `Session_confusion.xlsx` in the dataset record.

## Repository layout
| Folder | Contents |
|---|---|
| `data_acquisition/` | Data collection and 20-second practice scripts |
| `data/` | Dataset instructions and a small sample |
| `preprocessing/` | Signal quality assessment / data screening |
| `deep_learning/` | Training and evaluation of the four architectures |
| `firmware/` | ESP32-S3 inference firmware |
| `models/` | Exported final model |
| `results/` | Metrics tables, confusion matrices |
| `figures/` | Figures (PNG) |
| `cad/` | 3D-print files (STL / source CAD) |

## Quick start
```bash
git clone https://github.com/YOUR-USERNAME/semg-prosthetic-arm.git
cd semg-prosthetic-arm
pip install -r requirements.txt
# 1. download the dataset from the Zenodo DOI above into data/
# 2. run the screening script in preprocessing/
# 3. train/evaluate with the scripts in deep_learning/
```

## Hardware
List: ESP32-S3 board, sEMG sensors, servos, 3D-printed parts, power. Wiring diagram: TODO.

## Flashing the firmware
TODO: Arduino IDE / PlatformIO version, board settings, how to load the model.

## Citation
See [`CITATION.cff`](CITATION.cff).

## License
Code: MIT. Dataset and design files: see their respective records.
