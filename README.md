# CoRT — Code-Reviewing Tutor

> **Keeping learning on the job alive in the age of AI.**

CoRT is an IDE-based learning tutor that helps developers understand their AI-generated code changes and turn these changes into deeper engineering knowledge.

CoRT’s primary goal is to **help developers learn their craft**.

---

# Vision

For decades, software developers **learned primarily on the job**.

They implemented features, made mistakes, compared solutions, received feedback, and gradually developed engineering intuition through day-to-day work.

AI-assisted development changes this process fundamentally.

Today, AI can generate large parts of an implementation, explain APIs, write tests, and support pull request workflows. This increases productivity, but it can also reduce the learning opportunities that naturally came from working through code changes yourself.

CoRT aims to bring those learning opportunities back. It helps developers understand the code changes AI produced and turns those changes into personalized learning experiences.

---

# How CoRT Works

CoRT runs directly inside the developer’s IDE.

It helps developers understand selected parts of AI-generated code changes by asking fundamental and advanced questions about them. Instead of simply judging the code, CoRT turns specific code excerpts into learning material.

Depending on the setup, CoRT may choose the relevant subject area from a predefined curriculum. If a curriculum is used, CoRT can also track learning progress across topics and help guide the next steps in the learning journey.

In practice, CoRT:

* selects relevant code excerpts
* asks understanding-oriented questions
* adapts the depth of its questions to the developer’s level
* uses a curriculum when available to structure the learning path
* tracks progress across topics where configured
* helps turn code changes into durable understanding

The goal is not only to explain what the code does, but to help developers build the knowledge and intuition to work with it confidently in the future.

---

# How to run the skill

To start, point CoRT to one or more commits:


   > /code-reviewing-tutor {commit hash}  
   /cort d2911c9

   > Run CoRT on this branch compared to main
   
   > Ask me about the content of PR #168

---

# Installation

## Installation as a Personal Skill

If you want CoRT to be available in all local projects, you can install it as a personal skill.

On Windows, the target directory is:

```text
%USERPROFILE%\.copilot\skills\code-reviewing-tutor\
```

On Linux, the equivalent path is:

```text
~/.copilot/skills/code-reviewing-tutor/
```
