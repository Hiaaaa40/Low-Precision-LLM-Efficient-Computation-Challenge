# IEEE ICME 2026 Challenge  
## Low-Precision Large Language Model Efficient Computation Challenge

This challenge is an official challenge track of the  
**IEEE International Conference on Multimedia & Expo (ICME) 2026**.

---

## 🔹 Quick Start

- 📄 **Challenge Description (PDF):** [Download](../assets/ICME_challenge.pdf)
- 📝 **Registration Form:** https://forms.gle/eFQW3FXuPB8bVjWX9
- 💻 **Code, Tools, Datasets (GitCode Repository):** https://gitcode.com/your-username/your-repo-name
- 📦 **Download Code (ZIP from GitCode):** https://gitcode.com/your-username/your-repo-name/archive/refs/heads/main.zip

---

## 1. Challenge Background

With the rapid growth of large-scale language and multimodal models,
computational cost and energy efficiency have become major bottlenecks.
Low-precision numerical formats such as **HiFloat8, HiFloat4, and MXFP4** offer promising opportunities to significantly reduce memory footprint
and computation cost while maintaining model accuracy.

This challenge aims to promote **algorithmic and system-level innovations**
in low-precision training and inference for large models, with a strong
emphasis on **reproducibility** and **practical deployment**.

The challenge consists of **two independent sub-challenges**:
- **Sub-Challenge 1: W4A4 Quantization for Inference**
- **Sub-Challenge 2: W8A8 Quantization for Training**

Each participant or team may **choose to participate in only one sub-challenge**.
Submissions across multiple sub-challenges are not allowed.

📄 Full technical details are available in the challenge description PDF:  
👉 [Download the Challenge Description](../assets/ICME_challenge.pdf)

---

## 2. Participation and Registration

🔗 **Registration Form:**  
https://forms.gle/eFQW3FXuPB8bVjWX9

For registration inquiries:  
📧 icme_challenge_registration@your-domain.com

---

## 3. Sub-Challenges

### Sub-Challenge 1: W4A4 Quantization for Inference
- Supported formats: **HiFloat4 / MXFP4**
- Reference model: **Qwen3-32B**
- Requirement: average accuracy degradation < **0.5%** compared with FP16

### Sub-Challenge 2: W8A8 Quantization for Training
- Supported format: **HiFloat8**
- Test model: **Wan2.1**
- Requirement: accuracy degradation < **0.5%**

---

## 4. Evaluation Metrics

**Objective (60%)**
- Loss (30%)
- Inception model / FID (30%)

**Subjective (40%)**
- University volunteer scoring (40%)
  - Authenticity (20%)
  - Clarity (20%)

---

## 5. Important Dates

### 📝 Phase 1 — Registration
📅 Jan 30, 2026 – Mar 10, 2026

### 📤 Phase 2 — Submission
📅 Feb 10, 2026 – Mar 15, 2026

### 🔍 Phase 3 — Review
📅 Mar 16, 2026 – Mar 29, 2026

### 📢 Phase 4 — Announcement
📅 Mar 30, 2026

---

## 6. Submission

📧 **Submission Email:**  
submission_icme_challenge@your-domain.com

Each submission must be sent as a single archive (`.zip` / `.tar.gz`) and include:
- Quantized model weights (`.pt` / `.ckpt` / equivalent)
- Source code (training and/or inference)
- Technical report (**PDF**)
- Reproducibility scripts + instructions

---

## 7. Code, Tools, and Datasets

All engineering materials (baseline code, simulation tools, datasets, evaluation scripts)
will be maintained in the **GitCode repository**:

👉 https://gitcode.com/your-username/your-repo-name

---

## 8. Official Contact

📧 icme_challenge@your-domain.com

---

*Note: This challenge is jointly released by **Huawei Technologies Co., Ltd.** and
**Tsinghua University**. Baseline code, simulation tools, datasets, and evaluation
scripts will be released in stages. Please watch the GitCode repository for updates.*