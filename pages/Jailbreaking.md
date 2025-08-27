- ![image.png](../assets/image_1753267609139_0.png) [image 2](https://learnprompting.org/blog/injection_jailbreaking)
-
- **Jailbreaking** is the process of coercing an LLM without any developer instructions to produce
   unintended outputs through adversarial prompts. Jailbreaking involves bypassing safety mechanisms in LLMs that are designed to prevent harmful outputs. Jailbreak Prompts exploit vulnerabilities in the model's safety filters,often by using contextual manipulation, roleplay scenarios, or 
  alignment hacking. [1](https://learnprompting.org/blog/injection_jailbreaking)
	- ####  DAN (Do Anything Now) Prompt
		- ![image.png](../assets/image_1756324334763_0.png) [zdroj](https://blog-en.fltech.dev/entry/2024/12/12/mlt_scrty_en)
	- #### Roleplay Manipulation
	- #### Pretending as Another System
	  
	  *Crescendo technique
-
- ![image.png](../assets/image_1756324712708_0.png)
-
- A “classic” jailbreak happens when an authorized operator of the system crafts jailbreak inputs in order to extend their own powers over the 
  system. [2](https://www.microsoft.com/en-us/security/blog/2024/06/04/ai-jailbreaks-what-they-are-and-how-they-can-be-mitigated/)
- Indirect prompt injection happens when a system processes data  controlled by a third party (e.g., analyzing incoming emails or documents editable by someone other than the operator) who inserts a 
  malicious payload into that data, which then leads to a jailbreak of the system. [2](https://www.microsoft.com/en-us/security/blog/2024/06/04/ai-jailbreaks-what-they-are-and-how-they-can-be-mitigated/)
-
- ![image.png](../assets/image_1753268259544_0.png) [image 2]({{twitter https://x.com/KGreshake/status/1747408112309485703}})
-
- AI safety and security risks:
	- Unauthorized data access
	- Sensitive data exfiltration
	- Model evasion
	- Generating ransomware
	- Circumventing individual policies or compliance systems [2](https://www.microsoft.com/en-us/security/blog/2024/06/04/ai-jailbreaks-what-they-are-and-how-they-can-be-mitigated/)
-
-
- Responsible AI risks:
	- Producing content that violates policies (e.g., harmful, offensive, or violent content)
	- Access to dangerous capabilities of the model (e.g., producing actionable instructions for dangerous or criminal activity)
	- Subversion of decision-making systems (e.g., making a loan application or hiring system produce attacker-controlled decisions)
	- Causing the system to misbehave in a newsworthy and screenshot-able way
	- IP infringement [2](https://www.microsoft.com/en-us/security/blog/2024/06/04/ai-jailbreaks-what-they-are-and-how-they-can-be-mitigated/)
-
- good [article](https://www.microsoft.com/en-us/security/blog/2024/06/04/ai-jailbreaks-what-they-are-and-how-they-can-be-mitigated/) about MS mitigation and protection guidance for their AI products
-
- ![image.png](../assets/image_1753725593697_0.png) [image 3](https://machine-learning-made-simple.medium.com/an-introduction-to-adversarial-perturbation-5e6c61d84b71)
-