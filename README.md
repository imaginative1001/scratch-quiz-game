# scratch-quiz-game
as the description has said above, this is a customizable quiz game made in scratch, with a bucketload of custom extensions from turbowarp to help out with special features.

### features of the game:
- coming by default, a quiz about mathematical sets for 10th graders with *✨very creative✨* questions made by AI.
- don't like sets, or prefer a different topic? there's a settings tab to import your own quiz!

speaking of your own quiz...

## the .squiz file format
at it's core, it's a fancy .txt file with special formatting so the game can make out and read different sections, then write said sections to appropriate lists for your quiz.

for the game to read a .squiz file as an actual quiz, the file content is split to 3 sections, seperated from one another by three dashes "\-\-\-":

|section|what it holds|
|---|---|
|configurations|your quiz's configurations as listed in this order:<br>- quiz name (plain text).<br>- answer time limit (non-negative float, all questions).<br>- quiz theme color ("green" or "red").|
|questions|questions for your quiz in plain text.each new question is seperated by a new line.<br><br>a line for your question must be in this format:<br>"{question category}\|\|{question content}" (without quotes).|
|answers|4 answers (A, B, C, D) per question.each tuple of answers is seperated by a new line.<br><br>a tuple of answers must be in this format:<br>"{answer A}&{answer B}&{answer C}&{answer D}&" (without qoutes).<br><br>correct answers must be denoted by a asterisk. for example, if B is correct, write this:<br>"{answer A}&*{answer B}&{answer C}&{answer D}&" (without qoutes).<br><br>there can be multiple correct answers as of v1.3.0.|

after importing a quiz, you must RESTART the game for changes to apply. and by RESTART, i don't mean REFRESH (like F5), because i haven't implemented local storage, and REFRESHing still works like a "factory reset" button as of now. the same goes for exiting the tab, but that's the least of my concerns as closing the game is likely intentional by the user.

here is an example .squiz file if you didn't understand anything i said earlier as a visualization:

```
"Quiz thử nghiệm"
10
red
---
Nhị phân||Dịch 00110010 ra số nguyên không âm.
Nhị phân||Dịch 11010111 ra số nguyên không âm.
---
110010&*50&100&10&
*215&430&11010111&-40&
```
