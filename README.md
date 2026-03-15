# Stable Diffusion 1.5 + LoRA Fine-tuning on CUB-200 Dataset

## Overview

This project demonstrates fine-tuning Stable Diffusion 1.5 using Low-Rank Adaptation (LoRA) on the CUB-200-2011 dataset for high-quality text-to-image generation of bird species. The fine-tuned model specializes in generating accurate and detailed images of 200 different bird species while retaining the general capabilities of the base Stable Diffusion model.

## Features

- **Fine-tuned Stable Diffusion 1.5**: Uses LoRA to adapt the model for bird species generation
- **CUB-200-2011 Dataset**: Trained on 11,788 photos of 200 bird species
- **Efficient Training**: Only ~3-5 million trainable parameters (0.4% of total model)
- **High-Quality Outputs**: Generates museum-quality, species-accurate bird images
- **Lightweight Adapter**: Final LoRA weights are approximately 100MB

## Dataset

The CUB-200-2011 dataset contains:
- 11,788 images of 200 bird species
- Detailed annotations including species names, bird parts, and bounding boxes
- Perfect for training AI models to recognize and generate bird images

Dataset source: [Kaggle CUB-200-2011](https://www.kaggle.com/datasets/wenewone/cub2002011)

## Model Architecture

- **Base Model**: Stable Diffusion 1.5 (runwayml/stable-diffusion-v1-5)
- **Fine-tuning Method**: LoRA (Low-Rank Adaptation)
- **Rank**: 16
- **Trainable Parameters**: ~3-5 million
- **Training Steps**: 4000-6000 steps

## Requirements

- Python 3.8+
- Jupyter Notebook
- CUDA-compatible GPU (recommended for training)
- Required Python packages (see notebook for installation)

## Installation

1. Clone or download this repository
2. Install required dependencies by running the installation cells in the notebook
3. Download the CUB-200-2011 dataset from Kaggle

## Usage

### Training

1. Open `tti-code-final.ipynb` in Jupyter Notebook
2. Follow the cells sequentially to:
   - Install dependencies
   - Load and preprocess the dataset
   - Set up the LoRA configuration
   - Train the model (requires GPU)

### Inference

1. Load the trained LoRA weights from the `weights/` directory
2. Use the inference cells in the notebook to generate images from text prompts
3. Generated images will be saved in the `CPU generated images/` directory

## Project Structure

```
├── tti-code-final.ipynb          # Main notebook with training and inference code
├── weights/                      # Trained LoRA weights and model card
│   ├── adapter_config.json
│   ├── adapter_model.safetensors
│   └── README.md
├── CPU generated images/         # Generated images from inference
└── README.md                     # This file
```

## Results

The fine-tuned model can generate highly accurate images of bird species based on text descriptions. Examples include specific bird species with correct anatomical features, colors, and poses.

## License

[Specify license if applicable]

## Acknowledgments

- Stable Diffusion team for the base model
- CUB-200-2011 dataset creators
- Hugging Face PEFT library for LoRA implementation