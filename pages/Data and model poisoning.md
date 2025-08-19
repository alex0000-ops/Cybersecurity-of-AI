- ![image.png](../assets/image_1753730775585_0.png) [image 1](https://massedcompute.com/faq-answers/?question=What%20is%20the%20difference%20between%20data%20poisoning%20and%20adversarial%20attacks%20in%20machine%20learning?)
-
- Data poisoning involves the deliberate  and  malicious contamination of data to compromise the performance of AI and ML systems. It attacks strike at the training phase. By introducing, modifying, or 
  deleting selected data points in a training dataset, adversaries can induce biases, errors, or specific vulnerabilities that manifest when the compromised model makes decisions or predictions. [1](https://www.nightfall.ai/ai-security-101/data-poisoning) -- definicia 1 
  
  Data poisoning is a type of adversarial attack that targets AI and machine learning (ML) model training datasets to degrade or control model behavior. Attackers try to slip misleading or incorrect information into the training dataset by adding new data, changing existing data, or even deleting some data to corrupt the model’s understanding. [2](https://www.wiz.io/academy/data-poisoning)  -- definicia 2
-
-
- impact:
	- Biases Introduced into Decision-Making
	  Biases introduced through data poisoning can distort a model's perception of data, leading
	  to skewed outputs and erroneous conclusions. These biases might manifest in various ways, such as racial or gender discrimination, which is particularly harmful in applications like recruitment or credit scoring.
	- ### Reduced Accuracy, Precision, and Recall
	  
	  Data 
	  poisoning can significantly reduce a model's accuracy, precision, and 
	  recall. The quality of the predictions or classifications degrades, 
	  leading to higher error rates. This drop in performance can disrupt 
	  applications relying on high accuracy, resulting in poor user 
	  experiences and decision-making failures.
	  
	  Accuracy refers to a 
	  model's ability to predict or classify correctly. When training data is 
	  corrupted, the model might learn incorrect associations, leading to 
	  decreased precision—its ability to consistently perform—and recall—its 
	  effectiveness in identifying all relevant instances.
- ### Potential for System Failure or Exploitation
  
  When
  models operate on poisoned data, the risk of systemic failure or 
  exploitation increases. An adversary could craft data poisoning 
  strategies to trigger failures, such as denial-of-service attacks or 
  unintended behavior in AI-driven processes. 
  
  AI systems exploiting
  poisoned models can become gateways for further attacks, especially in 
  integrated environments where multiple systems rely on shared model 
  insights. Ensuring resilient architecture with fail-safes against 
  poisoned data manipulation can prevent cascading failures.
- based on their intent:
	- **Targeted Attacks**: The adversary aims to influence the model's behavior for specific inputs without degrading its overall performance. [1](https://www.nightfall.ai/ai-security-101/data-poisoning)
	- **Nontargeted Attacks**: The goal here is to degrade the model's overall performance. By adding noise or irrelevant data points, the attacker can reduce the accuracy, precision, or recall of the model across various inputs. [1](https://www.nightfall.ai/ai-security-101/data-poisoning)
-
-
- ![image.png](../assets/image_1753735433654_0.png) [image 2](https://mindgard.ai/blog/ai-under-attack-six-key-adversarial-attacks-and-their-consequences)
-
- --utoky podla fazy AI/ML lifecycle
- id:: 6887da62-477c-4d28-b2df-38a0e9297dcc
  Data poisoning can target different stages of the LLM lifecycle, including
	- pre-training (learning from general data)
	- fine-tuning (adapting models to specific tasks)
	- embedding (converting text into
	   numerical vectors). [3](https://genai.owasp.org/llmrisk/llm042025-data-and-model-poisoning/)
	- **Pre-training:** The process where a model is trained on a large dataset to understand general linguistic patterns.
	- **Fine-tuning:** Adapting a pre-trained model to a specific task or domain using a curated dataset.
	- **Embedding:** The conversion of categorical data into numerical representations that the model can process. [zdroj](https://medium.com/@anandpawar26/ep04-llm03-training-data-poisoning-2a836fc8a973)
-
-
-
- Backdoor attacks are increasingly relevant in a world where users often rather than building models from scratch. The danger lies in the fact that these externally sourced models, especially those trained on rare datasets and thus more valuable, can be tampered with by malicious 
  providers. [5](https://www.cobalt.io/blog/backdoor-attacks-on-ai-models)
-
- defence strategies:
	- data validation
	- regular model auditing
	- diverse data sources
	- robust learning
	- provenance tracking
-
- types:
	- **backdoor attacks** - In a attackers embed hidden triggers within the training data. These 
	  triggers are usually some patterns or features that the model can  recognize based on its training, imperceptible to the human eye. When the model encounters this embedded trigger, it behaves in a specific pre-programmed way the attacker wanted it to behave. [2](https://www.sentinelone.com/cybersecurity-101/threat-intelligence/backdoor-attacks/)
	-
	- **data injection** - occurs when malicious samples are added to the training dataset, with 
	  the goal of manipulating the model’s behavior during deployment. The problem with these manipulations is that the source where malicious data was injected is untraceable. The bias gradually becomes subtly apparent long after the model has already been deployed.
	-
	- **mislabeling attacks** - The attacker modifies the dataset by assigning incorrect labels to a portion of the training data. The model learns from this corrupted data and becomes less accurate 
	  during deployment, rendering the model useless and unreliable.
	-
	- **data manipulation** -  involves altering the existing data within the training set through various methods. This includes adding incorrect data to skew results, removing essential data points that would otherwise guide accurate learning, or injecting adversarial samples designed to cause the model to misclassify or behave unpredictably. These attacks severely degrade the performance of the ML model if unidentified during training.
-
- If weight poisoning at fine-tuning time can be already threatening, an even worse scenario could happen if the **weights are poisoned in the pre-training phase introducing vulnerabilities that can still be exploited *_after*_ fine-tuning**. Exposing a poisoned pre-trained model online instead of a poisoned training set for fine-tuning is much more subtle because deep learning models are shady by definition and it’s much harder to detect adversarial alterations. [4](https://towardsdatascience.com/backdoor-attacks-on-language-models-can-we-trust-our-models-weights-73108f9dcb1f/)
-
- Clustering methods can be particularly effective in spotting outliers. Advanced ML models can learn to recognize patterns associated with poisoned data, providing an additional layer of security.
-
-