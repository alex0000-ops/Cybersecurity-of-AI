- Evasion attacks involve subtly modifying inputs (images, audio files, 
  documents, etc.) to mislead models at inference time, making them a 
  stealthy and effective means of bypassing a control system.
  
  The attack’s objective is to generate an input that is misclassified 
  without needing to understand the AI model's internal mechanisms, making
   evasion attacks stealthy and particularly difficult to counter. [1](https://mindgard.ai/blog/ai-under-attack-six-key-adversarial-attacks-and-their-consequences)
-
- why evasion attack matter:
	- Affecting security systems, including facial recognition or intrusion detection systems.
	- Impacting autonomous vehicles by altering input data.
	- Affecting financial models that detect fraudulent transactions. [2](https://www.startupdefense.io/cyberattacks/evasion-attacks-ml)
-
- how attack work:
	- **Identifying the target model**
	- **Crafting adversarial examples**
	- **Testing and refining** [2](https://www.startupdefense.io/cyberattacks/evasion-attacks-ml)
-
- Evasion attacks occur after the machine learning model has been trained 
  and deployed. This is a key differentiator because, unlike poisoning 
  attacks, which affect the training phase, or model-stealing attacks, 
  which attempt to duplicate a model, evasion attacks happen during 
  operation. [2](https://www.startupdefense.io/cyberattacks/evasion-attacks-ml)
- ![image.png](../assets/image_1753351428027_0.png)[image 1](https://mindgard.ai/blog/ai-under-attack-six-key-adversarial-attacks-and-their-consequences)
-
- techniques:
	- Adversarial Perturbations
	- Gradient-Based Methods
		- fgsm vs bim
		- pgm
		- carlini-wagner attack
	- black box evasion attacks
	- feature manipulation
	- reinforcement learning-base attacks
	- Transferability Exploits
-
- --techniky podla znalosti utocnika
-
-
- Vulnerabilities in Machine Learning Algorithms Exploited by Evasion Attacks
	- Overreliance on Statistical Patterns
	- High Dimensional Feature Spaces
	- Assumptions About Input Integrity
	- Sensitivity to Input Perturbations
	- Generalization Challenges
	- Implementation Considerations
-
-
-
- [DeepFooL: a simple and accurate method to fool deep neural networks](https://arxiv.org/abs/1511.04599)
- [Audio Adversarial Examples: Targeted Attacks on Speech-to-Text](https://arxiv.org/abs/1801.01944)
- [Mitigating Evasion Attacks to Deep Neural Networks via Region-based Classification](https://dl.acm.org/doi/10.1145/3134600.3134606)
-
- --white box
- ### Fast Gradient Sign Method (FGSM)
  
  At its core, FGSM is a white-box attack, meaning it requires knowledge of the model’s architecture and parameters. The idea is to perturb the input data by adding a small amount of noise based on the gradient of the loss with respect to the input. The simplicity of FGSM lies in its effectiveness in creating adversarial examples with minimal computational cost. [zdroj](https://medium.com/@zachariaharungeorge/a-deep-dive-into-the-fast-gradient-sign-method-611826e34865)
- ![image.png](../assets/image_1755707089154_0.png) [zdroj]({{video https://www.youtube.com/watch?v=oZYgaD004Dw}})
-
-