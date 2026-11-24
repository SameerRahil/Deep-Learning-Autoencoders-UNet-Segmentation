# Autoencoders to U-Net: Reconstruction, Denoising and Liver Tumor Segmentation

Project 2 of CS 437 Deep Learning, LUMS, Spring 2026. The first notebook studies how much information autoencoders keep; the second builds up from autoencoders to a U-Net that segments liver tumors in CT scans.

## Parts

| Part | Notebook | What it covers |
| --- | --- | --- |
| 1. Linear and convolutional autoencoders | [`1_linear_and_conv_autoencoders.ipynb`](notebooks/1_linear_and_conv_autoencoders.ipynb) ([nbviewer](https://nbviewer.org/github/SameerRahil/Deep-Learning-Autoencoders-UNet-Segmentation/blob/main/notebooks/1_linear_and_conv_autoencoders.ipynb)) | Linear (LAE) and convolutional (CAE) autoencoders for reconstruction on CIFAR-10 and MNIST and for denoising noisy MNIST. Reconstructions are fed to a classifier to measure how much useful information survives. Results are saved to [`results/overall_results.json`](results/overall_results.json). |
| 2. Autoencoders to U-Net (LiTS17) | [`2_autoencoders_to_unet_lits.ipynb`](notebooks/2_autoencoders_to_unet_lits.ipynb) ([nbviewer](https://nbviewer.org/github/SameerRahil/Deep-Learning-Autoencoders-UNet-Segmentation/blob/main/notebooks/2_autoencoders_to_unet_lits.ipynb)) | CT windowing and overlays, tumor slice selection, a slice dataset, convolutional and denoising autoencoder baselines, a segmentation autoencoder trained with cross-entropy and Dice, a U-Net with skip connections, and NIfTI export for viewing predictions in MITK. |

If GitHub cannot display a notebook, the nbviewer link next to it opens the same file.

## Results

**Classifier accuracy on reconstructed images** (higher means the autoencoder kept more of what matters):

| Input to the classifier | CIFAR-10 | MNIST (denoising) |
| --- | --- | --- |
| Original images | 74.08% | 99.17% |
| Linear autoencoder output | 28.30% | 92.64% |
| Convolutional autoencoder output | 49.90% | 97.46% |

**Liver tumor segmentation (LiTS17, validation Dice):** segmentation autoencoder 0.68 after 10 epochs; U-Net with skip connections 0.78 after 15 epochs.

## Stack

Python, PyTorch, NumPy, nibabel, Matplotlib, kagglehub.

## Running the notebooks

The notebooks were run on Google Colab or Kaggle with a GPU. Open one in Colab, set the runtime to GPU, and run the cells in order. MNIST and CIFAR-10 download through torchvision. LiTS17 comes from a Kaggle mirror through kagglehub, so you need a Kaggle account.

## About

Coursework for CS 437 Deep Learning, LUMS, Spring 2026, shared as part of my portfolio (course grade: A+). The notebooks keep the original handout text and my implementations, answers and outputs.

If you are taking this course, please do your own work.

**Sameer Rahil**, BS Computer Science, LUMS. More projects at [github.com/SameerRahil](https://github.com/SameerRahil).
