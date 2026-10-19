# CoRT — Code-Reviewing Tutor

> **Keeping learning on the job alive in the age of AI.**

CoRT’s primary goal is to **help developers learn their craft**.

It helps developers understand AI-generated code changes by asking fundamental and advanced questions about them. CoRT does not judge your code; the skill uses it as learning material to teach you.

---

# Vision

For decades, software developers **learned primarily on the job**.

They implemented features, made mistakes, compared solutions, received feedback, and gradually developed engineering intuition through day-to-day work.

AI-assisted development changes this process fundamentally.

Today, AI can generate large parts of an implementation, explain APIs, write tests, and support pull request workflows. This increases productivity, but it can also reduce the learning opportunities that naturally came from working through code changes yourself.

CoRT's goal is not only to make developers explain what the code does, but to help them build the knowledge and intuition to work with it confidently in the future.

---

# How CoRT Works

CoRT runs directly inside the developer’s IDE.

Each session begins with a choice:

* **Explore the code:** follow questions grounded in the code, without learning goals or progress ratings.
* **Work toward curriculum goals:** focus on relevant unfinished objectives in `references/curriculum.md` and save demonstrated progress. 

In practice, CoRT:

* selects relevant code excerpts
* asks understanding-oriented questions
* adapts the depth of its questions to the developer’s level
* follows the learner’s chosen session mode
* tracks progress only in curriculum mode
* helps turn code changes into durable understanding

---

# How to run the skill

To start, point CoRT to one or more commits:


   > /code-reviewing-tutor {commit hash}  
   > Run CoRT on commit # d2911c9

   > Run CoRT on this branch compared to main
   
   > Ask me about the content of PR #168

---

# Installation

## Installation as a Personal Skill

If you want CoRT to be available in all local projects, you can install it as a personal skill.

```text
~/.agents/skills/code-reviewing-tutor/
```

---

# How to build a curriculum

For curriculum mode, add short learning objectives as Markdown bullets in the installed skill's `references/curriculum.md`, for example:

```markdown
- Understand async/await.
- Trace dependency injection.
- Know HTTP methods and return codes.
- Explain features of hexagonal architecture.
```

