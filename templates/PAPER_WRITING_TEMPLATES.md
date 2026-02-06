# Paper Writing Templates & Examples

## 1. Title Formulation

### Formula
```
[SYSTEM/METHOD NAME]: [SPECIFIC TECHNIQUE] for [SPECIFIC PROBLEM] in [SPECIFIC DOMAIN]
```

### Examples from Top Venues

**Strong Titles** (CCS/USENIX/S&P):
- "CrypTFlow: Secure TensorFlow Inference" (S&P 2020)
- "Proof-of-Learning: Definitions and Practice" (S&P 2021)
- "FLASH: Fast and Robust Framework for Privacy-Preserving Machine Learning" (PETS 2022)
- "SoK: Privacy-Preserving Computation Techniques for Deep Learning" (PETS 2020)

**Applying to Your Work**:

❌ **Weak**: "Federated Learning for LLM Security"
✅ **Strong**: "Fed-OCL: Byzantine-Resilient Federated Learning for Privacy-Preserving Prompt Injection Detection"

❌ **Weak**: "Improving Privacy in FL"
✅ **Strong**: "PrivateGuard: Adaptive Differential Privacy for Communication-Efficient Federated Learning"

---

## 2. Abstract Templates

### Standard Conference Abstract (250 words)

```markdown
[PROBLEM & MOTIVATION - 2-3 sentences]
[Opening hook with real-world impact]
[Specific problem statement]
[Why it matters NOW]

[GAP IN EXISTING WORK - 2-3 sentences]
Current approaches [cite category 1] suffer from [limitation 1].
Recent work [cite category 2] addresses [aspect], but fails to handle [limitation 2].
Existing solutions face a fundamental trade-off between [X] and [Y].

[PROPOSED SOLUTION - 3-4 sentences]
We propose [SYSTEM NAME], a [technique category] that [key innovation].
Our approach combines [method 1] and [method 2] to achieve [goal].
[SYSTEM NAME] provides [theoretical guarantee] through [mechanism].
[Optional: Architecture/design highlight]

[EXPERIMENTAL RESULTS - 2-3 sentences]
We evaluate [SYSTEM NAME] on [X datasets/scenarios] against [Y baselines].
Results show [Z% improvement] in [metric 1] while maintaining [constraint].
[SYSTEM NAME] achieves [specific milestone] with [additional benefit].

[IMPACT/AVAILABILITY - 1 sentence]
This work [broader contribution] and has implications for [application].
[Optional: Code/data availability]
```

### Example: Fed-OCL Abstract

```markdown
Large Language Models (LLMs) deployed in production face critical security risks 
from prompt injection attacks, where adversaries manipulate model behavior through 
crafted inputs. Existing detection methods require centralized data collection, 
violating privacy regulations like GDPR and eroding user trust, particularly in 
sensitive domains like healthcare and finance.

Current federated learning approaches for collaborative security enable multi-party 
training without data sharing, but remain vulnerable to Byzantine attacks where 
malicious participants poison the global model. Prior defenses either sacrifice 
privacy by omitting differential privacy guarantees, or incur prohibitive utility 
loss and communication overhead, limiting practical deployment.

We propose Fed-OCL (Federated One-Class Learning), a Byzantine-resilient framework 
that combines adaptive differential privacy with secure aggregation for privacy-
preserving prompt injection detection. Our approach employs coordinate-wise median 
aggregation to filter Byzantine updates while maintaining (ε,δ)-differential privacy 
guarantees through Gaussian noise calibration. Fed-OCL achieves 40% communication 
reduction via gradient compression and adaptive client sampling.

We evaluate Fed-OCL on four prompt injection datasets (PromptBench, BIPIA, AdvPrompt, 
TensorTrust) against six state-of-the-art baselines, simulating up to 100 clients 
with 30% Byzantine participants. Results show Fed-OCL achieves 0.89 AUC (+6% over 
FedAvg-DP) while providing ε=1.0 privacy guarantee, with <5s aggregation latency. 
Under 30% Byzantine clients, Fed-OCL maintains 0.85 AUC while baselines degrade to 
0.72.

This work enables privacy-preserving collaborative LLM security in federated 
settings without trusted third parties. Code and datasets available at [URL].
```

---

## 3. Introduction Structure (Conference Paper)

