---
title: "XAI in Medical Imaging: 19 Methods, Limitations, and Future Scope"
description: "A comprehensive breakdown of current Explainable AI techniques, their clinical trade-offs, and the open research gaps we aim to tackle in our B.Tech minor project."
pubDate: 2026-06-12
readingTime: "12 min read"
tags:
  [
    "Explainable AI",
    "Medical Imaging",
    "Deep Learning",
    "Research",
    "Project Planning",
  ]
draft: false
---

As we move deeper into our B.Tech minor project on Medical Image Analysis, understanding the existing landscape of Explainable AI (XAI) is critical. Based on recent systemic reviews of the field, I have compiled a comprehensive breakdown of how 19 different XAI methods are currently being applied in medical imaging.

More importantly, this post explores the absolute "State-of-the-Art" techniques and outlines the massive, unsolved gaps in the field that our team can potentially target.

---

### 📊 Comprehensive Review of Current XAI Methods

Below is a tabular summary of how these 19 techniques perform in real-world clinical scenarios, the specific diseases they help diagnose, and their inherent architectural trade-offs.

<div class="relative overflow-x-auto shadow-md sm:rounded-lg my-8 border border-outline/10">
  <table class="w-full text-sm text-left text-on-surface-variant">
    <thead class="text-xs text-on-surface uppercase bg-surface-container-high border-b border-outline/20">
      <tr>
        <th scope="col" class="px-6 py-4 font-bold">XAI Method</th>
        <th scope="col" class="px-6 py-4 font-bold min-w-[150px]">Imaging Modalities</th>
        <th scope="col" class="px-6 py-4 font-bold min-w-[200px]">Key Diseases Diagnosed</th>
        <th scope="col" class="px-6 py-4 font-bold min-w-[250px]">Real-World Strengths</th>
        <th scope="col" class="px-6 py-4 font-bold min-w-[250px]">Real-World Limitations</th>
      </tr>
    </thead>
    <tbody class="divide-y divide-outline/10">
      <tr class="bg-surface hover:bg-surface-variant/10 transition-colors">
        <td class="px-6 py-4 font-bold text-primary">LIME</td>
        <td class="px-6 py-4">MRI, CT, X-ray, Fundus</td>
        <td class="px-6 py-4">Alzheimer's, Thyroid, Lung cancer, COVID-19, Pneumonia, Retinoblastoma, Glaucoma</td>
        <td class="px-6 py-4">Highlights influential features to make models easily understandable.</td>
        <td class="px-6 py-4 text-error/90">Inconsistent explanations across runs, computationally intensive, lacks dedicated evaluation metrics.</td>
      </tr>
      <tr class="bg-surface-container-lowest hover:bg-surface-variant/10 transition-colors">
        <td class="px-6 py-4 font-bold text-primary">SHAP</td>
        <td class="px-6 py-4">MRI, CT, X-ray, Fundus, Endoscopy</td>
        <td class="px-6 py-4">Alzheimer's, Breast/Renal cancer, Kidney injury, COVID-19, Coronary Artery Disease, Gastrointestinal</td>
        <td class="px-6 py-4">Provides a fair, theoretically robust, and consistent distribution of feature influence.</td>
        <td class="px-6 py-4 text-error/90">Extremely slow for high-resolution images; explanations can be too mathematically complex for clinicians.</td>
      </tr>
      <tr class="bg-surface hover:bg-surface-variant/10 transition-colors">
        <td class="px-6 py-4 font-bold text-primary">CAM</td>
        <td class="px-6 py-4">MRI, CT, X-ray</td>
        <td class="px-6 py-4">Brain tumour, Knee injury/pain, Breast cancer, Osteoarthritis</td>
        <td class="px-6 py-4">Offers clear visual explanations by explicitly outlining key regions.</td>
        <td class="px-6 py-4 text-error/90">Highly restrictive (requires global average pooling layers); may miss some critical diagnostic areas.</td>
      </tr>
      <tr class="bg-surface-container-lowest hover:bg-surface-variant/10 transition-colors">
        <td class="px-6 py-4 font-bold text-primary">Grad-CAM</td>
        <td class="px-6 py-4">MRI, CT, X-ray, Fundus</td>
        <td class="px-6 py-4">Brain/Lung cancer, Alzheimer's, Glaucoma, COVID-19, Tuberculosis, Gastrointestinal</td>
        <td class="px-6 py-4">Highly versatile across CNN architectures; improves localization with high-resolution heatmaps.</td>
        <td class="px-6 py-4 text-error/90">Imprecise for tiny features; success heavily depends on manual selection of the convolutional layer.</td>
      </tr>
      <tr class="bg-surface hover:bg-surface-variant/10 transition-colors">
        <td class="px-6 py-4 font-bold text-primary">G-Grad-CAM</td>
        <td class="px-6 py-4">X-ray</td>
        <td class="px-6 py-4">COVID-19</td>
        <td class="px-6 py-4">Generates sharp, high-resolution visualisations emphasizing critical regions.</td>
        <td class="px-6 py-4 text-error/90">Computationally heavy; guided backpropagation can introduce confusing visual noise.</td>
      </tr>
      <tr class="bg-surface-container-lowest hover:bg-surface-variant/10 transition-colors">
        <td class="px-6 py-4 font-bold text-primary">Grad-CAM++</td>
        <td class="px-6 py-4">Fundus (Endoscopy)</td>
        <td class="px-6 py-4">Gastrointestinal</td>
        <td class="px-6 py-4">Excellent at detecting fine features and multiple occurrences of the same object.</td>
        <td class="px-6 py-4 text-error/90">Produces ambiguous, confusing heatmaps when critical regions overlap or are too close together.</td>
      </tr>
      <tr class="bg-surface hover:bg-surface-variant/10 transition-colors">
        <td class="px-6 py-4 font-bold text-primary">Saliency Map</td>
        <td class="px-6 py-4">MRI, Fundus</td>
        <td class="px-6 py-4">Brain morphology (adolescents), Papilledema</td>
        <td class="px-6 py-4">Instantly highlights regions where slight pixel changes drastically alter the diagnosis.</td>
        <td class="px-6 py-4 text-error/90">Visualizations are notoriously noisy and difficult to interpret without extra processing or expert help.</td>
      </tr>
      <tr class="bg-surface-container-lowest hover:bg-surface-variant/10 transition-colors">
        <td class="px-6 py-4 font-bold text-primary">LRP</td>
        <td class="px-6 py-4">X-ray, MRI</td>
        <td class="px-6 py-4">Dentistry, Pneumonia, TMJ-ADD, Brain tumour, Alzheimer's</td>
        <td class="px-6 py-4">Traces network logic backward to assign clear importance to individual pixels.</td>
        <td class="px-6 py-4 text-error/90">Architecture-dependent; occasionally overemphasizes regions that lack actual clinical relevance.</td>
      </tr>
      <tr class="bg-surface hover:bg-surface-variant/10 transition-colors">
        <td class="px-6 py-4 font-bold text-primary">Surrogate Model</td>
        <td class="px-6 py-4">X-ray</td>
        <td class="px-6 py-4">Chest diseases</td>
        <td class="px-6 py-4">Enables fast, efficient testing; mimics human clinician logic without computational lag.</td>
        <td class="px-6 py-4 text-error/90">Fails to capture deep nuances, leading to oversimplified or incorrect explanations of the main model.</td>
      </tr>
      <tr class="bg-surface-container-lowest hover:bg-surface-variant/10 transition-colors">
        <td class="px-6 py-4 font-bold text-primary">IG</td>
        <td class="px-6 py-4">MRI</td>
        <td class="px-6 py-4">TMJ-ADD</td>
        <td class="px-6 py-4">Provides detailed, theoretically grounded mapping of influential regions.</td>
        <td class="px-6 py-4 text-error/90">Computationally intensive; highly sensitive to the choice of the "baseline" image, which can ruin accuracy.</td>
      </tr>
      <tr class="bg-surface hover:bg-surface-variant/10 transition-colors">
        <td class="px-6 py-4 font-bold text-primary">Counterfactual</td>
        <td class="px-6 py-4">X-ray</td>
        <td class="px-6 py-4">Chest diseases, Pneumonia, Edema, fractures</td>
        <td class="px-6 py-4">Offers actionable "what-if" insights highly valuable for personalized medicine.</td>
        <td class="px-6 py-4 text-error/90">Very slow to compute; generating realistic "fake" medical images requires immense domain knowledge.</td>
      </tr>
      <tr class="bg-surface-container-lowest hover:bg-surface-variant/10 transition-colors">
        <td class="px-6 py-4 font-bold text-primary">OA (Occlusion)</td>
        <td class="px-6 py-4">X-ray, CT</td>
        <td class="px-6 py-4">COVID-19, Pneumonia</td>
        <td class="px-6 py-4">Intuitive and straightforward method for verifying broad areas of importance.</td>
        <td class="px-6 py-4 text-error/90">Computationally slow; provides a blurry, generalized explanation rather than precise localization.</td>
      </tr>
      <tr class="bg-surface hover:bg-surface-variant/10 transition-colors">
        <td class="px-6 py-4 font-bold text-primary">RISE</td>
        <td class="px-6 py-4">X-ray, CT</td>
        <td class="px-6 py-4">COVID-19, Pneumonia</td>
        <td class="px-6 py-4">Versatile across models; generates highly detailed, pixel-level importance scores.</td>
        <td class="px-6 py-4 text-error/90">Random masking causes variability; requires many averaged iterations to get stable results.</td>
      </tr>
      <tr class="bg-surface-container-lowest hover:bg-surface-variant/10 transition-colors">
        <td class="px-6 py-4 font-bold text-primary">PI (Permutation)</td>
        <td class="px-6 py-4">Multi-modality</td>
        <td class="px-6 py-4">Obesity</td>
        <td class="px-6 py-4">Directly highlights the absolute most critical data points/pixels for a diagnosis.</td>
        <td class="px-6 py-4 text-error/90">Highly unreliable when dealing with correlated features (shuffling one breaks the interpretation of another).</td>
      </tr>
      <tr class="bg-surface hover:bg-surface-variant/10 transition-colors">
        <td class="px-6 py-4 font-bold text-primary">MSA</td>
        <td class="px-6 py-4">Multi-modality</td>
        <td class="px-6 py-4">Cybersickness, Chronic pain</td>
        <td class="px-6 py-4">Provides a global sensitivity measure to understand complex variable interactions.</td>
        <td class="px-6 py-4 text-error/90">Oversimplifies data; struggles significantly with highly nonlinear, complex interactions.</td>
      </tr>
      <tr class="bg-surface-container-lowest hover:bg-surface-variant/10 transition-colors">
        <td class="px-6 py-4 font-bold text-primary">GAR</td>
        <td class="px-6 py-4">X-ray, CT</td>
        <td class="px-6 py-4">COVID-19</td>
        <td class="px-6 py-4">Provides fantastic layer-specific insights into how attention models process images.</td>
        <td class="px-6 py-4 text-error/90">Sensitive to model architecture and initialization; calculations can be disrupted by noise.</td>
      </tr>
      <tr class="bg-surface hover:bg-surface-variant/10 transition-colors">
        <td class="px-6 py-4 font-bold text-primary">Attention-based</td>
        <td class="px-6 py-4">X-ray, CT</td>
        <td class="px-6 py-4">COVID-19</td>
        <td class="px-6 py-4">Provides focused, direct analysis by extracting the model's natural internal weights.</td>
        <td class="px-6 py-4 text-error/90">Prone to "hyper-focus," potentially missing smaller, less obvious details crucial for diagnosis.</td>
      </tr>
      <tr class="bg-surface-container-lowest hover:bg-surface-variant/10 transition-colors">
        <td class="px-6 py-4 font-bold text-primary">AS (Ablation)</td>
        <td class="px-6 py-4">X-ray</td>
        <td class="px-6 py-4">COVID-19</td>
        <td class="px-6 py-4">Optimizes massive architectures by identifying redundancies without losing performance.</td>
        <td class="px-6 py-4 text-error/90">Pulling one component can inadvertently affect others, making the true impact highly confusing to interpret.</td>
      </tr>
      <tr class="bg-surface hover:bg-surface-variant/10 transition-colors">
        <td class="px-6 py-4 font-bold text-primary">DTD</td>
        <td class="px-6 py-4">MRI</td>
        <td class="px-6 py-4">TMJ-ADD</td>
        <td class="px-6 py-4">Mathematically rigorous (Taylor series), drastically enhancing model transparency.</td>
        <td class="px-6 py-4 text-error/90">Highly subjective (depends on root point selection); difficult to implement in non-ReLU architectures.</td>
      </tr>
    </tbody>
  </table>
