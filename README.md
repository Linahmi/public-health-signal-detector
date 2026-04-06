# Public Health Signal Detector

Classifies health-related social media posts into 5 epidemiological 
categories and tracks outbreak signals over time.

## Pipeline
1. Load real health tweets (cardiffnlp/tweet_topic_multi)
2. Sentence-BERT embeddings → K-means discovers 10 health subtopics
3. Zero-shot classification with facebook/bart-large-mnli into 5 categories
4. Outbreak signal score: symptom volume this week / 3-week baseline
5. Gradio dashboard: live classifier + trend chart + subtopic map + error analysis

## Categories
- Symptom report
- Prevention behavior
- Misinformation
- News / official report
- Irrelevant

## Live demo
https://huggingface.co/spaces/lina0092/puclic-health-signal-detector

## Relevance
Miniature version of the Crowdbreaks platform built by the Digital 
Epidemiology Lab at EPFL (Müller & Salathé, 2019). Same NLP pipeline, 
same signal detection logic, extended with unsupervised topic discovery.

## Stack
Python · HuggingFace Transformers · Sentence-BERT · scikit-learn · Gradio · Plotly