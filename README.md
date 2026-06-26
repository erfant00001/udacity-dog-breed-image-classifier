# Dog Breed Image Classifier

![Python](https://img.shields.io/badge/Python-3.x-blue) ![PyTorch](https://img.shields.io/badge/PyTorch-pretrained%20CNN-ee4c2c) ![License](https://img.shields.io/badge/License-MIT-green) ![Udacity](https://img.shields.io/badge/Udacity-AI%20Programming%20with%20Python-02b3e4)

A command-line application that uses **pre-trained Convolutional Neural Networks** (ResNet, AlexNet, and VGG) to classify images of dogs by breed, and to evaluate how well each architecture distinguishes dogs from non-dogs.

> Completed as the final project of the **Udacity — AI Programming with Python Nanodegree**.

## Overview

The program classifies a folder of pet images with a chosen pre-trained CNN, then compares the predicted labels against the true labels embedded in each image filename. For each architecture it reports whether the image **is a dog**, whether the **specific breed** matched, and summary statistics — so you can decide which model performs best.

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
pip install torch torchvision pillow

# Run a single architecture
python check_images.py --dir pet_images/ --arch vgg --dogfile dognames.txt

# Or run all three architectures in a batch
sh run_models_batch.sh
```

| Flag | Default | Description |
|------|---------|-------------|
| `--dir` | `pet_images/` | Folder of images to classify |
| `--arch` | `vgg` | CNN architecture: `resnet`, `alexnet`, or `vgg` |
| `--dogfile` | `dognames.txt` | Text file listing valid dog names |

## Results

All three architectures correctly identified dogs as dogs on the test images; VGG gave the strongest overall breed-classification performance. See `check_images.txt` for the uploaded-image analysis answers.

## Acknowledgements

Starter code and project specification provided by **Udacity** as part of the *AI Programming with Python Nanodegree*. Implementation by Erfan Taatizadeh.

## ⚠️ Academic integrity

This repository is shared as a personal portfolio and learning reference. If you are currently enrolled in this Nanodegree, please do **not** copy or submit this code as your own — doing so violates the [Udacity Honor Code](https://www.udacity.com/legal/en-us/honor-code).

## License

Released under the [MIT License](LICENSE) for the author's own contributions. Udacity-provided starter code remains the property of Udacity.
