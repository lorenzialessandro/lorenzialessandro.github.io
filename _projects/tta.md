---
layout: page
title: TTA for Image Classification
description: Enhancing image classifiers with test-time adaptation techniques
img: assets/img/TPT.png
importance: 1
category: research
related_publications: false
---

This project explores **Test Time Adaptation (TTA)** methods to optimize image classifier performance during inference. Unlike traditional fine-tuning that requires extensive computational resources and labeled datasets, TTA adjusts models dynamically at test time, making it an efficient alternative for real-world applications.

---

## Key Objectives
1. **Dynamic Model Adaptation**: Enable real-time model improvements during inference without retraining.
2. **Innovative Augmentation Techniques**: Evaluate and develop cutting-edge image augmentation strategies to improve generalization.
3. **Context-Aware Prompt Engineering**: Refine zero-shot classification prompts to improve their alignment with input data.
4. **Comprehensive Evaluation**: Benchmark proposed methods against industry-standard datasets like ImageNet-A.

---

## Background and Motivation
### The Challenge of Fine-Tuning
Traditional fine-tuning approaches, while effective, often require:
- Extensive computational resources for retraining large-scale models like CLIP.
- Access to large, labeled datasets that may not be feasible in many scenarios.

### The TTA Advantage
TTA offers a lightweight and adaptable alternative, dynamically improving model performance during inference. This is particularly valuable for deploying models in resource-constrained environments or handling unseen data distributions.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/TPT.png" title="TTA Workflow Overview" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

---

## Project Contributions

### Task 1: Image Augmentation
#### Objective:
Enhance TTA performance through advanced image augmentation techniques.

#### Techniques Explored:
1. **PreAugment**: Baseline method applying straightforward augmentations.  
2. **AugMix**: Combines multiple augmentations to improve robustness against distribution shifts.  
3. **AutoAugment**: Learns augmentation policies optimized for the dataset.  
4. **DiffusionAugment**: Leverages generative diffusion models to synthesize diverse augmentations.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/augmentations.png" title="Augmentations  Workflow Overview" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

#### Results:
Augmentations significantly improved the model's ability to generalize to out-of-distribution data, as seen on ImageNet-A benchmarks.

| Augmentation Technique | Avg Accuracy (%) |
|-------------------------|------------------|
| PreAugment              | 27.51           |
| AugMix                  | 28.80           |
| AutoAugment             | 30.36           |
| DiffusionAugment        | See notebook    |


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/augmentations_result_1.png" title="PreAugment Results" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/augmentations_result_2.png" title="AugMix Results" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

---

### Task 2: Prompt Engineering
#### Objective:
Refine prompt templates for zero-shot classification in CLIP to enhance model alignment with input data.

#### Approach:
- **Baseline Prompts**: Standard templates like “a photo of a {label}.”  
- **Dynamic Prompts**: Generated contextually using an image captioning system, creating prompts tailored to the specific content of the image.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/image_captioning_schema.png" title="Prompt Engineering Results" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


#### Results:
Dynamic prompts showed potential for better contextual alignment but slightly underperformed compared to the baseline in accuracy.

| Method    | Avg Loss | Avg Accuracy (%) |
|-----------|----------|------------------|
| Baseline  | -        | 47.87           |
| Dynamic   | 2.5711   | 42.13           |


---

## Technical Highlights
1. **Backbone Model**: Leveraged OpenAI’s **Contrastive Language–Image Pretraining (CLIP)** for its zero-shot classification capabilities.
2. **Augmentation Design**: Introduced novel augmentation pipelines to enhance model robustness.
3. **Evaluation Framework**: Conducted rigorous testing on challenging datasets, with insights documented in the project's [notebook](https://github.com/LuCazzola/TTA_DL-Project/blob/main/notebook.ipynb).

---

## Results and Achievements
1. Developed and benchmarked advanced augmentation techniques, with **AutoAugment** achieving the best performance.
2. Demonstrated the potential of prompt engineering for improving zero-shot classification.
3. Highlighted areas for future work, including better dynamic prompt generation and augmentation fine-tuning.

---

## Resources

<div class="repositories">
  {% include repository/repo.liquid repository="LuCazzola/TTA_DL-Project" %}
</div>

- **Code Repository**: [GitHub Repository](https://github.com/LuCazzola/TTA_DL-Project)  
- **Additional Details**: [Project Page](https://www.lucazzola.it/TTA.html)

