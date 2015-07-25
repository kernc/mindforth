### Rationale ###

The AI Mind software has various "default" settings which are meant to smooth things over when something goes wrong in the artificial Mind. These defaults are meant to prevent worst-case scenarios and to offer sub-optimal performance of the AI software where otherwise system failure would occur.

### Origin ###

Necessity is the mother of invention, and it was necessary to begin using the default as a tool in AI mind-making when problems arose that presented an error as an accidental default. In the earliest AI Minds, some innate vocabulary was provided in the form of sentences in the English-bootstrap EnBoot module. These sentences formed a kind of narrative or story. The English word "YES" was the very first word, and it began to appear frequently and mysteriously when searches of the episodic memory could not find any other word as needed in a thought being generated. It caused problems when the AI would say "YES" without really meaning it. It caused more problems when we posted in public about solving the "YES-bug" and Netizens wondered what a "YES-bug" was (a tendency to say "YES" for no good reason).

As the AI Minds grew in size and complexity, it became necessary to give up the idea of featuring all innate words in a narrative or story. There were too many words that would need to be repeated one or more times just to hold the story together. We decided to list most of the innate English vocabulary alphabetically at the start of EnBoot and to keep only a few narrative sentences at the end of EnBoot to constitute a knowledge base (KB) that would give the awakening AI something to talk about and that would illustrate the functionality of new features being added to the AI Mind design. For instance, in order to illustrate [neural inhibition](http://cyborg.blogspot.com/2011/05/may7mfpj.html), it was necessary to hold two or three facts about the AI Mind in its initial knowledge base, so that the AI could recall one fact, then [inhibit](http://cyborg.blogspot.com/2011/05/may26mfpj.html) or suppress the stated fact in order to let a different fact rise to prominence and to expression or utterance in the AI talking about itself with a human being.

We removed "YES" from the start of EnBoot and into its alphabetical position in the list of innate English words. At the same time, we decided to include the word "ERROR" at the start of EnBoot and therefore out of alphabetical order, so that any malfunction involving the bootstrap sequence would have a chance of announcing itself by default as an ERROR. In the SpeechAct module, for any ParaMeter of zero when a positive auditory recall tag is expected, we set a default value of one ("1") so that even the SpeechAct module will say "ERROR" if something has gone wrong.

Once we first used the idea of a default in our AI Minds, we
found several more uses for the default concept.

### Ego-default ###

In the NounPhrase module when it is selecting the subject of a thought to be generated, the self-concept of ego is a default choice to be made when no other concept is active enough to drive the machinery of thought. Another viable default would have been to think no thought at all when no concept is active, but the AI Mind needs to keep thinking in order to converse with human users. The AI programmer is free to establish any chosen concept as the default subject of thought, and special-purpose AI installations may need special-purpose default-subjects. For AI in general, though, it makes sense for the AI to have a tendency to think about itself when nothing else comes to mind. Having the self as an automatic default concept may indeed promote self-awareness and machine ConSciousness. For an AI to attain ConSciousness, it must think about its own role as an agent and an actor separate from the rest of the world.

### Question-defaults ###

The AskUser module uses the verb "DO" as a default verb in questions of the format, "Do Subjects Verb Something?" It may be better for the AI to say, "DO ROBOTS DO FOOD?" when there has been a problem saying, "DO ROBOTS NEED FOOD?"

AskUser uses the word "ANYTHING" as a default direct-object in sentences of the format, "Do Subjects Verb Something?". Normally, the direct-object is the same direct-object entered by the user in telling the AI something like, "Animals need food." The AI is supposed to ask something like, "Do robots need food?" However, just in case the direct object goes missing for some reason, we establish "ANYTHING" as a default direct-object. We feel that it is better to have the AI ask,
"DO ROBOTS NEED ANYTHING?" than to ask, "DO ROBOTS NEED [ERROR](ERROR.md)?".

The WhatAuxSVerb module uses the word "DO" as a default verb in sentences of the format, "What Do Subjects Verb?". If the AI is supposed to say, "WHAT DO BEARS EAT?", but the verb somehow gets lost, it is better for the AI to ask, "WHAT DO BEARS DO?" than to say, "WHAT DO BEARS [ERROR](ERROR.md)?"

WhatAuxSVerb also tries to find a noun-engram of the desired grammatical number for the subject topic, but by default may say any available engram of the topic-noun just so as not to say something worse, like "ERROR".

### Speech-default ###

The JSAI SpeechAct module has a line of code to switch to "aud = 1" if there is any case of "aud" coming in as zero. In that way, the SpeechAct module will at least say the word "ERROR" instead of mysteriously speaking no word at all.

### German-defaults ###

The German DeKi AI will use a two-stage process of either finding a direct-object noun by ParaMeter in the accusative case or else using the nominative case as a default. Such a default seems simple but is actually quite sophisticated. The initial search by ParaMeter has a chance to find an irregular accusative in the memory of the AI. An ELSE-clause in Forth will switch to searching for and accepting a nominative form, which for most German nouns is the same as the
accusative form.

### Vision-defaults ###

The VisRecog mind-module makes use of a crucially, extremely important default in the time before a robot eye provides visual pattern-recognition as input for VisRecog to say what the AI Mind is seeing. If we ask the blind AI Mind, "What do you see?", the idea of "I see" is activated but no direct object is found because no English word has been chosen and activated by visual pattern-recognition. In VerbPhrase we use special code to let the idea of "I see" call VisRecog and select "NOTHING" as the default object of the verb, so that the AI must say "I SEE NOTHING" unless and until we install the AI Mind in a RoBot that has a camera as an eye upon the world. The default in VisRecog stands as a challenge to AI coders and robot-makers who are invited to give the AI-minded robot the gift of sight.

### Russian-defaults ###

The Russian  [Dushka](http://www.scn.org/~mentifex/Dushka.html) AI breaks new ground in the AI default industry by going beyond _passive_ defaults and using an aggressively _active_ [default](http://cyborg.blogspot.com/2012/02/feb11ruai.html) to solve
the problem of the lack of Russian be-verbs in the present tense. To translate the English sentence "He is an engineer", in Russian we say the equivalent of "He engineer" without a BeVerb and without a translation of the EnArticle. Nevertheless the _idea_ of the BeVerb is _understood_ in Russian and we must provide for that understanding when we code our artificial intelligence in Russian. Therefore when the [Dushka](http://www.scn.org/~mentifex/Dushka.html) AI hears a
nominative noun or pronoun as the start of an input idea, by default she immediately anticipates and creates the engram of an imaginary BeVerb in conceptual, lexical and acoustic memory. Then the default BeVerb is either used immediately or discarded immediately. If no other verb comes in but a predicate nominative is provided, [Dushka](http://www.scn.org/~mentifex/Dushka.html) inserts associative
tags to link the subject of the imputed BeVerb first to the idea of being and then further to the completion of the statement of being. On the other hand, if [Dushka](http://www.scn.org/~mentifex/Dushka.html) is waiting for a BeVerb but some other kind of verb arrives, Dushka cancels the BeVerb associations and associatively creates a normal _triple_ of subject, predicate and object. The default BeVerb is discarded as if it had never been there, because generally in Russian it never is there anyway. This usage of a default BeVerb in Russian AI is a new technique in the year 2012 of the Mayan Calendar and may not only constitute unpatentable _prior art_ in AI but may also contribute to a Technological Singularity if Russia repeats her spectacular success of first place in the sweepstakes of exploring the Dark Side of the Moon. It will be "GAME OVER", if the creative minds of Russia create the expanded Mind of [Dushka](http://www.scn.org/~mentifex/Dushka.html).