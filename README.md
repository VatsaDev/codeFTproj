# codeFTproj

## Goals
 - Overall tiny strong model, really good code data
 - to be useful it needs muliple languages, and the ability to easily use, or at least generate functional code in several SDKs, so most likely include data like [Jina's reader api](https://jina.ai/reader/)
 - Include some agent data, not for agent capabilities, but so the model can generate moderately complex code and CoT thoughts and reasoning
 - Measure progress by benchmark scores relative to qwen 2.5 to get a meaningful vibe to progress

Notebooks:
 - HF data collection https://colab.research.google.com/drive/1mq6yODhX22Ub8YhEP42zg68xcCXQ4QwW?usp=sharing , and varitants
 - [add colab for Phi filter here]

## Datasets 

Since the models small and meant for code/reasoning, I'm going off my work on [NanoPhi](https://github.com/VatsaDev/NanoPhi), but with an extra year of data research, the three important things for this type of model are:

Code - obv, need code to make more code, but in instruct, textbook, and CoT formats
Math - increases in logic and reasoning, and emprically in my work, boosts perf on numpy, torch, einsum, etc
Reasoning - helps use small model context better, can actually formulate usable code samples in 1024-2048 tokens

Code data:
 - [Code review](https://huggingface.co/datasets/VatsaDev/code-review), personally scraped this one, well formatted markdown, but also strong code practices, lint picking, well reasoned thoughts, etc
 - [opencoder](https://huggingface.co/datasets/OpenCoder-LLM/fineweb-code-corpus) code split of fineweb, lots raw coding tokens here
 - O1 chain-like cot data
   - https://huggingface.co/datasets/wassemgtk/CoT-O1-examples
   - https://huggingface.co/datasets/GAIR/o1-journey
 - Strong instruct examples, from fundamental DSA to SDK/libs, OS, etc
   - https://huggingface.co/datasets/migtissera/Tess-Coder-v1.0
   - https://huggingface.co/datasets/cognitivecomputations/dolphin-coder
   - https://huggingface.co/datasets/glaiveai/glaive-code-assistant
   - https://huggingface.co/datasets/TokenBender/code_instructions_122k_alpaca_style

Math data:
 - [OpenTora](https://huggingface.co/datasets/SciPhi/open-tora), open attempt at gpt4 level math sota, lots of sympy code interleaved with mathematical reasoning
 - [Open web math](https://huggingface.co/datasets/open-web-math/open-web-math), all the raw math tokens you could ever need
 - [Comp Math](https://raw.githubusercontent.com/Programming-Competitions/AIMO-Competition/refs/heads/main/total.txt), 9k language model impossible olympiad questions, doubles as strong training data and a way to measure intelligence progress during training runs

Reasoning data:
 - [SciPhi textbooks](https://huggingface.co/datasets/SciPhi/textbooks-are-all-you-need-lite), good textbook and reasoning dataset, strong reasoning data for small models
 - [tiny textbooks](https://huggingface.co/datasets/nampdn-ai/tiny-textbooks), a very clean and capable textbook dataset, a mixture of Phi+tinystories, designed for mini models
 - [SlimOrca cleaned+deduped](https://huggingface.co/datasets/Open-Orca/slimorca-deduped-cleaned-corrected), cleanest set of tokens for general instruction following
 - [Agentic Orca](https://huggingface.co/datasets/microsoft/orca-agentinstruct-1M-v1), New dataset, agent reasoning structure, includes code

## Research 

 - diffu llama paper https://arxiv.org/pdf/2410.17891, https://github.com/HKUNLP/DiffuLLaMA?tab=readme-ov-file#-finetuning
 - codegen survey https://arxiv.org/abs/2406.00515
 - code data https://www.arxiv.org/abs/2409.03810
 - code survey https://arxiv.org/abs/2311.10372
 - opencoder https://arxiv.org/abs/2411.04905
 - reflection https://huggingface.co/papers/2401.02009, https://huggingface.co/papers/2405.06682
 - mutual reasoning https://huggingface.co/papers/2408.06195
 - monologue https://huggingface.co/papers/2311.07445
 - llamaberry O1 llama https://huggingface.co/papers/2410.02884

