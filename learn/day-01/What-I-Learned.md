🧠 How Large Language Models (LLMs) Work

Introduction

LLM stands for Large Language Model. It is an Artificial Intelligence model that is trained to understand and generate human language. Most modern LLMs such as ChatGPT, Gemini, Claude and Llama are based on the Transformer architecture, which was introduced by Google in 2017 through the research paper "Attention Is All You Need."

Whenever we give an input like:

«"Hi, how are you?"»

the model does not understand English directly. Instead, it processes the input through several steps before generating a response.

---

1. Tokenization

The first step is Tokenization.

In this step, the input text is divided into smaller pieces called tokens. A token is not always a complete word. It can be a full word, part of a word, punctuation, or even a single character depending on the tokenizer used.

For example,

Input:

I love AI!

Tokens:

["I", "love", "AI", "!"]

After tokenization, each token is assigned a unique numerical ID.

Token| Token ID (Example)
I| 101
love| 5832
AI| 9021
!| 12

Different LLMs use different tokenizers, so the same word may have different token IDs in different models.

Why is tokenization important?

Computers cannot understand human language directly. They only understand numbers, so tokenization converts text into a format that the model can process.

---

2. Vector Embeddings

After tokenization, each token is converted into a vector embedding.

A vector embedding is simply a list of numbers that represents the meaning of a token. These vectors help the model understand relationships between different words.

For example,

- Cat and Dog will have similar vector representations because both are animals.
- King and Queen will also be close because they have related meanings.
- Cat and Laptop will be far apart because they are not related.

Although embeddings are created in hundreds or thousands of dimensions, they are usually shown in 2D or 3D graphs for easy understanding.

Embeddings help the LLM understand not only individual words but also the relationship between them.

---

3. Positional Encoding

The Transformer processes all tokens at the same time (in parallel).

Since all tokens are processed together, the model does not automatically know the order of words.

For example,

Sentence 1

«The dog chased the cat.»

Sentence 2

«The cat chased the dog.»

Both sentences contain the same words, but their meanings are completely different.

To solve this problem, Positional Encoding adds position information to every token. This allows the Transformer to understand the order of words and the overall structure of the sentence.

Without positional encoding, the model would not be able to distinguish between these two sentences correctly.

---

4. Self-Attention

Self-attention is the most important part of a Transformer.

It allows every word in the sentence to look at all the other words and determine which ones are important.

For example,

«I deposited money in the bank.»

Here, the word bank refers to a financial institution.

But in,

«We sat near the river bank.»

the same word refers to the side of a river.

The model understands the correct meaning by looking at the surrounding words. This ability to understand context is made possible through the Self-Attention mechanism.

---

5. Transformer Layers

After embeddings, positional encoding, and self-attention, the information passes through multiple Transformer layers.

Each layer improves the model's understanding of the sentence.

The deeper the information moves through the layers, the better the model understands grammar, context, and relationships between words.

This is one of the reasons why LLMs can generate meaningful and natural responses.

---

6. Output Generation

Once the Transformer has processed the input, it predicts the next most probable token.

For example,

Input:

«Cats like»

Possible predictions:

Token| Probability
milk| 63%
fish| 21%
sleeping| 10%
pizza| 6%

These probabilities are calculated using the Softmax function.

The selected token is added to the sentence and then given back to the model as input.

This process repeats continuously until the model generates an EOS (End of Sequence) token or reaches the maximum token limit.

---

Training vs Inference

During the training phase, the model already knows the correct answer. It compares its prediction with the actual answer and calculates the error.

This error is reduced using Backpropagation and Gradient Descent, allowing the model to improve over time.

During the inference phase (when we use ChatGPT or another LLM), there is no backpropagation because the model is not learning anymore. It only uses the knowledge gained during training to predict one token after another.

---

Role of Softmax

The Softmax function converts the model's output scores into probabilities.

For example,

Token| Probability
milk| 63%
fish| 21%
pizza| 10%
water| 6%

The token with the highest probability is usually selected.

The model's creativity is controlled by parameters such as Temperature. A lower temperature produces more accurate and predictable responses, while a higher temperature produces more creative and diverse responses.

---

Summary

The complete working of an LLM can be summarized as:

User Input
      ↓
Tokenization
      ↓
Vector Embeddings
      ↓
Positional Encoding
      ↓
Self-Attention
      ↓
Transformer Layers
      ↓
Softmax
      ↓
Next Token Prediction
      ↓
Repeat until EOS

Conclusion

Large Language Models work by converting human language into numerical representations, understanding the relationships between words using embeddings and self-attention, and predicting one token at a time until a complete response is generated. The Transformer architecture has become the foundation of almost every modern LLM because it can process information efficiently and understand context much better than older sequence models.
