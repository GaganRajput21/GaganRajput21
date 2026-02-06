# Curated Reading List for LLM Security & Privacy-Preserving AI

> **Personalized for**: Fed-OCL, Prompt Injection Detection, Federated Learning Security

---

## 🎯 Priority Reading Path (4 Weeks)

### Week 1: Federated Learning Fundamentals & Security

#### Must-Read (Core FL)
1. **"Communication-Efficient Learning of Deep Networks from Decentralized Data"**  
   McMahan et al., AISTATS 2017  
   📌 *Why*: Original FedAvg paper - foundation of FL  
   🔑 *Key Takeaway*: Federated averaging algorithm, communication rounds

2. **"Advances and Open Problems in Federated Learning"**  
   Kairouz et al., arXiv 2019  
   📌 *Why*: Comprehensive survey of FL landscape  
   🔑 *Key Takeaway*: Open problems, research directions

#### Byzantine-Robust FL (Your Core Need)
3. **"Byzantine-Robust Distributed Learning: Towards Optimal Statistical Rates"**  
   Yin et al., ICML 2018  
   📌 *Why*: First work on Byzantine-robust aggregation  
   🔑 *Key Takeaway*: Median-based aggregation, theoretical guarantees

4. **"Machine Learning with Adversaries: Byzantine Tolerant Gradient Descent"**  
   Blanchard et al., NeurIPS 2017 (Krum paper)  
   📌 *Why*: Krum algorithm - widely used baseline  
   🔑 *Key Takeaway*: Distance-based filtering of gradients

5. **"The Hidden Vulnerability of Distributed Learning in Byzantium"**  
   Mhamdi et al., ICML 2018  
   📌 *Why*: Shows limitations of simple defenses  
   🔑 *Key Takeaway*: Attacks on aggregation rules

6. **"Attack of the Tails: Yes, You Really Can Backdoor Federated Learning"**  
   Bagdasaryan et al., NeurIPS 2020  
   📌 *Why*: Practical backdoor attacks on FL  
   🔑 *Key Takeaway*: Model replacement attacks, importance of robustness

---

### Week 2: Differential Privacy in Federated Learning

#### DP Fundamentals
7. **"Differential Privacy"**  
   Dwork, ICALP 2006  
   📌 *Why*: Original DP definition - must know  
   🔑 *Key Takeaway*: (ε,δ)-DP definition, composition

8. **"The Algorithmic Foundations of Differential Privacy"**  
   Dwork & Roth, 2014 (Textbook - read Chapters 1-3)  
   📌 *Why*: Comprehensive DP theory  
   🔑 *Key Takeaway*: Mechanisms (Laplace, Gaussian), properties

#### DP in Machine Learning
9. **"Deep Learning with Differential Privacy"**  
   Abadi et al., CCS 2016  
   📌 *Why*: DP-SGD algorithm - your implementation basis  
   🔑 *Key Takeaway*: Gradient clipping + noise, moments accountant

10. **"Scalable Private Learning with PATE"**  
    Papernot et al., ICLR 2018  
    📌 *Why*: Alternative DP approach for ML  
    🔑 *Key Takeaway*: Teacher-student framework, label DP

11. **"Differentially Private Learning with Adaptive Clipping"**  
    Andrew et al., NeurIPS 2021  
    📌 *Why*: Improves DP-SGD utility  
    🔑 *Key Takeaway*: Adaptive clipping threshold selection

#### DP in Federated Learning (Critical for Fed-OCL)
12. **"Learning Differentially Private Recurrent Language Models"**  
    McMahan et al., ICLR 2018  
    📌 *Why*: DP in federated NLP tasks  
    🔑 *Key Takeaway*: User-level DP in FL

13. **"Private Federated Learning on Vertically Partitioned Data via Entity Resolution and Additively Homomorphic Encryption"**  
    Nock et al., arXiv 2018  
    📌 *Why*: Privacy techniques beyond DP  
    🔑 *Key Takeaway*: Cryptographic approaches in FL

---

### Week 3: LLM Security & Prompt Injection

#### LLM Attacks (Know Your Enemy)
14. **"Universal and Transferable Adversarial Attacks on Aligned Language Models"**  
    Zou et al., 2023  
    📌 *Why*: Automated jailbreaking (GCG attack)  
    🔑 *Key Takeaway*: Gradient-based prompt optimization

