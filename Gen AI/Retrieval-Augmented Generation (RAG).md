
# Notes :

- LLMs have showcased impressive text generation capabilities, but they grapple with a central challenge: **producing content that’s not just coherent but also contextually accurate and grounded in real-world knowledge**. This limitation is especially troublesome in contexts where precision and factual correctness are paramount.
- LLMs tend to hallucinate this can be tackled by employing the RAG approach
	- General-purpose language models are pre-trained on vast amounts of data from everywhere. But this doesn't mean that it knows the answer to every question. General LLMs fall short in cases like up-to-date or relevant information, domain-specific context, fact-checking, etc.
- In 2020, Meta researchers came up with a [paper](https://arxiv.org/abs/2005.11401v4) introducing one of such "assisting" techniques – retrieval augmented generation (RAG). At its core, RAG is an innovative technique that merges the capabilities of natural language generation (NLG) and information retrieval (IR).
- **The fundamental idea behind RAG is to bridge the gap between the vast knowledge in general-purpose language models and the need for precise, contextually accurate, and up-to-date information**


# Resources :
- 🔥 [Retrieval augmented generation (RAG) explained [+ examples] | SuperAnnotate](https://www.superannotate.com/blog/rag-explained)
- [What is Retrieval-Augmented Generation (RAG)? (youtube.com)](https://www.youtube.com/watch?v=T-D1OfcDW1M)
- [META Paper - Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks](https://arxiv.org/pdf/2005.11401v4)
- DEMO (LLAMA3 + RAG) : 
	- [Llama3 RAG on Google Colab. In this article, we’ll set up a… | by Tharindu Madhusanka | May, 2024 | Medium](https://medium.com/@tharindumadhusanka99/llama3-rag-on-google-colab-73c43aa53281)
	- [Llama3_RAG_for_web_url.ipynb - Colab (google.com)](https://colab.research.google.com/drive/1Za5ezR4JSeSkl5l07G_PfulnopoA3q9X?usp=sharing#scrollTo=YLV0mqaSYy4V)

# Tags
#RAG, #NLP, #LLMs #NLG, #IR, #Llama3