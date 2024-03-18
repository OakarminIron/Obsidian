This categorizes all the available agents along a few dimensions.

- [[Intended Model]] Type
	- Whether this agent is intended for Chat Models (takes in messages, outputs message) or LLMs (takes in string, outputs string). 
	- The main thing this affects is the prompting strategy used. 
	- You can use an agent with a different type of model than it is intended for, but it likely won't produce results of the same quality. (တိတိကျကျဒီရည်ရွယ်ချက်အတွက်သုံးတာ)
- [[Supports Chat]] History
	- Whether or not these agent types support chat history. 
	- If it does, that means it can be used as a chat-bot. If it does not, then that means it's more suited for single tasks.(တစ်ခါခိုင်း) Supporting chat history generally requires better models, so earlier agent types aimed at worse models may not support it.(Bing ဆိုအစပိုင်း History မရဘူး)
- [[Supports Multi-Input]] Tools
	- Whether or not these agent types support tools with multiple inputs. 
	- If a tool only requires a single input, it is generally easier for an `LLM` to know how to invoke it.
	- Therefore, several earlier agent types aimed at worse models may not support them.
	- Input ဆိုတာမှာ IO (Voice,Picture လဲပါသလို Data Api လဲပါနိုင်)
- [[Supports Parallel Function Calling]]
	- Having an `LLM` call multiple tools at the same time can greatly speed up agents whether there are tasks that are assisted by doing so.
	- However, it is much more challenging for `LLMs` to do this, so some agent types do not support this.
- [[Required Model Params]]
	- Whether this agent requires the model to support any additional parameters. 
	- Some agent types take advantage of things like `OpenAI` function calling, which require other model parameters. 
	- If none are required, then that means that everything is done via prompting
	