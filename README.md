# 🌌 Wan 2.1 — Text-to-Video AI Generator

> Generate videos straight from natural language prompts using Alibaba’s cutting-edge **Wan 2.1 T2V 1.3B** model.

[![License](https://img.shields.io/badge/license-educational-blue.svg)](#license)
[![Python](https://img.shields.io/badge/python-3.8+-blue.svg)](#)
[![Torch](https://img.shields.io/badge/powered_by-pytorch-red.svg)](#)

---

## ✨ Why This Repo?

This project was built to **explore the future of AI-driven media** using open-source tools. With **Wan 2.1**, you can generate videos from just a text description — unlocking potential in:

- 🎨 Creative storytelling  
- 🧪 Research workflows  
- 🎞️ Automated content generation

> 🖥️ Runs even on modest hardware like **RTX 3050 + i5 13th Gen + Windows 11**  
> 🔋 Supports offloading and memory-efficient execution

---

## 🚀 Features

✅ Text-to-Video Generation  
✅ Pretrained 1.3B model (UMT5 + VAE)  
✅ Offloading for low VRAM GPUs  
✅ Torch-based, modular architecture  
✅ Windows/Linux friendly setup  

---

## 📦 Installation

### 1️⃣ Clone the repo
```bash
git clone https://github.com/Theubaa/Wan-2.1.git
cd Wan-2.1


2️⃣ (Optional) Set up a virtual environment
bash

venv\Scripts\activate  # On Windows
3️⃣ Install required packages

pip install torch torchvision einops transformers ftfy accelerate easydict
🎬 Quick Start

python generate.py `
  --task t2v-1.3B `
  --size 832*480 `
  --ckpt_dir ./Wan2.1-T2V-1.3B `
  --prompt "Two anthropomorphic cats in comfy boxing gear and bright gloves fight intensely on a spotlighted stage." `
  --offload_model True `
  --t5_cpu `
  --sample_shift 8 `
  --sample_guide_scale 6
💡 PowerShell users: Use backticks (`) for line breaks
💡 Bash users: Use \ instead

📁 Checkpoint Files
Create a folder named Wan2.1-T2V-1.3B and place the following inside:

models_t5_umt5-xxl-enc-bf16.pth

Wan2.1_VAE.pth

🔐 These files are not included in this repo. You must obtain them directly from the authors or release site.

⚙️ Optional Flags
Flag	Description
--sample_steps	Number of denoising steps (default: 50)
--sample_shift	Time shift for style diversity
--sample_guide_scale	Guidance strength for prompt adherence

⚠️ Notes
🕒 Generation may take 2–5 minutes depending on GPU

🧠 Use --t5_cpu + --offload_model to reduce VRAM use

🔒 FlashAttention fallback is handled automatically

📄 License
This repository is provided for educational and experimental use only.
All model weights, research, and architecture are the property of Alibaba DAMO Academy.

🙌 Acknowledgements
🤖 Alibaba Wan Team

🔥 HuggingFace Transformers

🧠 PyTorch, Accelerate, TorchVision, Einops

Made with ❤️ by Theubaa
