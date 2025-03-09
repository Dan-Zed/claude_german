# German Practice System

A lightweight spaced repetition system for German vocabulary and grammar practice, designed to work with Claude.

## System Files

- **german_progress.json**: Your actual progress tracking file
- **instructions.md**: User guide explaining how to use the system
- **system_implementation.md**: Technical details for Claude
- **example_progress.json**: Example of what your progress file will look like after use
- **vocab.txt**
- **grammar_topics.md**

## Getting Started

1. The system is ready to use - no setup required
2. Your progress will be tracked in `german_progress.json`
3. Start a new session using the prompt below

## Start a Practice Session

To begin practicing, start a new conversation with Claude and use the following prompt:

```
lets practice German using our system in /path/to/project.

instructions are in <instructions> intructions.md, system_implementation.md </instructions>
lesson material is in <material> vocab.txt, grammar_topics.md </material>
progress file to be updated is in <progress> german_progress.json </progress>
with an example in example_progress.json

let me know that you understand then we will go from there
```


## Customization

Feel free to edit `instructions.md` to add any personal learning preferences or notes. The system is designed to be lightweight and adaptable to your needs.