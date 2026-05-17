**Task 6: Attention and Transformer Reflection**

**1. Why RNNs Struggle with Long-Term Dependencies**

Recurrent Neural Networks (RNNs) process information sequentially step-by-step. During backpropagation, gradients must travel backwards through every single historical time step. If sequence lengths are long, repeatedly multiplying by weight values ($W$) causes exponential degradation. This is known as the Vanishing Gradient Problem. The network forgets earlier tokens, rendering it incapable of connecting distant contexts within long sentences.

**2. How LSTMs Help with Memory**

Long Short-Term Memory (LSTM) cells introduce a structural component called the Cell State ($c\_t$), which acts as an internal conveyor belt running straight through the sequence. Information is added or removed using three specific gates:

•	Forget Gate: Decides what historical context to discard.

•	Input Gate: Decides what new incoming tokens should modify the internal state.

•	Output Gate: Controls what processed data gets passed along to the next layer hidden state.

By maintaining linear gradient flow through the cell state, LSTMs effectively mitigate the vanishing gradient problem.

**3. What Attention Solves in Sequence-to-Sequence Tasks**

Traditional encoder-decoder architectures create an operational bottleneck: they compress an entire input sequence into a single, fixed-size context vector before decoding. Attention bypasses this limitation. Instead of relying on a single static vector, attention allows the decoder to look back at all encoder hidden states at every step. It calculates a dynamic distribution of weights to focus primarily on the most relevant input tokens, regardless of how far back they appear in the text sequence.

**4. Why Transformers are Important in Modern NLP \& Generative AI**

Transformers completely eliminate recurrence via Self-Attention. This architecture provides two major benefits:

•	Parallelization: Instead of reading text word-by-word, Transformers process entire sequences simultaneously. This allows models to be trained efficiently on massive hardware clusters.

•	Bidirectional Context: The system evaluates how every single word relates to every other word in a sentence at the same time, capturing rich contextual nuances.

This scalability forms the bedrock foundation for state-of-the-art Large Language Models (LLMs) and modern Generative AI systems.