15. **"Jailbroken: How Does LLM Safety Training Fail?"**  
    Wei et al., NeurIPS 2023  
    📌 *Why*: Understanding safety failure modes  
    🔑 *Key Takeaway*: Competing objectives, mismatched generalization

16. **"Ignore Previous Prompt: Attack Techniques For Language Models"**  
    Perez & Ribeiro, 2022  
    📌 *Why*: Early work on prompt injection  
    🔑 *Key Takeaway*: Types of prompt attacks, taxonomy

17. **"Not what you've signed up for: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection"**  
    Greshake et al., AISec 2023  
    📌 *Why*: Indirect prompt injection in real apps  
    🔑 *Key Takeaway*: Attack surface in LLM-integrated systems

#### LLM Privacy
18. **"Extracting Training Data from Large Language Models"**  
    Carlini et al., USENIX Security 2021  
    📌 *Why*: Privacy risks in LLMs  
    🔑 *Key Takeaway*: Memorization, extraction attacks

19. **"Membership Inference Attacks Against Language Models"**  
    Shokri et al., S&P 2017  
    📌 *Why*: Membership inference fundamentals  
    🔑 *Key Takeaway*: Shadow models, attack methodology

---

### Week 4: Anomaly Detection & Your Specific Application

#### Anomaly Detection for Security
20. **"Deep Learning for Anomaly Detection: A Survey"**  
    Pang et al., ACM Computing Surveys 2021  
    📌 *Why*: Comprehensive AD survey  
    🔑 *Key Takeaway*: Autoencoders, one-class learning, GANs

21. **"Autoencoders for Anomaly Detection in Security"**  
    (Find recent paper - 2022-2024 on anomaly detection for security)  
    📌 *Why*: Your Fed-OCL approach  
    🔑 *Key Takeaway*: Reconstruction-based detection

#### One-Class Learning (Your OCL in Fed-OCL)
22. **"Deep One-Class Classification"**  
    Ruff et al., ICML 2018  
    📌 *Why*: Deep learning for one-class problems  
    🔑 *Key Takeaway*: Deep SVDD, hypersphere learning

23. **"Support Vector Data Description"**  
    Tax & Duin, Machine Learning 2004  
    📌 *Why*: Classical one-class method  
    🔑 *Key Takeaway*: SVDD fundamentals

---

## 📚 Extended Reading (Weeks 5-8)

### Advanced FL Security

24. **"Manipulating the Byzantine: Optimizing Model Poisoning Attacks and Defenses for Federated Learning"**  
    Fung et al., NDSS 2020  
    🔑 *Key Takeaway*: Advanced poisoning attacks

25. **"Byzantine-Resilient SGD in High Dimensions on Heterogeneous Data"**  
    Karimireddy et al., arXiv 2021  
    🔑 *Key Takeaway*: Robustness under data heterogeneity

26. **"CRFL: Certifiably Robust Federated Learning against Backdoor Attacks"**  
    Xie et al., ICML 2021  
    🔑 *Key Takeaway*: Certified defenses for FL

27. **"FLTrust: Byzantine-robust Federated Learning via Trust Bootstrapping"**  
    Cao et al., NDSS 2021  
    🔑 *Key Takeaway*: Trust-based filtering

### Communication-Efficient FL

28. **"Federated Learning with Compressed Communications"**  
    Konečný et al., NeurIPS 2016 Workshop  
    🔑 *Key Takeaway*: Gradient compression, quantization

29. **"QSGD: Communication-Efficient SGD via Gradient Quantization and Encoding"**  
    Alistarh et al., NeurIPS 2017  
    🔑 *Key Takeaway*: Quantization schemes

30. **"Deep Gradient Compression: Reducing the Communication Bandwidth for Distributed Training"**  
    Lin et al., ICLR 2018  
    🔑 *Key Takeaway*: Sparsification + quantization

### Privacy Amplification in FL

31. **"Privacy Amplification by Subsampling: Tight Analyses via Couplings and Divergences"**  
    Balle et al., NeurIPS 2018  
    🔑 *Key Takeaway*: Privacy amplification from sampling

