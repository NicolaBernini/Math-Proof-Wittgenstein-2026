# Math-Proof-Wittgenstein-2026

Wittgenstein Math Proofs 


## What does it mean for an AI to “understand” mathematics?

One major trend in Math-AI today is to formalize mathematics in proof assistants like Lean 4 and let AI models learn from formally verified proofs.

This is clearly powerful — but I think it is ​not sufficient​.

Why? Because correctness alone does not imply ​understanding​.

For both humans and AI, the hard part of mathematics is not checking that a proof is valid, but knowing how to continue when faced with a new problem.

Here I found Ludwig Wittgenstein’s idea surprisingly relevant.

He famously argued that:
“Understanding is knowing how to go on.”

If we take this definition seriously in the context of AI, then “understanding mathematics” means:
- recognizing which rule applies in a given situation,
- knowing which move is legal next,
- and avoiding moves that ​look plausible but are actually invalid​.

This led me to an experiment:
I rewrote a standard proof from functional analysis (Corollary 2.11 in Brezis’ book) in a way that makes the ​continuation logic explicit​:
- what the current “board state” is,
- which rules are being applied,
- why a certain step is allowed,
- and where common misuses happen.

The original proof is correct and elegant — but like many advanced math textbooks, it is not pedagogical in the sense of teaching “how to go on”. It assumes that skill already exists.

My hypothesis is that AI-pedagogical math material should be written differently: not just formally correct, but explicitly structured around ​rules, triggers, and continuation​.

Formalization in Lean may be the next step — but even before that, making the practice of reasoning explicit already adds value.
I’ve committed both versions (original + continuation-explicit) to a public GitHub repo and would love feedback, especially from people working on Math-AI, formal methods, or AI reasoning more broadly.



