AI language models such as Gemini and GPT are highly capable, but their 
knowledge is limited to the data available during training. Information published 
afterwards cannot be accessed without external sources like web search plugins, 
fine-tuning, and retrieval integrations (. Lewis et al. (2020) showed that connecting 
language models to retrieved knowledge rather than relying solely on memorised 
information improves performance on knowledge-intensive tasks. This project 
applies that idea to recent LangChain documentation. 
The domain chosen for this project is the official documentation of LangChain 1.0 
and LangGraph 1.0, both released-on 22 October 2025. LangChain is a widely used 
Python toolkit for building AI-powered applications from simple chatbots to complex 
multi-agent systems. Version 1.0 was a complete architectural overhaul  new agent 
creation patterns, a middleware system, and breaking changes to import paths that 
made older guidance obsolete. 
Three things made this the right choice. The baseline model Gemini 2.5 Flash , has 
a confirmed training cutoff of January 2025, nine months before LangChain 1.0 
existed. It has no knowledge of these changes whatsoever. Beyond that, the 
documentation is simply too large to fit in a single prompt , retrieval is not optional 
here, it is necessary. And unlike many domains where a wrong answer is merely 
unhelpful, a hallucinated API call in a developer context produces broken production 
code. Accuracy here genuinely matters.  
One point worth addressing is that LangChain documentation is publicly available 
online. A model with web search could theoretically find it. But this evaluation is 
against a plain LLM without web search , the standard RAG benchmarking condition 
(Lewis et al., 2020) and a realistic constraint in many production environments. The 
test is against what the model knows from training data alone. That makes the 
comparison both fair and meaningful, and as Section 5 shows, the results are clear. 