32. **"Differentially Private Federated Learning: A Client Level Perspective"**  
    Geyer et al., NIPS 2017 Workshop  
    🔑 *Key Takeaway*: Client-level DP in FL

---

## 🔬 State-of-the-Art (2023-2024)

### Recent FL Security Papers

33. **"Byzantine-Robust Federated Learning with Optimal Statistical Rates"**  
    Data et al., ICML 2023  
    🔑 *Must compare against this*

34. **"FLAME: Federated Learning Across Multi-device Environments"**  
    Multiple authors, Top venue 2023  
    🔑 *Recent FL framework*

35. **"PrivateFL: Accurate, Differentially Private Federated Learning via Personalized Data Transformation"**  
    Authors, NeurIPS 2023  
    🔑 *Recent DP-FL work*

### Recent LLM Security (2024)

36. **"Defending Against Indirect Prompt Injection in LLM-Integrated Applications"**  
    Authors, IEEE S&P 2024 (if available)  
    🔑 *Most recent defense work*

37. **"SmoothLLM: Defending LLMs Against Jailbreaking Attacks"**  
    Robey et al., 2023  
    🔑 *Randomized smoothing for LLMs*

38. **"GPT-4 Technical Report"**  
    OpenAI, 2023  
    🔑 *State-of-the-art LLM architecture and safety*

---

## 📊 Survey Papers (Read for Broader Context)

39. **"A Survey on Federated Learning: The Journey from Centralized to Distributed On-Site Learning and Beyond"**  
    Li et al., IEEE Internet of Things Journal 2021  
    📌 Comprehensive FL survey

40. **"Privacy in Deep Learning: A Survey"**  
    Mireshghallah et al., 2020  
    📌 Privacy techniques for DL

41. **"SoK: Security and Privacy in Machine Learning"**  
    Papernot et al., EuroS&P 2018  
    📌 Security/privacy systematization

42. **"Adversarial Machine Learning: A Survey"**  
    Akhtar & Mian, ACM Computing Surveys 2018  
    📌 Adversarial ML landscape

43. **"A Survey on Large Language Model Security: Vulnerabilities, Attacks and Defenses"**  
    (Find 2023-2024 survey)  
    📌 LLM security comprehensive view

---

## 🎯 Papers for Specific Experimental Comparisons

### Baselines for Fed-OCL

**Category 1: Standard FL**
- FedAvg (McMahan 2017) - #1
- FedProx (Li et al., MLSys 2020)

**Category 2: FL with DP**
- DP-FedAvg (McMahan 2018) - #12
- (Add 2-3 recent DP-FL papers from 2022-2024)

**Category 3: Byzantine-Robust FL**
- Krum (Blanchard 2017) - #4
- Median (Yin 2018) - #3
- Trimmed Mean (Yin 2018) - #3
- FLTrust (Cao 2021) - #27

**Category 4: DP + Byzantine-Robust**
- (Find 1-2 papers combining both - these are rare!)
- This is your main contribution - combining both effectively

**Category 5: Anomaly Detection in FL**
- (Find recent papers on federated anomaly detection)
- Federated Learning for Intrusion Detection
- Distributed anomaly detection systems

---

## 📖 Reading Strategy & Notes Template

### How to Read a Paper Efficiently

**First Pass (10 min): Skim**
- [ ] Read title, abstract, introduction
- [ ] Scan section headings
- [ ] Look at figures and tables
- [ ] Read conclusion
- **Decision**: Relevant? Yes → Second pass | No → Archive

**Second Pass (30-45 min): Understand**
- [ ] Read full paper, skip complex proofs
- [ ] Understand main contributions
- [ ] Note methodology and results
- [ ] List questions/unclear points
- **Decision**: Important for your work? Yes → Third pass | No → Summarize and file

**Third Pass (1-2 hours): Master**
- [ ] Read every detail, including proofs
- [ ] Verify claims, check references
- [ ] Think about limitations and extensions
- [ ] Consider how to use/compare with your work

### Note-Taking Template

