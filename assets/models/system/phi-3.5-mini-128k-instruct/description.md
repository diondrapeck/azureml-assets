Phi-3.5-mini is a lightweight, state-of-the-art open model built upon datasets used for Phi-3 - synthetic data and filtered publicly available websites - with a focus on very high-quality, reasoning dense data. The model belongs to the Phi-3 model family and supports 128K token context length. The model underwent a rigorous enhancement process, incorporating both supervised fine-tuning, proximal policy optimization, and direct preference optimization to ensure precise instruction adherence and robust safety measures.

### Resources
🏡 [Phi-3 Portal](https://azure.microsoft.com/en-us/products/phi-3) <br>
📰 [Phi-3 Microsoft Blog](https://aka.ms/phi3.5-techblog) <br>
📖 [Phi-3 Technical Report](https://arxiv.org/abs/2404.14219) <br>
👩‍🍳 [Phi-3 Cookbook](https://github.com/microsoft/Phi-3CookBook) <br>

### Model Summary
|      |      |
|------|------|
| **Architecture** | Phi-3.5-mini has 3.8B parameters and is a dense decoder-only Transformer model using the same tokenizer as Phi-3 Mini. |
| **Inputs** | Text. It is best suited for prompts using chat format. |
| **Context length** | 128K tokens |
| **GPUs** | 512 H100-80G |
| **Training time** | 10 days |
| **Training data** | 3.4T tokens |
| **Outputs** | Generated text in response to the input |
| **Dates** | Trained between June and August 2024 |
| **Status** | This is a static model trained on an offline dataset with cutoff date October 2023 for publicly available data. Future versions of the tuned models may be released as we improve models. |
| **Supported languages** | Arabic, Chinese, Czech, Danish, Dutch, English, Finnish, French, German, Hebrew, Hungarian, Italian, Japanese, Korean, Norwegian, Polish, Portuguese, Russian, Spanish, Swedish, Thai, Turkish, Ukrainian |
| **Release date** | August 20, 2024 |
| License | MIT |

## Release Notes 
This is an update over the June 2024 instruction-tuned Phi-3-mini release based on valuable user feedback. The model used better post-training techniques and additional data leading to substantial gains on multilingual, multi-turn conversation quality, and reasoning capability. We believe most use cases will benefit from this release, but we encourage users to test in their particular AI applications. We appreciate the enthusiastic adoption of the Phi-3 model family, and continue to welcome all feedback from the community.

### Multilingual
The table below highlights multilingual capability of Phi-3.5-mini on multilingual MMLU, MEGA, and multilingual MMLU-pro datasets. Overall, we observed that even with just 3.8B active parameters, the model is very competitive on multilingual tasks in comparison to other models with a much bigger active parameters.

| Benchmark | Phi-3.5-mini-instruct | Phi-3.0-mini-128k-instruct | Mistral-7B-Instruct-v0.3 | Mistral-Nemo-12B-Ins-2407 | Llama-3.1-8B-Ins | Gemma-2-9B-Ins | Gemini-1.5-Flash | GPT-4o-mini-2024-07-18 (Chat) |
|---|---|---|---|---|---|---|---|---|
| Multilingual MMLU | 55.4 | 51.08 | 47.4 | 58.9 | 56.2 | 63.8 | 77.2 | 72.9 |
| Multilingual MMLU-Pro | 30.9 | 30.21 | 15.0 | 34.0 | 21.4 | 43.0 | 57.9 | 53.2 |
| MGSM | 47.9 | 41.56 | 31.8 | 63.3 | 56.7 | 75.1 | 75.8 | 81.7 |
| MEGA MLQA | 61.7 | 55.5 | 43.9 | 61.2 | 45.2 | 54.4 | 61.6 | 70.0 |
| MEGA TyDi QA | 62.2 | 55.9 | 54.0 | 63.7 | 54.5 | 65.6 | 63.6 | 81.8 |
| MEGA UDPOS | 46.5 | 48.1 | 57.2 | 58.2 | 54.1 | 56.6 | 62.4 | 66.0 |
| MEGA XCOPA | 63.1 | 62.4 | 58.8 | 10.8 | 21.1 | 31.2 | 95.0 | 90.3 |
| MEGA XStoryCloze | 73.5 | 73.6 | 75.5 | 92.3 | 71.0 | 87.0 | 20.7 | 96.6 |
| **Average** | **55.2** | **52.3** | **47.9** | **55.3** | **47.5** | **59.6** | **64.3** | **76.6** |

### Long Context

Phi-3.5-mini supports 128K context length, therefore the model is capable of several long context tasks including long document/meeting summarization, long document QA, long document information retrieval. Phi-3.5-mini outperforms Gemma-2 family which only supports 8K context length and is competitive with other much larger open-weight models such as Llama-3.1-8B-Instruct, Mistral-7B-Instruct-v0.3, and Mistral-Nemo-12B-Instruct-2407.

| Benchmark | Phi-3.5-mini-instruct | Llama-3.1-8B-instruct | Mistral-7B-instruct-v0.3 | Mistral-Nemo-12B-instruct-2407 | Gemini-1.5-Flash | GPT-4o-mini-2024-07-18 (Chat) |
|---|---|---|---|---|---|---|
| GovReport | 25.9 | 25.1 | 26.0 | 25.6 | 27.8 | 24.8 |
| QMSum | 21.3 | 21.6 | 21.3 | 22.1 | 24.0 | 21.7 |
| Qasper | 41.9 | 37.2 | 31.4 | 30.7 | 43.5 | 39.8 |
| SQuALITY | 25.3 | 26.2 | 25.9 | 25.8 | 23.5 | 23.8 |
| SummScreenFD | 16.0 | 17.6 | 17.5 | 18.2 | 16.3 | 17.0 |
| **Average** | **26.1** | **25.5** | **24.4** | **24.5** | **27.0** | **25.4** |

RULER: a retrieval-based benchmark for long context understanding
| Model | 4K | 8K | 16K | 32K | 64K | 128K | Average |
|--|--|--|--|--|--|--|--|
| **Phi-3.5-mini-instruct** | 94.3 | 91.1 | 90.7 | 87.1 | 78.0 | 63.6 | **84.1** |
| **Llama-3.1-8B-instruct** | 95.5 | 93.8 | 91.6 | 87.4 | 84.7 | 77.0 | **88.3** |
| **Mistral-Nemo-12B-instruct-2407** | 87.8 | 87.2 | 87.7 | 69.0 | 46.8 | 19.0 | **66.2** |

RepoQA: a benchmark for long context code understanding
| Model | Python | C++ | Rust | Java | TypeScript | Average |
|--|--|--|--|--|--|--|
| **Phi-3.5-mini-instruct** | 86 | 67 | 73 | 77 | 82 | **77** |
| **Llama-3.1-8B-instruct** | 80 | 65 | 73 | 76 | 63 | **71** |
| **Mistral-7B-instruct-v0.3** | 61 | 57 | 51 | 61 | 80 | **62** |

## Intended Use

### Primary Use Cases
The model is intended for broad commercial and research use in multiple languages. The model provides uses for general purpose AI systems and applications which require:

1) Memory/compute constrained environments
2) Latency bound scenarios
3) Strong reasoning (especially code, math and logic)

Our model is designed to accelerate research on language and multimodal models, for use as a building block for generative AI powered features. 

### Out-of-Scope Use Cases
Our models are not specifically designed or evaluated for all downstream purposes. Developers should consider common limitations of language models, as well as performance difference across languages, as they select use cases, and evaluate and mitigate for accuracy, safety, and fairness before using within a specific downstream use case, particularly for high-risk scenarios. Developers should be aware of and adhere to applicable laws or regulations (including privacy, trade compliance laws, etc.) that are relevant to their use case.

**Nothing contained in this Model Card should be interpreted as or deemed a restriction or modification to the license the model is released under.**

## Responsible AI Considerations
Like other language models, the Phi family of models can potentially behave in ways that are unfair, unreliable, or offensive. Some of the limiting behaviors to be aware of include:

* Quality of Service: The Phi models are trained primarily on English text and some additional multilingual text. Languages other than English will experience worse performance as well as performance disparities across non-English. English language varieties with less representation in the training data might experience worse performance than standard American English.   
* Multilingual performance and safety gaps: We believe it is important to make language models more widely available across different languages, but the Phi 3 models still exhibit challenges common across multilingual releases. As with any deployment of LLMs, developers will be better positioned to test for performance or safety gaps for their linguistic and cultural context and customize the model with additional fine-tuning and appropriate safeguards.
* Representation of Harms & Perpetuation of Stereotypes: These models can over- or under-represent groups of people, erase representation of some groups, or reinforce demeaning or negative stereotypes. Despite safety post-training, these limitations may still be present due to differing levels of representation of different groups, cultural contexts, or prevalence of examples of negative stereotypes in training data that reflect real-world patterns and societal biases. 
* Inappropriate or Offensive Content: These models may produce other types of inappropriate or offensive content, which may make it inappropriate to deploy for sensitive contexts without additional mitigations that are specific to the use case. 
* Information Reliability: Language models can generate nonsensical content or fabricate content that might sound reasonable but is inaccurate or outdated.  
* Limited Scope for Code: Majority of Phi-3 training data is based in Python and use common packages such as "typing, math, random, collections, datetime, itertools". If the model generates Python scripts that utilize other packages or scripts in other languages, we strongly recommend users manually verify all API uses.
* Long Conversation: Phi-3 models, like other models, can in some cases generate responses that are repetitive, unhelpful, or inconsistent in very long chat sessions in both English and non-English languages. Developers are encouraged to place appropriate mitigations, like limiting conversation turns to account for the possible conversational drift.

Developers should apply responsible AI best practices, including mapping, measuring, and mitigating risks associated with their specific use case and cultural, linguistic context. Phi-3 family of models are general purpose models. As developers plan to deploy these models for specific use cases, they are encouraged to fine-tune the models for their use case and leverage the models as part of broader AI systems with language-specific safeguards in place. Important areas for consideration include:

* Allocation: Models may not be suitable for scenarios that could have consequential impact on legal status or the allocation of resources or life opportunities (ex: housing, employment, credit, etc.) without further assessments and additional debiasing techniques.
* High-Risk Scenarios: Developers should assess the suitability of using models in high-risk scenarios where unfair, unreliable or offensive outputs might be extremely costly or lead to harm. This includes providing advice in sensitive or expert domains where accuracy and reliability are critical (ex: legal or health advice). Additional safeguards should be implemented at the application level according to the deployment context. 
* Misinformation: Models may produce inaccurate information. Developers should follow transparency best practices and inform end-users they are interacting with an AI system. At the application level, developers can build feedback mechanisms and pipelines to ground responses in use-case specific, contextual information, a technique known as Retrieval Augmented Generation (RAG).   
* Generation of Harmful Content: Developers should assess outputs for their context and use available safety classifiers or custom solutions appropriate for their use case. 
* Misuse: Other forms of misuse such as fraud, spam, or malware production may be possible, and developers should ensure that their applications do not violate applicable laws and regulations.

## Training Data
Our training data includes a wide variety of sources, totaling 3.4 trillion tokens, and is a combination of 
1) publicly available documents filtered rigorously for quality, selected high-quality educational data, and code;
2) newly created synthetic, “textbook-like” data for the purpose of teaching math, coding, common sense reasoning, general knowledge of the world (science, daily activities, theory of mind, etc.);
3) high quality chat format supervised data covering various topics to reflect human preferences on different aspects such as instruct-following, truthfulness, honesty and helpfulness. 

