---
layout: post
title: "Three limits on understanding language"
date: 2025-12-31
---

A common accusation against LLMs is that they don’t understand what they are saying, that they are merely parroting what they have heard, and that training giant neural nets for next-token prediction on big written corpuses cannot instill any kind of semantic comprehension.

I think these critiques are probably wrong. But they are not *trivially* wrong. In fact, there are strong limitative arguments that suggest pure induction from lexical corpuses can’t instill comprehension on their own!

These limitative principles are so cool that I decided to devote a post just to articulating them. In a future post, I’ll discuss whether LLMs are really cognitively hamstrung by these limitations. Enjoy!

### Gold’s Theorem

[Gold’s Theorem](https://en.wikipedia.org/wiki/Language_identification_in_the_limit#Gold's_theorem) proves it is impossible to learn a language by observation.

…

No, not really. People do it all the time. But it is a critical limitative result which sheds light on *how* they do it. Let’s begin with some definitions.

A *string* is a sequence of symbols. A *language* is a set of strings which marks some strings as valid and all others as invalid. For instance, English includes “I threw a wombat” but not “wombat wombat a threw a I.” Programming languages accept some programs as grammatical and rejects others as gibberish. Some languages are finite, like the language consisting only of the strings “Jack is cool,” “Silas’ mustache is glorious,” and “water is wet.” Some languages are infinite, like the language consisting of all even-length strings: “aa”, “aaaa”, “aaaaaa”, …

So, let’s play a game. I’m thinking of a language, and I’m going to list out all its strings.[^1] Your job is to guess the language. But I’m not going to tell you whether you get it right or not, I’m just going to keep listing strings. You win if, after a finite number of timesteps, you settle on the correct language and do not revise your guess.

Now, winning this is trivial for finite languages. At some point I will run out of strings to say and stop talking. You now know the complete language. But what about infinite languages? What’s your strategy? Stop and think for a moment, if you are so inclined!

Unfortunately, there is no winning strategy. Every language-learning algorithm falls into one of two categories:[^2]

1. It generalizes beyond the text it has seen. For instance, if it sees “ab”, “aab”, and “aaab”, it might guess that “aaaab” belongs to the language. However, since it never receives negative feedback, it won’t know whether this is correct until “aaab” is listed, and for infinite languages “aaab” may *never* be listed and the waiting never terminates. So it’s impossible to correct overgeneralization in a finite number of timesteps.
2. It never generalizes beyond the text it has seen. If it sees “ab”, “aab”, and “aaab”, the guess just consists in those three strings. But that means the guess will always, at every timestep, be a finite language. So the guess will never be correct for any infinite language.

This is theoretically impossible. So Gold’s question was: how the heck do human children learn English just by listening to it?

Now, there are a wealth of practical answers to this question, including:

- We don’t need to have perfect grasps of the language, just enough to get around with.
- We receive negative feedback when communication fails.
- We’re neurally wired up to be inclined to learn in certain ways; we’re not considering an algorithm that would work for any theoretical language, just the ones humans are likely to come up with.

But Gold’s Theorem shows that *you do need a practical answer*. Theoretically, all the text in the world could not tell you whether a new sentence will be grammatically valid English, unless you rely on the learner and the historical processes that created English having some extra information in common. So what is that extra information? That’s a great place for cognitive scientists to start. And it provides strong intuitive backing for the next thinking tool I’m going to introduce.

### Doug’s Law

In *Gödel, Escher, Bach,* Doug Hofstadter writes about a letter in a bottle, written in Japanese. Hofstadter argues that this letter contains multiple messages. Obviously there is the *inner* message, which is the message written in Japanese. But when someone starts looking at the letter, a second message is also conveyed to them: that this letter is written in Japanese. This is called the *outer* message, the knowledge of how to properly interpret the language to get the inner message. Hofstadter makes the following observation:

It would be of no use to include in the inner message a translation of the sentence “This message is in Japanese,” since it would take someone who knew Japanese to read it. And before reading it, he would have to recognize the fact that, as it is in Japanese, he can read it. You might try wriggle out of this by including translations of the statement “This message is in Japanese” into many different languages. That would help it practical sense, but in a theoretical sense the same difficulty is there. An English-speaking person still has to recognize the “Englishness” of the message; otherwise it does no good. Thus one cannot avoid the problem that one has to find out how to decipher the inner message from the outside.

Ten years later, Stevan Harnad came up with a similar example in “The Symbol Grounding Problem:” “Suppose you had to learn Chinese as a first language and the only source of information you had was a Chinese/Chinese dictionary!” At best, you could only learn that 狗 is typically followed by 毛茸茸的, 尾巴, 动物, and the like. You’d never learn that the symbol 狗 refers to dogs. And even if the dictionary had helpful sentences like “Each of these symbols refers to an object in the world; this section is about animals,” it would do you no good if those sentences were written in Chinese. For to learn the instructions on how to interpret the language, you must first know how to interpret the instructions.

“Hofstadter’s Law” is taken, so I like to call this Doug’s Law: *How to interpret a language cannot be communicated in that language alone.* Sure, there are ways to figure it out if you have some prior knowledge about what the language is likely to be, or you are already “wired up” to interpret the language somehow. But then you are not learning from that language alone: critical information and skills are already encoded in you. Writing “here’s how you should wire up a brain to understand this dictionary; first, …” in Chinese would again be futile.

### The symbol-grounding problem

Harnad was the first to name the problem this, but the idea dates back to at least Searle’s “Chinese room” thought experiment. Let’s look at a modified example of it: suppose John is given an enormous book with a bunch of canned responses and symbol-manipulation rules in Chinese, a language he does not speak. John memorizes the book and then discards it. Whenever someone passes John a note written in Chinese, like 你家狗叫什么名字, he consults his memory of the rulebook, mentally swaps out a bunch of symbols, and knows to reply with 我的狗叫宝.

Now, John can give cogent replies to any Chinese statement. And the people who read them will definitely *interpret* them as meaningful. But it remains a fact that John does not understand Chinese. He has no idea what these symbols mean. And because he has discarded the book and does all the operations mentally, it is difficult to say that it is “the room” or “the system” which understands what the symbols mean; all of it is happening in John’s head, and John has no idea what’s going on.

There are interesting replies to this, like that John is running a “virtual mind” which possesses understanding, but none of them avoid the simple fact that John does not understand what he is saying. So we should not be at all confident that a Chinese-room like language model, which just learns completions based on sentence structure and statistical regularity, has any idea what it is saying.

The symbol grounding problem is a challenge for formal-system theories of cognition, whose proponents believe that minds really are doing symbolic manipulations and that the formal system explains cognition. The argument roughly goes:

1. Knowing all of the rules of the formal system for a language, which strings map to which other strings, does *not* imply that you know what those strings *mean.* (argued by Chinese room)
2. We know what we mean when we say words like “dog.” (premise)
3. Therefore, our knowledge about the word “dog” does not just consist in knowing the symbolic role of the “dog” token in some kind of formal system.

I find this pretty damn persuasive.

But note that it is not strictly entailed by Doug’s Law. Doug’s Law only asserts that you cannot learn the meaning of symbols in a language if all you have is a text stream of those symbols and *no* prior knowledge of how that language works. The symbol grounding problem makes a stronger claim, that even if you do understand the rules of the full formal system, you *still* might not know what the symbols mean.

### Implications for language models

Now, all of these are theoretical limitative results. As we saw, Gold’s Theorem does not in practice restrict the ability of children to learn English; it just informs us that kids must be getting some help outside of the text stream, either by being “wired up” in such a way as to make learning English more likely, or by receiving some other kind of feedback.

If LLMs were purely inductive models with no computational constraints, storing all their next-token predictions in a massive lookup table, and operating on an alien language with no semantic patterns in syntax, then yes, I would imagine they would fail pretty badly at understanding even if they become quite good mimics. But if LLMs receive any “help”, anything in their computational environment, training, or corpus that can link syntax to semantics, then these theoretical limits do not strictly apply. And I think there are good reasons to think that modern LLMs do get “help.” But that is an article for another time.

[^1]: For infinite languages, this means that for any string, I will eventually say that string after some finite number of timesteps; just as if I start counting from 1, 2, 3, … up to infinity, for any *N* I will eventually say that number after *N* timesteps.
[^2]: There could be probabilistic strategies or alternatives which are between the two cases, but they also fail. The formal proof is just a little more detail than I’d like to get into, but Gold’s paper is pretty readable if you’re curious!
