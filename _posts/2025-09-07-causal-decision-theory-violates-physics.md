---
layout: post
title: "Causal Decision Theory Violates Physics"
date: 2025-09-07
---

A common objection to one-boxing in [Newcomb’s problem](https://en.wikipedia.org/wiki/Newcomb's_paradox): *it doesn’t change anything.* Once the money is or isn’t in the box, your decision does not magically cause it to appear or disappear. It’s fixed.

How does one argue that one-boxing doesn’t change anything? By comparing what would happen if you did to what would happen if you didn’t. If in each scenario, the amount of cash in the box were *different*, then obviously it would be wrong to say that it makes no difference.

Now if you are really facing a Newcomb problem, one of those scenarios is a pure hypothetical. Either you take the box or you don’t, so we have to *imagine* what would happen if you chose something different. This is a counterfactual.

But counterfactuals are difficult. Suppose Hal is a deterministic robot, and one day he stands in the middle of a busy road and points a gun at Adam (a human) and pulls the trigger. W might have questions about what *would have* happened if Hal *hadn’t* killed the person. However, Hal is deterministic: he only does what his deterministic physical circuits tell him to do. So if Hal doesn’t kill Adam, there must be some physical difference that caused that change. But which physical difference?

- Hal is hit by a car.
- Hal has a freak mechanical glitch so his finger can’t close around the trigger despite intending to shoot.
- Hal has a freak software glitch so he crashes before he can form the intention to shoot.
- Hal’s programming is different, such that he has a hardcoded rule not to pull *this* trigger on *this* day at *this* person.
- Hal’s programming is different, such that he would never kill anyone.
- Hal’s programming is different, such that in scenarios like this he judges it unjustified to kill someone.
- Hal fires but Adam ducks just at the right moment.

Which possible world we should look depends on the question we want to ask! If we don’t know whether Hal shot Adam and are trying to figure out how to *respond* in either case, we should consider “what would be the most likely scenario where Hal didn’t kill Adam?” In that case, if we know Hal’s programming and hardware are extremely reliable, the relevant possible world is the one where Hal is hit by a car; if we know he was built by Meta, the relevant possible world is the one where he glitches out.

But if we’re asking about whether Hal is *morally culpable* for killing Adam, the relevant worlds change! If you’re trying to kill someone and a freak accident stops you, you’re just as morally culpable as a killer. So we need to compare a world in which Hal deliberately shoots Adam (the actual world) to a world in which Hal *deliberately abstains* from shooting Adam. However, Hal is deterministic. So that’s got to be a world in which his programming and/or environment is different. If you imagine a world where *neither* of those things change, but Hal’s action changes, your imagination is inconsistent with the laws of physics.

Therefore, it is perfectly justified to say “if Hal deliberately refused to shoot, then his programming would be different,” without saying Hal refusing to shoot *causes* his programming to be different.

Unconvinced? Here’s an even simpler example: suppose a smoker collapses and is rushed to the hospital for lung surgery. The doctors know that blackened lungs are a near-foolproof sign of lethal lung cancer; fortunately, her longs are still light. It is not a stretch to say that “if her lungs were black, then she would have lung cancer,” even though the mere pigmentation of one’s lungs is not what *causes* lung cancer.

Now, to Newcomb’s problem. Chell, the deterministic causal decision theory robot, must decide: one-box or two? She imagines two possible worlds: one where she takes the box, and one where she doesn’t. Because she is deterministic, one of those worlds does *not* follow from her present state: she is either going to take the extra box, or she isn’t. So in one of the hypothetical worlds, either:

1. Something about Chell’s environment or programming is different.
2. Chell violates the laws of physics.

CDT only considers changes causally downstream of an intended action—it does not imagine worlds where there are *any* changes before the moment of action. So CDT opts for #2. However, CDT won’t say “if Chell were to choose X, then the laws of physics would be different”, because CDT is supposed to isolate only *causal* effects of choosing X, and clearly choosing X does not *cause* the laws of physics to change. Thus, CDT imagines a hypothetical world in which the laws of physics are exactly the same and the world state is exactly the same but where a deterministic agent does not follow those laws of physics. In other worlds, CDT imagines a contradictoryworld. I don’t just mean counterfactual—I mean *contradictory*. It is contradictory to have a world in which gravity sometimes repels *and* “gravity always attracts” is a law of physics. Either the phenomenon has to go, or the laws have to go, you cannot have both.

What is the alternative? If a deterministic agent makes a choice other than the one they were determined to make, something must be different about their initial state! This is how Functional Decision Theory reasons. In order for you to make a different choice now, something must have been different in you one step before. To cause that difference, there must have been something one step before *that*, and so on. Eventually, something had to have been different *at the time the predictor scanned you.* So the relevant world to consider *is* a world in which the contents of the boxes are different—and it’s not so far-fetched to say that “if I were to take two boxes, then the big box would be empty.” Hopefully now the following quote from Yudkowsky makes sense:

> Just as an FDT agent does not imagine that it is possible for 6288 + 1048 to sum to one thing this week and another thing next week, she does not imagine that it is possible for her decision function to, on the same input, have one output today and another tomorrow. Thus, she does not imagine that there can be a difference between her action today and a sufficiently competent prediction about that action yesterday. In Newcomb’s problem, when she weighs her options, the only scenarios she considers as possibilities are “I one-box and the box is 99% likely to be full” and “I two-box and the box is 99% likely to be empty.” ([Yudkowsky & Soares](https://arxiv.org/abs/1710.05060), pg 5)

*[**UPDATE:** Jesse Clifton in the comments points out that the above quote and the FDT paper reason in terms of* counterlogicals*—imagining that a mathematical function had a different output—rather than counterfactuals about initial conditions. I think the counterfactual approach is sounder and a necessary consequence of the counterlogical thinking, which is why I’m arguing for it here, but it’s not accurate to attribute that to Yudkowsky & Soares. For more on this, [read Jesse’s excellent article](https://jesseclifton.substack.com/p/why-not-all-one-boxers-acausally).]*