### Introduction Outline (3-4 pages)

**Page 1: Motivation**
```markdown
## 1. Introduction

[Paragraph 1: Opening Hook]
- Start with recent incident, statistic, or compelling scenario
- Establish real-world importance
- 3-5 sentences

Example:
"In March 2023, a prompt injection attack on a major AI assistant enabled 
unauthorized access to confidential corporate data, affecting 10,000+ users 
[Citation]. This incident highlights a growing threat: as Large Language Models 
(LLMs) become integrated into mission-critical systems, their vulnerability to 
adversarial manipulation poses severe security and privacy risks. Recent studies 
show that over 80% of commercial LLM applications lack robust defenses against 
prompt injection attacks [Citation]."

[Paragraph 2: Technical Context]
- Explain necessary background
- Define key concepts
- Set up the problem technically
- 5-7 sentences

Example:
"Prompt injection attacks manipulate LLM behavior by embedding adversarial 
instructions within user inputs or retrieved documents [Citation]. Unlike 
traditional adversarial examples that perturb pixels or tokens, prompt injections 
exploit the model's instruction-following capability, causing it to ignore safety 
guidelines or leak sensitive information [Citation]. Detecting such attacks 
requires analyzing semantic anomalies in input distributions, a task complicated 
by the vast diversity of legitimate prompts across domains and users."
```

**Page 1-2: Problem Statement & Challenges**
```markdown
[Paragraph 3: The Core Problem]
- Formal problem definition
- Scope and constraints
- 4-6 sentences

Example:
"We address the problem of privacy-preserving prompt injection detection in 
federated settings, where multiple organizations wish to collaboratively train 
a detector without sharing their proprietary user queries. This scenario is 
critical for industries like healthcare, finance, and legal services, where 
data sharing is restricted by regulations (HIPAA, GDPR, CCPA) [Citation]. The 
challenge is to achieve high detection accuracy while providing formal privacy 
guarantees and robustness against adversarial participants."

[Paragraph 4: Why It's Hard - Challenge 1]
- First major challenge with technical depth
- Why existing solutions fail
- 4-5 sentences

[Paragraph 5: Why It's Hard - Challenge 2]
- Second major challenge
- Trade-offs involved
- 4-5 sentences

[Paragraph 6: Why It's Hard - Challenge 3]
- Third challenge (if applicable)
- Practical deployment concerns
- 3-4 sentences
```

**Page 2-3: Limitations of Existing Work**
```markdown
[Paragraph 7-9: Related Work Categories & Limitations]
Organize into 2-3 categories:

"Existing approaches fall into three categories: centralized detection, 
privacy-oblivious federated learning, and privacy-preserving FL with 
limited robustness."

**Category 1**: Centralized Detection Methods
- Brief description
- Key papers [cite 3-4]
- Limitations (why they fail for your problem)

**Category 2**: Federated Learning for Security
- Brief description  
- Key papers [cite 3-4]
- Limitations (privacy? robustness? efficiency?)

**Category 3**: Privacy-Preserving FL
- Brief description
- Key papers [cite 3-4]
- Limitations (utility loss? no Byzantine defense?)

[Paragraph 10: Gap Summary]
"In summary, existing work faces a trilemma: solutions optimized for privacy 
sacrifice robustness to Byzantine attacks, Byzantine-resilient methods leak 
sensitive information, and approaches addressing both incur prohibitive 
communication costs. No prior work simultaneously achieves strong privacy 
guarantees, Byzantine resilience, and practical efficiency."
```