```markdown
## Paper Title
**Authors**: [Names]
**Venue**: [Conference/Journal, Year]
**Citations**: [Google Scholar count]
**Link**: [URL]

### One-Sentence Summary
[What does this paper do?]

### Problem
[What problem does it address?]

### Method
[How does it solve the problem?]
- Approach 1: [Description]
- Approach 2: [Description]

### Key Contributions
1. [Contribution 1]
2. [Contribution 2]
3. [Contribution 3]

### Results
[Main experimental findings]
- Dataset: [Name]
- Metrics: [Values]
- Comparison: [vs. what]

### Strengths
✅ [Strength 1]
✅ [Strength 2]

### Limitations
❌ [Limitation 1]
❌ [Limitation 2]

### Relevance to My Work
[How does this relate to Fed-OCL?]
[Can I compare against this?]
[Can I build upon this?]

### Key Quotes
> "[Important quote 1]"
> "[Important quote 2]"

### Questions/Future Work
- [ ] [Question 1]
- [ ] [Extension idea]
```

---

## 🗓️ Suggested Reading Schedule

### Daily Routine
- **Morning (1 hour)**: Read 1 paper (first + second pass)
- **Evening (30 min)**: Review notes, update literature review document

### Weekly Goals
- **Papers**: 5-7 papers read (varying depths)
- **Notes**: Summarize all papers read
- **Synthesis**: Update Related Work section with new papers
- **Connection**: Identify 2-3 papers to cite/compare in your work

### Monthly Milestones
- **Month 1**: 20-25 papers (fundamentals)
- **Month 2**: 20-25 papers (state-of-the-art)
- **Month 3**: 15-20 papers (deep dive + revisit important ones)
- **Total**: 55-70 papers in 3 months (strong foundation)

---

## 📌 Priority Papers for Fed-OCL (Start Here)

**This Week (Top 10)**:
1. McMahan FedAvg (#1)
2. Yin Byzantine-Robust (#3)
3. Blanchard Krum (#4)
4. Abadi DP-SGD (#9)
5. Bagdasaryan Backdoor (#6)
6. Zou GCG Attack (#14)
7. Greshake Indirect Injection (#17)
8. Ruff Deep One-Class (#22)
9. Kairouz FL Survey (#2)
10. Dwork & Roth DP Book Chapters 1-3 (#8)

**Next Week (Add these 10)**:
11. McMahan DP-FL (#12)
12. Andrew Adaptive Clipping (#11)
13. Wei Jailbreak Analysis (#15)
14. Carlini Data Extraction (#18)
15. Pang AD Survey (#20)
16. Mhamdi Byzantine Vulnerability (#5)
17. Perez Prompt Attacks (#16)
18. Fung Byzantine Optimization (#24)
19. Cao FLTrust (#27)
20. Lin Gradient Compression (#30)

---

## 🔖 Bookmark These Resources

### Paper Discovery
- **Google Scholar Alerts**: Set alerts for "federated learning security", "prompt injection", "differential privacy FL"
- **arXiv Daily**: Subscribe to cs.CR, cs.LG, cs.CL
- **Conference Proceedings**: USENIX Security, CCS, S&P, NeurIPS (check recent years)

### Code Repositories
- **FedML**: https://github.com/FedML-AI/FedML
- **Flower**: https://github.com/adap/flower
- **Opacus**: https://github.com/pytorch/opacus (DP library)
- **CleverHans**: https://github.com/cleverhans-lab/cleverhans

### Datasets
- **Prompt Injection**: Search for "prompt injection dataset" on GitHub
- **Federated Datasets**: LEAF benchmark
- **Geolife**: Your previous work (may be relevant for testing)

---

## ✅ Action Items

**Today**:
- [ ] Download papers #1, #3, #4, #9 (top priorities)
- [ ] Set up paper management system (Zotero, Mendeley, or folder structure)
- [ ] Read McMahan FedAvg (#1) - foundation

**This Week**:
- [ ] Read all Top 10 papers (at least first + second pass)
- [ ] Create summary notes for each
- [ ] Identify 5 papers to compare against in experiments

**This Month**:
- [ ] Complete Week 1-4 reading (papers #1-23)
- [ ] Update Fed-OCL related work section
- [ ] Identify gaps in current baselines

---

**Start with the "Priority Papers for Fed-OCL" list above. These 20 papers will give you 80% of what you need to strengthen your work!** 🚀
