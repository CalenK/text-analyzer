Describe: wordCounter()

Test: "It should return 1 if a passage has just one word."
Code:
const text = "hello";
wordCounter(text);
Expected Output: 1

Test: "It should return 2 if a passage has two words."
Code:
const text = "hello there";
wordCounter(text);
Expected Output: 2

Test: "It should return 0 for an empty string."
Code: wordCounter("             ");
Expected Output: 0

Test: "It should not count numbers as words."
Code: wordCounter("hi there 77 19");
Expected Output: 2

Describe: numberOfOccurrencesInText()

Test: "It should return 0 occurrences of a word for an empty string."
Code:
const text = "";
const word = "red";
numberOfOccurrencesInText(word, text);
Expected Output: 0

Test: "It should return 1 occurrence of a word when the word and the text are the same."
Code:
const text = "red";
const word = "red";
numberOfOccurrencesInText(word, text);
Expected Output: 1

Test: "It should return 0 occurrences of a word when the word and the text are different."
Code:
const text = "red";
const word = "blue";
numberOfOccurrencesInText(word, text);
Expected Output: 0

Test: "It should return the number of occurrences of a word."
Code:
const text = "red blue red red red green";
const word = "red";
numberOfOccurrencesInText(word, text);
Expected Output: 4

Test: "It should return a word match regardless of case."
Code:
const text = "red RED Red green Green GREEN";
const word = "Red";
numberOfOccurrencesInText(word, text);
Expected Output: 3

Test: "It should return a word match regardless of punctuation."
Code:
const text = "Red! Red. I like red, green, and yellow.";
numberOfOccurrencesInText(word, text);
Expected Output: 3

Describe: offensiveWording()

Test: "It should remove a word that is offensive."
Code:
const text = "Man that's some crazy zoinks."
const word = "zoinks"
offensiveWording(word, text);
Expected Output: 0

Test: "It should remove words that are offensive."
Code:
const text = "Holy zoinks that muppeteer is causing quite the trouble.";
const word = "muppeteer";
offensiveWording(word, text);
Expected Output: 0

Test: "It should remove the most offensive word."
Code:
const text = "Mighty zoinks look at that big biffaroni.";
const word = "biffaroni";
offensiveWording(word, text);
Expected Output: 0

Test: "It should remove the offensive word."
Code:
const text = "Hey let's do a lil loopdaloop for fun.";
const word = "loopdaloop";
offensiveWording(word, text);
Expected Output: 0

Describe: boldPassage()

Test: "It should return null if no word or text in entered."
Code:
const text = "";
const word = "";
boldPassage(word, text);
Expected Output: null

Test: "It should return a non-matching word in a p tag."
Code:
const word = "hello";
const text = "yo";
boldPassage(word, text):
Expected Output: <p>yo</p>

Test: "It should return a matching word in a strong tag."
Code:
const word = "hello";
const text = "hello";
boldPassage(word, text);
Expected Output: <p><strong>hello</strong></p>

Test: "It should wrap words that match in strong tags but not words that don't."
Code:
const word = "hello";
const text = "hello there";
boldPassage(word, text);
Expected Output: <p><strong>hello</strong> there</p>

Test: "It should put part of a word that matches another word in strong tags"
Code:
const word = "pen";
const text = "happen"
boldPassage(word, text);
Expected Output: <p>hap<strong>pen</strong></p>