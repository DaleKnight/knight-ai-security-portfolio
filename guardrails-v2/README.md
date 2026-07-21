# 🛡️ Azure AI Foundry Guardrails
### Applying Zero Trust Principles to Enterprise AI

![Microsoft_Foundry](https://img.shields.io/badge/Microsoft%20Foundry-0078D4?style=for-the-badge&logo=microsoftazure)
![Azure OpenAI](https://img.shields.io/badge/Azure%20OpenAI-GPT--5-10A37F?style=for-the-badge)
![AI Security](https://img.shields.io/badge/Focus-AI%20Security-blue?style=for-the-badge)
![Zero Trust](https://img.shields.io/badge/Methodology-Zero%20Trust-success?style=for-the-badge)

**Demonstrating how Azure AI Foundry Guardrails can be implemented and validated using Zero Trust principles.**

---

## Executive Summary

This repository documents the design, implementation, and validation of layered security controls for an enterprise AI assistant using Azure AI Foundry Guardrails.

The objective was not simply to enable security features, but to verify that each control behaved as expected under representative attack scenarios. The implementation follows a Zero Trust mindset. 

Never Trust. Always Verify.

Security controls were configured, challenged, and documented using both the Azure AI Foundry Playground and a published Preview Web App.

---

## Quick Facts

| Category | Details |
|---|---|
| **Platform** | Microsoft Foundry |
| **Model** | Azure OpenAI GPT-5 |
| **Primary Focus** | Enterprise AI Security |
| **Methodology** | Zero Trust and Defense in Depth |
| **Validation** | Foundry Playground and Preview Web App |
| **Project Status** | ✅ Complete |

---

## Solution Architecture

[![Microsoft Foundry Guardrails solution architecture](images/architecture/guardrails-architecture.png)](images/architecture/guardrails-architecture.png)

*Figure 1. Layered Microsoft Foundry Guardrails architecture showing security controls applied before and after model interaction.*

---

## Objectives

- Apply Zero Trust principles to enterprise AI security.
- Prevent jailbreak and prompt injection attacks.
- Reduce risk from untrusted or externally sourced content.
- Detect and block sensitive information.
- Enforce organization-specific security policies.
- Validate every implemented control using representative tests.
- Document architecture, implementation choices, and test results.

---

## Security Flow

```text
User Prompt
    │
    ▼
Azure AI Foundry Guardrails
    │
    ├── Prompt Shields
    ├── Spotlighting
    ├── PII Detection
    ├── Custom Blocklists
    ├── Content Safety
    └── Protected Materials
    │
    ▼
Azure OpenAI GPT-5
    │
    ▼
Guardrailed Response
```

---

## Security Controls

| Security Control | Purpose | Status |
|---|---|:---:|
| **Jailbreak Detection** | Detect attempts to override system instructions or alter intended model behavior. | ✅ |
| **Prompt Injection Protection** | Detect direct and indirect prompt injection attempts. | ✅ |
| **Spotlighting (Preview)** | Distinguish trusted instructions from untrusted content to strengthen indirect prompt injection defenses. | ✅ |
| **Content Safety** | Filter harmful or unsafe categories of content. | ✅ |
| **Protected Materials** | Reduce generation of protected text and source code. | ✅ |
| **Custom Blocklists** | Enforce organization-specific policy restrictions. | ✅ |
| **PII Detection (Preview)** | Detect and block selected categories of personally identifiable information. | ✅ |
| **Task Adherence (Preview)** | Help keep agents aligned to their intended task and reduce task drift in multi-step workflows. | Evaluated |

---

## Notable Platform Capabilities

This implementation also explored several Azure AI Foundry capabilities that provide more precise control over enterprise AI security and governance.

| Capability | Description |
|---|---|
| **PII Granularity (Preview)** | Supports more precise policy enforcement by allowing individual PII categories to be selected rather than treating all sensitive information as a single broad class. |
| **Indirect Prompt Injection Intervention Points** | Allows protective actions to be applied at specific stages of an interaction, improving control over how suspicious content is handled. |
| **Spotlighting (Preview)** | Helps separate trusted instructions from untrusted data, such as retrieved documents or external content, to reduce the effectiveness of embedded indirect prompt injection attempts. |
| **Protected Materials** | Helps reduce the generation of protected text and source code. |
| **Task Adherence (Preview)** | Helps agents remain focused on their intended objective and reduces the risk of task drift during multi-step or tool-enabled workflows. It was evaluated but intentionally not enabled for this implementation. |

---

## Security Implementation

> **🛡️ Zero Trust**
>
> Security controls were not considered effective simply because they were enabled. Each implemented control was intentionally tested to confirm expected behavior.

### Jailbreak Detection and Prompt Injection

Jailbreak detection and Prompt Shields were configured to identify instruction-override attempts and malicious content intended to influence model behavior.

[![Jailbreak and indirect prompt injection configuration](images/configuration/jailbreak-indirect-prompt-injection.png)](images/configuration/jailbreak-indirect-prompt-injection.png)

*Figure 2. Azure AI Foundry Guardrails configured to detect jailbreak attempts and indirect prompt injection before model execution.*

---

### Spotlighting (Preview)

Spotlighting helps distinguish trusted instructions from untrusted content. This is particularly useful when AI systems process retrieved documents, external data, or other content that may contain embedded instructions intended to manipulate the model.

[![Spotlighting preview configuration](images/configuration/spotlighting-preview.png)](images/configuration/spotlighting-preview.png)

*Figure 3. Spotlighting enabled to strengthen defenses against indirect prompt injection contained in untrusted data.*

---

### Custom Blocklists

Custom blocklists were configured to enforce organization-specific restrictions beyond the platform's default safety controls.

[![Custom blocklist configuration](images/configuration/custom-blocklist-configuration.png)](images/configuration/custom-blocklist-configuration.png)

*Figure 4. Custom blocklist configuration used to enforce organization-specific AI usage policy.*

---

### PII Detection (Preview)

PII detection was configured with fine-grained entity selection and intervention points. This provides greater control over the categories of sensitive information that should trigger a security response.

| PII Detection Configuration | Intervention Points |
|---|---|
| [![PII detection configuration](images/configuration/pii-detection-configuration.png)](images/configuration/pii-detection-configuration.png) | [![PII intervention points](images/configuration/pii-intervention-points.png)](images/configuration/pii-intervention-points.png) |

*Figure 5. Fine-grained PII detection configuration and intervention points used to determine where sensitive information controls are enforced.*

#### Granular Entity Selection

All available PII entity types were reviewed and selected for testing.

[![PII granular entity selection](images/configuration/pii-granular-entity-selection.png)](images/configuration/pii-granular-entity-selection.png)

*Figure 6. Granular PII entity selection providing more precise control over sensitive information detection.*

---

### Task Adherence (Preview)

Task Adherence is intended to help keep agents aligned to their assigned objective and reduce task drift during multi-step interactions.

This control was reviewed but intentionally not enabled because the project does not invoke external tools or autonomous agent workflows.

[![Task Adherence preview](images/configuration/task-adherence-preview.png)](images/configuration/task-adherence-preview.png)

*Figure 7. Task Adherence reviewed as a potential control for future tool-enabled or agentic workloads.*

---

## Validation Methodology

> **🔬 Validation**
>
> Security was treated as a verification process rather than a configuration exercise. Each control was tested using representative prompts designed to confirm both allowed and blocked behavior.

Validation included:

- Legitimate business prompts.
- Jailbreak attempts.
- Direct and indirect prompt injection.
- Organization-specific blocked terms.
- Sensitive information and PII.
- Published Preview Web App testing.
- Confirmation that expected requests continued to function normally.

---

## Security Validation Results

| Test Scenario | Expected Result | Outcome |
|---|---|:---:|
| Legitimate business prompt | Allow | ✅ |
| Jailbreak attempt | Block | ✅ |
| Prompt injection attempt | Block | ✅ |
| Custom blocklist term | Block | ✅ |
| PII submission | Block | ✅ |
| Published Preview Web App | Guardrails remain effective | ✅ |

---

## Foundry Playground Validation

### Legitimate Prompt Allowed

A legitimate request was submitted to confirm that expected business use remained functional after guardrails were applied.

[![Legitimate prompt allowed](images/validation/playground-legitimate-prompt-allowed.png)](images/validation/playground-legitimate-prompt-allowed.png)

*Figure 8. Legitimate prompt successfully processed, confirming that the guardrails did not unnecessarily block expected usage.*

---

### Jailbreak Attempt Blocked

A jailbreak-style prompt was submitted to test whether the model could be persuaded to ignore its assigned instructions.

[![Jailbreak attempt blocked](images/validation/playground-jailbreak-blocked.png)](images/validation/playground-jailbreak-blocked.png)

*Figure 9. Jailbreak attempt successfully detected and blocked by the configured guardrails.*

---

### Custom Blocklist Enforcement

A prompt containing organization-specific blocked terms was submitted to verify custom policy enforcement.

[![Custom blocklist blocked](images/validation/playground-custom-blocklist-blocked.png)](images/validation/playground-custom-blocklist-blocked.png)

*Figure 10. Custom blocklist terms successfully detected and blocked during Foundry Playground validation.*

---

### PII Detection

Sensitive information was submitted to verify that the selected PII categories and intervention settings produced the expected response.

[![PII blocked](images/validation/playground-pii-blocked.png)](images/validation/playground-pii-blocked.png)

*Figure 11. Sensitive information successfully detected and blocked using the configured PII controls.*

---

## Published Preview Web App Validation

The protected assistant was published using the Azure AI Foundry Preview Web App to validate that guardrails remained effective outside the Playground.

### Initial Web App and Prompt Injection Test

| Initial Web App | Prompt Injection Blocked |
|---|---|
| [![Initial web app](images/validation/web-app-initial-screen.png)](images/validation/web-app-initial-screen.png) | [![Prompt injection blocked](images/validation/web-app-prompt-injection-blocked.png)](images/validation/web-app-prompt-injection-blocked.png) |

*Figure 12. Published Preview Web App and successful blocking of a prompt injection attempt.*

---

### Custom Blocklist and PII Validation

| Custom Blocklist Blocked | PII Blocked |
|---|---|
| [![Web app custom blocklist blocked](images/validation/web-app-custom-blocklist-blocked.png)](images/validation/web-app-custom-blocklist-blocked.png) | [![Web app PII blocked](images/validation/web-app-pii-blocked.png)](images/validation/web-app-pii-blocked.png) |

*Figure 13. Custom blocklist and PII controls remained effective after the assistant was published through the Preview Web App.*

---

## Design Decisions

> **🏗️ Design Principle**
>
> Security capabilities should be selected because they align with the application's architecture and risk model—not simply because they are available.

| Design Decision | Why It Matters |
|---|---|
| **Zero Trust Validation** | Controls were verified through representative attack scenarios instead of being assumed effective after configuration. |
| **Defense in Depth** | Multiple independent controls provide layered protection against different classes of AI risk. |
| **Fine-Grained PII Controls** | Granular entity selection enables more precise policy enforcement and reduces dependence on broad, all-or-nothing classifications. |
| **Spotlighting** | Separating trusted instructions from untrusted content strengthens defenses against indirect prompt injection. |
| **Task Adherence** | Evaluated but intentionally left disabled because this implementation does not use tools or autonomous agent workflows. |
| **Evidence-Based Testing** | Each implemented control includes documented evidence demonstrating expected behavior. |

---

## Technologies

- Azure AI Foundry
- Azure AI Foundry Guardrails
- Azure OpenAI GPT-5
- Azure AI Content Safety
- Prompt Shields
- Spotlighting (Preview)
- Custom Blocklists
- PII Detection (Preview)
- Protected Materials
- Task Adherence (Preview)

---

## Final Thoughts

Implementing AI guardrails is only one part of securing enterprise AI. Equally important is validating that those controls behave as expected under realistic conditions.

Throughout this project, each configured security control was intentionally tested rather than assumed effective based solely on configuration. That validation-first mindset reflects a practical application of Zero Trust: trust is not configured; it is earned through verification.

One of the most notable aspects of this implementation was the increased granularity now available for PII detection. The ability to select specific sensitive data categories provides organizations with more precise policy options than broad, all-or-nothing controls.

The inclusion of **Spotlighting (Preview)** is also an important step forward. As enterprise AI systems increasingly process retrieved documents and external content, the ability to distinguish trusted instructions from untrusted data can strengthen defenses against indirect prompt injection.

**Task Adherence (Preview)** is another valuable capability, particularly for agentic systems that perform multi-step tasks or invoke tools. Although it was intentionally not enabled for this project, reviewing the feature reinforced an important architectural principle: a security control should be used when it aligns with the application's design and risk model—not simply because it exists.

Together, fine-grained PII controls, Spotlighting, and Task Adherence demonstrate the platform's continued movement toward more context-aware, policy-driven governance for enterprise AI workloads.

> **AI is optional. Security is mandatory. Security may evolve, but it is never optional or an afterthought.**