We are focusing on the quality of data that could potentially improve the reasoning ability for the model, and we filter the publicly available documents to contain the correct level of knowledge. As an example, the result of a game in premier league in a particular day might be good training data for frontier models, but we need to remove such information to leave more model capacity for reasoning for the small size models. More details about data can be found in the [Phi-3 Technical Report](https://arxiv.org/pdf/2404.14219).

## Sample Inputs and Outputs (for real-time inference)

### **Sample input**
```json
{
  "input_data": {
    "input_string": [
      {
        "role": "user",
        "content": "I am going to Paris, give me a list of 10 places to visit"
      }
    ],
    "parameters": {
      "temperature": 0.7,
      "top_p": 0.9,
      "do_sample": true,
      "max_new_tokens": 1000
    }
  }
}
``` 

### **Sample output**
```json
{
  "output": " 1. Eiffel Tower: Visit the iconic symbol of Paris, offering breathtaking views of the city.\n\n2. Louvre Museum: Explore one of the world's largest and most visited museums, home to thousands of works of art, including the Mona Lisa.\n\n3. Notre-Dame Cathedral: Marvel at the stunning Gothic architecture of this famous cathedral, although note that it is currently under renovation due to the 2019 fire.\n\n4. Montmartre: Discover this historic and artistic neighborhood, famous for its bohemian past and the stunning Sacré-Cœur Basilica.\n\n5. Seine River Cruise: Take a relaxing cruise on the Seine River, seeing some of the city's most famous landmarks like the Louvre, Notre-Dame, and the Eiffel Tower from a unique perspective.\n\n6. Champs-Élysées: Visit this famous avenue lined with shops, cafes, and theaters. Don't forget to check out the Arc de Triomphe at its end.\n\n7. Palace of Versailles: Take a day trip from Paris to explore the opulent palace and gardens of Versailles, a UNESCO World Heritage site.\n\n8. Sacré-Cœur Basilica: Located at the highest point in the city, this basilica offers panoramic views of Paris.\n\n9. Latin Quarter: Stroll through this historic and vibrant neighborhood, famous for its student life, lively atmosphere, and cafes.\n\n10. Musée d'Orsay: Visit this museum, housing an impressive collection of Impressionist and Post-Impressionist art, including works by Monet, Degas, Renoir, and Van Gogh."
}
```

## Trademarks
This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft trademarks or logos is subject to and must follow [Microsoft’s Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks). Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship. Any use of third-party trademarks or logos are subject to those third-party’s policies.