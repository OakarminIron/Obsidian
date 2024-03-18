- [[🦜️🔗Open AI]] `pip install langchain-openai`
```python
	from langchain_openai import ChatOpenAI  
	from langchain_openai import OpenAI  
	llm = OpenAI()  
	chat_model = ChatOpenAI(model="gpt-3.5-turbo-0125")
```

- [[🦜️🔗Ollama]] - Fetch a model via `ollama pull llama2`
	```python
	from langchain_community.llms import Ollama  
	from langchain_community.chat_models import ChatOllama  
	llm = Ollama(model="llama2")  
	chat_model = ChatOllama()
	```

- [[🦜️🔗Cohere]] `pip install cohere`
	```python
	from langchain_community.chat_models import ChatCohere
	chat_model = ChatCohere()
	```

- [[🦜️🔗Anthropic]] `pip install langchain-anthropic`
	```python
	from langchain_anthropic import ChatAnthropic
	chat_model = ChatAnthropic(model="claude-3-sonnet-20240229", temperature=0.2, max_tokens=1024)
	```
