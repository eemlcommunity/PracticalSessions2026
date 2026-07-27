# Multimodal Learning Tutorial — EEML 2026

A hands-on tutorial on **vision-language models**, where you build the pieces yourself.

There are 14 🧩 **TODO** blanks to fill in. A collapsible **Hint** cell sits just above each exercise, titled
with the TODO it unlocks, so you can unblock yourself without jumping to the answers.

**Part I** (Sections 1–4) builds a vision encoder from scratch and trains it three different ways.
**Part II** (Section 5) puts a real unified model — Janus-Pro-1B — through both generation and understanding.

> ⚠️ Needs a GPU — set **Runtime → Change runtime type → T4 GPU** before running.

## How to run

1. Open the **STUDENT** notebook in Colab — click the badge:

   [Open In Colab](https://colab.research.google.com/drive/1ssMvHtVdW4Mqfj8x2iMhKS-pn5q0DFB_?usp=sharing)
2. **Runtime → Change runtime type → T4 GPU.** Part I trains faster on a GPU; Part II requires one and asserts it.
3. Run cells top to bottom. Fill in each `# TODO` when you reach it, opening the hint cells above it if you get stuck.

## Outline

### 1. Attention & Vision Transformers

The architecture everything else is built on.

- What a VLM is made of: vision encoder, language encoder, fusion, prediction head
- What a vision encoder is, and why we need one
- Turning an image into a sequence of patch tokens
- Positional embeddings
- 🧩 Scaled dot-product self-attention and the MLP block — **TODOs 1–4**
- 🧩 The full [ViT](https://arxiv.org/abs/2010.11929) forward pass — **TODOs 5–6**

### 2. Supervised learning

Train the ViT the familiar way: with labels.

- 🧩 The cross-entropy loss, from scratch — **TODO 7**
- The training loop on CIFAR-10
- Loading a pretrained ViT, and what the extra data buys you

### 3. Self-supervised learning: Masked Autoencoders

Learn representations with no labels at all — hide 75% of the image, then reconstruct it.

- 🧩 The reconstruction (MSE) loss — **TODO 8**
- 🧩 Randomly masking patches — **TODO 9**
- 🧩 The [MAE](https://arxiv.org/abs/2111.06377) encoder–decoder — **TODO 10**
- Reconstructions before and after training
- Reusing the pretrained MAE representation on a downstream task

### 4. Contrastive learning: CLIP

Supervise images with text instead of labels, and get a shared image–text embedding space.

- 🧩 The [CLIP](https://arxiv.org/abs/2103.00020) contrastive loss — **TODO 11**
- Pre-training at scale, and zero-shot transfer
- Choosing between supervised, self-supervised and contrastive — and why it isn't either/or

### 5. Unified Understanding and Generation Models

- Setup, loading [Janus-Pro-1B](https://huggingface.co/deepseek-community/Janus-Pro-1B), and its "decoupled" architecture
- Understanding 🖼️ → 📝: ask the model questions about an image
- 🧩 Generation 📝 → 🖼️, autoregressively over 576 discrete VQ tokens (no diffusion!): classifier-free guidance
  and temperature sampling — **TODOs 12–13**
- 🧩 Capstone (optional): make the model grade its own drawings, and show the score tracks guidance strength —
  **TODO 14**
- Bonus: interleaved create → critique → recreate, and "editing" through the text bottleneck
- Wrap-up

### Appendix

- Types of multimodal fusion: dual vs joint encoders, and hybrids
- Recommended reading
