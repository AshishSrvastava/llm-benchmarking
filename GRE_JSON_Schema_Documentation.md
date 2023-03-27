# GRE JSON Schema Documentation
This document provides a guide for contributors to the JSON schema used for the standardized format of questions and passages in language modeling evaluation.

## Secrtions

The schema is organized into two main sections: lines and questions.

### `lines` section

The lines section contains passages of text that are used as the basis for questions in the questions section. Each entry in the lines section is a key-value pair, where the key is a string representing a unique identifier for the passage and the value is an object containing the following fields:

- `title`: a string representing the title of the passage
- `content`: an array of strings representing the lines of text in the passage

### `questions` section
The `questions` section contains the questions that are used for evaluating language models. Each entry in the `questions` section is a key-value pair, where the key is a string representing a unique identifier for the question and the value is an object containing the following fields:
- `section`: an integer representing the section in which the question appears
- `type`: a string representing the type of question
- `passage`: an object representing the passage on which the question is based. This object contains a single field, lines_id, which is a string representing the unique identifier of the passage.
- `prompt`: a string representing the question prompt
- `blanks` (optional): an array of objects representing the blank fields in the question prompt. Each object contains two fields: id, a string representing a unique identifier for the blank field, and choices, an array of objects representing the answer choices for the blank field. Each object in the choices array contains two fields: label, a string representing a unique identifier for the answer choice, and text, a string representing the text of the answer choice.
- `answer`: an array of strings representing the correct answer(s) to the question
- `p+` (optional): an integer representing the difficulty level of the question, with higher numbers indicating greater difficulty
- `explanation` (optional): a string representing an explanation of the correct answer(s) to the question