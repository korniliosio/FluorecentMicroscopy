# Virtual Fluorescence Microscopy Using Deep Learning: Predicting Cellular Structures from Label-Free Images

## Abstract

Fluorecent microscopy is a powerful tool for visualizing cellular structures and processes. However, conventional fluorescent imaging requires the use of fluorescent dyes or proteins, which can be invasive, constly and may alter cellular behavior. In this project, we explore the use of deep learning techniques to predict fluorescent images from label-free bright-field microscopy images, enabling non-invasive visualization of cellular structures.

Using the Light My Cells dataset, we aim to develop an image-to-image translation model that can accurately predict fluorescent images from label-free images. The model will learn to predict the distribution and intensity of fluorescent signals based on the features present in the label-free images, initially forcusing on cell nuclei and expanding as necessary. Its performance will be evaluated by comparing generated images with experimentally acquired fluorescence images using metrics such as Mean Absolute Error (MAE), Structural Similarity Index (SSIM), and biologically relevant measures of cellular structure reconstruction.

The project ultimately seeks to explore the potential and limitations of virtual fluorescence microscopy as a computational alternative to conventional fluorescence imaging.

## Dataset

The project will use **Light My Cells**, a publicly available microscopy dataset developed through the France-BioImaging initiative and hosted in the BioImage Archive (S-BIAD1047).

The dataset was designed for training and evaluating machine learning models that predict fluorescence microscopy images from label-free transmitted-light images.

| Characteristic | Description |
|---|---|
| **Dataset** | Light My Cells |
| **Total images** | 56,984 2D microscopy images |
| **Acquisition sets** | 2,574 |
| **Independent studies** | 30 |
| **Input modalities** | Bright-field (BF), Phase Contrast (PC), Differential Interference Contrast (DIC) |
| **Fluorescence targets** | Nuclei, Mitochondria, Tubulin, Actin |
| **Image format** | OME-TIFF |
| **Source** | BioImage Archive — S-BIAD1047 |

The dataset contains microscopy images of biological samples acquired using different imaging techniques. Each usable training example consists of two spatially corresponding images:

- **Input (X):** A label-free transmitted-light microscopy image showing cellular morphology.
- **Target (Y):** An experimentally acquired fluorescence image of the same field of view, highlighting a specific cellular structure.

For the initial implementation, we will focus on **bright-field images as inputs and nuclear fluorescence images as targets**.

This selection provides a well-defined image-to-image prediction task, while keeping the computational requirements manageable.

If time and resources permit, we may extend the approach to predicting mitochondrial fluorescence.

**Dataset source:** https://www.ebi.ac.uk/biostudies/BioImages/studies/S-BIAD1047

## Challenges explored

The project presents several challenges related to both the biological characteristics of microscopy images and the limitations of deep learning models.

- **Biological accuracy:** Generating visually realistic fluorescence images does not necessarily guarantee biological correctness. Predicted structures must accurately reflect the underlying cellular morphology and fluorescence distribution.

- **Information limitations:** Certain fluorescent signals may represent molecular information that is not directly observable in bright-field images, making exact reconstruction inherently difficult.

- **Dataset variability:** Differences in cell types, imaging equipment, illumination, and experimental conditions may affect model generalization to unseen samples.

- **Evaluation:** Traditional image similarity metrics, such as MAE and SSIM, may not adequately capture biological accuracy. Additional structure-based evaluation methods may be necessary.

- **Computational constraints:** Training image-to-image deep learning models can be computationally demanding, requiring a balance between model complexity, image resolution, and available hardware.