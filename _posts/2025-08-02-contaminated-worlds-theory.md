---
layout: post
title: "Contaminated Worlds Theory"
date: 2025-08-02
---

A big challenge for FDT in its current formulation is that it requires modeling *counterpossible* worlds, not just counterfactual ones:

> If a certain decision function outputs *cooperate* on a certain input, then it does so of logical necessity; there is no possible world in which it outputs defect on that input, any more than there are possible worlds where 6288 + 1048 ≠ 7336. The above notion of subjunctive dependence therefore requires FDT agents to evaluate counterpossibilities, in the sense of Cohen (1990), where the antecedents run counter-to-logic. … [An FDT agent] cannot simply imagine a world in which she implements *fn* instead of *d*; she must imagine a world in which all predictors of *d* predict as if *d* behaved like *fn*—and then we are right back to where we started, with a need for some method of predicting how an algorithm would behave if (counterpossibly) *d* behaved different from usual.[^1]

Now, it actually isn’t that hard to model counterpossible implications via [hyperlogic](https://www.cambridge.org/core/journals/review-of-symbolic-logic/article/logic-of-hyperlogic-part-a-foundations/D612493AFF2035E8BA0B7037DA5B91D6) or similar. The problem is that FDT considers *high-level* changes and doesn’t really specify what depends on what when a change is made. Take the example impossible world where 6288 + 1048 ≠ 7336. Here are just a handful of the ways that could be interpreted:

1. The formula is literal and involves no change in conventions. Subtract 1048 from both sides and you get 6288 ≠ 6288. Subtract 6288 from both sides and you get 0 ≠ 0. Add any *n* to both sides and you get *n* ≠ *n*, so no number is equal to itself.
2. The addition operator changes to be a piecewise function which behaves like normal addition except when its two operands are 6288 and 1048. So 1 + 6288 + 1047 = 7336, so addition is no longer associative or commutative.
3. The addition operator isn’t piecewise but is instead a different function like subtraction instead. In this world it might be the case that 6288 + (-1048) = 7336.
4. 1048 no longer refers to the number you get when you add up one thousand and forty-eight ones, but some other number. This doesn’t change the fact that six thousand two hundred eighty-eight plus one thousand and forty-eight equals seven thousand three hundred thirty-six, only the fact that 6288 + 1048 ≠ 7336. So the place value system doesn’t work.
5. Everything to the left of an equals sign is in base 10. Everything to the right is in base 16.

You see the analogous problems for FDT. FDT really recommends one-boxing. If we imagine a world in which FDT instead recommends two-boxing, what changes about it? Does FDT use a different procedure to model alternatives? Or is it a piecewise function, differing exactly in this one input? Or is FDT a non-rigid designator that simply refers to something else in this world? Or does FDT remain formalized the same way but the laws of logic are different? What changes about the physical environs? If you are a physical system and predictors are physical systems, how does a change in some abstract, mathematical function impact what *physically* happens? And so on.

A while ago I thought of an interesting way to (maybe! speculatively! if it works!) sidestep the problem. It probably won’t work, but it is interesting. [Wolfgang Schwarz wrote](https://www.umsu.de/wo/2018/688):

> First, mathematicians are familiar with reductio arguments, which appear to involve impossible suppositions. … “If A were the case then a contradiction would be the case; so A is not the case.” …
>
> If that is how subjunctive supposition works, FDT is doomed. **For if A is a mathematically false proposition, then anything whatsoever mathematically follows from A.** … So then anything whatsoever would be the case on a counterpossible supposition that FDT produces a certain output for a certain decision problem. We would get: *If FDT recommended two-boxing in Newcomb’s Problem, then the second box would be empty*, but also *If FDT recommended two-boxing in Newcomb’s Problem, then the second box would contain a million*, and *If FDT recommended two-boxing in Newcomb’s Problem, the second box would contain a round square*.

This sounds really bad. But consider:

1. “Anything whatsoever” can only be proven in worlds in which we suppose FDT recommends something that it does not, in fact, recommend.
2. Therefore, if we suppose FDT recommends two-boxing when in fact it recommends one-boxing, we can prove anything in that world.
3. However, if we suppose FDT recommends one-boxing and this in fact is the case, we cannot prove everything; for instance, we cannot prove a contradiction .
4. Therefore, if we can identify all of the worlds in which everything is provable and rule them out, we are only left with actions which are in fact recommended by FDT.

Think of it this way: when we imagine *epistemically* possible worlds—which may or may not be logically possible—some of them are “contaminated” by contradictions. You can’t compare contaminated worlds to clean worlds, because any statement is both true and false of a contaminated world. But this very property sets contaminated worlds apart from clean worlds, because there are statements like 0 = 1 which cannot be proven in a clean world but can in a contaminated world.

This sort of trick has been used in logic before. I first learned about a key technique in Nagel & Newman’s *Gödel’s Proof:*

> [If] the calculus is not consistent, every formula is a theorem—which is the same as saying that from a contradictory set of axioms any formula can be derived. But this has a converse: namely, if not every formula is a theorem (i.e., if there is at least one formula that is not derivable from the axioms), then the calculus is consistent. The task, therefore, is to show that there is at least one formula that cannot be derived from the axioms.[^2]

The way to do that in propositional logic is to find a property which all axioms have, which is preserved inductively by all rules of inference, but which some formulas don’t have.[^3] The property Nagel & Newman exploit is that all the axioms, and everything that can be created from them, are *tautologies*: it does not matter what proposition you substitute for the symbols *p* and *q*, they will always be valid. In contrast, the formula *p* ∧ *q* is not tautological: it is true if *p* = “the sky is blue” and *q* = “Jack Thompson is super cool and smart”, but not true if *p* = “the sky is red.” Therefore, *p* ∧ *q* is not an axiom, nor can it be proven from the axioms, and therefore the calculus is consistent. Beautiful.[^4]

Now, this doesn’t neatly map onto a procedure for telling if an FDT-world is contaminated or not. There is no axiomatic formal system for FDT (yet); one would have to enforce a pretty strict object-language vs. metalanguage distinction between alternate models of FDT and what the actual mathematics in the world is; and failure to locate a proof of consistency does not indicate that the system is inconsistent. We have some Gödel and Turing limitations to deal with, too.[^5] Nevertheless, FDT might just be scope-limited enough for such an approach to succeed. This is speculative, but it is worth [shutting up and doing the impossible](https://www.lesswrong.com/posts/nCvvhFBaayaXyuBiD/shut-up-and-do-the-impossible).

[^1]: Yudkowsky, Eliezer, and Nate Soares. “Functional Decision Theory: A New Theory of Instrumental Rationality.” arXiv:1710.05060. Version 2. Preprint, arXiv, May 22, 2018. [https://doi.org/10.48550/arXiv.1710.05060](https://doi.org/10.48550/arXiv.1710.05060).
[^2]: Nagel, Ernest, and Newman, James R.. *Godel's Proof*. Oxford: Taylor & Francis Group, 2005. Accessed August 2, 2025. ProQuest Ebook Central.
[^3]: Technically, substitute “well-formed formula” (or wff) for “formula” here. A wff is just a formula that is grammatically valid even if false. *p* ∧ ¬*p* is a wff, even though it’s false. *pq*∧¬∧*as*∨*f*∧→ is not a wff, it’s gibberish.
[^4]: This was one of those moments, of which I have many, where I visibly gaped at an idea on a book and both felt a sense of wonder and beauty and also felt immensely stupid for never thinking of it myself. I slightly tear up at these moments, and it has been happening to me ever since reading some really cool CS paper when I was 16. (At the time, I remember being a little alarmed at the strength of emotion!)
[^5]: However, Gödel’s [second incompleteness theorem](https://en.wikipedia.org/wiki/G%C3%B6del's_incompleteness_theorems#Second_incompleteness_theorem) isn’t as limitative as it might seem here, since I think most decision theorists would be happy with a demonstration that FDT is consistent with arithmetic or some external system which is *not* modified by a counterpossible.
