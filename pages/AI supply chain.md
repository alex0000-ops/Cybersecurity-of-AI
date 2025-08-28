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
- This opacity makes them susceptible to malicious manipulation, such as backdoors introduced during training or fine-tuning phases, model conversion.These backdoors typically remain dormant under normal conditions, only activating when specific triggers are introduced, leading to behaviors such as data leakage, misclassification, or unauthorized actions. Traditional security measures, including Software Bills of Materials (SBOMs) and static code analysis tools, are ill-suited to detect such threats within AI models.[zdroj](https://www.trendmicro.com/vinfo/nl/security/news/cybercrime-and-digital-threats/exploiting-trust-in-open-source-ai-the-hidden-supply-chain-risk-no-one-is-watching)
-
- vkladanie backdoor alebo skodlive spravanie:
	- pretrained models from opensource repositories (Hugging Face, Github)
	- datasets with triggers (clean-label backdoor)
	- [Python Package Index (PyPI)](https://blog.orsinium.dev/posts/py/pypi-squatting/) and [Node Package Manager (npm)](https://blog.sonatype.com/pypi-and-npm-flooded-with-over-5000-dependency-confusion-copycats) (typosquatting, dependency confusion)
	- pluging and AI agents with own code [zdroj](https://protectai.com/threat-research/unveiling-ai-supply-chain-attacks-on-hugging-face)
-
- **1. Attacks on the training phase: corrupting the foundation**
	- Data poisoning: - Example: GPT-based chatbots intentionally trained with 
	  id:: 68b05ee9-89b4-426e-8707-ff51ff8184f6
	  poisoned dialogue that triggers unsafe behavior when prompted with 
	  specific inputs.
	- Label poisoning: - Example: A sentiment analysis model is fine-tuned with 
	  reviews where positive text about a competitor's product is 
	  intentionally mislabeled as "negative."
	-
- **2. Attacks on the storage and distribution (supply chain) phase: post-training tampering**
  These attacks exploit weaknesses in the way models are stored, shared, and distributed — occurring after the model has been trained but before it is deployed.
	- Weight-level manipulation: - Example: A malware is inserted by modifying a small set
	   of model weights, by embedding arbitrary binary malware code directly into the least significant bits of a neural network's pre-trained model weights,  allowing the hidden malware to be covertly distributed within seemingly benign AI models, with minimal impact on the model's performance.
-
- **3. Attacks on the loading and deployment phase: exploiting the runtime environment**
- Remote code execution (RCE) via deserialization: Some model formats (e.g., Python's pickle and older PyTorch *.pt* files) are inherently capable of executing code. Attackers embed malicious 
  code into the serialized model file, which runs on the server when the 
  model is loaded. - Example: A payload embedded in a *.pkl* file that opens a reverse shell back to the attacker's machine upon loading.
-
- Risks:
	- #### [Traditional Third-party Package Vulnerabilities](https://github.com/OWASP/www-project-top-10-for-large-language-model-applications/blob/main/2_0_vulns/LLM03_SupplyChain.md#1-traditional-third-party-package-vulnerabilities)
	- ####   [Vulnerable Pre-Trained Model](https://github.com/OWASP/www-project-top-10-for-large-language-model-applications/blob/main/2_0_vulns/LLM03_SupplyChain.md#4-vulnerable-pre-trained-model)
	- #### [Vulnerable LoRA adapters](https://github.com/OWASP/www-project-top-10-for-large-language-model-applications/blob/main/2_0_vulns/LLM03_SupplyChain.md#6-vulnerable-lora-adapters)
	- #### [Unclear T&Cs and Data Privacy Policies](https://github.com/OWASP/www-project-top-10-for-large-language-model-applications/blob/main/2_0_vulns/LLM03_SupplyChain.md#9-unclear-tcs-and-data-privacy-policies)
	- [zdroj](https://genai.owasp.org/llmrisk/llm032025-supply-chain/)
-
- --mitigation strategies
- First, companies need to treat AI integrations the same way they treat any other third-party dependency—with skepticism until proven otherwise. That means doing full vetting before bringing in an external AI model, tool, or service. Vet the model’s origin, scrutinize the data sources it was trained on, and if possible, run security testing against it before deploying it in production environments.
- Second, organizations should harden their development and deployment pipelines. That includes using Software Bills of Materials (SBOMs). Knowing exactly what models, datasets, and libraries are embedded in your systems—and tracking changes over time—makes it harder for malicious updates or poisoned models to slip through unnoticed.
- Third, API integrations need to be treated with real caution. External AI services shouldn’t be given unchecked access deep into critical systems. Implement strict access controls, monitor API traffic 
  for anomalies, and be ready to pull the plug if an external service starts behaving strangely.
- Fourth, organizations need to extend threat detection and monitoring to include AI behaviors. That means setting up systems that can spot when an AI model suddenly starts behaving in ways that weren’t part of its intended function. Unexpected outputs, unusual data requests, strange 
  error patterns—these could be early warning signs of tampering or compromise. [zdroj](https://www.offsec.com/blog/ai-and-supply-chain-attacks/)
-
- -- priklady/scenarios
- https://owasp.org/www-project-machine-learning-security-top-10/docs/ML06_2023-AI_Supply_Chain_Attacks
-