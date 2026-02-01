<div align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=28&duration=3000&pause=1000&color=58A6FF&center=true&vCenter=true&width=500&lines=M.Tech+Researcher;Architecting+Privacy-Preserving+AI;Defending+LLM+Agents;Building+Trustworthy+Systems" alt="Typing SVG" />
</div>

<div align="center">
  <a href="https://www.linkedin.com/in/gagandeep-singh-dev/">
    <img src="https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
  <a href="mailto:gagandeep.singh.1290j@gmail.com">
    <img src="https://img.shields.io/badge/Email-Contact_Me-D14836?style=for-the-badge&logo=gmail&logoColor=white" />
  </a>
</div>

<br />

<div align="center">
  <h3>👨‍🔬 Research Focus</h3>
  <p>I am a researcher bridging the gap between theoretical <b>Differential Privacy</b> and deployable <b>AI defense systems</b>. My work focuses on securing <b>Large Language Model (LLM) agents</b> against adversarial attacks using privacy-preserving architectures.</p>
</div>

---

### 🛡️ Featured System: Fed-OCL Framework
**Paper:** *Federated Anomaly Detection: Collaborative Prompt Injection Defense without Data Sharing* (Targeting CCS 2026)

This diagram represents the **Privacy-Preserving Data Flow** I designed for securing distributed LLM agents:

```mermaid
graph LR
    subgraph "Security Silo (Client Side)"
    A[🤖 User Query] -->|Input| B(Local LLM Agent);
    B -->|Detection| C{Anomaly Filter};
    C -->|Gradients| D[🔒 DP-SGD Engine];
    D -->|Noise Injection| E[Clipped Gradients];
    end

    subgraph "Secure Aggregation (Server)"
    E -->|Encrypted Update| F[🛡️ Secure Aggregator];
    F -->|Weighted Avg| G((Global Defense Model));
    end

    G -.->|Updated Weights| B;
    
    style D fill:#f9f,stroke:#333,stroke-width:2px
    style F fill:#bbf,stroke:#333,stroke-width:2px
---

### 📚 Selected Publications

| Status | Title | Focus Area |
| :--- | :--- | :--- |
| **[Draft]** | *Federated Anomaly Detection: Collaborative Prompt Injection Defense* | 🛡️ **LLM Security** |
| **[In Press]** | *A Hybrid Differential Privacy Framework for LBS* | 📍 **Differential Privacy** |
| **[Submitted]** | *Explainable Anomaly Detection for Secure CI/CD* | 🔍 **XAI / System Security** |

---

### 🛠️ Research Arsenal
<div align="center">
  <img src="https://skillicons.dev/icons?i=python,pytorch,tensorflow,docker,kubernetes,azure,git,latex,linux&theme=dark" />
  <br/>
  <br/>
  <img src="https://img.shields.io/badge/Privacy-Opacus_(DP)-blue?style=flat-square&logo=security" />
  <img src="https://img.shields.io/badge/Federated-Flower_(Flwr)-green?style=flat-square&logo=leaf" />
  <img src="https://img.shields.io/badge/Attacks-Adversarial_Toolbox-red?style=flat-square&logo=target" />
</div>

<br/>

<div align="center">
  <img src="https://raw.githubusercontent.com/GaganRajput21/GaganRajput21/output/github-contribution-grid-snake.svg" alt="snake animation" />
</div>

<div align="center">
  <br />
  <i>"Security is not a product, but a process." — Bruce Schneier</i>
</div>
