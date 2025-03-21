# GUI-Xplore

GUI-Xplore is a novel dataset designed to enhance cross-application and cross-task generalization for GUI agents. It provides exploration videos for diverse applications, combined with five structured downstream tasks, aiming to push the boundaries of generalizable GUI automation.

## 🚀 News
- [2025-02-27] Accepted by CVPR 2025
- [2025-03-18] Initial release of GUI-Xplore dataset and benchmark.


## 🔥 Features
- **Exploration-then-Reasoning**: A new paradigm that enables GUI agents to learn from exploration videos.
- **Cross-App & Cross-Task Generalization**: Unlike prior datasets, GUI-Xplore enables models to adapt to new applications without explicit retraining.
- **Large-Scale Dataset**: Covering 312 apps across 33 subcategories, with 32,569 QA pairs for evaluation.
- **Baseline Framework - Xplore-Agent**: A novel GUI agent leveraging Action-aware GUI Modeling and Graph-Guided Environment Reasoning.

## 📌 TODO
- [✅] Release GUI-Xplore dataset.
- [ ] Open-source the Xplore-Agent model.
- [ ] Provide pre-trained checkpoints.
- [ ] Add evaluation scripts for benchmarking.

## 📂 Dataset
GUI-Xplore provides a comprehensive benchmark for evaluating GUI agents. The dataset consists of:

- 312 apps from six major categories: Entertainment, Productivity, Health, Shopping, Travel, News.
- Exploration videos (115+ hours) capturing user interactions across all screens.
- Five hierarchical downstream tasks:
  - Application Overview – Understanding an app's primary functionality.
  - Page Analysis – Interpreting the purpose of specific GUI screens.
  - Application Usage – Inferring the correct navigation path.
  - Action Recall – Identifying past interactions in an app.
  - Action Sequence Verification – Reasoning about the logical order of actions.

## 📥 Download
- Dataset link: [HuggingFace](https://huggingface.co/datasets/9211sun/GUI-Xplore)
- Format: .mp4 (videos), .json, .png (annotations)

## 🏗️ Method
### Xplore-Agent: A Baseline Model for GUI-Xplore
To fully utilize exploration videos, we propose Xplore-Agent, a framework that consists of:

**Action-aware GUI Modeling**
- Extracts keyframes based on GUI interactions (instead of fixed-interval sampling).
- Generates structured representations of GUI states.

**Graph-Guided Environment Reasoning**
- Constructs a GUI Transition Graph to model app structures.
- Uses LLM-based reasoning to answer GUI-related queries.

## 📝 Model Pipeline
1. Action-aware Keyframe Extraction: Identifies key transitions in GUI videos.
2. View Hierarchy Generation: Converts GUI screens into structured text representations.
3. GUI Clustering: Groups screens with similar functionalities.
4. GUI Transition Graph Construction: Builds a structured environment model.
5. Task-Specific Reasoning: Uses LLMs (e.g., GPT-4V) to generate answers for downstream tasks.

🔗 Full details in our paper: GUI-Xplore: Exploration-Guided Generalization for GUI Agents 

## 📊 Benchmark Results
### 📌 Cross-App Generalization
| Method | Ele. Acc. | Op. Acc. | StepSR |
|--------|-----------|----------|---------|
| GPT-4V | 5.06% | 66.12% | 4.02% |
| AUTO-UI | 7.40% | 24.87% | 2.17% |
| SeeClick | 6.64% | -- | 6.64% |
| CogAgent | 17.18% | 73.54% | 15.80% |
| Xplore-Agent | 30.73% | 84.63% | 30.39% |

### 📌 Multi-Task Evaluation
| Method | Overview | Page Analysis | App Usage | Recall | Sequence Verification | Avg. Score |
|--------|----------|---------------|-----------|---------|---------------------|------------|
| VideoTree | 89.75% | 91.05% | 65.73% | 21.70% | 21.61% | 57.97% |
| GPT       | 96.88% | 82.12% | 66.48% | 22.60% | 28.85% | 59.39% |
| Xplore-Agent | 99.25% | 92.86% | 68.21% | 24.36% | 36.54% | 64.24% |

## 📜 Citation
If you use GUI-Xplore in your research, please cite:
```bibtex
@article{your2025gui-xplore,
  title   = {GUI-Xplore: Exploration-Guided Generalization for GUI Agents},
  author  = {Yuchen Sun, Shanhui Zhao, Tao Yu, Hao Wen, Samith Va, Mengwei Xu, Yuanchun Li, Chongyang Zhang},
  journal = {CVPR 2025},
  year    = {2025}
}
```

## 📬 Contact
For questions, reach out via:
- Email: sunyc22@sjtu.edu.cn
- GitHub Issues: Open an Issue

🎉 Star this repo if you find it useful! 🚀 