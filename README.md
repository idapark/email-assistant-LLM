# Personalized Email Assistant Using User and Task Models

This repository contains the implementation and report for a personalized email assistant project conducted as part of the course **ELEC-E7852** Computational Design Interaction during Fall 2024 at Aalto University. The project utilized user and task models to generate contextually appropriate emails tailored to the recipient's relationship with the sender. The project is heavily based on a Jupiter Notebook of the course that is made by Joongi Shin at Aalto University. The task of the assingment was to modify the parameters for the LLM to make better predictions.

- See the full report: [Here](/report.pdf)

- For example when the generated topic was "Trip to Spain":
![image](https://github.com/user-attachments/assets/47d47136-7812-4e73-b915-f7139f05f7c6)

---

## Overview

The goal of this project was to develop an email assistant capable of:

1. Understanding user preferences through a user model.
2. Adapting tone, formality, and content based on the relationship between the sender and recipient using a task model.
3. Generating emails aligned with sender characteristics and recipient expectations based on the igven title of the email and recipient.

The assistant was trained on a small dataset of 15 example emails and evaluated for its ability to replicate sender behavior across various topics and recipient types.

---

## Technologies & Tools

- **Jupyter Notebook**: For scripting, model implementation, prototyping and running experiments.
- **ChatGPT**: Assisted in integrating user and task models into the workflow.
- **Email Dataset**: A dataset of 15 sample emails for training and evaluation.

---
## Approach
### User Model
The user model was designed to collect and store information about the sender's preferences, including:
- Who the sender is
- Sender's job
- Sender's response time
### Task Model
The task model was responsible for generating emails based on:
- Who the recipient is
- The recipient's relationship with the sender.
- Goal of the email
- Tone of the email
- Amount of grammatical errors
- Amount of used emojis

### Process
- The user model was initialized and updated with parameters extracted from the email dataset.
- The task model used these parameters to generate emails aligned with the dataset's ground truth for each recipient.
- Evaluation was performed by comparing the assistant-generated emails to the dataset's examples.

## Evaluation Results
### Topic: Trip to Spain
The email assistant generated emails that:
- Matched formality and tone based on the recipient (e.g., for the neding of the emails, "Take care" vs. "Love").
- Appropriately included emojis for informal recipients but excluded them for professional ones.
### Topic: Lunch
The assistant demonstrated:
- Contextual awareness by including scuba diving references for informal recipients (e.g., friends or family).
- Professional restraint in excluding such details for work-related recipients.

## Discussion & Conclusions
### Insights
- The assistant successfully adapted tone, formality, and style to different recipients.
- It preserved the sender's personality traits, such as formality levels and emoji usage.
### Limitations
- Grammatical Corrections: The LLM's tendency to fix grammatical errors prevented it from fully mimicking the sender's true style.
- Data Limitations: Some key contextual information (e.g., face-to-face interactions) was unavailable, leading to gaps in personalization.
- Over-Similarity: Attempts to add parameters (e.g., cultural information) resulted in overly similar emails.
### Future Work
- Incorporate non-email data (e.g., conversation transcripts) for richer contextual understanding.
- Develop methods to preserve sender-specific quirks, such as typos and grammar errors, for a more authentic representation.

## Acknowledgments
This project was completed as part of the course ELEC-E7852 during Fall 2024 at Aalto Universtiy. Special thanks to Joongi Shin and Antti Oulasvirta for their guidance and to the developers of the course-provided Jupyter Notebook example, which served as the foundation for this implementation.

