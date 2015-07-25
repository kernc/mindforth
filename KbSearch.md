### Diagram ###

```
The baton-variable "yesorno" follows spreading activation through the KB: 

do cats? YES                        do cats? YES
do cats eat? YES                    do cats eat? YES
do cats eat worms? NO               do cats eat fish? YES

Concepts envisioned as neuronal fibers linked by associative tags
-----------------------------------------------------------------
-------CATS-----*---------*--------------------------------------
----------------|---------|--------------------------------------
------BIRDS-----v-!-------v-------------------*---------*--------
----------------|-|-------|-------------------|---------|--------
-------FISH-----v-|-------v-!-------*---------v---------v-!------
----------------|-|-------|-|-------|---------|---------|-|------
------WORMS-----v-|-------v-|-------v-!-------v-!-------v-|------
----------------|-|-------|-|-------|-|-------|-|-------|-|------
--------EAT-----v-|-------?-*-------?-*-------?-*-------v-|------
----------------|-|-------------------------------------|-|------
------CATCH-----?-*-------------------------------------?-*------
-----------------------------------------------------------------
```

### Purpose ###

KbSearch is an experiment in seeing if an artificial intelligence
can give simple "yes" or "no" answers to questions about what
the AI knows in its KnowledgeBase (KB). When the module was first
implemented on 17.SEP.2008, it could only answer "yes" and not
"no" or "don't know." It does not provide answers with a quarantee
of universal truth; it only makes assertions based on what
the AI thinks it knows.


### Entelechy ###

The KbSearch module aims for the following entelechy goals.
  * Elaborate as prompted on "YES" or "NO" responses.
  * Supply related ideas as afterthoughts to replies.
  * Answer NO if a definite negation is found in memory.
  * Answer I DO NOT KNOW if no affirmation is found.
  * Answer YES if query-baton remembers the fact in question.
  * Follow spread of activation through affirmative remembrance.
  * Use a baton variable to accompany a positive remembrance.
  * It shall seek remembrance of an idea input as a question.
  * It shall search the KB for affirmation or negation.
  * It shall be activated by input of a "DOES...?" question.
  * It shall be activated by input of a "DO...?" question


### Code ###

http://code.google.com/p/mindforth/wiki/ForthMindTextFile
permits both visual inspection of the KbSearch module code
and operational inspection of the KbSearch functionality
when the AI software is running. First the
http://www.winzip.com compression utility for Windows must
be used to extract and auto-install the
http://prdownloads.sourceforge.net/win32forth/W32FOR42_671.zip?download
of the Win32Forth language into which the AI source code is loaded.
See the UserManual for instructions.

### Operation ###

First the KbSearch module detects the word "do" in the input stream
as presumably the first word of a fact-finding question, such as
"Do cats eat fish?" As the elements of the question continue to
come in, KbSearch sends each concept into the KnowledgeBase to
see if spreading activation follows the same course as the
link-up of concepts expressed in the input query. Like a baton
being passed in a relay-race, the "yesorno" variable follows
the spread of activation and keeps track of the likelihood
of "yes" as an answer to the question. As long as the
chain of ideation in the KnowledgeBase continues to match
the series of concepts held in the input question, the
"yesorno" variable holds a yes-flag that will cause the
AI Mind to answer "yes" at the end of a perfect match-up
between query and knowledge.

More work remains to be done so that KbSearch will also
find negative knowledge so as to answer "no" to a question.
Although the AI may simply ignore questions for which it
does not find a "yes" answer, it would be an improvement
if KbSearch could answer "I do not know" to some questions.

The use of a [statuscon](http://code.google.com/p/mindforth/wiki/var#statuscon) variable in some of the NLP modules
may make it possible for the AI to have some leeway in its
choice of either a one-word "yes" answer or an answer that
repeats some of the words in the question, so as to say
something like, "Yes, we have no bananas."

The KbSearch module is an example of a hidden power of the
AI Mind. Up until the human user suddenly receives a
terse "yes" answer to something, with no verbose elaboration,
there is no indication that the AI is smart enough to
answer "yes" or "no" to something. As more and more such
"hidden iceberg" modules take root in the AI Mind, the
human users become less and less aware of how powerful
an artificial intelligence they are dealing with.


### Debug ###

TBA

### Links ###

TBA

### Wikipedia ###

TBA