**Page 3-4: Our Approach & Contributions**
```markdown
[Paragraph 11-12: High-Level Approach]
"We present Fed-OCL, a framework that resolves this trilemma through three 
key insights:

**Insight 1**: [First key idea]
[Brief explanation - 2-3 sentences]

**Insight 2**: [Second key idea]
[Brief explanation - 2-3 sentences]

**Insight 3**: [Third key idea]
[Brief explanation - 2-3 sentences]

Based on these insights, Fed-OCL integrates [components] to achieve [goals]."

[Paragraph 13: Contributions List]
"Our contributions include:

• **Novel Framework**: Fed-OCL, the first Byzantine-resilient federated 
  learning system for prompt injection detection with formal DP guarantees.

• **Adaptive Privacy Mechanism**: An adaptive noise calibration scheme that 
  achieves (ε,δ)-DP while minimizing utility loss through [specific technique].

• **Efficient Aggregation**: Coordinate-wise median aggregation combined with 
  gradient compression, reducing communication by 40% compared to FedAvg.

• **Theoretical Analysis**: Formal privacy-utility convergence bounds and 
  Byzantine resilience guarantees under [threat model].

• **Comprehensive Evaluation**: Extensive experiments on 4 datasets with up 
  to 100 clients, demonstrating 0.89 AUC with ε=1.0 privacy, even under 30% 
  Byzantine participants.

• **Open-Source Release**: Implementation, datasets, and evaluation scripts 
  publicly available at [URL] for reproducibility."

[Paragraph 14: Paper Organization]
"The remainder of this paper is organized as follows. Section 2 provides 
background on [topics]. Section 3 formally defines our threat model and 
problem statement. Section 4 presents the Fed-OCL framework and theoretical 
analysis. Section 5 describes our experimental methodology. Section 6 presents 
and analyzes results. Section 7 discusses limitations and future work. 
Section 8 reviews related work, and Section 9 concludes."
```

---

## 4. Related Work Section

### Organization Strategy

**Option A: Chronological + Categorical**
```markdown
## 2. Related Work

We organize related work into three main categories: [Cat 1], [Cat 2], [Cat 3].

### 2.1 [Category 1 Name]
[Subfield description - 2-3 sentences]

**Early Work (pre-2020)**: [Paper 1] [Citation] introduced [concept]...
[2-3 sentences on seminal work]

**Recent Advances (2020-2024)**: More recent work by [Authors] [Citation] 
improved upon this by [advancement]...
[3-4 sentences on recent work]

**Limitations for Our Problem**: While these approaches [strength], they 
fail to address [gap 1] and [gap 2], making them unsuitable for [our scenario].

### 2.2 [Category 2 Name]
[Similar structure]

### 2.3 [Category 3 Name]
[Similar structure]

### 2.4 Comparison with Our Work
[Taxonomy table or detailed comparison]
```

**Option B: Problem-Solution-Limitation**
```markdown
## 2. Related Work

### 2.1 Federated Learning for Security Applications
[Describe the problem space]

**Solutions**: Various approaches have been proposed...
- [Paper 1]: [Brief description]
- [Paper 2]: [Brief description]
- [Paper 3]: [Brief description]

**Limitations**: These solutions [limitation 1], [limitation 2]...

### 2.2 [Next category]
[Repeat structure]
```

### Comparison Table Example

```markdown
### 2.5 Summary and Positioning

Table 1 compares Fed-OCL with representative prior work across key dimensions.

| Approach | Privacy | Byzantine-Resilient | Communication | Application |
|----------|---------|-------------------|---------------|-------------|
| FedAvg [Citation] | ✗ | ✗ | O(nd) | Generic FL |
| DP-FedAvg [Citation] | ✓ (ε-DP) | ✗ | O(nd) | Generic FL |
| Krum [Citation] | ✗ | ✓ (50%) | O(nd) | Byzantine FL |
| RFA [Citation] | ✓ (ε-DP) | ✗ | O(nd²) | Privacy FL |
| [Recent Work] | ✓ (ε-DP) | ✓ (20%) | O(nd) | Generic FL |
| **Fed-OCL (Ours)** | ✓ (ε,δ-DP) | ✓ (30%) | O(0.6nd) | LLM Security |

Fed-OCL is the first to simultaneously provide formal DP guarantees, Byzantine 
resilience up to 30%, and communication efficiency, specifically designed for 
prompt injection detection.
```

---

## 5. Methodology Section Structure

### Template

