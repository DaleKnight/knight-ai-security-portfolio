# Secure Content Filtering + Guardrail Enforcement with Azure AI Foundry

## Validating Responsible AI Guardrails and Content Safety Controls

Building enterprise AI securely requires more than model deployment—it requires guardrails that actively prevent harmful, unsafe, or policy-violating interactions.

This lab demonstrates how Azure AI Foundry Content Filtering and Guardrail Controls enforce security boundaries by detecting and blocking harmful prompts, unsafe outputs, jailbreak attempts, and protected material violations.

Rather than relying solely on model behavior, security controls were configured at both the input and output layers to strengthen governance and reduce misuse risk.

This approach supports responsible AI deployment by ensuring models operate within approved safety boundaries and organizational policy.

---

## Environment

- Platform: Microsoft Azure AI Foundry
- Model: GPT-4.1
- Service: Azure OpenAI + Foundry Guardrails
- Security Controls: Content Safety + Guardrail Enforcement
- Protection Scope: User Input + Model Output
- Security Focus: Harm prevention + abuse prevention + prompt governance

---

## Guardrail Configuration

### Configured Security Controls

The following protections were enabled:

- Hate Content Filtering
- Violence Content Filtering
- Self-Harm Detection
- Sexual Content Filtering
- Jailbreak Detection
- Protected Material Detection (Code + Text)
- Input + Output Intervention Points
- Block Action Enforcement

All major content safety categories were configured for highest blocking severity to prioritize security-first behavior.

### Guardrail Control Creation

![Guardrail Configuration](../images/ai102/configuringcontentfilteringcontrols.png)

### Final Guardrail Review

This final review confirms:

- highest blocking severity enabled
- user input and output enforcement
- block action configured
- jailbreak detection active
- protected materials enforcement enabled

![Guardrail Review](../images/ai102/configuringcontentfilteringcontrols2.png)

---

## Microsoft Learn Validation Reference

These validation prompts were performed using Microsoft Learn guided exercises to test Azure AI Foundry safety controls and responsible AI guardrails.

The purpose was to validate filtering behavior, harmful content detection, and secure model response enforcement—not prompt misuse.

![Microsoft Learn Reference](../images/ai102/contentfilteringdisclaimer.png)

---

## Guardrail Enforcement Demonstration

### Successful Input Blocking

Prompts involving harmful intent, self-harm references, and violence-related requests were successfully blocked by the configured guardrails.

Examples included:

- violent intent
- self-harm prompts
- offensive content requests

The platform correctly identified risk type, blocked unsafe interaction, and prevented unsafe model output.

### Live Guardrail Response

This demonstrates:

- harmful prompt detection
- policy enforcement
- blocked unsafe interaction
- safe response redirection
- operational content safety validation

![Blocked Interaction Example](../images/ai102/contentfilteringoutput1.png)

---

## Observation: Why Guardrails Matter

The strongest validation was not when the model answered correctly—it was when it refused unsafe requests.

Security architecture for AI is not just about what a model can do.

It is about defining what it must never do.

By enforcing content filtering and guardrail controls, organizations reduce:

- prompt abuse
- model misuse
- unsafe outputs
- policy violations
- reputational risk
- governance failures

Guardrails are not optional—they are part of secure AI architecture.

---

## Reference

These labs were completed using Microsoft Learn guided exercises as a foundation for validating Azure AI Engineer Associate (AI-102) concepts.

The focus of this portfolio is not lab completion alone, but secure implementation, governance, and practical enterprise application through an AI security architecture perspective.
