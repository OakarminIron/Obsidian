The core idea of agents is to use a language model to choose a sequence of actions to take. 
- In agents, a language model is used as a reasoning engine to determine which actions to take and in which order.
- This is the chain responsible for deciding what step to take next. This is usually powered by a language model, a prompt, and an output parser.(ဘာဆက်လုပ်မယ်ဆိုတာကိုဆုံးဖြတ်တာ Seems like function below)
- Different agents have different prompting styles for reasoning, different ways of encoding inputs, and different ways of parsing the output. 

The [[Agent executor]] is the runtime for an agent. This is what actually calls the agent, executes the actions it chooses, passes the action outputs back to the agent, and repeats. In pseudo-code, this looks roughly like:
```python
next_action = agent.get_action(...)  
while next_action != AgentFinish:  
observation = run(next_action)  
next_action = agent.get_action(..., next_action, observation)  
return next_action
```

[[🦜️🔗🕴️Type]]
