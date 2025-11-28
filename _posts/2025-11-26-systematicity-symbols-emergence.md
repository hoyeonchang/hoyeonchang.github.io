---
layout: post
title: "The Systematicity Challenge, Symbols, and Emergence in Connectionist Networks"
date: 2025-11-04 09:00:00
description: 
tags: 
categories: 
featured: false
related_posts: true
---

<div style="text-align: justify;" markdown="1">
## Fodor & Pylyshyn (1988) and the Systematicity Debate

In 1988, Jerry Fodor and Zenon Pylyshyn published a seminal critique titled *"Connectionism and Cognitive Architecture: A Critical Analysis"* (Fodor & Pylyshyn, 1988). At the time, connectionism was gaining significant traction, fueled by breakthroughs in brain research. For instance, researchers had discovered that functionally distinct cortical areas share a remarkably similar neuronal structure. Such advances led to a growing belief that higher-order problems like thought and intelligence could be reduced to, and understood through, the way such neurons connect to encode information.

This connectionist optimism was understandable. Previous philosophical discussions on the mechanisms of thought relied heavily on subjective phenomena rather than objective, empirical backing. The promise that the brain could be objectively understood through the interaction of neurons via synapses seems to be, back then and even now, constructive and compelling. In this context, Fodor's critique was a provocative theoretical challenge.

