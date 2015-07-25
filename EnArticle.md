AiTree CognitiveChainReaction MileStones UserManual

### Diagram ###

```
   /^^^^^^^^\    EnArticle inserts "a" or "the"    /^^^^^^^^^\
  /   EYE    \              ____________          /   EAR     \
 /            \            /            \        /             \
|              |   | |    (  Sentence    )      | auditory      |
|   _______    |   | |     \____________/       | memory        |
|  /image  \   |   | |             |  \______   | channel       |
| / percept \--|-----+             |  / Verb \  | where         |
| \ engram  /  |  a|c|f            | ( Phrase ) | EnArticle     |
|  \_______/   |  b|o|i            |  \______/  | activates     |
|              |  s|n|b       _____V__/   |     | an engram of  |
|   visual     |  t|c|e      /  Noun  \   |     | "a" or "the"  |
|              |  r|e|r     (  Phrase  )  |     |               |
|   memory     |  a|p|s      \________/   |     |               |
|              |  c|t|  ______|__  |      |     |               |
|   channel    |  t| | (EnArticle) |      |     |               |
|              |   | |  \ "the" /  |      |     |               |
|    ______    |   | |   \ "a" /   |    __V__   |               |
|   /      \   |   | |    \___/    |   / En  \  |     "I"       |
|  / reentry\  |   | |     ________V_ ( Verbs )-|--- "have"     |
| /   of     \ |   |_|_   ( English  ) \_____/  |     "a"       |
| \remembered/ |  /     \  \ Nouns  /-----------|-- "dream"     |
|  \ image  /--|--\ Psi /---\      /            |               |
|   \______/   |   \___/     \____/             |               |
```

### Purpose ###

EnArticle inserts an English article ("a" or "the") before a noun during the generation of a thought. The indefinite article "a" is important for expressing ideas of the "Is-a" variety, as described at http://en.wikipedia.org/wiki/Is-a on Wikipedia. Logical inference kicks in when it becomes known that something or some one "Is-a" member of a supervenient class of entities. For instance, if you tell the Strong AI Mind that "Mary is a woman." the AI may reasonably infer something about Mary and may then ask you, "Does Mary have a child?" If you answer "No", the AI retroactively negates the inferred idea of Mary having a child.

Proper usage of "a" or "the" makes the AI Mind seem more intelligent in conversation with human beings.

### Function ###

The module EnArticle is designed to be called from NounPhrase (or other modules) but not necessarily do anything. EnArticle tests for various conditions and inserts "a" or "the" before a noun only if conditions warrant the insertion. If the condition is found of a singular subect and a verb of being, as in "I am" or "You are" or "He is", EnArticle tries to insert the indefinite article "a" before the noun.

A further function of EnArticle is to insert the definite article "the" if a noun refers to a topic already under discussion. The AI software must set some kind of temporary flag to enable EnArticle to insert "the" instead of "a" before a noun.

The principle or technique of having NounPhrase call EnArticle without a predetermined decision to insert an article before a noun may also be at play in the function of the EnAdjective module for English adjectives or the EnAdverb module for English adverbs. Threshold levels of quasi-neuronal activation may also be involved. If a Mind tries to insert adjectives before a noun, only one or more sufficiently activated adjectives will be able to surface in the consciousness and find verbal expression. Likewise only a sufficiently activated adverb will be included in a thought. With EnArticle, it is not so much activation as logic that plays a role in selecting an article to be inserted.

### Debugging ###

A Mind coder or AI maintainer may find it useful to insert temporary "alert" messages into the EnArticle module to reveal the status of test-flags when the module is called. Since the behavior of EnArticle depends upon test-conditions, observing the status of test-flags allows the programmer to understand why EnArticle is performing or not performing in a certain way.


### SeeAlso ###

http://ai.neocities.org/AiSteps.html

http://aihub.net/artificial-intelligence-lab-projects

http://dl.acm.org/citation.cfm?doid=307824.307853

http://en.wikipedia.org/wiki/Is-a


### AI For You ###

Click to run

[![](http://farm1.static.flickr.com/51/179758367_f283f0d6e0_s.jpg)](http://ai.neocities.org/AiMind.html)

AI For You

### MemeSpace ###

AdminisTrivia AiChat AiEvolution AiHasBeenSolved AiTree BrainTheory CognitiveChainReaction ConSciousness EnTelEchy ForthMindTextFile GenerationOfThought InFerence JavaScript KbSearch KbTraversal KnowledgeBase MachineLearning MasPar MeanderingChain MileStones MindGrid MindModule MindRexx MovingWave NaturalLanguageProcessing OldestLivingAiMind PortingOfCode QuIckening RecursiveSelfImprovement RoadMap RoBot ScienceMuseums SeedAi SelfReferentialThought SpreadingActivation SubConscious SuperComputer SuperIntelligence TechnologicalSingularity TimeLine UserManual