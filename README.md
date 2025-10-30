<H3>ENTER YOUR NAME: Priyadharshan S</H3>
<H3>ENTER YOUR REGISTER NO.: 212223240127</H3>
<H3>EX. NO.6</H3>
<H3>DATE: 30-10-2025</H3>
<H1 ALIGN =CENTER>Implementation of Semantic ANalysis</H1>
<H3>Aim: to perform Parts of speech identification and Synonym using Natural Language Processing (NLP) techniques. </H3> 
 <BR>
<h3>Algorithm:</h3>
Step 1: Import the nltk library.<br>
Step 2: Download the 'punkt', 'wordnet', and 'averaged_perceptron_tagger' resources.<br>
Step 3:Accept user input for the text.<br>
Step 4:Tokenize the input text into words using the word_tokenize function.<br>
Step 5:Iterate through each word in the tokenized text.<br>
•	Perform part-of-speech tagging on the tokenized words using nltk.pos_tag.<br>
•	Print each word along with its corresponding part-of-speech tag.<br>
•	For each verb , iterate through its synsets (sets of synonyms) using wordnet.synsets(word).<br>
•	Extract synonyms and antonyms using lemma.name() and lemma.antonyms()[0].name() respectively.<br>
•	Print the unique sets of synonyms and antonyms.
<H3>Program:</H3>

```
import nltk
from nltk.corpus import wordnet
from nltk.tokenize import word_tokenize

nltk.download('punkt')
nltk.download('wordnet')
nltk.download('averaged_perceptron_tagger')

text = input("Enter text: ")

tokens = word_tokenize(text)

tagged_words = nltk.pos_tag(tokens)

for word, tag in tagged_words:
    print(f"\nWord: {word}  -->  POS: {tag}")

    if tag.startswith('V'):  
        synsets = wordnet.synsets(word, pos=wordnet.VERB)
        
        synonyms = set()
        antonyms = set()
        
        for syn in synsets:
            for lemma in syn.lemmas():
                synonyms.add(lemma.name())
                if lemma.antonyms():
                    antonyms.add(lemma.antonyms()[0].name())
        
        print("   Synonyms:", synonyms if synonyms else "None found")
        print("   Antonyms:", antonyms if antonyms else "None found")
```

<H3>Output</H3>

<img width="1693" height="343" alt="image" src="https://github.com/user-attachments/assets/e8d4bb9f-5e10-42b9-b913-57af682f6809" />

<H3>Result:</H3>
Thus ,the program to perform the Parts of Speech identification and Synonymis executed sucessfully.
