# The IEEE International Conference on Multimedia & Expo (ICME) 2026 Low-Precision Large Language Model Efficient Computation Challenge

This challenge is an official challenge track of the  
**IEEE International Conference on Multimedia & Expo (ICME) 2026**.

> **Note:** This page provides a brief overview of the challenge.  
> The **complete project description, technical details, rules, and all related files** are available in the official **GitCode repository**，[Low-precision LLM Efficient Computation Challenge – GitCode](https://gitcode.com/GCC-GlobalComputingConsortium/Low-precision_Large_Language_Model_Efficient_Computation_Challenge).

---

> **Latest release:** v1.2 (2026-01-26)  
> If you are seeing an older version, please hard refresh the page (Ctrl/Cmd + Shift + R).
> <!-- rebuild -->
---

## 🔹 Quick Start

- 💻 **Complete Project Repository (GitCode):**  
  [Low-precision LLM Efficient Computation Challenge – GitCode](https://gitcode.com/GCC-GlobalComputingConsortium/Low-precision_Large_Language_Model_Efficient_Computation_Challenge)

- 📄 **Challenge Description (PDF):**  
  [Download the Challenge Description (PDF)](assets/ICME_challenge_2026-01-23.pdf)

- 📝 **Registration Form:**  
  [Register for the Challenge](https://forms.gle/eFQW3FXuPB8bVjWX9)


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
👉 [Download the Challenge Description (PDF)](assets/ICME_challenge_2026-01-23.pdf)

---

## 2. Participation and Registration

🔗 **Registration Form:**  
https://forms.gle/eFQW3FXuPB8bVjWX9

For registration inquiries:  
📧 zhaoy21@tsinghua.org.cn

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

| Phase | Description | Date |
|------|-------------|------|
| Registration | Challenge registration period | Feb 10, 2026 – Apr 10, 2026 |
| Submission | Result submission window | Mar 15, 2026 – Apr 30, 2026 |
| Review | Review & reproducibility verification | May 1, 2026 – May 12, 2026 |
| Announcement | Final results announcement | **May 15, 2026** |

---

## 6. Submission

📧 **Submission Email:**  zhaoy21@tsinghua.org.cn

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

## 8. Awards

The challenge includes **two independent sub-challenges**, each evaluated separately.  
For **each sub-challenge**, the following awards will be granted:

- **First Prize**
- **Second Prize**
- **Third Prize**

Each team may participate in **only one sub-challenge**.  
Teams submitting to multiple sub-challenges will be **disqualified from all rankings and awards**.

In addition to the ranked prizes, the organizing committee will also present the following **special awards**:

- **Technical Innovation Award**
- **Engineering Excellence Award**
- **Application Potential Award**
- **Judges’ Special Award**

All award-winning submissions are required to **publicly release their source code and related technical materials** as a condition for receiving any award.

The award announcement schedule follows the timeline specified in **5. Important Dates**.

---

## 9. Official Contact

📧 zhaoy21@tsinghua.org.cn

---

*Note: This challenge is jointly released by **Global Computing Consortium  (GCC)** and **Dr. Wenbo Ding from Tsinghua University**. Baseline code, simulation tools, datasets, and evaluation
scripts will be released in stages. Please watch the GitCode repository for updates.*
