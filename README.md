# Human Simulacra: Benchmarking the Personification of Large Language Models
This repository contains the code and data for Human Simulacra. 
- 🌟For data📖, please refer to [The Human Simulacra Dataset](#dataset).
- 🌟For reproduction🔍, please refer to [Reproduction](#reproduction).
- 🌟If you want to make your own characters with a unique life story🪄, please refer to [Character Customization](#make).

For any questions or concerns regarding this dataset, please feel free to reach out to us. We appreciate your interest and are eager to assist😊.
## Overview
Large language models (LLMs) are recognized as systems that closely mimic aspects of human intelligence. This capability has attracted attention from the social science community, who see the potential in leveraging LLMs to replace human participants in experiments, thereby reducing research costs and complexity. In this paper, we introduce a benchmark for large language models personification, including a strategy for constructing virtual characters' life stories from the ground up, a Multi-Agent Cognitive Mechanism capable of simulating human cognitive processes, and a psychology-guided evaluation method to assess human simulations from both self and observational perspectives. Experimental results demonstrate that our constructed simulacra can produce personified responses that align with their target characters. 

<div align="center">
<a href="https://github.com/hasakiXie123/Human-Simulacra/">
    <img src="figures/dataset.jpg" alt="dataset" width="600" class="center">
</a>
  
<a>Figure 1: **Left**: Information model for virtual characters. **Right**: Process of constructing life stories for target characters using semi-automated strategy. At each step, humans are involved in thoroughly reviewing the generated content, ensuring that it is free from biases and harmful information.</a>
</div>

<div align="center">
<a href="https://github.com/hasakiXie123/Human-Simulacra/">
    <img src="figures/model.jpg" alt="model" width="600" class="center">
</a>
  
<a>Figure 2: **Multi-Agent Cognitive Mechanism.** This mechanism involves four LLM-driven agents. The **Thinking Agent** / **Emotion Agent** handles logical/emotional analysis and logical/emotional memory construction. The **Memory Agent** manages retrieval of memories, while the **Top Agent** coordinates all activities. Upon receiving a stimulus, these agents collaborate to generate appropriate responses, simulating complex human cognitive processes.</a>
</div>

<div align="center">
<a href="https://github.com/hasakiXie123/Human-Simulacra/">
    <img src="figures/evaluation.jpg" alt="evaluation" width="600" class="center">
</a>
  
<a>Figure 3: **Psychology-guided evaluation.** The self report assesses the simulacra‘s self-awareness through character-specific questions based on their life stories. The observer report evaluates the realism of simulacra by creating scenario-based assessments analyzed by human judges. </a>
</div>

<a name="dataset"></a>
## The Human Simulacra Dataset📖

<a name="reproduction"></a>
## Reproduction🔍

### Installation
1. To get started, first clone the repository and setup the environment:
```
## Set up the environment
git clone https://github.com/hasakiXie123/Human-Simulacra.git
cd Human-Simulacra

## Install required packages
conda env create -f environment.yml

## Activate the environment
conda activate LLMP
cd LLMP
```
2. Adjust the path section of Config/config.py to suit your situation:
```python
## for example, if your current directory is "/root/abc/Human-Simulacra/LLMP"
for path/directory in the path section of Config/config.py:
    replace "/root/Desktop/LLMP" with "/root/abc/Human-Simulacra/LLMP"
    # e.g., Attributes_Directory = "/root/abc/Human-Simulacra/LLMP/Characters/Attributes"
```

### Chat with simulacra based on MACM/Prompt/RAG
1. Adjust the following lines of Config/config.py to suit your situation:
```
Model_for_evaluation = "gpt-4-1106-preview" # choose the base model for simulacra
Model_for_agent = "gpt-4-1106-preview" ## agent in MACM
OPENAI_API_KEY = "Your OPENAI_API_KEY"
OPENAI_BASE_URL = "https://api.openai.com/v1"
API_KEY = "Your API_KEY"
BASE_URL = "https://api.openai.com/v1" # or any api company
```
If you want to use a local model, for example, a Llama-2-7b model based on the [Fastchat library](https://github.com/lm-sys/FastChat):
```
OPENAI_API_KEY = "EMPTY"
OPENAI_BASE_URL = "http://localhost:8000/v1" 
API_KEY = "EMPTY"
BASE_URL = "http://localhost:8000/v1" 
```
2. Run the following commands:
```
## Chat with simulacra based on the MACM method. The simulacra is simulating Mary Jones.
python multi_agent_cognitive_mechanism.py --character_name "Mary Jones" --method macm
## Chat with simulacra based on the prompt method.
python multi_agent_cognitive_mechanism.py --character_name "Mary Jones" --method prompt
## Chat with simulacra based on the rag method.
python multi_agent_cognitive_mechanism.py --character_name "Mary Jones" --method rag
```

### Psychology-guided evaluation

### Bandwagon effect replication
1. Adjust the following lines of Config/config.py to suit your situation:
```
Model_for_evaluation = "gpt-4-1106-preview" # choose the base model for simulacra
Model_for_agent = "gpt-4-1106-preview" ## agent in MACM
OPENAI_API_KEY = "Your OPENAI_API_KEY"
OPENAI_BASE_URL = "https://api.openai.com/v1"
API_KEY = "Your API_KEY"
BASE_URL = "https://api.openai.com/v1" # or any api company
```
If you want to use a local model, for example, a Llama-2-7b model based on the [Fastchat library](https://github.com/lm-sys/FastChat):
```
OPENAI_API_KEY = "EMPTY"
OPENAI_BASE_URL = "http://localhost:8000/v1" 
API_KEY = "EMPTY"
BASE_URL = "http://localhost:8000/v1" 
```
2. We currently support replicating the bandwagon effect with MACM-based simulacra, run the following commands:
```
python bandwagon_effect.py --character_name "Mary Jones"
## Controlled experiment (without group pressure)
python bandwagon_effect.py --character_name "Mary Jones" --control
```
<a name="make"></a>
## Make your own characters🪄
### Character Attributes
- Generate attributes randomly
  
- Customize attributes
  
### Character Biography

### Life Story Generation

## Contributing
Contributions to enhance the usability and quality of this dataset are always welcomed. If you're interested in contributing, feel free to fork this repository, make your changes, and then submit a pull request. For significant changes, please first open an issue to discuss the proposed alterations.

## Acknowledgements
- 🌟 We appreciate the guidance of the psychologists from Tongji University throughout the process.
- 🌟 We build the self report evaluation code based on the [OpenCompass library](https://github.com/open-compass/opencompass).




