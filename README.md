# shakespeare-gpt
A minimal, educational Implementation of a character-level GPT trained on Shakespeare, inspired by Andrej Karpathy’s nanoGPT.

# Shakespeare GPT – A Character-Level Transformer Trained from Scratch

This is my personal implementation of a character-level GPT model, trained to generate Shakespearean text using a decoder-only Transformer architecture. The goal was to **learn and implement** the core ideas behind GPT models, following [Andrej Karpathy's](https://youtu.be/kCc8FmEb1nY?si=bQ_MIzMNKzJ2ZYlr) legendary "Lets Build GPT from scratch" series.

---

## What This Project Does

- Trains a small autoregressive Transformer model on Shakespeare's works
- Learns to predict the **next character** given a context of previous characters
- Generates coherent, Shakespeare-style text character-by-character
- Built entirely from scratch using **PyTorch**, with a focus on understanding the internals

---

## Goals & Motivation

This project was an educational deep dive into:

- **Self-Attention** – Understanding how the model decides "what to focus on"
- **Positional Encoding** – How transformers handle sequence order without recurrence
- **Autoregressive Modeling** – Predicting one character at a time, based only on the past
- **Decoder-only Transformer** – Building a GPT-style architecture from the ground up

---

## How Attention Works

At the heart of Transformers is **self-attention**, which allows the model to weigh different parts of the input sequence dynamically.

### Core Steps:
1. **Inputs** are projected into **Query (Q)**, **Key (K)**, and **Value (V)** vectors.
2. The attention mechanism computes:

$$
\text{Attention}(Q, K, V) = \text{softmax}\left( \frac{QK^T}{\sqrt{d_k}} \right)V
$$



3. **Masked self-attention** ensures each character only attends to the ones before it (causality).
4. **Multi-head attention** enables the model to learn different types of patterns in parallel.

---

## 🏗️ Transformer Architecture (GPT-Style)

This project uses a **decoder-only Transformer**, like GPT:

![](/Annotated-Transformers-Architecture.webp)

## Sample Output

<div style="max-height: 300px; overflow-y: auto; background: #000000; color: #f8f8f2; padding: 1em; border: 1px solid #444; font-family: monospace; font-size: 0.9em;">



```text
And treason to there anger at the daunts
Hot forbids to give York not lie!

GLOUCESTER:
Say night, my noble scools,
By some eartaff'd and kill'd my sovereign
Hard prison Chamilia: so fare your peers worth
That you, should not see do bring them.

CAPULET:
What say we must better on that steel years?

LADY CAPULET:
There arise they sabel, though you prove!

Nurse:
Faretch, because sir, nor further lady heart.

JULIET:
What, or else dowry honger will not go and us:
Ask thou, tutost very distrent me! I am cull'd
Inform thy holy and Saint Cliffold spile cowards
Ermon begins, presently, whose thrices are creeks no
The enviom'd passable, and the kindwells: I do consul.

Lords:
Being person
Beforedy, some that what is sue in thy sin,
How they dare choose. Fivility, you shall not an
Finisher sainted yours: so thy be bittern is thee
valoued as I have made my is all;
Think all this lets in a nay, but obey is.

FRIAR LAURENCE:
But they not not sue bear me.

FRILANCE:
Provost:
And this daughts and mine here! where
JULIET:
Ay, I am sure near so nop in peace or grace.
What would you have less,
Let purchase for you, and not be honded encommended:
For me, some powers at enter the noble senses,
And so, trove as you, good uprison;
And in the court'sympating heart of the time;
A drunk hell, for mine.

FRUMIO:
Pray, good sheep--O, this in fool the quiet.

Shepherd:
I that like infortion true and some pactly of you banish,
And mothers simplain how the counsel, have you but loss
Reckows in chept depart suition my injust,
Con breaks that may not so brings wandered.
The dretime of thise of the lance:
If ever thou heart inforce their advantage deceive
To thee who shuns mose advantainted daours
Shall even yourself untLuck and living dreads;
The thinish would enough is palace our deep!
Where we must glad that falter for Exetest,
And whether by use, which eas a liventy.

TYBUS:
My lord Watchman:
But lead the pries power a foot.

Clown:
Ay, a lord, soby!

MAMILLIUS:
None, lord,
A mate, Conspirat

...

TYBUS:
My lord Watchman:
But lead the pries power a foot.

Clown:
Ay, a lord, soby!

MAMILLIUS:
None, lord,
A mate, Conspirat


