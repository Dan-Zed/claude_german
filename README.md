# German Practice System

A lightweight spaced repetition system for German vocabulary and grammar practice, designed to work with Claude.

## System Files

- **german_progress.json**: Your actual progress tracking file
- **instructions.md**: User guide explaining how to use the system
- **system_implementation.md**: Technical details for Claude
- **example_progress.json**: Example of what your progress file will look like after use

## Getting Started

1. The system is ready to use - no setup required
2. Your progress will be tracked in `german_progress.json`
3. Start a new session using the prompt below

## Start a Practice Session

To begin practicing, start a new conversation with Claude and use the following prompt:

```
I'd like to practice German using our system in /Users/daniel.more/Documents/code_projects/german/practice_system/. Please load my progress and generate a lesson for today.
```

For a more focused session, you can specify a particular area:

```
I'd like to practice German focusing on modal verbs. Please use our system in /Users/daniel.more/Documents/code_projects/german/practice_system/.
```

## Customization

Feel free to edit `instructions.md` to add any personal learning preferences or notes. The system is designed to be lightweight and adaptable to your needs.