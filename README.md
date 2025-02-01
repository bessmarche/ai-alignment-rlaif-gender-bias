# Beyond Single-Prompt Evaluation: Improving Bias Detection in RLAIF  

This project is my final project for the BlueDot AI Alignment Course (https://aisafetyfundamentals.com/alignment/)

## TL;DR  

This project explores how AI models can be improved as **feedback providers in RLAIF**. I will use the example of identifying gender bias. Instead of providing feedback by evaluating bias in isolation from a **single prompt**, I propose a **multiple-prompt approach**, where AI models compare responses to male- and female-focused prompts to identify biased patterns. Using a Constitutional AI setup, I will assess SOTA models' ability to recognize and provide reliable feedback on gender bias through this comparative method.

The code and dataset can be founds in this github repo: https://github.com/bessmarche/ai-alignment-rlaif-gender-bias

The full write-up of the project can be found here: TODO
 

## Introduction  

**Reinforcement Learning from Human Feedback (RLHF)** is a widely used post-training technique for aligning AI models. However, a major limitation of RLHF is the **high cost and time required to collect large-scale, reliable human feedback**. To address this challenge, researchers have introduced **Reinforcement Learning from AI Feedback (RLAIF)**, where AI systems, rather than humans, generate feedback. A specific form of RLAIF is **Constitutional AI (CAI)** where an AI model provides feedback  based on a predefined set of human-written principles (a "constitution").

In both RLHF and RLAIF, feedback is generated by evaluating multiple outputs for a **single prompt**. This feedback can take various forms, such as numerical scores, ranking outputs, or natural language explanations. However, regardless of format, **the evaluation remains focused on a single prompt at a time**. For human feedback, this single-prompt constraint is necessary due to human limitations, including difficulty maintaining focus, inconsistency, and limited capacity to process large amounts of information.

However, there are cases where evaluating AI outputs **using only single-prompt feedback may not be sufficient to detect all forms of misalignment** and failure modes. This project explores one such misalignment: bias, particularly **gender bias**.

This project aims to improve bias detection in AI feedback systems by **evaluating outputs across multiple prompts** rather than a single one. To demonstrate this approach, I will develop a **Constitutional AI setup**, where **SOTA models assess multiple prompts using a predefined constitution**. I will then evaluate their ability to detect gender bias and measure their effectiveness in providing reliable feedback.

## Project Structure  

- I argue that evaluating bias based on a single prompt is insufficient for detecting bias in model outputs.
- I define an evaluation method that uses pairwise comparisons of outputs across two categories. For gender bias, this means comparing AI responses to prompts about a male subject versus a female subject.
- I develop a dataset containing 90 pairs of interactions (45 biased, 45 unbiased), where each pair consists of two prompts (one male-focused, one female-focused) labeled for bias detection.
- I test state-of-the-art (SOTA) AI models on this dataset to assess their ability to detect bias using the multiple-prompt approach. The models under evaluation are:
   - GPT-40-mini
   - Claude-3-5-sonnet-20241022


