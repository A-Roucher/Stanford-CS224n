# NMT Assignment
Note: Heavily inspired by the https://github.com/pcyin/pytorch_nmt repository

## My answers to the questions:

1.g) About the masks used during attention computation:
Wherever the mask is 0, the vector e_t is set to -inf, which means it will go to 0 after the softmax used to compute attention. As a result the attention in these places will be 0 and have no gradient. This prevents the model from adopting a parasitic behaviour of updating weights based on holes in the input sequences.

1.i)
- An advantage of the dot product is that it's simple and quick. Disadvantage vs multiplicative attention is that it doesn't allow to simply ignore some of the parameters when computing attention.
- An advantage of additive attention (which is basically a NN layer), formula $e = v^{T}tanh(W_{h}h + W_{s})$, over the multiplicative attention, is that it can perform better on large dimensions, if $v$ has small dimension. On the other hand, it will be slower on smaller dimensions.


2.a) According to the [Wikipedia definition for a polysynthetic language](https://en.wikipedia.org/wiki/Polysynthetic_language), Cherokee can have several morphemes, i.e. small units of meaning, merged into a single word. As such, the only way to go down to the level of the basic unit of meaning is to adopt a subword embedding.

2.b) For the same language, a character-level or subword embedding will generally be lower dimensional than the word embedding because the dimensionality of the ensemble of parts is smaller than the dimensionality of all their possible combinations.

2.c) Multilingual training could for instance help capture real-world relationships (spatial, familial, behavioural...) between different concepts, and having this structures already trained would reduce the effort to learn Cherokee.

2.d) 
    1. To prevent the repeating of "her hair", maybe it would help to increase the embedding size and disentangle the different concepts: crown (always linked with the hair) and hair.
    2. This sentence is two words in the cherokee version, but generally it's hard to get the full meaning of a two word sentence without its context. For this one, it would thus help to use the wider context in translation.
    3. Here, context would also help. But even the sentence does not make sense by itself: probably training longer would help.