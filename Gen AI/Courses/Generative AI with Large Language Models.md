
# Resources :
- [Generative AI with Large Language Models | Coursera](https://www.coursera.org/learn/generative-ai-with-llms)

# Notes

## Lecture 1

- **Foundation models :**
	- BERT
	- GPT
	- LLaMa
	- FLAN-T5
	- BLOOM
	- PaLM

### Prompts and completions
- LLMs take human written instructions and perform tasks
- The text that you pass to an LLM is known as a **==prompt==**
- The space or memory that is available to the prompt is called the ==**context window**== (typically a few 1000 words)
- The output of the model is called a **==completion==**
	- The completion is comprised of the text contained in the original prompt, followed by the generated text
	
```
PROMPT : Which is the capital of Bulgaria?
COMPLETION: The capital of Bulgaria is Sofia
```

- The act of using the model to generate text is known as **==inference==**


The prompt is passed to the model, the model then predicts the next words, and generates an answer


![[Screen Shot 2024-03-09 at 15.15.11.png]]
# Tags 
#LLMs, #prompt, 