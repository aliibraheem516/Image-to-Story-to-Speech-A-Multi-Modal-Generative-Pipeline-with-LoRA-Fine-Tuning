# Image-to-Story-to-Speech: A Multi-Modal Generative Pipeline with LoRA Fine-Tuning

This project demonstrates a multi-modal AI pipeline that converts an image into a spoken story. It combines **image captioning**, **story generation**, and **text-to-speech synthesis** to create an end-to-end workflow. The language model is fine-tuned using **LoRA (Low-Rank Adaptation)** for efficient and lightweight training.

---

## Table of Contents
1. [Overview](#overview)
2. [Features](#features)
3. [Workflow](#workflow)
4. [Usage](#usage)
5. [Results](#results)
6. [Dependencies](#dependencies)
7. [License](#license)

---

## Overview

The project takes an image as input, generates a textual description using an image captioning model, creates a short story based on the caption using a fine-tuned language model, and finally converts the story into speech using a text-to-speech model. The pipeline integrates computer vision, natural language processing, and speech synthesis.

---

## Features

- **Image Captioning**: Generate a textual description of an image using a pre-trained model (`Salesforce/blip-image-captioning-base`).
- **Story Generation**: Fine-tune a language model (`Qwen/Qwen2.5-1.5B-Instruct`) using **LoRA** to generate short stories from the image caption.
- **Text-to-Speech**: Convert the generated story into an audio file using a text-to-speech model (`facebook/mms-tts-eng`).
- **Efficient Fine-Tuning**: Use **LoRA (Low-Rank Adaptation)** to fine-tune the language model with minimal computational resources.
- **End-to-End Pipeline**: Seamlessly integrate image processing, text generation, and speech synthesis.

---

## Workflow

### Step 1: Image Captioning
- Use the `transformers` pipeline to load a pre-trained image captioning model (`Salesforce/blip-image-captioning-base`).
- Provide an image (e.g., `profile.jpeg`) to generate a textual description.

### Step 2: Story Generation
- Load a pre-trained language model (`Qwen/Qwen2.5-1.5B-Instruct`) and tokenizer.
- Fine-tune the model using **LoRA** on a story generation dataset (`story_generation_dataset.json`).
- Generate a short story from the image caption using the fine-tuned model.

### Step 3: Text-to-Speech
- Use a text-to-speech model (`facebook/mms-tts-eng`) to convert the generated story into speech.
- Save the output as an MP3 file (`output.mp3`).

---

## Usage

1. Place your image in the working directory (e.g., `profile.jpeg`).
2. Run the Jupyter notebook (`code.ipynb`) step by step:
   - Generate the image caption.
   - Fine-tune the model and generate the story.
   - Convert the story to speech and save the audio file.

3. The final output will be an MP3 file (`output.mp3`) containing the narrated story.

---

## Results

- **Image Caption**: A textual description of the input image.
- **Generated Story**: A short, coherent story based on the image caption.
- **Audio Output**: An MP3 file narrating the generated story.

---

## Dependencies

- Python 3.7+
- Libraries:
  - `datasets`
  - `transformers`
  - `pydub`
  - `peft`
  - `bitsandbytes`
  - `torch` (with CUDA support)

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

- Hugging Face for pre-trained models and libraries.
- LoRA for efficient fine-tuning.
- Google Colab for GPU support.

---
