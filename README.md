# Wan 2.1 - Text-to-Video AI Generator

👋 This repository was created to explore and experiment with **text-to-video generation** using the powerful **Wan 2.1 T2V 1.3B** model released by Alibaba. The goal is to **generate videos from natural language prompts** for use in AI research, media automation, and creative storytelling.

This repo serves as a clean and fully working wrapper to run the model locally on consumer-grade GPUs (like RTX 3050) with options to offload memory and run inference even on constrained hardware.

---

## 🚀 Features

- Generate short videos from just a text prompt (Text-to-Video)
- Pretrained 1.3B model (UMT5-based encoder + VAE decoder)
- Works with low VRAM GPUs using CPU offloading
- Torch-based implementation with customizable inference
- Tested on Windows 11, RTX 3050, i5 13th Gen CPU

---

## 📦 Installation

### 1. Clone the repo
```bash
git clone https://github.com/Theubaa/Wan-2.1.git
cd Wan-2.1
```

### 2. Set up a virtual environment (optional but recommended)
```bash
python -m venv venv
venv\Scripts\activate  # On Windows
```

### 3. Install dependencies
```bash
pip install torch torchvision einops transformers ftfy accelerate easydict
```

---

## 🎬 Usage Example

```powershell
python generate.py `
  --task t2v-1.3B `
  --size 832*480 `
  --ckpt_dir ./Wan2.1-T2V-1.3B `
  --prompt "Two anthropomorphic cats in comfy boxing gear and bright gloves fight intensely on a spotlighted stage." `
  --offload_model True `
  --t5_cpu `
  --sample_shift 8 `
  --sample_guide_scale 6
```

💡 PowerShell users: Use the backtick (`` ` ``) for line breaks.  
💡 Bash users: Replace backticks with `\`.

---

## 📁 Required Checkpoints

Place these inside a folder named `Wan2.1-T2V-1.3B`:

- `models_t5_umt5-xxl-enc-bf16.pth`
- `Wan2.1_VAE.pth`

> These are not provided in this repo. You'll need to download them from official sources or request them based on Alibaba's release terms.

---

## ⚙️ Optional Parameters

- `--sample_steps` → Number of inference steps (default: 50)
- `--sample_shift` → Time shift control for diversity
- `--sample_guide_scale` → Classifier-free guidance scale

---

## ⚠️ Notes

- Generation time may take several minutes on 6–8GB GPUs
- `--offload_model` and `--t5_cpu` help reduce GPU usage
- FlashAttention is disabled for compatibility by default

---

## 📄 License

This repository is for **educational and experimental use** only.  
Model and architecture rights belong to **Alibaba DAMO Academy**.

---

## 🙌 Credits

- [Alibaba Wan Team](https://damo.alibaba.com/) for the original model
- HuggingFace Transformers & Tokenizers
- PyTorch + Accelerate + TorchVision
