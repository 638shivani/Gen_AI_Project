# Text-to-Video Generation Using Generative AI

## Project Overview

Text-to-Video Generation is a Generative AI project that converts natural language text prompts into short video clips using a pre-trained diffusion model.

The project is developed using Python in Google Colab. It uses the DAMO Text-to-Video Synthesis (MS-1.7B) model with LoRA fine-tuning to adapt the model efficiently.

## Objective

The main objective is to generate short, realistic video clips automatically from user-provided text descriptions.

## Technologies Used

- Python
- Google Colab
- PyTorch
- Hugging Face Diffusers
- DAMO Text-to-Video Synthesis (MS-1.7B)
- Transformers
- PEFT (Parameter-Efficient Fine-Tuning)
- LoRA (Low-Rank Adaptation)
- ImageIO

## Model Architecture

**DAMO Text-to-Video Synthesis (MS-1.7B)**

- Pre-trained diffusion model with 1.7 billion parameters.
- Generates video frames based on text descriptions.
- Uses a text encoder to convert prompts into embeddings.
- Uses a diffusion process to generate video frames.

## Working Process

1. **Text Prompt Input:** The user provides a natural language description of the desired video.

2. **Text Encoding:** The text encoder converts the input prompt into meaningful embeddings.

3. **Pre-trained Diffusion Model:** The DAMO Text-to-Video model processes the text embeddings and generates video frames.

4. **LoRA Fine-Tuning:** LoRA is applied to the UNet using a low-rank adaptation configuration to train additional parameters while keeping the original model weights frozen.

5. **Video Generation:** The model generates a sequence of frames based on the given prompt.

6. **Video Conversion:** ImageIO combines the generated frames into an MP4 video.

## LoRA Configuration

The project uses the following LoRA parameters:

- Rank (r): 2
- LoRA Alpha: 8
- Target Modules: to_q, to_k
- Dropout: 0.05
- Learning Rate: 0.0001
- Epochs: 2

LoRA reduces the number of trainable parameters by keeping the original pre-trained model weights frozen and training only additional adapter parameters.

## Example Input

"A cinematic video of a dog running in a green park, realistic motion, detailed fur, soft lighting, high detail, smooth motion, dynamic."

## Output

The model generates a short video of a dog running in a green park.

## Project Implementation

The project was implemented in Google Colab using a pre-trained Hugging Face diffusion pipeline.

The generated video contains 20 frames and is saved in MP4 format using ImageIO at 4 FPS.

## Repository Structure

```text
Text-to-Video-Generation-Using-Generative-AI/
│
├── text_to_video_fine_tuning.ipynb
├── README.md
└── finetuned_video.mp4
```

## How to Run

1. Clone or download this repository.
2. Open the Jupyter Notebook in Google Colab.
3. Install the required Python libraries.
4. Load the pre-trained DAMO Text-to-Video model.
5. Configure and apply LoRA.
6. Run the notebook cells.
7. Provide your own text prompt.
8. Generate and save the video.

## Applications

- AI-generated animations
- Text-based video creation
- Creative content generation
- Educational video generation
- Automated video production

## Conclusion

This project demonstrates how Generative AI and diffusion models can transform natural language descriptions into video content. By integrating the DAMO Text-to-Video model with LoRA, the project explores parameter-efficient model adaptation and automated video generation.
