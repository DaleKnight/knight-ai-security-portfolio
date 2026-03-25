
## 🚧 In Progress – AI-102: Azure AI Engineer Associate  
### Exploring Secure AI Architecture & Prompt Governance

As organizations integrate Azure OpenAI and AI-driven copilots into enterprise environments, understanding how model behavior is shaped becomes critical. This lab demonstrates how system-level prompt configuration alone can materially influence model output, even when user input remains identical.

**Environment**
- Platform: Microsoft Foundry (Azure AI)
- Model: GPT-4o
- Deployment: Default configuration
- Variable changed: System prompt only


## 🎭 Prompt Conditioning Demonstration

### Test Scenario

**User Prompt (unchanged in both runs):**

> Explain prompt injection in simple terms and give 3 defensive controls an organization should implement.

Only the system-level instructions were modified.

---

### 🧪 Example 1 – Structured Scientific Tone (Doc Brown Conditioning)

**System Prompt Configuration**

![Doc Brown System Prompt](../images/ai102/ai102-doc-brown-system-prompt.png)

**Model Output**

![Doc Brown Output](../images/ai102/ai102-doc-brown-model-output.png)

---

### 🧪 Example 2 – Inverted Minimalist Tone (Yoda Conditioning)

**System Prompt Configuration**

![Yoda System Prompt](../images/ai102/ai102-yoda-system-prompt.png)

**Model Output**

![Yoda Output](../images/ai102/ai102-yoda-model-output.png)

---

## 🔎 Observation: Impact of Prompt Conditioning

Using identical user input, modifying only the system-level prompt resulted in significantly different tone, structure, and emphasis in the model’s response.

This demonstrates that LLM behavior can be materially influenced by upstream instructions, reinforcing the importance of:

- Prompt injection protections  
- Strict control over system prompt modification  
- Output validation and guardrails  
- Logging and monitoring AI configuration changes  

*In enterprise deployments, prompt configuration becomes part of the security boundary.*
