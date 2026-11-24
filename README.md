# Perplexity Explorer

An interactive, in-browser educational tool to explore how causal language models assign probabilities to tokens and calculate sentence perplexity.

Live Demo: [https://vedikaydv.github.io/perplexity-explorer/](https://vedikaydv.github.io/perplexity-explorer/)

## Features
- **In-Browser LLM**: Runs `Xenova/distilgpt2` (q8 quantized) entirely client-side using [Transformers.js](https://huggingface.co/docs/transformers.js), with no backend server or API keys required.
- **Token Probabilities**: Breaks sentences into tokens, measures preceding logits, and applies numerically stable softmax.
- **Step-by-Step Perplexity**:
  1. Computes the product of surprise ($1/P$).
  2. Measures token sequence length ($N$).
  3. Displays Perplexity as $(\text{Product})^{1/N}$, calculated stably in log-space: $\exp(\text{mean}(-\ln P))$.
- **Next Token Prediction**: Visualizes the top 8 predicted tokens following the sequence with horizontal probability bars.
- **Simulated Mode**: An interactive sandbox where you can set custom tokens and probabilities to build intuition with instant live updates.

## Local Setup
No build step or dependencies required! Simply open `index.html` in any modern web browser or serve locally:

```bash
python3 -m http.server 8080
```
Then visit `http://localhost:8080`.