```markdown
## 3. Methodology

### 3.1 Overview
[High-level system architecture]

Figure 1 illustrates the Fed-OCL architecture, consisting of [components]:
[Describe each component briefly]

[Include system diagram]

### 3.2 Threat Model

**Adversary Knowledge**: We consider a [white/gray/black-box] adversary with 
[specific knowledge].

**Adversary Capability**: The adversary can [list capabilities]:
- Compromise up to f < n/3 clients (Byzantine clients)
- Inject arbitrary gradients during training
- [Other capabilities]

**Adversary Goal**: The adversary aims to [primary goal] while [secondary constraint].

**Assumptions**: We assume [list assumptions]:
1. The central server is trusted (but curious)
2. Communication channels are authenticated
3. [Other assumptions]

### 3.3 Problem Formulation

**Notation**: Let D = {D₁, ..., Dₙ} denote n clients' private datasets...

**Objective**: Our goal is to learn a global model θ* that minimizes:
[Mathematical formulation]

Subject to:
- Privacy: (ε,δ)-differential privacy for each client
- Robustness: Accuracy ≥ α even with f Byzantine clients
- Efficiency: Communication cost ≤ β

### 3.4 Fed-OCL Framework

#### 3.4.1 Local Training with DP-SGD
Each client i performs [steps]...

**Algorithm 1**: DP-SGD Local Training
[Pseudocode]

**Privacy Analysis**: The local training satisfies [privacy guarantee] by 
[mechanism]. Using moments accountant [Citation], the privacy cost per round 
is [formula].

#### 3.4.2 Byzantine-Robust Aggregation
The server collects {∇θᵢ} from n clients and performs:

**Algorithm 2**: Coordinate-wise Median Aggregation
[Pseudocode]

**Robustness Analysis**: This aggregation rule tolerates up to [formula] 
Byzantine clients because [intuition + proof sketch].

#### 3.4.3 Communication Optimization
To reduce communication overhead, we apply:
1. Gradient sparsification: [technique]
2. Quantization: [technique]
3. [Other optimizations]

**Complexity Analysis**: 
- Baseline FedAvg: O(nd) communication per round
- Fed-OCL: O(0.6nd) communication (40% reduction)
[Explain where savings come from]

### 3.5 Theoretical Analysis

**Theorem 1** (Privacy Guarantee): Fed-OCL satisfies (ε,δ)-differential 
privacy where ε = [formula] after T rounds.

*Proof Sketch*: [High-level proof idea]
[Full proof in appendix]

**Theorem 2** (Byzantine Resilience): If at most f < n/3 clients are 
Byzantine, Fed-OCL converges to within [bound] of the optimal solution.

*Proof Sketch*: [High-level proof idea]

**Theorem 3** (Convergence): Under [assumptions], Fed-OCL converges at 
rate O([formula]).

*Proof Sketch*: [High-level proof idea]
```

---

## 6. Experimental Section Structure

### Template

