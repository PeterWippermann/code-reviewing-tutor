# CoRT -- Code Reviewing Tutor

> **Keeping learning on the job alive in the age of AI.**

CoRT is an IDE-based code reviewing tutor that reviews real project code
and uses its findings to create contextual learning opportunities for
developers.

Unlike conventional AI code reviewers, CoRT's primary goal is **not** to
improve the code. Its primary goal is to **improve the developer**.

------------------------------------------------------------------------

# Vision

For decades, software developers learned primarily **on the job**.

They implemented features, made mistakes, received feedback during code
reviews, discussed alternative solutions, and gradually developed
engineering intuition.

Modern AI-assisted development fundamentally changes this process.

Today, AI generates large parts of the implementation, explains APIs,
writes tests, and even performs pull request reviews. While this
dramatically increases productivity, it also removes many of the
learning opportunities that naturally existed during everyday software
development.

CoRT aims to bring these learning opportunities back.

Rather than replacing AI, CoRT complements it by transforming everyday
code reviews into personalized learning experiences.

------------------------------------------------------------------------

# Philosophy

CoRT follows a simple principle:

> **The review is the means. Learning is the goal.**

A traditional reviewer asks:

-   Is the code correct?
-   Is it maintainable?
-   Should this be merged?

CoRT asks additional questions:

-   What can the developer learn from this code?
-   Which engineering principle is demonstrated here?
-   Which misconception might have led to this implementation?
-   Which topic should the developer study next?
-   How can today's review improve tomorrow's code?

Every review becomes a learning opportunity.

------------------------------------------------------------------------

# How CoRT works

CoRT is intended to run **directly inside the developer's IDE (primarily
Visual Studio Code)**.

Whenever the developer requests a review, CoRT analyzes the code and
produces:

-   constructive review findings
-   explanations behind each finding
-   references to engineering principles
-   follow-up questions that encourage critical thinking
-   optional learning tasks
-   recommendations for further study

The goal is **not** to provide another automated code review.

The goal is to create a mentor-like dialogue around the code.

------------------------------------------------------------------------

# Learning on the Job

CoRT embraces the idea that developers learn best while working on real
software.

Instead of isolated tutorials or artificial exercises, CoRT uses the
developer's own production code as learning material.

Every code review is therefore:

-   relevant
-   contextual
-   immediately applicable
-   directly connected to the developer's daily work

Learning happens naturally while building software.

------------------------------------------------------------------------

# Design Principles

-   Learning before automation
-   Explanations before solutions
-   Context over theory
-   Curiosity over correctness
-   Encourage critical thinking
-   Meet developers where they work: inside the IDE

------------------------------------------------------------------------

# MVP Scope

The first version focuses exclusively on one capability:

**Review Coach**

Future extensions may include additional coaching agents such as:

-   Planning Coach
-   Implementation Coach
-   Debugging Coach
-   Reflection Coach

The Review Coach is intentionally developed first because code review
naturally provides the richest learning opportunities with minimal
disruption to existing development workflows.

------------------------------------------------------------------------

# Installation

> **Coming soon**

Installation instructions will be added once the first public version is
available.

------------------------------------------------------------------------

# Project Status

🚧 Early concept / MVP in development

------------------------------------------------------------------------

# Contributing

Contributions, ideas, discussions, and feedback are welcome.

If you have ideas for improving CoRT or want to discuss AI-supported
learning in software engineering, feel free to open an issue or start a
discussion.

------------------------------------------------------------------------

# License

TBD
