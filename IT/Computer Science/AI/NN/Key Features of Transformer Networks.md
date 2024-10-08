
1. **Self-Attention Mechanism**: The core of the Transformer is the self-attention mechanism, which allows the model to weigh the importance of different words in a sentence, regardless of their position. This lets the Transformer look at all the input tokens simultaneously and decide which parts are most relevant to the current processing step.
    
2. Positional Encoding: Transformers process input tokens in parallel. Since there's no inherent order in parallel processing, positional encoding is used to inject information about the position of each token in the sequence.
    
3. **Encoder-Decoder Architecture**: The Transformer typically consists of an **encoder** and a **decoder**. The encoder takes the input sequence and converts it into a set of feature-rich representations. The decoder then uses these representations to generate the output sequence. This structure is particularly useful in tasks like machine translation (e.g., converting English to French).
    
4. **Multi-Head Attention**: Instead of performing attention once, the Transformer uses multiple "attention heads" that can focus on different parts of the sentence simultaneously. Each head learns different aspects of the sentence (e.g., grammar, meaning), making the model more powerful.
    
5. Feed-forward Layers: After the attention layers, the model includes standard [[Feed-forward]] neural network layers to further process the outputs from the attention layers. These feed-forward layers are applied to each position independently and are fully connected.
    
6. Parallelisation: Since Transformers can process the entire input sequence at once, they're highly parallelised, which makes training much faster compared to other network. This is particularly useful for large-scale models.
    