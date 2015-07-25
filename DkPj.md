## Abstract ##

The DeKi Programming Journal (DKPJ) is both a tool in coding German [Wotan](http://www.scn.org/~mentifex/DeKi.txt) open-source artificial intelligence (AI) and an archival record of the history of how the German SuperComputer AI evolved over time.


## Fri.16.NOV.2012 -- Merging the English and German Source Code ##

The German DeKi artificial intelligence starts fresh today
from a copy of the 15nov12A.F MindForth AI in English.
We will substract English-specific portions of the code and
gradually add in the features that yield a German AI Mind.


## Sat.17.NOV.2012 -- Morphing MindForth into Wotan ##

Today in the German Supercomputer AI Wotan we continue the
transformation of the originally English AI source code into
strictly German AI source code. We run through a series of
small steps before we implement the special algorithms for
thinking in German by manipulating complex German verb-forms.

First we remove the vestiges of the EnBoot English bootstrap,
because we are now running on the DeBoot German bootstrap.
Then we check that the DeKi (German AI) still loads and still
runs, but we stop and change the Transcript header to
"Transcript of 20121117 Wotan AI interview" so as to emphasize
the provocative name of the provocatively named Wotan AI Mind.

Next in the up-front declaration of variables we change the "vault"
value from "611" for the English bootstrap to "940" for the DeBoot
German bootstrap, which must be longer than the EnBoot because we
must include many more irregular forms in German than in English.
The DeKi still loads and runs, but we notice that some of the
personal pronouns have different concept numbers from what we have
been using in [English](http://www.scn.org/~mentifex/AiMind.html) and in [Russian](http://www.scn.org/~mentifex/Dushka.html). Let us change the Psi numbers.

Next we comment out the establishment of the English "en" array,
which has been supplanted by the German "de" array. Then we have
to invite a ".de" report instead of a ".en" report.

Then we change all instances of EnArticle to DeArticle, even though
we are not yet ready to change all the code of the mind-module.

Now we change EnReify to DeReify. The DeKi AI still runs.

We change EnParser to DeParser, and EnCog to DeCog. The AI runs.


## Sat.17.NOV.2012 -- Approaching the OutBuffer ##

Now we will try to make use of the OutBuffer in the Wotan German AI,
as we did with the verb-forms in the [Dushka](http://www.scn.org/~mentifex/Dushka.html) Russian AI.


## Sun.18.NOV.2012 -- Debugging the Hello-World Version ##

We debug the Wotan SuperComputer Strong AI in German by removing
lines of code which we merely commented out in our last session.
Along the way, we discover some DeKi concepts which do not have
the right three-digit concept-numbers to correspond properly with
the other AI Minds in [English](http://www.scn.org/~mentifex/AiMind.html) and in [Russian](http://www.scn.org/~mentifex/Dushka.html). We make the necessary changes. With the words for "what" and "be" set properly, we no longer get "ICH IRRTUM IRRTUM ICH" as the erroneous output from the WhatBe question-asking module, but rather we get "ICH WAS BIN ICH".


## Sun.18.NOV.2012 -- Debugging AudRecog ##

In our last DeKi coding session, Wotan was able to recognize
the German verb "KENNEN" for "to know", but not shorter inflected
forms of the verb. We were puzzled, because one of the other AI
Minds, apparently the [Russian AI](http://www.scn.org/~mentifex/Dushka.html), easily recognizes inflected forms of verbs. Therefore we debug the DeKi AudRecog module by doing a line-by-line comparison with the JavaScript AudRecog code in the [Dushka](http://www.scn.org/~mentifex/Dushka.html) Russian AI Mind. We soon come across the "prc" variable for "provisional recognition", which is in the [Russian AI](http://www.scn.org/~mentifex/Dushka.html) but apparently lacking in the [MindForth](http://www.scn.org/~mentifex/mindforth.txt) and [Wotan](http://www.scn.org/~mentifex/DeKi.txt) AI Minds.


## Wed.21.NOV.2012 -- Verb-Negation Needs Work ##

In the German Wotan AI, we need to move away from the English way of negating verbs and implement the negation of verbs in German without using an auxiliary verb.


## Thurs.22.NOV.2012 -- Restricting Output with Negative Logic ##

In the VerbGen module there is a problem when we try to substitute zero ("0") for an inflectional character that we want to get rid of. Win32Forth displays an unwelcome character for the zero. What we propose doing to solve this problem is not to substitute a different
character such as zero, but rather to conditionalize the very showing of any character. We can use some negative "IF NOT" logic to conditionalize the processing of the last few positions in the OutBuffer.


## Sat.24.NOV.2012 -- Making VerbGen Work ##

We need to concatenate some conditions in the VerbGen module by cascading some OR-clauses. In the English MindForth AI, we discovered that we could start with one initial pair of conditions governed by "OR" and then add as many more "OR" choices as we felt we needed.

As we got VerbGen to work better and better, we discovered a legacy flaw in the NounPhrase module. The "subjpsi" value was being set too capriciously. We commented out the setting code and instead we put a blanket setting at the very end of the motjuste-determination code, so that when the "subjectflag" is set to one ("1") the "motjuste", since it is indeed a subject, has its concept-number value transferred to the "subjpsi" variable. Then in VerbGen, the "subjpsi" value is a determinant in selecting an inflectional ending.


## Sun.25.NOV.2012 -- Improving Parameter Performance ##

Right now the main problem with the German artificial intelligence
Wotan involves the proper setting of each searchable ParaMeter during
thinking and the output of thought. From the [Dushka Russian AI](http://www.scn.org/~mentifex/Dushka.html) we obtain some useful techniques for manipulating the "dba" values.

For incoming verbs, we could perhaps assume a default "dba" of "3" third person, unless a personal pronoun like "I" or "YOU" dislodges the default "dba" of "3" and replaces it with a "1" or a "2".


## Mon.26.NOV.2012 -- Setting "dba" after Verbs ##

Today in the Wotan German AI we will work on a way to assign the correct "dba" values to a noun or pronoun that enters the AI after a verb, so that the item will have either a "dba" of "4" as an accusative direct object, or a "dba" of "1" as a predicate nominative for a verb of being. We will try to use the new "audverb" variable to record the concept number of a "heard" verb, so that we may then test for both a positive "audverb" value and for "800" as the psi number that indicates a be-verb requiring a "dba" of "1" for a predicate nominative.

The new method of using "audverb" to govern dba-settings is working remarkably well. It is setting a "dba" of "4" for direct objects and of "1" for predicate nominatives. It is only a small change in the overall code, and so we may wait until we do some work on German verb-negation before we upload the source code that uses the "audverb" mechanism.


## Tues.27.NOV.2012 -- Negation of German Verbs ##

The negation of German verbs is different from the negation of most English verbs, because the English word "not", along with an auxiliary form of "do", usually comes before the actual English verb, as in, "I do not understand you." It is relatively simple to keep tabs on the word "not" preceding an English verb and to then insert a negational "jux" in the engram of the English verb. In German, where
the word "nicht" for "not" will often come not before but after the verb, it becomes necessary retroactively to set the negational "jux" tag. However, we also set the "seq" tag retroactively on a verb, so it is no more complicated to set the "jux" tag retroactively.

English verbs of being are negated retroactively, and so we can perhaps treat German verbs in general as if they were like English verbs of being for purposes of retroactive negation. Just as we had the variable "tbev" for "time of be-verb", so we make up a variable "tdzw" for "time of deutsches Zeitwort" or "time of German verb".

After we use "tdzw" to store 250=NICHT as the negational "jux" on a German verb, now in VerbPhrase we need to change the code that used an English auxiliary verb to negate a sentence and simply put 250=NICHT after a negated German verb. We will worry later about whether the direct object is a pronoun or not.

## Sat.26.JAN.2013 -- Enlarging the DeBoot Sequence ##

We will try to enlarge the bootstrap sequence with "MAENNER ARBEITEN" in order to demonstrate the storage and retrieval of ideas which have a subject and a verb but no direct object. This feature has recently been added to the English MindForth AI. Using the verb "ARBEITEN" will also help in getting the VerbGen module to deal properly with German verbs that have a stem ending in "T". We will also add to DeBoot the sentence "FRAUEN HABEN EIN KIND" to serve as a premise for machine reasoning with the InFerence module. If someone enters "EVA IST EINE FRAU," the AI should make an InFerence and ask, "HAT EVA EIN KIND".


## Sat.26.JAN.2013 -- Verbs without Objects ##

From the English MindForth AI we import the "transcon" code for simple ideas of subject and verb but no object or predicate nominative. It turns out that the DeKi German AI is having difficulty in recognizing some words, so the new algorithm is basically functional but errors creep in when the AI makes erroneous recognitions. We may need to make sure that the AudRecog module is working in the same way for both English MindForth and German Wotan AI.


## Wed.30.JAN.2013 -- Implementing German AI InFerence ##

Today we are porting the InFerence module from the English MindForth AI into the German Wotan AI. First we drag-and-drop the entire InFerence module from the 24jan13A.F MindForth into the Wotan DeKi source code immediately after the VerbPhrase module. Then we enter the current date at the end of the InFerence comments. Until we declare seven variables (prednom; seqverb; seqtqv; inft; subjnom; dobseq; becon), the German AI will not even "fload". Then it does not create a Psi-array record of any inference, because we have declared the seven variables but we have not yet used them where they belong outside of the InFerence module itself.

## Thurs.31.JAN.2013 -- Troubleshooting the InFerence Module ##

Yesterday in the Wotan German AI we implemented the InFerence module from the English MindForth AI, but we need to continue troubleshooting the German AI functionality because the AI was creating silent inferences with only a subject and a verb but not yet the direct object of the verb.


## Fri.1.FEB.2013 -- Asking Users to Confirm an Inference ##

The Wotan German AI seems to be inserting the wrong "tqv" retroactively across the boundary between sentences, when we type in "eva ist eine frau" in order to trigger an inference. A contributing factor is the code at the start of InStantiate which converts any zero "seqneed" to a 5=noun seqneed by default. It may be time to comment out that code. When we comment out the line setting "tqv" to 5=noun by default, suddenly the AI makes the correct silent InFerence, but we do not know if anything else has gone wrong that was depending on the line
of code that has been commented out.

Then we discover that AskUser is not posing a question based on the silent inference because there is a left-over requirement for a plural noun-phrase number ("nphrnum"). When we comment out that requirement, as we did earlier in the English MindForth AI, we get not the ideal question of "HAT EVA EIN KIND?" but rather the faulty output of "HABEN EVA IRRTUM". This AskUser output is nevertheless gratifying and encouraging, because it reveals that a silent inference has been made, and that the German Wotan AI is trying to ask a yes-or-no question so that a human user will either confirm or refute the InFerence.
