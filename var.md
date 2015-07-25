## Table of Variables ##

### abc ###

AudBuffer transfer character.

### act ###

activation level.

### actbase ###

AudRecog discrimination activation base.

### actran ###

PsiDecay holder of activation-levels.

### adjcon ###

insert-adjective condition-flag.

### adverbact ###

_adverbial activation-level_ - potentially a holder of a threshold-level trigger for calling an adverb-module.

### aftjux ###

after-jux for negation of verb of being.

### anset ###

Before vowel set article AN insertion.

### atcd ###

Antecedent for EnPronoun or DePronoun or RuPronoun.

### aud ###

auditory recall-tag for activating engrams.

### audbase ###

recall-vector for VerbGen module.

### audjuste ###

NounPhrase motjuste aud to SpeechAct module.

### becon ###

_be-conditional_ – carries a flag from the OldConcept recognition module indicating that new input includes a verb of being which may permit the InFerence module to make a general inference about the subject of the input so that the InFerence module can look for prior knowledge as the basis of an inference.

### bias ###

Holds the expectation of what part-of-speech (POS) will be
assigned to a word being parsed or instantiated as a concept.

### dobseq ###

_direct-object-subSEQuent word_ – is used only within the InFerence module to hold onto the psi identifier of a noun or pronoun that was the direct object of a verb retrieved from memory as part of an inference that will require the same direct object to be associated with the verb if the inference is to be confirmed or refuted as a valid inference.

### fyi ###

The fyi (for your information) variable holds a single-digit
number that determines the display mode of the AI Mind.
With fyi at zero (0), the display is in normal mode. With
fyi at one (1), the AI is in transcript mode. With fyi at
two (2), tutorial mode is in effect. With fyi at three (3),
diagnostic mode is in effect for troubleshooting.

### inft ###

_inference-time_ – holds the current time at the start of the InFerence module so that the AskUser module can ask a question based upon pre-existing knowledge before the formation of a silent inference in the AI memory.

### kbtv ###

The kbtv (knowledge-base traversal) variable holds a numeric
value that rotates through a range of integer numbers.
In the KbTraversal module, the rotating kbtv value
determines which natural-language bootstrap concept
will be reactivated to start a fresh chain of thought
going when there has recently been no user input.
By rotating thorugh a range of values set by the
AI programmer, kbtv causes the AI Mind to rotate
through a variety of subject-matter concepts serving
as points of departure for conversational gambits
when the AI Mind offers to interact with a human user.

### midway ###

_halfway back through memory_ – holds a default value of one for the very beginning of the AI memory but is available for the dynamic setting of a limit on searches when the AI Mind has been living and thinking for such an enormously long time that it is not necessary to search the entire mental history of the AI to find a word or a concept. On the other hand, AI coders could establish a mechanism to set midway back to the beginning in order to conduct a truly exhaustive search of memory.

### moot ###

As in legally _moot_ – is a flag to prevent the formation of associative tags during mental operations which are not truly a part of cognition, such as the processing of an input query, the formation of a silent inference, or the creation of an output query.

### prednom ###

_Predicate nominative_ -- a noun or adjective expressed in the nominative case as part of a predicate based on an intransitive verb of being or becoming or seeming or so forth.

### psi ###

The psi variable (from the Greek letter "psi") is a numeric
identifier of a concept in the conceptual Psi array.
The psi concepts represent neuronal fibers, or interwoven
gangs of fibers, in the mindgrid as theorized in the
AI theory of mind serving as the basis of mindforth AI.

### quobj ###

_query object_ – holds onto the psi identifier of a word chosen by the InFerence module to be the direct object of a query created by the AskUser module.

### qusub ###

_query subject_ – is a transfer-vehicle of the subject-identifier from any module prompting a question into the specific module that will ask the question.

### quverb ###

_query verb_ – is set in the InFerence module with the identifier of a verb concept serving as part of an inference being made about user input. Then the AskUser module transforms the quverb identifier into the yes-or-no-verb identifier ynverb so that AskUser can use the query-verb to ask a question expecting a yes-or-no answer.

### seq ###

_subSEQuent_ – is the following or subsequent concept with which a concept in a sentence of thought is associated.

### seqtqv ###

_subSEQuent time-quod-vide (time-which-see)_ – is used only within the InFerence module to latch onto the specific time-point in memory of a verb which was linked in the past to a concept now occurring within user input as a predicate nominative which identifies a class of entities from which an inference can be drawn and assigned to the subject of the user input. For instance, if the AI knows "Boys play games" and the user inputs "John is a boy," the old verb "play" can now be used to infer, "John plays games," because John is a boy.

### seqverb ###

_subSEQuent-concept VERB_ – is an interstitial carrier of a verb-identifier in the InFerence module, permitting a verb which was used in old knowledge to be used as part of an inference of new knowledge and as part of a question seeking confirmation or refutation of an inference.

### statuscon ###

The term statuscon is not itself a variable but instead it
denotes a class of "condition" variables as in the popular
"defcon" term for "defense condition". When the statuscon
variables come into use, they will permit a MindModule
to be at or below a quiescent threshold so that the module
will not perform its main operational function, but will
remain merely ready to do so.

### subjnom ###

_subject nominative_ – is a concept identified in the OldConcept recognition module as the subject of an input causing the AI to make an inference.

### subjpsi ###

The subjpsi (subject psi concept) variable originates in
the NounPhrase module to keep track of the psi concept number
of any personal pronoun chosen to be the subject of a
sentence being generated. In the BeVerb module, subjpsi
supports conditional logic that intervenes in the wrong
choice of a verb of being, causing the grammatically
correct verb-form to be substituted for the originally
wrong choice. As the mindforth AI evolves, this technique
of verb-form intervention is not an admission of failure
but rather an example of the gradual improvement of an AI
algorithm as it performs its mission.

### t ###

_time_ – is incremented during AudInput and in the InFerence module during the creation of a silent inference in memory. Time "t" is not the real time of the external world, but is rather an internal counter of moments when sensory engrams and related concepts are stored in the time-dimension of the AI MindGrid.

### yncon ###

_yes-or-no condition_ – is a status flag that a module like InFerence can set to a positive one in order to trigger the calling of the AskUser module by the English cognition EnCog module.

### ynverb ###

_yes-or-no-verb_ – identifier of a verb to be used in AskUser for the asking of a question expecting a yes-or-no answer.