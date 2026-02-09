# The IEEE International Conference on Multimedia & Expo (ICME) 2026 Large Language Model Low-Precision Efficient Computation Challenge

This challenge is an official challenge track of the  
**IEEE International Conference on Multimedia & Expo (ICME) 2026**.

> **Note:** This page provides a brief overview of the challenge.  
> The simulation tools, benchmarks, and related resources used in this challenge will be **released progressively**.  
> Please **follow this page for the latest updates and announcements**.

---



## 🔹 Quick Start

- 💻 **Complete Project Repository (GitCode):**  
  [Low-precision LLM Efficient Computation Challenge – GitCode](https://gitcode.com/GCC-GlobalComputingConsortium/Low-precision_Large_Language_Model_Efficient_Computation_Challenge)

- 📝 **Registration Form:**  
  [Register for the Challenge](https://forms.gle/eFQW3FXuPB8bVjWX9)

  [Alternative Registration Form](https://wj.qq.com/s2/25735334/aa1d/) (**Only use this link when you have trouble opening the first registration link.**)


---


## 1. Challenge Description

## Challenge Details
The challenge centers on **Text-to-Image** and **Text-to-Video** generation tasks. This challenge establishes two primary research directions focusing on low-precision computation for Large Language Models(LLM).

**Direction A – Quantization-Aware Training (QAT).**  
Participants are required to use specified public datasets and pre-trained models to perform quantization-aware fine-tuning using the **HiFloat8 (HiF8)** numerical format [1]. The objective is to optimize model accuracy on downstream tasks while reducing training and computation costs.

**Direction B – Post-Training Quantization (PTQ).**  
Participants are required to apply inference-time quantization directly to pre-trained models to achieve model compression and acceleration. Low-precision formats such as **HiFloat4 (HiF4)** or **MXFP4** are used in this direction.

Based on these two research directions, **two sub-challenges** are set up. Each sub-challenge adheres to the unified principles stipulated in the *Evaluation Criteria* section.  

Each participant may **choose only one sub-challenge** to participate in.

---

### Sub-Challenge 1: W4A4 Quantization for Inference (HiF4 / MXFP4)

LLM inference faces significant deployment costs, which often constrain application proliferation. Quantizing the weights and activations of the linear layers in LLM effectively enhances inference performance.

This sub-challenge focuses on **4-bit weight and activation quantization (W4A4)**, restricted to either the **HiF4** or **MXFP4** numerical format. Participants are required to develop and apply quantization strategies to the open-source, state-of-the-art multimodal generative model **Wan 2.2**.
We will utilize the comprehensive OpenS2V-5M dataset and associated VBench[2] metrics to rank the score.

Participants are allowed to keep a limited number of Transformer blocks in high precision: **a maximum of 5 layers for MXFP4 and 2 layers for HiF4**.

#### Mini-Challenge for W4A4 Quantization

To promote and encourage research into low-precision data formats for quantization, a **Mini-Challenge** is established under this sub-challenge. This track will **not be formally ranked** against the main competition leaderboards. However, submissions to this track will be collectively eligible for consideration in the **Innovation Award** category.

The reference model for this Mini-Challenge is **Pangu-72B-2512**. Evaluation is conducted on standard downstream task datasets, using the **mean absolute percentage precision loss** as the final metric.

The objective is to achieve a **W4A4 inference average precision loss that is no more than 1% lower than the BF16 average baseline** on the following datasets:
- SuperGPQA  
- IF-Eval  
- AIME2025  
- LiveCodeBench V6  
- BFCL-V3  

**Only submissions that satisfy this objective will qualify for evaluation for the Innovation Award.**

---

### Sub-Challenge 2: W8A8 Quantization for Training (HiF8)

LLM training incurs high costs and lengthy iteration cycles, limiting rapid development. Quantizing the weights and activations of linear layers, and utilizing low-precision formats within attention layers, can effectively reduce data movement costs and accelerate training via low-precision computation. 

This task focuses on **8-bit weight** and **activation quantization** and **attention quantization**, strictly limited to the **HiF8 numerical format**. The test model is **Wan2.1 T2V-1.3B**.

Participants are encouraged to employ **delayed scaling strategies**[3] wherever possible to further minimize quantization overhead and accelerate training. 

The training methodology will be evaluated based on the video generation quality produced by the post-training model using the **BestWishYsh** dataset. 

The **Vbench** evaluation metric will be used, aiming for a precision loss of **less than 0.5%**.

Participants are allowed to keep a limited number of Transformer blocks in high precision: up to **5 layers** when training with HiF8.


#### Mini-Challenge for W8A8 Quantization

A Mini-Challenge is also established under this sub-challenge to encourage further exploration of low-precision training methodologies. This track will **not be formally ranked** on the main competition leaderboard, but eligible submissions will be considered for the **Innovation Award**.

The test model for this Mini-Challenge is **OpenPangu1B**. Participants are encouraged to employ delayed scaling strategies to reduce quantization overhead and accelerate training.

Evaluation will be conducted on a set of language model benchmarks, including but not limited to:
- MMLU  
- GSM8K  
- MATH500  
- HellaSwag  
- ARC  
- PIQA  

The target objectives are:
- Training loss **less than 0.5%**
- Precision loss **less than 1.0%**

**Only submissions that satisfy both objectives will qualify for evaluation for the Innovation Award.**


---

## 2. Participation and Registration

🔗 **Registration Form:**  
[Register for the Challenge](https://forms.gle/eFQW3FXuPB8bVjWX9)
[Alternative Registration Form](https://wj.qq.com/s2/25735334/aa1d/) (**Only use this link when you have trouble opening the first registration link.**)

For registration inquiries:  
📧 zhaoy21@tsinghua.org.cn

### Participation Terms

- **Award-winning teams** are required to **[open source](https://docs.google.com/document/d/12AIKYPwdNWGMnQunCr4xBw059Wh4HeRd/edit?usp=sharing&ouid=116450756627452381830&rtpof=true&sd=true) their final submissions on GitCode**, including all source code, relevant materials, and team information.
- Participants should **ensure that all necessary internal approvals** (e.g., institutional, corporate, or legal) are obtained **prior to participation**.
- **Participation in this challenge constitutes acceptance of all terms and conditions** set forth by the organizers.
- **Each participating team is permitted to register for and submit to only one sub-challenge.**  
  Multiple registrations or submissions across different sub-challenges by the same team are strictly prohibited.  
  If such behavior is identified, the **Organizing Committee reserves the right to disqualify the team from the challenge**.

---


## 3. Evaluation Criteria

All submissions will be evaluated based on the following primary criteria, totaling **100%**.  
The evaluation is divided into two main categories: **Objective Evaluation** and **Subjective Evaluation**.


### I. Objective Evaluation (70% of total score)

This section utilizes quantitative metrics to measure model performance.  
The final score is calculated based on comparative rankings. The score of objective evaluation is based on the **percentile ranking** in the following components.

#### 1. Baseline Requirement

This metric measures the discrepancy or degree of loss between the model output and the target data. A lower loss indicates superior and more accurate model performance.

**Requirement:**

- **Sub1**
  - The average loss in VBench accuracy metrics, when comparing the full-precision baseline model to the **MXFP4** quantized model, must be **less than 1%**.
  - The average loss in VBench accuracy metrics, when comparing the full-precision baseline model to the **HiF4** quantized model, must be **less than 0.5%**.

- **Sub2**
  - Precision loss of **less than 0.5%**.

Only submissions meeting this baseline requirement will proceed to the ranking phase.



#### 2. Quality & Diversity Metrics: VBench (50%)

- **VBench**:  
  A comprehensive benchmark for video generation performance.



#### 3. Quantitative Proportions (20%)

- Refers to the score derived from quantified performance rankings across specified benchmarks.


| Percentile Rank | Core Quality Score (Weight: 50%) | Quantitative Ratio Score (Weight: 20%) |
|-----------------|----------------------------------|----------------------------------------|
| Top 10%         | 50                               | 20                                     |
| Top 11% – 25%   | 45                               | 18                                     |
| Top 26% – 50%   | 35                               | 14                                     |
| Top 51% – 75%   | 20                               | 8                                      |
| Bottom 25%      | 10                               | 4                                      |
| Unqualified     | 0                                | 0                                      |


---

### II. Subjective Evaluation (30% of total score)

This section involves perceptual quality scoring by a panel of human judges, consisting of technical experts and university student volunteers.

#### 1. Realism and Clarity (20%)

- **Judges:**  
  University student volunteers.

- **Criteria:**  
  Volunteers will evaluate the visual realism of the generated content. The review will determine the extent to which the images or videos appear to be authentic captures rather than synthetic or AI-generated, based on semantic consistency, image quality, and dynamism.



#### 2. Innovation (10%)

- **Judges:**  
  Technical experts.

- **Criteria:**

  - **Algorithmic Originality (Weight: 40%)**  
    Evaluates the degree of innovation in the quantization methodology, focusing on whether novel concepts are introduced or substantial improvements are made to existing methods.

  - **HiFloat-Native Exploration (Weight: 30%)**  
    Examines whether the solution deeply leverages the unique characteristics of the HiFloat data format and includes quantization algorithms or computational workflows highly optimized for it.

  - **Generalizability (Weight: 20%)**  
    Assesses the transferability of the solution and its potential applicability to alternative model architectures or diverse task scenarios.

  - **Engineering Value (Weight: 10%)**  
    Focuses on code quality and standardization, reproducibility, and the ease of practical deployment.

---

## 4. Important Dates

| Phase | Description | Date |
|------|-------------|------|
| Registration | Challenge registration period | Feb 10, 2026 – Apr 10, 2026 |
| Submission | Result submission window | Mar 15, 2026 – Apr 20, 2026 **(Tentative)** |
| Review | Review & reproducibility verification | Apr 15, 2026 – Apr 23 2026 **(Tentative)** |
| Announcement | Final results announcement | Apr 27, 2026 **(Tentative)** |
| Camera-Ready Deadline | Final results announcement | **May 15, 2026** |

---

## 5. Submission

📧 **Submission Email:**  zhaoy21@tsinghua.org.cn

Each submission must be sent as a single archive (`.zip` / `.tar.gz`) and include:
- Quantized model weights (`.pt` / `.ckpt` / equivalent)
- Source code (training and/or inference)
- Technical report (**PDF**)
- Reproducibility scripts + instructions


> **Please note:**  
>  
> - Award-winning teams are required to open-source all source code, materials, and team information.  
> - The participating team acknowledges and agrees that the submitted materials are original and do not infringe on any third-party rights.  
>  
> For details, please refer to the **Awards** section.

---

## 6. Code, Tools, and Datasets

The **HiFloat8 (HiF8) simulation toolkit** used in this challenge has been officially released.

Participants are required to download and use the HiF8 simulation tools from the following repository:

👉 **[HiFloat8 Simulation Toolkit (GitHub)](https://github.com/global-computing-consortium/HiFloat8)**

Detailed deployment instructions, environment configuration, and usage examples are provided in the **README** file of the repository.

Please note that the simulation tools for **Sub-Challenge 1 (HiF4 / MXFP4)** will be released at a later stage.  
Participants are advised to follow this page for the latest updates.

---

## 7. Awards

Awards are established for this challenge to recognize both overall performance and technical innovation.

The **First, Second, and Third Prizes** are awarded **separately for each sub-challenge**, based on the **total evaluation score** within that sub-challenge.  
The **Innovation Awards** are evaluated **across all sub-challenges**, including Mini-Challenge submissions, and are judged solely on originality and breakthrough.

- **First Prize (Each Sub-Challenge):**  
  **$3,000** — Top 1 participant in each sub-challenge

- **Second Prize (Each Sub-Challenge):**  
  **$2,000** — Top 2 participant in each sub-challenge

- **Third Prize (Each Sub-Challenge):**  
  **$1,000** — Top 3 participant in each sub-challenge

- **Innovation Awards (Four places, cross-track):**  
  **$800** per award  
  Evaluated exclusively based on the **Innovation** criterion  
  *(Eligible submissions include all main-track and Mini-Challenge entries)*


> **Mandatory Open-Source Requirement**  
>  
> All award-winning teams are required to open-source their final submission, including source code, materials, and team information, on **GitCode**.  
>  
> This is a **mandatory condition** for receiving any award. Failure to comply within **7 working days** after the award announcement may result in **disqualification and revocation of the award**.  
>  
> Alternatively, teams may voluntarily **forfeit their awards** if they choose not to comply with the open-source requirement.

---

## 8. Official Contact

📧 zhaoy21@tsinghua.org.cn

---

## 9. Organizers

- **Qianlin Zhang from Global Computing Consortium (GCC)**

- **Dr. Wenbo Ding from Tsinghua University**

---

### References

[1] Luo Y., Zhang Z., Wu R., et al.  
**Ascend HiFloat8 Format for Deep Learning.**  
*arXiv preprint*, arXiv:2409.16626, 2024.

[2] Peng H., Wu K., Wei Y., et al.  
**FP8-LM: Training FP8 Large Language Models.**  
*arXiv preprint*, arXiv:2310.18313, 2023.

[3] Huang Z., He Y., Yu J., et al.  
**VBench: Comprehensive Benchmark Suite for Video Generative Models.**  
In *Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)*, 2024, pp. 21807–21818.


*Note: Baseline code, simulation tools, datasets, and evaluation
scripts will be released in stages. Please watch the GitCode repository for updates.*
