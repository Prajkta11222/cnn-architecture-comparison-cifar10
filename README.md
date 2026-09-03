# CNN Architecture Comparison on CIFAR-10

## Project Overview

This Deep Learning project compares four Convolutional Neural Network (CNN) architectures:

- LeNet
- AlexNet
- VGG-11
- ResNet-18

All models are evaluated on the CIFAR-10 dataset to study the trade-off between classification accuracy, model parameter count, and training time.

The project was implemented using PyTorch in Google Colab.

---

## Objectives

The main objectives of this project are:

1. Implement four different CNN architectures.
2. Train the models on the CIFAR-10 dataset.
3. Compare their test accuracy.
4. Compare the number of trainable parameters.
5. Compare training time.
6. Analyze the accuracy-parameter trade-off.
7. Identify the most suitable architecture based on the experimental results.

---

## Dataset

The project uses the CIFAR-10 dataset.

| Property | Details |
|---|---|
| Dataset | CIFAR-10 |
| Total Images | 60,000 |
| Training Images | 50,000 |
| Test Images | 10,000 |
| Number of Classes | 10 |
| Image Size | 32 × 32 |
| Image Type | RGB |

The dataset contains the following classes:

`airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck`

The dataset is loaded directly in the Google Colab notebooks and is not included in this repository.

---

## Technologies Used

- Python
- PyTorch
- Torchvision
- Google Colab
- Pandas
- Matplotlib

---

## Training Configuration

The models were trained using the following recorded configuration:

| Setting | Value |
|---|---|
| Framework | PyTorch |
| Optimizer | Adam |
| Learning Rate | 0.001 |
| Batch Size | 64 |
| Number of Epochs | 15 |
| Loss Function | CrossEntropyLoss |
| Execution Environment | Google Colab / CUDA GPU |

---

## CNN Architectures

### LeNet

LeNet is a lightweight CNN architecture with a small number of parameters. It provides a simple baseline for image classification.

### AlexNet

AlexNet is a deeper CNN architecture that uses convolutional layers, ReLU activations and dropout in its classifier.

### VGG-11

VGG-11 uses a deeper stacked convolutional architecture. In this experiment, it has the largest number of parameters among the four models.

### ResNet-18

ResNet-18 uses residual or skip connections, allowing information to pass through shortcut connections between layers.

---

## Experimental Results

The following are the actual recorded results from the project implementation.

| Model | Parameters | Test Accuracy | Training Time |
|---|---:|---:|---:|
| LeNet | 62,006 | 64.62% | 201.05 sec |
| AlexNet | 35,855,178 | 76.01% | 446.36 sec |
| VGG-11 | 128,807,306 | 10.00% | 947.16 sec |
| ResNet-18 | 11,181,642 | 76.75% | 478.17 sec |

---

## Results Analysis

### Accuracy

ResNet-18 achieved the highest recorded test accuracy of **76.75%**, followed by AlexNet with **76.01%**.

LeNet achieved **64.62%**.

VGG-11 achieved only **10.00%** in the recorded experiment, which is approximately the random-guess level for a 10-class dataset.

### Parameters

LeNet was the smallest model with only **62,006 parameters**.

VGG-11 had the largest parameter count with **128,807,306 parameters**.

ResNet-18 used **11,181,642 parameters**, substantially fewer than AlexNet and VGG-11.

### Training Time

LeNet had the shortest recorded training time at **201.05 seconds**.

VGG-11 required the longest recorded training time at **947.16 seconds**.

### Accuracy-Parameter Trade-off

ResNet-18 achieved the highest accuracy while using substantially fewer parameters than AlexNet and VGG-11.

Therefore, based on this experiment, **ResNet-18 provides the best overall accuracy-parameter trade-off among the four tested architectures**.

LeNet remains the most lightweight and fastest model.

---

## Visualizations

The project includes the following comparison graphs:

1. Test Accuracy Comparison
2. Parameter Count Comparison
3. Training Time Comparison
4. Accuracy vs Parameter Trade-off

These graphs are available in the `charts/` folder.

---

## Repository Structure

```text
cnn-architecture-comparison/
│
├── README.md
│
├── notebooks/
│   ├── Person1_LeNet_AlexNet.ipynb
│   ├── Person2_VGG11_ResNet18.ipynb
│   └── Person3_Evaluation_Analysis.ipynb
│
├── results/
│   └── results_table.csv
│
├── charts/
│   ├── accuracy_comparison.png
│   ├── parameter_comparison.png
│   ├── training_time_comparison.png
│   └── accuracy_vs_parameters.png
│
├── report/
│   └── CNN_Architecture_Comparison_Report.pdf
│
└── presentation/

    └── CNN_Architecture_Comparison_Presentation.pptx


How to Run

The project notebooks are designed for Google Colab.

Steps
Open the required .ipynb file from the notebooks/ folder.
Open it in Google Colab.
Select a GPU runtime if available.
Run the cells sequentially.
The CIFAR-10 dataset will be downloaded automatically.
Training and evaluation results will be displayed in the notebook.

Conclusion

The experiment demonstrates that a larger CNN does not necessarily provide better performance.

LeNet was the smallest and fastest architecture.

AlexNet achieved higher accuracy but required many more parameters.

VGG-11 had the largest parameter count and longest training time, but achieved only 10.00% test accuracy in the recorded experiment.

ResNet-18 achieved the highest test accuracy of 76.75% with 11,181,642 parameters.

Based on the recorded experimental results, ResNet-18 provides the most favorable overall balance between accuracy and parameter count among the four tested architectures.

Future Scope

Future improvements may include:

Training for more epochs.
Hyperparameter tuning.
Data augmentation.
Learning-rate scheduling.
Proper validation-based model selection.
Investigating the low VGG-11 performance.
Testing additional CNN architectures.
Comparing lightweight architectures such as MobileNet.
Model pruning and quantization.
Measuring inference time and memory usage.
Project Deliverables

This repository contains:

Source notebooks
Experimental results
Comparison charts
Final project report

Note
The results reported in this repository are the actual recorded results from the project implementation. They should not be interpreted as universal performance rankings for these architectures on all datasets or training configurations.
