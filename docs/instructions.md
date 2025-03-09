# German Practice System Instructions

This is a lightweight system for practicing German vocabulary and grammar using spaced repetition principles. The system tracks your progress with vocabulary and grammar topics, prioritizing items based on your comfort level and time since last practice.

## System Overview

- **Progress Tracking**: Your progress is stored in `german_progress.json`
- **Vocabulary Source**: Words are sourced from `vocab.txt`
- **Grammar Topics**: Grammar concepts are sourced from `grammar_topics.md`

## How Comfort Levels Work

Comfort levels are rated on a scale of 1-5:
- **1**: "No idea" - You struggle to recall the meaning/usage
- **2**: "Somewhat familiar" - You recognize but can't use confidently 
- **3**: "Workable" - You can use it but with some hesitation
- **4**: "Comfortable" - You can use correctly with little effort
- **5**: "Mastered" - Effortless recall and natural usage

## Session Structure

Each practice session follows this flow:
1. Load your previous progress
2. Generate a personalized lesson plan based on:
   - Items with lower comfort scores (higher priority)
   - Items you haven't practiced recently (higher priority)
   - A mix of new items and review items
3. Practice through conversation
4. Rate your comfort level with each item
5. Save your updated progress


## Advanced Options

You can customize your practice session with additional instructions:
- "I want to focus more on vocabulary today"
- "I'd like to work with only grammar concepts from the 'Cases' section"
- "Let's do a short/long session today"

## Under the Hood

The system uses a simple weighting algorithm to determine which items to practice:
- Recently practiced items with high comfort scores are less likely to appear
- New items and items with low comfort scores are prioritized
- Some previously mastered items are included for reinforcement

Your progress JSON file grows organically as you practice, only tracking items you've actually worked with.