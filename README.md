# Detecting Factuality Hallucinations in Large Language Models Challenges and Solutions

Repository of the Master's Thesis in Data Science at University of Milano-Bicocca by Cristian Ceccarelli. 

## ABSTRACT

In recent years, the emergence of Large Language Models (LLMs) has revolutionized the
field of Natural Language Processing (NLP), driving significant advancements in sev-
eral applications, including text generation, machine translation, and conversational AI.
Despite their remarkable capabilities, these models exhibit a critical limitation: their
tendency to generate inaccurate or misleading content, a phenomenon known as hallu-
cination. Hallucinations in LLMs can be categorized into two primary types: factuality
hallucinations, where the model generates information that is contradictory, unverifiable,
or misaligned with real-world knowledge, and faithfulness hallucinations, when the gener-
ated content is inconsistent with the input or the context provided by the user.

This study aims to conduct an in-depth investigation into the phenomenon of hallu-
cinations in LLMs, examining their types, underlying causes, and the principal methods
developed for their detection, with a focus on factuality hallucinations. To provide a
comprehensive overview, this work presents a systematic review of the existing litera-
ture, categorizing hallucination detection strategies into three main approaches: methods
based on knowledge retrieval from external sources, uncertainty estimation approaches
through the analysis of the internal states of the LLM, and zero-resources and black-box
approaches, based on strategies to assess the consistency of the generated output. Beyond
the theoretical analysis, this work also presents an experimental study comparing different
hallucination detection methods and assessing their effectiveness on different benchmark
datasets, highlighting the strengths and limitations of each approach.

The findings show that no approach consistently outperforms the others across all
contexts. Supervised classification methods demonstrate superior performance in assess-
ing the factual accuracy of long texts, yet their effectiveness diminishes when applied
to shorter texts. Conversely, zero-resources and black-box approaches exhibit more sta-
ble and adaptable performance across several contexts. Furthermore, the integration of
external knowledge within the approaches generally leads to an overall improvement in
performance. However, the observed performance gains are not always substantial. No-
tably, further refining the knowledge retrieval process has the potential to yield even more
significant improvements, emphasizing the importance of enhancing retrieval mechanisms
to optimize hallucination detection strategies.

In conclusion, this study provides a significant contribution to the field of hallucination
detection by presenting a comprehensive comparative analysis of existing methodologies.
Additionally, it highlights potential future research directions aimed at enhancing the
transparency and reliability of AI models.


## Structure of the Repository
The repository is structured in the following way:

- **Results**: Results obtained during the sperimental analysis. It is composed of:

  - *Few Shot:* Results obtained using few-shot prompting (both with and without knowledge integrated)
  - *Hidden States:* Results obtained by extracting the internal states of the LLM and classifying them.
  - *SelfCheckGPT:* Results obtained using SelfCheckGPT (BERTScore, NLI, and LLM prompt, both with and without knowledge)
  - *Text Classification:* Results obtained through text classification. It is divided in only answer, where it was provided only the answer, and query+answer where it was provided both the query and the answer.
    
- **Source Code**: Code developed during the work. It is composed of:
  
  - *Few Shot:* Code developed for the few-shot prompting approaches.
  - *SelfCheckGPT:* Code developed to use SelfCheckGPT and its variants.
  - *Text Classification:* Code developed for text classification using BERT, GPT-2 and RoBERTa. It is divided in only answer, where it was provided only the answer, and query+answer where it was provided both the query and the answer.
  - *Uncertainty Estimation:* Code developed for the classification of internal states of the LLM.
  - *Utils:* Code developed for knowledge retrieval and extraction of LLM internal states.
    
- **data**: Data used for the experiments. It contains *FactBench* dataset and all the dataset with the retrieved knowledge.
  
- **embeddings_saplma/felm**: Example of the internal states extracted from the last layer of the LLM for FELM dataset (internal states extracted from the other layers and for the other datasets were not loaded due to space constraints).

