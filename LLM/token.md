<h1>Tokens in the API</h1>

<p>When interacting with the OpenAI API, you're billed based on the total number of tokens in both your input (prompt) and the model's output (response). A token represents a chunk of text, which could be a word, part of a word, or even punctuation.</p>

<h2>What is a Token?</h2>
<p>A token is a unit of text that is processed by the language model. For example, the word "apple" would be one token, but longer words or phrases may be split into multiple tokens. Tokens can consist of words, punctuation, or other parts of text.</p>

<h2>Token Limit</h2>
<p>Each model has a maximum number of tokens it can handle. The total number of tokens in a request (input + output) must not exceed the model's token limit. For example, GPT-3 has a token limit of 4096 tokens, meaning the total length of both the input and the output cannot exceed this number.</p>

<h2>How Token Usage Affects Billing</h2>
<p>You are billed based on the number of tokens processed by the API. This includes both the input tokens you send to the model and the output tokens the model generates. For instance, if your input is 10 tokens and the model's output is 50 tokens, you'll be billed for a total of 60 tokens.</p>

<h2>Example</h2>
<ul>
  <li>Input prompt: 10 tokens</li>
  <li>Model response: 50 tokens</li>
  <li>Total tokens: 60 tokens</li>
</ul>

<h2>Key Concepts</h2>
<ol>
  <li><strong>Tokens</strong> are chunks of text processed by the model.</li>
  <li><strong>Token limit</strong> refers to the maximum number of tokens a model can handle in a single request.</li>
  <li><strong>Billing</strong> is based on the total number of tokens processed by the model.</li>
</ol>