```markdown
## 4. Experimental Evaluation

### 4.1 Experimental Setup

#### 4.1.1 Datasets
We evaluate on four prompt injection datasets:

**Table 2**: Dataset Statistics

| Dataset | # Samples | # Malicious | Domain | Source |
|---------|-----------|-------------|--------|--------|
| PromptBench | 10,000 | 3,245 | General | [Citation] |
| BIPIA | 8,500 | 4,120 | Security | [Citation] |
| AdvPrompt | 12,000 | 5,800 | Adversarial | [Citation] |
| TensorTrust | 15,000 | 6,200 | Mixed | [Citation] |

**Data Preprocessing**: [Describe preprocessing steps]

**Train/Val/Test Split**: We use 60%/20%/20% split with stratification...

**Federated Data Partitioning**: We simulate n clients by partitioning each 
dataset according to [distribution]. To model realistic heterogeneity, we 
use Dirichlet distribution with α = [value].

#### 4.1.2 Baselines
We compare against six state-of-the-art methods:

1. **FedAvg** [Citation]: Standard federated averaging
2. **DP-FedAvg** [Citation]: FedAvg with differential privacy (ε=1.0)
3. **Krum** [Citation]: Byzantine-resilient aggregation
4. **Median** [Citation]: Coordinate-wise median
5. **[Recent Method 1]** [Citation]: [Brief description]
6. **[Recent Method 2]** [Citation]: [Brief description]

#### 4.1.3 Implementation Details
**Model Architecture**: BERT-base encoder [Citation] with autoencoder head...

**Hyperparameters**:
- Learning rate: 0.001 (locally), 1.0 (server)
- Batch size: 32
- Local epochs: 5
- Communication rounds: 100
- DP parameters: ε=1.0, δ=10⁻⁵, C=1.0 (clipping), σ=0.5 (noise)

**Hardware**: NVIDIA A100 GPU with 40GB RAM

**Software**: PyTorch 2.0, Flower FL framework, Python 3.10

**Statistical Rigor**: All experiments run with 5 random seeds. We report 
mean ± std and conduct t-tests for significance (p<0.05).

#### 4.1.4 Evaluation Metrics
- **AUC**: Area under ROC curve (primary metric)
- **F1-Score**: Harmonic mean of precision and recall
- **FPR@95TPR**: False positive rate at 95% true positive rate
- **Communication Cost**: Total bytes transmitted
- **Convergence Time**: Rounds to reach target accuracy

### 4.2 Main Results

**Research Question 1**: How does Fed-OCL compare to state-of-the-art in 
terms of detection accuracy and privacy?

**Table 3**: Detection Performance (PromptBench dataset, n=50 clients, 10% Byzantine)

| Method | AUC ↑ | F1 ↑ | FPR@95TPR ↓ | Privacy |
|--------|-------|------|-------------|---------|
| FedAvg | 0.83±0.02 | 0.79±0.03 | 0.18 | None |
| DP-FedAvg (ε=1.0) | 0.78±0.03 | 0.74±0.04 | 0.24 | ε=1.0 |
| Krum | 0.81±0.02 | 0.77±0.02 | 0.20 | None |
| [Baseline 4] | 0.80±0.03 | 0.76±0.03 | 0.22 | ε=2.0 |
| **Fed-OCL (Ours)** | **0.89±0.02** | **0.85±0.02** | **0.12** | ε=1.0 |

**Key Findings**:
- Fed-OCL achieves +6% AUC over best baseline (DP-FedAvg)
- Provides stronger privacy (ε=1.0 vs. ε=2.0) with better utility
- 33% reduction in FPR at fixed TPR

**Statistical Significance**: All improvements are statistically significant 
(p<0.01) based on paired t-tests.

[Continue with more research questions...]

### 4.3 Byzantine Resilience

**Research Question 2**: How robust is Fed-OCL to Byzantine attacks?

**Figure 2**: Detection accuracy vs. Byzantine client ratio

[Include figure showing Fed-OCL maintains performance while baselines degrade]

**Analysis**: [Explain what the figure shows and why]

### 4.4 Privacy-Utility Trade-off

**Research Question 3**: How does privacy budget affect utility?

**Figure 3**: AUC vs. ε (privacy budget)

[Include Pareto frontier plot]

**Analysis**: [Explain the trade-off and sweet spot]

### 4.5 Communication Efficiency

**Research Question 4**: What is the communication overhead?

**Table 4**: Communication Cost Comparison

| Method | Bytes/Round | Total Communication | Convergence Rounds |
|--------|-------------|---------------------|-------------------|
| FedAvg | 500 MB | 50 GB | 100 |
| Fed-OCL | 300 MB | 36 GB | 120 |

**Analysis**: Fed-OCL reduces communication by 40% per round but requires 
20% more rounds, resulting in 28% overall savings.

### 4.6 Ablation Study

**Research Question 5**: What is the contribution of each component?

**Table 5**: Ablation Results

| Configuration | AUC | Privacy | Byzantine-Resilient |
|--------------|-----|---------|-------------------|
| Full Fed-OCL | 0.89 | ✓ | ✓ |
| w/o DP | 0.91 | ✗ | ✓ |
| w/o Byzantine defense | 0.87 | ✓ | ✗ |
| w/o Communication opt | 0.89 | ✓ | ✓ |

**Analysis**: 
- DP costs ~2% AUC (0.91 → 0.89) but provides strong privacy
- Byzantine defense crucial: without it, attacks reduce AUC to 0.72
- Communication optimization doesn't affect accuracy

### 4.7 Sensitivity Analysis

**Research Question 6**: How sensitive is Fed-OCL to hyperparameters?

**Figure 4**: Sensitivity to clipping bound C and noise scale σ

[Include heatmap or multi-line plot]

**Analysis**: Fed-OCL is relatively robust to hyperparameter choices within 
reasonable ranges (C ∈ [0.5, 2.0], σ ∈ [0.3, 0.8]).
```

---

## 7. Discussion & Limitations

