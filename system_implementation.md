# German Practice System - Implementation Guide

This document provides implementation details for Claude to operate the German practice system. It describes how to handle the core functionality behind the scenes.

## Loading Progress

1. Use `read_file()` to load the progress JSON:
   ```javascript
   const progressData = JSON.parse(await read_file('/Users/daniel.more/Documents/code_projects/german/practice_system/german_progress.json'));
   ```

2. Also load the vocabulary and grammar sources:
   ```javascript
   const vocabSource = await read_file('/Users/daniel.more/Documents/code_projects/german/vocab.txt');
   const grammarSource = await read_file('/Users/daniel.more/Documents/code_projects/german/grammar_topics.md');
   ```

## Lesson Generation Algorithm

1. **Calculate priority scores** for each tracked item:
   ```
   priorityScore = (6 - comfortLevel) * 3 + daysSinceLastPractice
   ```
   This gives more weight to:
   - Lower comfort levels (1-2)
   - Items not practiced recently

2. **Select grammar topics** (one per session):
   - One new topic if available
   - One review topic with highest priority score

3. **Select vocabulary** (usually 5-8 words):
   - 60% new words that haven't been practiced
   - 40% review words with highest priority scores

## Practice Session Flow

1. **Present grammar concept** with explanation and examples
2. **Practice vocabulary** in the context of the grammar concept
3. **Create exercises** that combine the grammar and vocabulary
4. **Assess and rate** progress after each item or at session end

Importantly: do not update the progress json until the user decides to end the session and move on to a new topic


## Updating Progress

1. Update comfort levels based on user feedback
2. Update last practiced date for all items used in session
3. Add session to history with date, focus, and notes
4. Save updated JSON:
   ```javascript
   await write_file('/Users/daniel.more/Documents/code_projects/german/practice_system/german_progress.json', JSON.stringify(progressData, null, 2));
   ```
5. Make sure that the topic and words are practiced multiple times in a session before gauging comfort and performance.

## Special Considerations

- **Encoding**: Be mindful of German special characters when reading/writing files
- **New items**: When introducing new vocabulary or grammar, add them to the progress JSON
- **Session memory**: Keep track of items practiced in the current session

## Example Implementation

For vocabulary practice:
```
1. Present German word
2. Ask for meaning or usage in sentence
3. Provide feedback and correct usage
4. Practice a few times
5. Ask user for comfort level (1-5)
6. Update progress data
```

For grammar practice:
```
1. Explain grammar concept with examples
2. Guide user through creating their own examples
3. Practice using relevant vocabulary with this grammar
4. Practice a few more times
5. Ask user for comfort level (1-5)
6. Update progress data
```