# 🌀 Reproducing *Diffusion Priors as Plug-and-Play Models* on MNIST
Denoising diffusion probabilistic models(DDPMs) have emerged as powerful generative models capable of modeling complex data distributions.
Traditionally, DDPMs are retrained as stand-alone generators for each task. To overcome this limitation, a plug-and-play framework using pretrained DDPMs as conditional priors was introduced, enabling controllable generation through auxiliary differentiable

This is a reproduction project based on the NeurIPS 2022 paper:  
**[Diffusion Models as Plug-and-Play Priors](https://proceedings.neurips.cc/paper_files/paper/2022/hash/5e6cec2a9520708381fe520246018e8b-Abstract-Conference.html)**  
🔗 Original implementation: [AlexGraikos/diffusion_priors](https://github.com/AlexGraikos/diffusion_priors)

---

## 📌 Paper Summary

The original paper proposes a novel method for **text-to-image generation** using **diffusion models as priors** in CLIP latent space. Instead of a fixed Gaussian prior, they use a **learned diffusion prior**, enabling:

- Flexible, multimodal generation
- High-quality image synthesis
- Strong alignment with textual prompts

---

## 🧪 Reproduction Scope

This project reproduces only the **inference** aspect of the method, using a simplified dataset (MNIST). The goals are:

- ✅ To verify whether pretrained DDPMs can be guided via plug-and-play constraints
- ✅ To demonstrate controllability without retraining
  
Instead of text prompts, we use **digit labels** (0–9), and instead of CLIP space, we work directly in the image space.

---

## 🔧 What This Project Does

- 🧠 Uses a **pretrained U-Net DDPM**
- 🕹️ Applies a **horizontal dissimilarity loss** to steer image generation
- 🔄 **Only optimizes the input noise vector** (model weights are frozen)
- 🎯 Performs **plug-and-play inference** on MNIST digits

---

# Conclusion
This study shows that pretrained DDPMs can be guided with simple constraints for controllable generation without retraining, validated in lowdata settings like MNIST. For future work, this approach could be extended to more complex or high-dimensional
datasets used in the original study, such as FFHQ or TSP or applied to real-world scenarios requiring structure-aware sampling in limiteddata environments.

