
1. Input Embedding: The input tokens (words, for example) are converted into [[Vector]] using embedding. Positional encoding are then added to these embedding to give the model a sense of word order.

2. **Encoder**: Each encoder layer consists of two main components: multi-head self-attention and a [[Feed-forward]] neural network. The self-attention mechanism allows the encoder to focus on different parts of the input sequence. The feed-forward network processes the attention outputs, applying non-linear transformations.

3. **Decoder**: The decoder also uses self-attention but with an additional layer called "cross-attention," where it attends to the encoder’s output. This helps the decoder generate the correct output sequence by referring to the input sequence. After processing, it outputs the final predictions.

4. **Training**: During training, Transformers are trained on large datasets (e.g., language data) using tasks like masked language modelling or translation tasks. The model learns to predict missing words or to translate sentences between languages.