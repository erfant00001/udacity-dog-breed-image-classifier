# Dog Breed Image Classifier

![Python](https://img.shields.io/badge/Python-3.x-blue) ![PyTorch](https://img.shields.io/badge/PyTorch-pretrained%20CNN-ee4c2c) ![License](https://img.shields.io/badge/License-MIT-green) ![Udacity](https://img.shields.io/badge/Udacity-AI%20Programming%20with%20Python-02b3e4)

A command-line application that uses **pre-trained Convolutional Neural Networks** (ResNet, AlexNet, and VGG) to classify images of dogs by breed, and to evaluate how well each architecture distinguishes dogs from non-dogs.

> Completed as the final project of the **Udacity — AI Programming with Python Nanodegree**.

## Overview

The program classifies a folder of pet images with a chosen pre-trained CNN, then compares the predicted labels against the true labels embedded in each image filename. It reports, for each model architecture:

- whether the image **is a dog** (and whether the classifier agreed),
- whether the **specific breed** was matched, and
- summary statistics (percent correct dogs, breeds, and non-dogs).

The goal is to determine which of the three architectures provides the best classification performance — trading off accuracy against runtime.

## How it works

1. `get_pet_labels.py` — extracts the true pet label from each image filename.
2. `classifier.py` — wraps torchvision's pre-trained ResNet/AlexNet/VGG models for inference.
3. `classify_images.py` — runs the classifier and compares predictions to the true labels.
4. `adjust_results4_isadog.py` — flags whether each label is a dog using `dognames.txt`.
5. `calculates_results_stats.py` — computes count and percentage statistics.
6. `print_results.py` — prints a results summary (and optional misclassifications).
7. `check_images.py` — the main program that ties it all together.

## Getting started

```bash
# 1. Install dependencies
pip install torch torchvision pillow

# 2. Place your images in a folder (filenames encode the true label, e.g. Golden_retriever_01.jpg)

# 3. Run a single architecture
python check_images.py --dir pet_images/ --arch vgg --dogfile dognames.txt

# 4. Or run all three architectures in a batch
sh run_models_batch.sh
```

**Command-line arguments**

| Flag | Default | Description |
|------|---------|-------------|
| `--dir` | `pet_images/` | Folder of images to classify |
| `--arch` | `vgg` | CNN architecture: `resnet`, `alexnet`, or `vgg` |
| `--dogfile` | `dognames.txt` | Text file listing valid dog names |

## Results

All three architectures correctly identified dogs as dogs on the test images; VGG gave the strongest overall breed-classification performance. See `check_images.txt` for the answers to the uploaded-image analysis questions.

## Project structure

```
.
├── check_images.py                   # Main program
├── get_input_args.py                 # Command-line argument parsing
├── get_pet_labels.py                 # True labels from filenames
├── classifier.py                     # Pre-trained CNN inference
├── classify_images.py                # Run + compare predictions
├── adjust_results4_isadog.py         # Dog / not-a-dog flags
├── calculates_results_stats.py       # Statistics
├── print_results.py                  # Results printout
├── print_functions_for_lab_checks.py # Lab check helpers
├── test_classifier.py                # Classifier usage demo
├── run_models_batch*.sh              # Batch runners
├── dognames.txt                      # Valid dog names
└── imagenet1000_clsid_to_human.txt   # ImageNet class index → label map
```

## Note on large / binary files

The `pet_images/` and `uploaded_images/` sample image folders and the original submission `.zip` are **not** included here (binary assets). They can be added later with [Git LFS](https://git-lfs.com/):

```bash
git lfs install
git lfs track "*.jpg" "*.png" "*.zip"
git add .gitattributes <your-images>
git commit -m "Add image assets via LFS"
```

## Acknowledgements

Starter code and project specification provided by **Udacity** as part of the *AI Programming with Python Nanodegree*. Implementation by Erfan Taatizadeh.

## ⚠️ Academic integrity

This repository is shared as a personal portfolio and learning reference. If you are currently enrolled in this Nanodegree, please do **not** copy or submit this code as your own — doing so violates the [Udacity Honor Code](https://www.udacity.com/legal/en-us/honor-code). Use it only to learn from, or to compare approaches after completing your own work.

## License

Released under the [MIT License](LICENSE) for the author's own contributions. Udacity-provided starter code remains the property of Udacity.
