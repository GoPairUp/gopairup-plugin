---
name: write-a-quiz
description: Write, find or change a quiz game in GoPairUp. Use when a teacher asks for a quiz, review game, trivia, category board, exit ticket or questions on a topic for their class, or wants to fix or add to a quiz they saved.
---

# Write a quiz

GoPairUp plays a quiz as a team game on the whiteboard: groups take turns, the teacher marks
answers right or wrong, and another group can steal. Use the GoPairUp connector's tools.

## A new quiz

1. **Pick the class.** Call `list_classes` and match the class the teacher named. Ask the grade
   if neither the teacher nor the class name makes it clear.
2. **Tie it to standards.** Call `list_standards` with the subject (`ela`, `math`, `science` or
   `social_studies`), the grade (0 for kindergarten) and a few words of the topic. Pick one to
   three that the questions really assess, and pass their codes.
3. **Write the questions.**
   - Write at the class's grade: short sentences, familiar words, one idea per question.
   - Mix open questions, answered out loud (give the expected `answer`), with multiple choice
     (2 to 4 `choices` and the index of the `correct` one, from 0). Keep wrong choices plausible.
   - Ten to fifteen questions suits most lessons unless the teacher asks for a number.
   - Never put a student's name, or anything about a real student, in a question.
   - For a category board, give `board` instead of `questions`: categories with up to five
     questions each, easiest at the top, since lower rows are worth more.
   - Add an `exit_ticket` of a few multiple-choice questions only when the teacher wants one.
4. **Save it.** Call `create_quiz` with a title of 40 characters or fewer. Tell the teacher the
   title and how many questions it has, and that it's ready to review in GoPairUp.

Saving needs the GoPairUp monthly plan. If `create_quiz` says so, tell the teacher they can
subscribe in GoPairUp under Settings, and offer to show the questions in the chat instead.

## Changing a saved quiz

1. Call `list_quizzes` with words from the title or topic, and the class or grade if known.
   It answers summaries; use `next_cursor` only if the quiz isn't on the first page.
2. Call `get_quiz` for the questions and their `question_id`s.
3. Call `update_quiz` with only what changes: `edit_questions` (each rewritten whole),
   `remove_question_ids`, `add_questions`, `add_to_board` or `add_exit_ticket`. Every change
   lands or none does, so fix a refusal and send it again.