The crux of their argument was simple: connectionist approaches do not seem to be capable of explaining **systematicity**, a characteristic evidently possessed by human thought and mental representation. Systematicity is most intuitively explained through examples: anyone who can understand *"The rug is under the chair"* can inherently understand *"The chair is under the rug"*. This connects to compositionality, which posits that any complex expression can be fully understood through its constituent parts and the rules of their combination. Hence, systematicity is often regarded as an evidence for the requirement of compositionality (For a deeper discussion of these concepts, refer to Zoltán Szabó's entry on "Compositionality" in the Stanford Encyclopedia of Philosophy (Szabó, 2020).)

In this post, I want to revisit Fodor's argument: that it is difficult to explain cognitive systematicity without a mechanism that explicitly and compositionally manipulates symbols.

It would be helpful to briefly discuss Fodor's **Language of Thought (LoT)** hypothesis (Fodor, 1975) to understand the context. Through LoT, Fodor argued that the structure of thought can be conceived in linguistic terms since human thought has a compositional structure like language. While the LoT hypothesis seems intuitive, it faces several counterarguments, for example:

1. Its persuasiveness relies on subjective mental representation (phenomenology) and says little about how it operates mechanistically. Efforts to resolve this continue; for an interesting example, see Piantadosi's work on the computational origin of representation (Piantadosi, 2021).
2. The compositionality posited by LoT might be a *byproduct* of mental representations rather than the *causal mechanism* that enables thought, the view resonates with 'eliminative connectionism' we discuss later.

In short, Fodor believed that compositionality is a fundamental property of our mental structure, and that for anything to be called a "mind," there must be a mechanism capable of manipulating symbols. Naturally, he viewed connectionist networks, modeled by neurons and connection weights, with skepticism, as they seemed to be incapable of explaining such a compositional structure.

<br/>

## Three Responses to the Systematicity Challenge

The reactions to this debate can be broadly categorized into three approaches. (For a more comprehensive discussion, see Hummel's "Getting Symbols out of a Neural Architecture" (Hummel, 2011).)

**The first** is the view shared by Fodor that connectionist networks are fundamentally incompatible with the ability to handle symbols compositionally. This perspective suggests seeking alternatives like Turing machines, but it has become increasingly less prominent at least in modern AI community due to the undeniable success of connectionist networks.

**The second** response attempts to reconcile functionalist connectionism with symbols by finding mechanisms within neural networks that can process them. Notable examples include **Vector Symbolic Architectures (VSA)**, such as the tensor product representations proposed by Paul Smolensky (Smolensky, 1990). These efforts to bridge connectionism and symbolic processing continue to this day, though they have yet to achieve the kind of empirical success that would make them central to mainstream AI/ML research.

We should also mention Gary Marcus's critique of **gradient descent (GD)** in the early 2000s. In works like *The Algebraic Mind* (Marcus, 2001), Marcus argued that GD-based optimization, which relies on local information, cannot learn structures that process symbols. Specifically, he argued that compositional symbol processing requires mechanisms for **variable binding**, which GD is fundamentally unable to learn. (Whether modern neural networks trained with GD-based algorithms perform variable binding well remains an open question and an active research topic; for example, see Wu et al., 2025). Note that while Marcus broadly belongs to the camp seeking to reconcile connectionism with symbol-processing mechanisms, he is sometimes misunderstood as rejecting connectionism itself, presumably because in today's AI research, connectionist neural networks have become virtually synonymous with the ones obtained via GD-based optimization.

**The third** response is **eliminative connectionism**, a term coined by Steven Pinker in 1988 (Pinker & Prince, 1988). This view rejects the very necessity of symbolic processing mechanisms for performing functions like cognition. It argues that if a system behaves intelligently, that *is* intelligence, and we need not somehow identify an underlying mechanism that aligns with our subjective expectations. If a neural network, through an appropriate combination of weights, produces the expected behavior, we need not demand any necessary principles.

<br/>

## Eliminative Connectionism in the 2020s, and the Persistent Desire for Symbols

Eliminative connectionism appears to enjoy the most implicit support in the pragmatism-driven landscape of modern AI. Frontier models like GPT-5 not only possess vastly more knowledge than any individual but also perform tasks that seem to require high-level symbolic processing, such as complex coding, with remarkable ease. Some even argue these models have passed the Turing Test. If these models work, why deny that they can think and perceive, even if we dismiss the need to analyze their internal mechanisms?

Furthermore, these models are surpassing average human performance on benchmarks that ostensibly require symbolic processing. As performance improves, the persuasive power of eliminative connectionism grows. If one claims that "AI must now be acknowledged to have intelligence, and since its interior is a black box, we cannot refuse to acknowledge it just because we don't understand it," this implicitly represents eliminative connectionist thinking.

However, other studies show these modern neural networks breaking down surprisingly easily in settings designed to test true compositional symbol processing. Representative examples include Lake & Baroni (2018), Dziri et al. (2023), and Mirzadeh et al. (2024). Consider the **GSM-Symbolic** study as an example. The GSM8K benchmark has been widely used in LLM research to evaluate mathematical reasoning, consisting of word problems like: *"Natalia sold clips to 48 of her friends in April, and then she sold half as many clips in May. How many clips did Natalia sell altogether in April and May?"* State-of-the-art LLMs achieve quite high performance on this dataset. However, the GSM-Symbolic paper demonstrates that model performance drops dramatically when irrelevant sentences are added or character names are changed in ways that should not affect the reasoning. This fuels suspicion that these models are not processing symbols compositionally, but are merely stitching together patterns observed from massive data (commonly referred to as "pattern matching").

In the 2020s, we observe two major research directions responding to this contradictory situation.
The first (implicitly) maintains the eliminative connectionist view, treating the reported problems as issues that can ultimately be solved through incremental progress via quality data processing and engineering, following the same trajectory of neural network development since the 2010s. This perspective naturally aligns well with pragmatism, particularly with the massively grown AI industry, as it places these problems on an extension of the development direction established through astronomical investment.

The second camp feels discomfort with these failures and seeks to decompose and understand how neural networks actually operate. This leads directly to **Mechanistic Interpretability (MI)**, a reductionist attempt to reverse-engineer neural networks and explain their operation through intelligible interactions of components at a meso-scale (larger than individual neurons but smaller than the whole). While MI can be pursued for various purposes (e.g., pure curiosity, or the belief that understanding internal workings is necessary for safe control), I suggest that, viewed in this broader context, MI can be interpreted as driven by a desire to find symbol processing within connectionist networks. In other words, it reflects a wish to reject eliminative connectionism. Thus, while MI as a subfield developed around 2020, tracing its context reveals that it can be situated within a deep-rooted debate in philosophy of mind.

In summary, the academic community of the 2020s has yet to find consensus on the debate initiated by Fodor. Some believe the current paradigm of training connectionist networks via SGD has fundamental limitations requiring entirely different alternatives. Others expect that reverse-engineering the symbol-processing mechanisms of modern models will yield clues for breakthroughs. Yet another camp believes these problems can be gradually overcome within the current paradigm through more data and better processing. At least for now, the ultimate direction of the field remains an open question. Numerous research topics across subfields (disentanglement, MI, compositional generalization, geometric deep learning, data augmentation, etc.) are exploring this 'big puzzle'.

<br/>

## Symbols and Emergence

Complex debates aside, we have models like GPT-5 before us that demonstrate remarkable generalization. Even without discussing the necessity of symbolic mechanisms, these models perform impressively well. They seem to generate more complex ideas than humans, and the absurd behaviors we once laughed at somehow get fixed within a year. (Recall the problem of counting the letter 'r' in 'strawberry' from about a year ago; GPT-5 now answers correctly.) So we strive to find new failure modes. I am reminded of Tesler's theorem: *"Intelligence is whatever machines haven't done yet."*

In these moments, it is very tempting to use the word **"emergence"** : We scaled data and models, and unimaginable capabilities appeared. Why shouldn't we expect that highly complex phenomena like systematicity will also emerge unpredictably at some point? Perhaps the human brain was not so different. Accepting this simplifies everything. If we train networks better with good data, we will eventually create systematic neural networks. Whether we can find analyzable mechanisms inside becomes a question for later, rather than an immediate and necessary one.

It is interesting to observe that this **mystification** of certain complex phenomena has repeated throughout the history of science. Concepts like chemical bonding or life were once considered "emergent": difficult to explain but clearly present before our eyes. While emergence is seriously studied in complexity science, it is hard to shake the feeling that we sometimes use the word to offload things we cannot yet reduce to current knowledge. Historically, once a "new science" successfully explains a mysterious target reductively, previous attempts to settle the matter with the word "emergence" come to be viewed as antiquated. (Consider how the molecular biologist Jacques Monod sharply criticized Bergson's philosophy in *Chance and Necessity* (Monod, 1971).)

Of course, the systematicity we seek might indeed emerge from the current paradigm. Or it might be something that appears and is eventually understood as we continue this direction. We cannot know the future. But scientists who seek to reduce and understand complex phenomena cannot deny the strong desire to not settle for the comfort of emergence, but to deconstruct the problem or introduce new science to explain it. With no one knowing the answer, everyone is groping forward step by step within their own beliefs.

So, to me, the most important questions that keep ringing in my head are: What exactly is compositional symbol processing? How can it be implemented? Is it strictly necessary for genuine intelligence? Can it be naturally obtained through scale? How should we understand the "partially compositional" models before us? Is emergence a sufficient concept to entrust with explaining this phenomenon?

---

## References

Dziri, N., Lu, X., Sclar, M., Li, X. L., Jiang, L., Lin, B. Y., Welleck, S., West, P., Bhagavatula, C., Le Bras, R., Hwang, J. D., Sanber, S., Ren, X., & Choi, Y. (2023). Faith and Fate: Limits of Transformers on Compositionality. *Advances in Neural Information Processing Systems (NeurIPS)*.

Wu, Y., Geiger, A., & Millière, R. (2025). How Do Transformers Learn Variable Binding in Symbolic Programs? *Forty-Second International Conference on Machine Learning*.

Fodor, J. A. (1975). *The Language of Thought*. Harvard University Press.

Fodor, J. A., & Pylyshyn, Z. W. (1988). Connectionism and cognitive architecture: A critical analysis. *Cognition, 28*(1-2), 3–71.

Hummel, J. E. (2011). Getting symbols out of a neural architecture. *Connection Science, 23*(2), 109–118.

Lake, B., & Baroni, M. (2018). Generalization without systematicity: On the compositional skills of sequence-to-sequence recurrent networks. *International Conference on Machine Learning (ICML)*.

Marcus, G. F. (2003). *The Algebraic Mind: Integrating Connectionism and Cognitive Science*. MIT Press.

Mirzadeh, I., Alizadeh, K., Shahrokhi, H., Tuzel, O., Bengio, S., & Farajtabar, M. (2024). GSM-Symbolic: Understanding the Limitations of Mathematical Reasoning in Large Language Models. *arXiv preprint arXiv:2410.05229*.

Monod, J. (1974). On chance and necessity. In Studies in the Philosophy of Biology: Reduction and Related Problems (pp. 357-375). London: Macmillan Education UK.

Piantadosi, S. T. (2021). The computational origin of representation. *Minds and Machines, 31*, 1–58.

Pinker, S., & Prince, A. (1988). On language and connectionism: Analysis of a parallel distributed processing model of language acquisition. *Cognition, 28*(1-2), 73–193.

Smolensky, P. (1990). Tensor product variable binding and the representation of symbolic structures in connectionist systems. *Artificial Intelligence, 46*(1-2), 159–216.

Szabó, Z. G. (2020). Compositionality. *The Stanford Encyclopedia of Philosophy*.

</div>