</div>

---

### 🏆 The Current "State-of-the-Art" Techniques in Use

Based on current literature, two different methods are considered the pinnacle of the field, depending strictly on what you prioritize:

1. **For Theoretical Fairness (The Mathematical SOTA):** **SHAP** is explicitly identified as a state-of-the-art explanatory framework. Because it is deeply rooted in game theory and Shapley values, it provides a highly robust and mathematically fair distribution of "credit" among image features. However, it is computationally expensive and very slow for high-resolution images.
2. **For Versatile Visualizations (The Industry Standard):** **Grad-CAM** (along with its advanced variant, Grad-CAM++) is effectively the standard for medical imaging. It is highly versatile because it can be applied to a wide range of Convolutional Neural Networks (CNNs) without requiring specific layers. More importantly, it requires only a single backpropagation pass, making it computationally efficient enough for real-time or near-real-time medical applications.

---

### 🚀 Limitations & Gaps to Base Our Project On

For a B.Tech minor project, analyzing the unsolved problems in the field is an absolute goldmine. If we want to build a project that pushes XAI forward, here are the major limitations we could tackle:

<div class="space-y-6 mt-8">
  <div class="p-6 bg-surface-variant/10 border border-outline/20 rounded-xl">
    <h4 class="font-bold text-lg text-primary mb-2 flex items-center gap-2"><span>1.</span> The Lack of Specialized Evaluation Metrics (The Biggest Gap)</h4>
    <p class="text-sm text-on-surface-variant mb-4"><strong>The Problem:</strong> The researchers noted a massive gap: across all the papers reviewed, not a single author used mathematical metrics specifically designed to evaluate explainability. Everyone is currently borrowing standard Deep Learning and Computer Vision metrics, which completely fail to measure how "understandable" or "good" an explanation actually is.</p>
    <div class="p-4 bg-primary/10 rounded-lg border-l-4 border-primary">
      <p class="text-sm font-medium text-primary"><strong>💡 Project Idea:</strong> Focus the project on developing or testing a new, specialized quantitative metric to mathematically grade XAI heatmaps, attempting to establish a "ground truth" for what makes an explanation accurate.</p>
    </div>
  </div>

  <div class="p-6 bg-surface-variant/10 border border-outline/20 rounded-xl">
    <h4 class="font-bold text-lg text-primary mb-2 flex items-center gap-2"><span>2.</span> Sanity Checks and "Fake" Explanations</h4>
    <p class="text-sm text-on-surface-variant mb-4"><strong>The Problem:</strong> Methods that generate attribution maps (like Guided Backpropagation and G-Grad-CAM) completely fail "randomization" and "robustness" tests. Studies have shown that these XAI tools can sometimes produce beautiful, convincing visual heatmaps even if the AI model hasn't been properly trained at all.</p>
    <div class="p-4 bg-primary/10 rounded-lg border-l-4 border-primary">
      <p class="text-sm font-medium text-primary"><strong>💡 Project Idea:</strong> Work on enhancing the robustness and consistency of attribution maps, perhaps by building a framework that actively tests whether an XAI method is relying on true learned features or just generating misleading visual noise.</p>
    </div>
  </div>

  <div class="p-6 bg-surface-variant/10 border border-outline/20 rounded-xl">
    <h4 class="font-bold text-lg text-primary mb-2 flex items-center gap-2"><span>3.</span> Optimizing Computational Cost for Real-Time Use</h4>
    <p class="text-sm text-on-surface-variant mb-4"><strong>The Problem:</strong> Methods like LIME and SHAP are perturbation-based, meaning they require the model to recalculate predictions hundreds of times, resulting in massive computational overhead. This makes them practically useless in an emergency room where doctors need answers instantly.</p>
    <div class="p-4 bg-primary/10 rounded-lg border-l-4 border-primary">
      <p class="text-sm font-medium text-primary"><strong>💡 Project Idea:</strong> Focus on making a computationally heavy method (like SHAP) run faster, or build a hybrid model that balances the speed of gradient-based methods (like Grad-CAM) with the detailed accuracy of perturbation methods.</p>
    </div>
  </div>

  <div class="p-6 bg-surface-variant/10 border border-outline/20 rounded-xl">
    <h4 class="font-bold text-lg text-primary mb-2 flex items-center gap-2"><span>4.</span> Explainability for Multimodal Data</h4>
    <p class="text-sm text-on-surface-variant mb-4"><strong>The Problem:</strong> Currently, most XAI methods are only tested on simple, single-modality datasets (e.g., just looking at an X-ray). Real healthcare is multimodal, combining X-rays, MRI scans, CT scans, and microscopic data to make a single diagnosis.</p>
    <div class="p-4 bg-primary/10 rounded-lg border-l-4 border-primary">
      <p class="text-sm font-medium text-primary"><strong>💡 Project Idea:</strong> Design an XAI framework capable of handling a multimodal dataset, proving how the AI weighs an X-ray against a patient's clinical text data to make a decision.</p>
    </div>
  </div>

  <div class="p-6 bg-surface-variant/10 border border-outline/20 rounded-xl">
    <h4 class="font-bold text-lg text-primary mb-2 flex items-center gap-2"><span>5.</span> Generating Realistic "What-If" Images</h4>
    <p class="text-sm text-on-surface-variant mb-4"><strong>The Problem:</strong> Counterfactual explanations answer "what-if" questions by generating alternate fake images (using autoencoders) to show what would change a diagnosis. However, because medical data is so complex, these generated images often suffer from low quality and look completely unrealistic to a real doctor.</p>
    <div class="p-4 bg-primary/10 rounded-lg border-l-4 border-primary">
      <p class="text-sm font-medium text-primary"><strong>💡 Project Idea:</strong> Work on enhancing the image perturbation process (perhaps using advanced GANs) to generate high-quality, medically realistic counterfactual images.</p>
    </div>
  </div>
</div>

---

### 🧠 One Final, Important Takeaway

**Shattering the "Accuracy vs. Interpretability" Myth:** Traditionally, researchers believed there was a strict trade-off: if you make a model explainable, it loses diagnostic accuracy, and vice versa. The literature points out that emerging evidence proves this is definitively false. Improving a model's interpretability can actually help you find hidden errors and _enhance_ its overall accuracy.

As we define the exact scope for this project, we must remember: we do not have to sacrifice performance just to make our model explainable!
