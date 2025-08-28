- --definicia
- Útoky zneužívajúce dôveru v externé komponenty (modely, datasety, knižnice, pluginy) použité v AI systémoch.
  Útok zasahuje komponenty modelu ešte pred jeho nasadením, čím ohrozuje inferenčné prostredie bez priameho prístupu k nemu.
- LLM supply chains are susceptible to various vulnerabilities, which can affect the integrity of training data, models, and deployment platforms. These risks can result in biased outputs, security breaches, or system failures. While traditional software vulnerabilities focus on issues like code flaws and dependencies, in ML the risks also extend to third-party pre-trained models and data. [zdroj](https://genai.owasp.org/llmrisk/llm032025-supply-chain/)
-
- --zaradenie
- Lifecycle:      `artifacts_supply` / `training` / `data_pipeline`
- Harm:            `integrity` / `privacy`
- LLM tag:        [LLM03: 2025 Supply Chain Vulnerabilities ](https://genai.owasp.org/llmrisk/llm032025-supply-chain/)
-
- -- ako utok prebieha
-
- vkladanie backdoor alebo skodlive spravanie:
	- pretrained models from opensource repositories (Hugging Face, Github)
	- datasets with triggers (clean-label backdoor)
	- [Python Package Index (PyPI)](https://blog.orsinium.dev/posts/py/pypi-squatting/) and [Node Package Manager (npm)](https://blog.sonatype.com/pypi-and-npm-flooded-with-over-5000-dependency-confusion-copycats) (typosquatting, dependency confusion)
	- pluging and AI agents with own code [zdroj](https://protectai.com/threat-research/unveiling-ai-supply-chain-attacks-on-hugging-face)
-
- Risks:
	- #### [Traditional Third-party Package Vulnerabilities](https://github.com/OWASP/www-project-top-10-for-large-language-model-applications/blob/main/2_0_vulns/LLM03_SupplyChain.md#1-traditional-third-party-package-vulnerabilities)
	- ####   [Vulnerable Pre-Trained Model](https://github.com/OWASP/www-project-top-10-for-large-language-model-applications/blob/main/2_0_vulns/LLM03_SupplyChain.md#4-vulnerable-pre-trained-model)
	- #### [Vulnerable LoRA adapters](https://github.com/OWASP/www-project-top-10-for-large-language-model-applications/blob/main/2_0_vulns/LLM03_SupplyChain.md#6-vulnerable-lora-adapters)
	- #### [Unclear T&Cs and Data Privacy Policies](https://github.com/OWASP/www-project-top-10-for-large-language-model-applications/blob/main/2_0_vulns/LLM03_SupplyChain.md#9-unclear-tcs-and-data-privacy-policies)
	- [zdroj](https://genai.owasp.org/llmrisk/llm032025-supply-chain/)
-
- --mitigation strategies
- First, companies need to treat AI integrations the same way they treat 
  any other third-party dependency—with skepticism until proven otherwise.
   That means doing full vetting before bringing in an external AI model, 
  tool, or service. It’s not enough to assume that because something is 
  open-source, widely used, or offered by a known provider, it’s safe. Vet
   the model’s origin, scrutinize the data sources it was trained on, and 
  if possible, run security testing against it before deploying it in 
  production environments
- -- priklady/scenarios
- https://owasp.org/www-project-machine-learning-security-top-10/docs/ML06_2023-AI_Supply_Chain_Attacks
-