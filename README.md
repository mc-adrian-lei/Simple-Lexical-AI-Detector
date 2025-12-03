Simple Lexical AI Detector

What is this?

This is a lightweight, non-agentic Python utility designed to distinguish between human-written and AI-generated text using Lexical Analysis.

Unlike heavy deep-learning models (like RoBERTa or GPT-Zero) that require massive downloads and GPUs, this script uses statistical heuristics—specifically looking at sentence structure and vocabulary repetition—to make a determination.

How It Works: The "Lexical Hypothesis"

AI models are probabilistic engines designed to predict the next most likely word. This optimization often leads to specific statistical fingerprints that differ from human writing.

1. Burstiness (Sentence Length Variance)

The Concept: Humans are chaotic writers. We mix very short sentences with long, complex ones. This creates "spikes" or "bursts" in sentence length graphs.

The AI Pattern: AI models tend to "smooth out" text to be as readable and safe as possible. This often results in sentences of very uniform length and structure.

The Metric: We calculate the standard deviation or variance of sentence lengths. Low variance triggers the "Likely AI" flag.

2. Lexical Density (Repetition Ratio)

The Concept: Humans naturally vary their vocabulary to avoid sounding repetitive.

The AI Pattern: When an AI gets stuck in a context loop or tries to be overly emphatic, it often repeats specific "anchor words" or transition phrases (e.g., "crucial," "moreover," "landscape") more frequently than a human would.

The Metric: We measure the ratio of words appearing 4+ times against the total unique word count.

Use Cases

✅ 1. Academic & Educational Self-Reflection

Target: Students and Writers.

Use: Run your own drafts through the tool. If it flags your work as "Likely AI," it doesn't mean you are a robot; it means your writing might be monotone or overly repetitive.

Action: Vary your sentence length. Break up long paragraphs. Use more synonyms.

✅ 2. First-Pass Content Triage (SEO)

Target: Editors and SEO Specialists.

Use: Quickly scanning large batches of guest posts or freelance submissions.

Why: AI content often ranks poorly if it lacks "humanity." This tool can flag low-effort, mass-generated content that needs heavy editing before publication.

✅ 3. Spam Filtering

Target: Forum Moderators.

Use: Identifying low-effort, bot-generated comments which often use generic, highly repetitive phrasing.

Limitations

False Positives: Technical writing or legal documents (which require precise, repetitive language) may trigger false positives.

False Negatives: Advanced prompting ("Write in the style of Hemingway") can increase burstiness enough to fool this detector.

Scope: This is a heuristic tool, not a probabilistic one. It detects "robotic writing styles," not necessarily "robot authorship."

Usage

Run the script and paste your text when prompted:

python ai_detector.py


Or pipe a file directly:

cat essay.txt | python ai_detector.py
