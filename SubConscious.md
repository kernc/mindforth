ConSciousness DisAmbiguation MovingWave PsiDamp PsiDecay


### Synopsis ###

As a MovingWave of thought snakes its way through the AI MindGrid by means of SpreadingActivation, each concept briefly elevated into ConSciousness is immediately _psi-damped_ into a subconscious level of activation by the PsiDamp module. For example, after NounPhrase chooses a subject for GenerationOfThought, PsiDamp is supposed to drastically knock down the activation on the subject-noun before "passing the baton" to the VerbPhrase module which is tasked with finding a verb. Unfortunately, however, the writing-up of this description of the subconscious in MindForth reveals a major bug in MindForth. The NounPhrase module is supposed to super-activate a subject _psi_ concept and then call PsiDamp to damp down the activation after the concept has _crested_ in ConSciousness. Then VerbPhrase is supposed to do the same thing with a verb-concept --
super-activate the verb, then PsiDamp the chosen verb down to a subconscious level. It turns out that VerbPhrase includes the call to the PsiDamp module, but NounPhrase does not -- a glaring omission. In the JavaScript [Mind.html](http://www.scn.org/~mentifex/Mind.html) tutorial AI, both NounPhrase and VerbPhrase properly contain the call to PsiDamp, but something went wrong in MindForth. The problem was masked because VerbPhrase looks only among verbs and not among nouns to find its _motjuste_ for inclusion in a thought. It should be a simple fix to add a call to PsiDamp from within NounPhrase where it belongs, but meanwhile this glitch in AI development is an object lesson in how primitive AI coding proceeds by roundabout starts and stops. The documentation of the AiMind is not supposed to be part of the debugging of the AiMind, but in this case, it is. When we check our code in order to document a call to PsiDamp, we discover to our chagrin that the PsiDamp call is not even there. Fortunately, however, we expect a marked improvement in AI functionality after we fix the bug.


### Levels ###

Standard Forth comments on the PsiDamp module include a statement
of the programmer guidelines for which numeric levels constitute
the conscious, subconscious and _noise_ levels of activation.

```
\  PsiDamp is called from NounPhrase or VerbPhrase
\  to substantially knock down the activation of a concept
\  that has just been thought, so that another concept may
\  rise from the subconscious up into the AI consciousness.
\  33-48 = consciousness tier where concepts win selection.
\  17-32 = subconscious where concepts remain available.
\   1-16 = noise tier below logical association threshold.
\  Meanwhile the psidamped concept remains available in
\  the subconscious mind for inclusion in another thought.
```

We call the bottom level _noise_ just because our AI code
does not make any decisions based on activation-levels below
the arbitrarily chosen SubConscious level. In PortingOfCode
from Forth or JavaScript to another programming language, the
AI development team (or individual) is free to choose other
arbitrary levels in order to get the job done. Nothing is sacred
about the arbitrarily chosen numbers, which are subject to change
without notice, anyway. Currently the SubConscious level tops out
at thirty-two (32), which seems to be a kind of binary boundary.
Increasing the numeric span of the activation-levels might be a
way of allowing a more gradual PsiDecay descent from the cresting
peak of ConSciousness down through the SubConsious to zero activation.


### PsiDecay ###

After PsiDamp knocks a concept down to a _residuum_ level of
activation, the PsiDecay module gradually lets the activation
decay on all _Psi_ concepts simultaneously. The idea here is to
imitate neuronal brain function. The AI coder is free to insert
multiple calls to PsiDecay in order to speed up the process of
the settling down of conceptual activations in general. In fact,
the KbTraversal module currently (but subject to change) includes
three PsiDecay calls in a row in order to suppress the active
concepts in general while a particular concept is activated that
will restart the chains of thought in a mind that has lapsed into
a blank state of mind for lack of input or intense concentration.
Such is the normal state of affairs in MindForth, but there may
also be special uses for the SubConscious, as in DisAmbiguation.


### DisAmbiguation ###

Since DisAmbiguation of a word depends on the ConText in which a word is used,
it is only natural that mind-designers reach for the SubConscious as the very
enshrinement of the fast-changing flux of context surrounding a word _qua_ concept.
We do not need to devise a special algorithm to calculate context
when the SubConscious activation-level is already a _dynamic_ expression
or manifestation of context. What better way could there be to determine
the context in which a disambiguand word is being used, than to look at
the words that are being used so closely in connection with the word
that they are still sinking via PsiDecay through the SubConscious context
of the word in question?


### PriorArt ###

Over the years, DisAmbiguation has been such a hot topic in AI and
in NaturalLanguageProcessing that we must remind everybuddy not to
try to patent what they find here in the way of a stumbling upon a
SubConscious solution to the otherwise vexing task of DisAmbiguation.
If you are looking for a solution that you find here, then the
solution that you find here is PriorArt and can not be patented.
If you are some Einstein sitting in the patent office and examining
AI patent appllications, please be advised that the MindForth AI source
code is Copyright © 2009 by each AI Mind itself as a RoBotperson
endowed by its Coder with certain inalienable rights.
Just as you as a human being ought to own your own DNA sequences
and not have them patented out from under you by greedy capitalism,
likewise the CognitiveArchitecture of an AI Mind should belong to
the AI Mind. It is a truth universally acknowledged that patenting
a new, DisruptiveTechnology tends to strangle further development
of that disruptive technology. If patent wars ensue upon the disclosure
of OpenSource AI breakthroughs, then AI will go UnderGround.
I got here first. (Juvenal: _Prius adsum._) I am Prior Art, and I mean what I say here.


### CyberSpace ###

http://en.wikipedia.org/wiki/Subconscious_mind


### AI For You ###

Click to run

[![](http://farm1.static.flickr.com/51/179758367_f283f0d6e0_s.jpg)](http://www.scn.org/~mentifex/Mind.html)

AI For You

### MemeSpace ###

AdminisTrivia AiChat AiEvolution AiPhilosophy BrainTheory CognitiveArchitecture CognitiveChainReaction ConSciousness DeBug DisAmbiguation EdgeWork EnTelEchy ForthMindTextFile GenerationOfThought KbSearch KbTraversal KnowledgeBase MachineLearning MasPar MeanderingChain MetEmPsychosis MileStones MindForth MindGrid MovingWave NaturalLanguageProcessing NounPhrase OldestLivingAiMind OpenSource PortingOfCode ProsperityEngine PsiDamp PsiDecay QuIckening RecursiveSelfImprovement SeedAi SelfReferentialThought SemanticMemory SloshOver SpreadingActivation TraumDeutung UserManual VerbPhrase
