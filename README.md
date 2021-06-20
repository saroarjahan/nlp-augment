# nlp-augment
It takes an sentence as an input and augment it based on sense, pos tag synonym and synonyms.

## Installation
```pip install nlp-augment```


## How to use it?

```import augment```

<strong>Method 1:</strong> We applied word-sense disambiguation to each word of the input sentence, after the preprocessing stagethat removes stopwords and other uncommon characters. The synonymy relation was used to extract the list of sensesfor each word. Next, to find out which of these senses better fit the context of the sentence, Lesk’s algorithm wasemployed. The original version of this algorithm disambiguates words in short sentences. For that, the gloss ofthe word to disambiguate (dictionary of its senses) is compared to glosses of other words of the sentence. Then, thesense that shares the most significant number of common words with the glosses of other words of the phrase is chosenand assigned to the target word. <br>

```augment.sense('litle fox jump over lazy dog')```

```['litle fox jump over lazy dog', 'litle fox startle over lazy dog', 'litle fox start over lazy dog', 'litle fox jump over lazy pawl', 'litle fox jump over lazy detent']```

<strong>Method 2:</strong> We apply a Part of Speech (PoS) Tagging to each sentence, which is later used to extract all meanings(synsets) and synonyms that correspond to that word #PoS combination. This approach could widely expand thesemantic space over the previously mentioned data augmentation approach (method 1), as one word could have multiplemeanings of the same part of speech.<br>

```augment.pos('litle fox jump over lazy dog')```

```['litle fox jump over lazy dog', 'litle flim-flam jump over lazy dog', 'litle play a joke on jump over lazy dog', 'litle play tricks jump over lazy dog', 'litle trick jump over lazy dog', 'litle fob jump over lazy dog', 'litle pull a fast one on jump over lazy dog', 'litle play a trick on jump over lazy dog', 'litle confuse jump over lazy dog', 'litle throw jump over lazy dog', 'litle befuddle jump over lazy dog', 'litle fuddle jump over lazy dog', 'litle bedevil jump over lazy dog', 'litle confound jump over lazy dog', 'litle discombobulate jump over lazy dog', 'litle fox leap over lazy dog', 'litle fox saltation over lazy dog', 'litle fox startle over lazy dog', 'litle fox start over lazy dog', 'litle fox parachuting over lazy dog', 'litle fox jumping over lazy dog', 'litle fox jump over faineant dog', 'litle fox jump over indolent dog', 'litle fox jump over otiose dog', 'litle fox jump over slothful dog', 'litle fox jump over work-shy dog', 'litle fox jump over lazy domestic dog', 'litle fox jump over lazy canis familiaris', 'litle fox jump over lazy frump', 'litle fox jump over lazy cad', 'litle fox jump over lazy bounder', 'litle fox jump over lazy blackguard', 'litle fox jump over lazy hound', 'litle fox jump over lazy heel', 'litle fox jump over lazy frank', 'litle fox jump over lazy frankfurter', 'litle fox jump over lazy hotdog', 'litle fox jump over lazy hot dog', 'litle fox jump over lazy wiener', 'litle fox jump over lazy wienerwurst', 'litle fox jump over lazy weenie', 'litle fox jump over lazy pawl', 'litle fox jump over lazy detent', 'litle fox jump over lazy click', 'litle fox jump over lazy andiron', 'litle fox jump over lazy firedog', 'litle fox jump over lazy dog-iron']```


<strong>Method 3:</strong> We extract all possible meanings (synsets) of every complete word (after preprocessing), and then weretrieve the synonyms associated with every possible meaning. This significantly expands the semantic space of eachsentence compared to the first two methods. We are considering here all possible meanings (including every PoS thatthis word may belong to) as well as the similar words of each meaning regardless of the coherence of the correspondingcontext.

```augment.synonym('litle fox jump over lazy dog')```


```['litle fox jump over lazy dog', 'litle dodger jump over lazy dog', 'litle slyboots jump over lazy dog', 'litle charles james fox jump over lazy dog', 'litle george fox jump over lazy dog', 'litle flim-flam jump over lazy dog', 'litle play a joke on jump over lazy dog', 'litle play tricks jump over lazy dog', 'litle trick jump over lazy dog', 'litle fob jump over lazy dog', 'litle pull a fast one on jump over lazy dog', 'litle play a trick on jump over lazy dog', 'litle confuse jump over lazy dog', 'litle throw jump over lazy dog', 'litle befuddle jump over lazy dog', 'litle fuddle jump over lazy dog', 'litle bedevil jump over lazy dog', 'litle confound jump over lazy dog', 'litle discombobulate jump over lazy dog', 'litle fox leap over lazy dog', 'litle fox saltation over lazy dog', 'litle fox startle over lazy dog', 'litle fox start over lazy dog', 'litle fox parachuting over lazy dog', 'litle fox jumping over lazy dog', 'litle fox bound over lazy dog', 'litle fox spring over lazy dog', 'litle fox leap out over lazy dog', 'litle fox jump out over lazy dog', 'litle fox stand out over lazy dog', 'litle fox stick out over lazy dog', 'litle fox rise over lazy dog', 'litle fox climb up over lazy dog', 'litle fox jump off over lazy dog', 'litle fox derail over lazy dog', 'litle fox chute over lazy dog', 'litle fox parachute over lazy dog', 'litle fox jumpstart over lazy dog', 'litle fox jump-start over lazy dog', 'litle fox pass over over lazy dog', 'litle fox skip over lazy dog', 'litle fox skip over over lazy dog', 'litle fox alternate over lazy dog', 'litle fox jump complete lazy dog', 'litle fox jump concluded lazy dog', 'litle fox jump ended lazy dog', 'litle fox jump all over lazy dog', 'litle fox jump terminated lazy dog', "litle fox jump o'er lazy dog", 'litle fox jump over faineant dog', 'litle fox jump over indolent dog', 'litle fox jump over otiose dog', 'litle fox jump over slothful dog', 'litle fox jump over work-shy dog', 'litle fox jump over lazy domestic dog', 'litle fox jump over lazy canis familiaris', 'litle fox jump over lazy frump', 'litle fox jump over lazy cad', 'litle fox jump over lazy bounder', 'litle fox jump over lazy blackguard', 'litle fox jump over lazy hound', 'litle fox jump over lazy heel', 'litle fox jump over lazy frank', 'litle fox jump over lazy frankfurter', 'litle fox jump over lazy hotdog', 'litle fox jump over lazy hot dog', 'litle fox jump over lazy wiener', 'litle fox jump over lazy wienerwurst', 'litle fox jump over lazy weenie', 'litle fox jump over lazy pawl', 'litle fox jump over lazy detent', 'litle fox jump over lazy click', 'litle fox jump over lazy andiron', 'litle fox jump over lazy firedog', 'litle fox jump over lazy dog-iron', 'litle fox jump over lazy chase', 'litle fox jump over lazy chase after', 'litle fox jump over lazy trail', 'litle fox jump over lazy tail', 'litle fox jump over lazy tag', 'litle fox jump over lazy give chase', 'litle fox jump over lazy go after', 'litle fox jump over lazy track']```

## License

© 2021 Md Saroar Jahan

This repository is licensed under the MIT license. See LICENSE for details.
