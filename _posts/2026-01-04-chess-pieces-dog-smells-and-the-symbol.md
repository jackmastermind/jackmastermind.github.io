---
layout: post
title: "Chess pieces, dog smells, and the symbol-grounding problem"
date: 2026-01-04
---

Happy New Year! On Wednesday, [I discussed](https://jacktlab.substack.com/p/three-limits-on-understanding-language) the [symbol-grounding problem](https://www.sciencedirect.com/science/article/pii/0167278990900876):

> The symbol grounding problem is a challenge for formal-system theories of cognition, whose proponents believe that minds really are doing symbolic manipulations and that the formal system explains cognition. The argument roughly goes:
>
> 1. Knowing all of the rules of the formal system for a language, which strings map to which other strings, does *not* imply that you know what those strings *mean.* (argued by Chinese room)
> 2. We know what we mean when we say words like “dog.” (premise)
> 3. Therefore, our knowledge about the word “dog” does not just consist in knowing the symbolic role of the “dog” token in some kind of formal system.

Today, I’d like to dig a little deeper into the symbol-grounding problem and how it might be applied—or misapplied—to a variety of domains, including large language models.

### Symbolism: understanding chess

To begin, what is a formal system, or “symbol system” as it’s called in the original paper? The author, Stevan Harnad, offers eight criteria, all of which must be met:

> 1. a set of arbitrary *physical tokens* (scratches on paper, holes on a tape, events in a digital computer, etc.) that are
> 2. manipulated on the basis of *explicit rules* that are
> 3. likewise physical tokens and *strings* of tokens. The rule-governed symbol-token manipulation is based
> 4. purely on the *shape* of the symbol tokens (not their “meaning”), i.e. it is purely *syntactic*, and consists of
> 5. *rulefully combining* and recombining symbol tokens. There are
> 6. primitive *atomic* symbol tokens and
> 7. *composite* symbol-token strings. The entire system and all its parts-the atomic tokens, the composite tokens, the syntactic manipulations (both actual and possible) and the rules- are all
> 8. *semantically interpretable*: The syntax can be systematically assigned a meaning (e.g. as standing for objects, as describing states of affairs).

If you’ve ever taken a class in logic, that’s a textbook formal system. Logical terms are represented with little tokens: “and” becomes ∧, “or” becomes ∨, “not” becomes ¬, and “implies” becomes →. For instance, here I prove the [principle of explosion](https://en.wikipedia.org/wiki/Principle_of_explosion): if you assume *p* is both true and false, then literally any conclusion *q* follows from that. Below, I start with the string *p* ∧ ¬*p*, which is the representation of “*p* and not-*p,*” and follow a set of purely syntactic rules.

$$
\begin{align}
1&.\quad p\land \lnot p &\text{premise} \\
2&.\quad p &\text{rule:}\land \text{elimination on line 1} \\
3&.\quad p \lor q &\text{rule:}\lor\text{introduction on line 2} \\
4&. \quad \lnot p &\text{rule:}\land\text{elimination on line 1} \\
5&. \quad q & \text{rule: disjunctive syllogism on lines 3, 4} \\
6&.\quad (p\land\lnot p)\to q &\text{rule: discharge premise on line 1}
\end{align}
$$

We see how this meets all of Harnad’s criteria for a formal system. I am manipulating little physical tokens (the symbols *p,* ∧, *q*,etc). I add and subtract tokens from strings (formulas) based on syntactic rules (like ∧ elimination) which do not care which propositions *p* and *q* stand for, they only care about the composition of strings. However, everything in the system can be given a semantic *interpretation*: this system accurately represents logical truths.

If you’re feeling a little lost, here’s a formal system you’ve probably interacted with before: chess! A chessboard is a grid of 64 squares. You could easily write it out as a string: “white’s turn: blank, blank, rook, blank, queen, blank, king, blank…”. Given this string, there are a set of mechanical manipulations you could perform to it; for instance, if there is a white pawn in the second-from-top row and a blank space directly above it, you can replace the pawn’s current space with a blank and the top space with a queen, then replace the “white’s turn” token with a “black’s turn” token. A set of these purely mechanical manipulations suffices to define all the rules of chess, and a chess game could be written out fully in notation like my proof (although it’d be really long).

A key point is that chess pieces don’t have “meanings” *apart from their roles in the formal system*. If you have never played chess, and you ask “What does the token ‘rook’ mean?”, I reply “In the system, ‘rook’ can move to any blank space it has an uninterrupted vertical or horizontal line to. Each side has two, and they start on the corners of the string.” Well, that’s all you need to know to understand what ‘rook’ represents![^1] And it works just as well as an explanation if my system uses ‘车’ instead of rook. If you now ask “What does the token ‘车’ mean?”, and I give the same explanation, you still know everything. This brings us to:

---

**Lesson #1: The SGP does not apply to concepts which just are defined by their roles in formal systems.**

---

Suppose you say “Symbol-pushing computers can’t know anything!” and I ask “Could they know about chess?” If you say “no, not in any sense” then you are baking in your own assumptions about what knowledge is; the SGP does not imply your position. Our disagreement is either about (a) how we define “knowledge,” or (b) phenomenal consciousness. In which case, this article will not be enough to persuade you one way or the other. If you say “yes, in a sense, but chess seems like a special case,” then read on!

### Sensation: all you need?

Now, suppose I have Searle’s [Chinese room](https://en.wikipedia.org/wiki/Chinese_room) symbol mapping memorized. someone asks me “What does the ‘狗’ token mean?”, and I say “In the system, ‘狗’ usually appears in strings with ‘`蓬松的`’, ‘取回’, and ‘宠物’; ‘狗是哺乳动物’ is a string in the system; and whenever someone inputs ‘狗是什狗是什么’, I am supposed to respond with ‘狗是狼的驯化后代如今被当作宠物饲养’.” If I carry on like this, I can provide an exhaustive account of the role ‘狗’ plays within the system, but I will give you absolutely no knowledge of the thing which ‘狗’ refers to. I actually included a precise definition of ‘狗’ in the text above—but it’s *also* written in Mandarin. [Good luck.](https://jacktlab.substack.com/i/183031993/dougs-law)

Now, I will offer another type of knowledge. We are walking down the street, and a fluffy golden retriever, wagging its tail and panting happily, ambles past. I point at the golden retriever and say ‘狗.’

You have probably formed the hypothesis that ‘狗’ means dog. You don’t know this for sure. My pointing and saying ‘狗’ was compatible with ‘狗’ meaning golden retriever, or animal, or happy. Or maybe I wasn’t communicating anything at all—maybe I just felt like pointing and saying ‘狗’, and the dog had nothing to do to it. Theoretically, there are infinite interpretations of what I just did. Practically, you have a built-in, evolutionary capacity for *[folk psychology](https://en.wikipedia.org/wiki/Folk_psychology)*; you automatically assume that I have *intent to communicate*. You know Mandarin is spoken by humans, that human languages have things in common, and so it’s reasonable to assume that since ‘dog’ is a simple English word, it probably has a simple Mandarin interpretation like ‘狗’. And so forth.

So now imagine I attempt to grow your understanding of ‘狗’ and other symbols like it by providing sensory inputs. For each symbol, I give you all of the formal-system operations *and* a bunch of sensory examples of each. You learn sights, smells, sounds, tastes, & feels that go with each word. True, I cannot give you *all* of them, but I can give you so many and you have reasonable priors over how Mandarin is likely to work that I expect you will converge to a reasonable understanding with few errors. In this way, I think you *can* learn what ‘狗’ and symbols like it *mean.*

What’s been added? You might just say “sensory inputs,” but there’s actually a lot of other things contributing to your new understanding. Here are five off the top of my head:

1. Recognition that Mandarin is a *language,* intended to communicate things.
2. Recognition that Mandarin was developed by humans, and therefore attempts to communicate things in a way that humans would.
3. Strong folk psychology, which inclines you towards attributing intent, thoughts, and ideas to other people; you are inclined to interpret my pointing and talking as an attempt to *teach you the language*.
4. Inductive reasoning: if you see five examples of ‘狗’ you can form pretty good hypotheses for what it means.
5. An ability to practice, interact, and get feedback: if you misapply ‘狗’, you will get blank stares (which your folk psychology allows you to interpret as miscommunication).

Claude suggests a couple more:

1. Prior language: This is a huge one in the example as I’ve just presented it—you already have a *dog* concept, you’re just assigning a new symbol to it. However, this is not totally essential—babies learn a first language, after all, and whatever essential concepts are already installed in their brain, I doubt dogs are one.
2. Perceptual similarity judgments: if I show you a tabby cat and say ‘猫’, then show a German shepherd and say ‘狗’, and then I show you a beagle, you can make the inference that the beagle is more likely to be a ‘狗’ than a ‘猫’.

…and so on. From this, we can draw another lesson:

---

**Lesson #2: “Just add senses”** **may not be a drop-in solution to the SGP. Many** ***capabilities*** **for drawing inferences & connecting sensations go into human language-learning.**

---

### Computation: where to go from here?

Two different people, agreeing with Lesson #2, could draw very different conclusions for today’s AI systems.

*Skeptic:* It looks like there really is a fundamental difference between symbol-pushing and language-learning. Even if we admit AI can learn things about chess, there’s no way today’s models are developing human-level comprehension of real-world objects. There’s so much more behind meaning than statistical relationships between tokens. Maybe, once we figure out [neurosymbolic](https://en.wikipedia.org/wiki/Neuro-symbolic_AI) AI or embodied agents we’ll be able to cross that gap; maybe we never will. But we can throw today’s LLMs squarely in the “Chinese room” bin.

*Optimist:* It looks like there really is a fundamental difference between symbol-pushing and language-learning. LLMs are not formal systems—they meet very few of Harlan’s criteria—but at first they seemed close enough to be analogous. However, formal systems like the Chinese room lack so many of the capabilities necessary to actually learn a language; no wonder they’re so impoverished. Today’s LLMs have computational biases towards complicity, manipulate vectors and scalars rather than discrete tokens, train on multi-modal inputs, and get reinforcement learning to train them for semantic accuracy. Mechanistic interpretability (understanding how LLMs work) is still in its infancy, so we can’t be confident one way or another, but we’re seeing some signs of primitive world-models. Maybe it’ll turn out that LLMs turn out to be just as limited in practice, or maybe not. But we should be really skeptical that the theoretical assumptions behind the *symbol*-grounding problem apply to LLMs*.*

A skeptic might argue that the SGP applies to LLMs by the following argument:

1. Every Turing machine meets Harnad’s criteria for being a formal system.
2. Therefore, every Turing machine is subject to the SGP.
3. Every computer program is computationally equivalent to some Turing machine.
4. LLMs are computer programs.
5. Therefore, every LLM is computationally equivalent to a system subject to the SGP.

I actually think this is really under-addressed in Harnad’s paper, so I want to do a deeper dive on it in another post. But for now, keep in mind two things. First, Harnad was not trying to argue this level of generality, because he believed “connectionist” computer programs were *not* subject to the SGP—he believed there was a difference between whether something was running on a symbol system vs. *behaving as* a symbol system. Second, it’s quite possible that brains are computationally equivalent to Turing machines too. In that case, being computationally *equivalent* to something with SGP is not the issue, since presumably people with brains are able to understand things. [Always remember the brains!](https://jacktlab.substack.com/p/how-do-you-think-brains-work)

But even supposing the optimist is right and the SGP doesn’t literally transfer to LLMs, maybe there is an analogous “vector-grounding problem” which does apply. Does a similar conclusion transfer? Or is grounding really a matter of *capabilities* and *causal links* which Chinese rooms lack but LLMs could have?

I’ll be talking about the main paper on the vector-grounding problem, and offering my thoughts, soon. Stay tuned!

[^1]: I might be missing facts about *particular* rooks: that they are often made of wood, that they usually look like little castles—but you could play chess with coins, or thumbtacks, or on a computer. In any of those cases, there would still be rooks, and they would be totally specified by their roles in the symbol system.
