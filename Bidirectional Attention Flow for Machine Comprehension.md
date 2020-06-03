Bidirectional Attention Flow for Machine Comprehension
===
*Seo, Minjoon, et al., ICLR 2017*

## Main Contribution
Introduce the Bi-Directional Attention Flow (BIDAF) network, a hierarchical multi-stage architecture for modeling the representations of the context paragraph at different levels of granularity
### Proposed attention layer
1. Attention layer is not used to summarize the context paragraph into a fixed-size vector. Instead, the attention is computed for every time step, is allowed to flow through to the subsequent modeling layer
    - reduce the information loss caused by early summarization
2. Use a memory-less attention mechanism. The attention at each time step is a function of only the query and the context paragraph at the current time step and does not directly depend on the attention at the previous time step. gives a clear advantage over dynamic attention
    - force the attention layer to focus on learning the attention between the query and the context
    - enable the modeling layer to focus on learning the interaction within the query-aware context representation
    - allow the attention at each time step to be unaffected from incorrect attendances at previous time steps
3. Use attention mechanisms in both directions, query-to-context and context-to-query
    - provide complimentary information to each other

##  BiDAF Model
![](https://i.imgur.com/Nq2wFQ5.png)

1. **Character Embedding Layer** maps each word to a vector space using character-level CNNs.
2. **Word Embedding Layer** maps each word to a vector space using a pre-trained word embedding model.
3. **Contextual Embedding Layer** utilizes contextual cues from surrounding words to refine the embedding of the words. These first three layers are applied to both the query and context.
4. **Attention Flow Layer** couples the query and context vectors and produces a set of query-aware feature vectors for each word in the context.
- Context-to-query Attention
Context-to-query (C2Q) attention signifies which query words are most relevant to each context word.
- Query-to-context Attention
Query-to-context (Q2C) attention signifies which context words have the closest similarity to one of the query words and are hence critical for answering the query.

5. **Modeling Layer** employs a Recurrent Neural Network to scan the context. 
6. **Output Layer** provides an answer to the query.

## QA Experiment
![](https://i.imgur.com/IBQnc0x.png)

![](https://i.imgur.com/R3IrwaA.png)

## Cloze Test Experiment
![](https://i.imgur.com/YWGV7qd.png)

## Conclusion
This paper achieved the SOTA result on SQUAD and introduced the bidirectional attention mechanism, which is cruical for the following QA works.