```markdown
## 5. Discussion

### 5.1 Key Insights

**Finding 1**: [Important observation]
[Explanation and implications]

**Finding 2**: [Another observation]
[Explanation and implications]

### 5.2 Practical Deployment Considerations

**Scalability**: Fed-OCL scales to 100+ clients with [performance characteristics].
Deployment in production would require [considerations].

**Integration**: The framework can be integrated with existing [systems] via [API].

**Cost-Benefit Analysis**: The 2% accuracy cost for DP is justified in sensitive 
domains where [reasoning].

### 5.3 Limitations

**Computational Overhead**: Fed-OCL incurs 1.5x training time compared to 
FedAvg due to [reasons]. This may be prohibitive for [scenarios].

**Dataset Scope**: Our evaluation focuses on text-based prompt injection. 
Extension to multi-modal attacks (text + image) is future work.

**Adversary Model**: We assume at most 30% Byzantine clients based on [rationale]. 
Higher adversary fractions may require [alternative approaches].

**Generalization**: While we evaluate on prompt injection, applicability to 
other anomaly detection tasks requires further investigation.

### 5.4 Broader Impact

**Positive**: Enables privacy-preserving collaboration on security tasks, 
potentially protecting millions of users.

**Negative**: Adversaries might adapt attacks knowing defenses exist. Responsible 
disclosure and continuous updating needed.

**Ethical Considerations**: [Discuss fairness, bias, potential misuse]
```

---

## 8. Conclusion

```markdown
## 6. Conclusion

We presented Fed-OCL, a Byzantine-resilient federated learning framework for 
privacy-preserving prompt injection detection in LLM applications. Fed-OCL 
simultaneously achieves strong privacy guarantees (ε=1.0 differential privacy), 
robustness to Byzantine attacks (up to 30% malicious clients), and communication 
efficiency (40% reduction). Through extensive evaluation on four datasets with 
up to 100 simulated clients, we demonstrated that Fed-OCL outperforms state-of-
the-art baselines by +6% AUC while maintaining formal privacy guarantees.

Our work makes three key contributions: (1) a novel aggregation scheme combining 
coordinate-wise median with adaptive DP, (2) theoretical privacy-utility-
robustness bounds, and (3) empirical evidence of practical viability. Fed-OCL 
enables organizations to collaboratively defend against emerging LLM threats 
without compromising user privacy or data sovereignty.

**Future Work**: We plan to extend Fed-OCL to (1) multi-modal prompt injections, 
(2) Byzantine clients exceeding 30%, (3) cross-silo federated settings with 
institutional heterogeneity, and (4) integration with commercial LLM platforms.

**Availability**: Code, datasets, and experimental scripts are open-sourced at 
[URL] to facilitate reproducibility and further research.
```

---

## 9. Figure & Table Best Practices

### Figure Design Principles
- **Clear labels**: Large fonts (10-12pt), readable axis labels
- **Legends**: Position clearly, use descriptive names
- **Colors**: Colorblind-friendly palettes, avoid red-green
- **Error bars**: Show std dev or confidence intervals
- **Captions**: Detailed, self-contained

### Table Design Principles
- **Bold best**: Bold best result, underline second-best
- **Alignment**: Numbers right-aligned, text left-aligned
- **Units**: Clearly specify units
- **Statistical indicators**: *, **, *** for p-values
- **Captions**: Above table, describe what's compared

---

## 10. Common Writing Pitfalls to Avoid

❌ **Passive voice overuse**: "The model was trained..."
✅ **Active voice**: "We trained the model..."

❌ **Vague claims**: "Our method works well..."
✅ **Specific claims**: "Our method achieves 0.89 AUC, +6% over baselines..."

❌ **Unexplained jargon**: "We use DP-SGD with moments accountant"
✅ **Explained terms**: "We use DP-SGD [Citation], which adds calibrated noise 
to gradients. We track privacy loss using the moments accountant method [Citation]."

❌ **Missing motivation**: "We propose X..."
✅ **Motivated design**: "To address [challenge], we propose X, which [approach]..."

❌ **Results without analysis**: "Table 2 shows the results."
✅ **Results with insight**: "Table 2 shows Fed-OCL achieves 0.89 AUC. This 
improvement stems from [reason], demonstrating that [insight]."

---

**Use these templates as starting points. Adapt to your specific work, venue requirements, and supervisor feedback!**
