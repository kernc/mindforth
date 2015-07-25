EnCog KbRetro KbSearch KbTraversal

### Diagram ###
```
   /^^^^^^^^^\ Generation of "do robots need food" /^^^^^^^^^\
  /   EYE     \     | | |       ___________       /   EAR     \
 /             \    | | |      /   EnCog   \     /  auditory   \
|   ________    |   | | |      \___________/    |   memory      |
|  /"robots"\   |   | | |  ____/___  |   |      |   channel     |
| / percept  \--|---+ | | / Noun-  \ |   |      |     ______    |
| \ engram   /  |  r| | | \ Phrase / |   |      |    /"do"  \   |
|  \________/   |  o| | |  \______/  |   |      |   /"robots"\  |
|               |  b| | |   |   _____V_  |      |  /  "need"  \ |
|               |  o| | |   |  (AskUser)-|------|-(   "food"   )|
|   visual      |  t| | |   |   \_____/  |      |  \__________/ |
|               |  s| | |  _V__________  |      |  ________     |
|   memory      |   |n| | (WhatAuxSVerb)-|------|-/ "what" \    |
|               |   |e| |  \__________/  |      |(   "do"   )   |
|   channel     |   |e| |         _______V____  | \"robots"/    |
|               |   |d| |        / VerbPhrase \ |  \"need"/     |
|               |   | |f|        \____________/ |   \____/      |
|               |   | |o|        /   |     |    |     ____      |
|               |   | |o|  _____/  __V___  |    |    /    \     |
|   _______     |   | |d| (WhoBe) (WhatBe) |    |   /"what"\    |
|  /fresh  \    |   |_|_|  \___/   \____/  |    |  /  "do"  \   |
| / image   \   |  /     \      ___________V_   | / "robots" \  |
| \ engram  /---|--\ Psi /     / WhatAuxSDo  \--|-\   "do"   /  |
|  \_______/    |   \___/      \_____________/  |  \________/   |
```


The DiaGram above shows the AskUser module along with other Mind modules that ask questions. The AskUser module is unique in being called directly by the EnCog English cognition module. EnCog calls AskUser only when a form of artificial curiosity causes the AI Mind to formulate a query-idea. NounPhrase calls WhatAuxSVerb (for "What Do Subjects Verb?") when no direct object is found to go with the given verb in a thought being generated. Likewise, VerbPhrase calls WhatAuxSDo ("What Do Subjects Do?") when the AI is thinking about a particular subject but can not find an associated verb to complete a thought about the subject. VerbPhrase also calls WhoBe to ask "Who is so-and-so?" about a subject known to be masculine or feminine. VerbPhrase calls WhatBe to ask "What is such-and-such?" about a thing that may already be known as the object of one or more verbs but
is not yet known as the subject of any verb.

### Operation ###

The AskUser module is tightly integrated with the WhatAuxSDo module, the EnCog module, and the KbRetro module. There needs to be some sort of grammatical or even philosophical trigger for the AI Mind to start asking questions that are really a departure from whatever conversation is already occurring. Currently two conditions must be fulfilled before the high-level EnCog module abandons normal thought and veers off into AskUser to pose a question. The mind-designer or AI coder arbitrarily establishes these conditions and may therefore change these conditions. First the AI must encounter a plural noun (e.g., "unicorns") about which it can not find knowledge in the knowledge base (KB). So the VerbPhrase module calls WhatAuxSDo to ask, "What do unicorns do?" Whatever the human user tells the AI Mind about unicorns goes into the KB. Perhaps the human user says, "Unicorns fight battles". The AskUser module then takes part of the response-idea and changes to a different subject in order to form a query-idea such as "Do robots fight battles" or "Do you fight battles?" or "Do I fight battles?" The query-idea needs only a "Yes" or "No" response from the human user to impart knowledge to the AI Mind. The KbRetro module acts upon the terse yes-or-no response to adjust the knowledge base retroactively. If the answer is "Yes", KbRetro leaves the query-idea alone as a confirmed idea. If
the answer is "No", KbRetro keeps the associations linking the concepts in the query-idea but inserts an adverbial "NOT modifier into the verb-engram to negate the original query idea. If the original question was "Do robots need food?", now the knowledge stored is, "Robots do not need food". If, on the other hand, the human user answers "Maybe" or anything else different from "Yes" or "No", the KbRetro module goes into the original query-idea and zeroes out the associative tags from concept to concept, so that the AI Mind has gained neither a positive affirmation of the idea nor a negative denial of the idea.

### Purpose ###

[Predecessor](http://mind.sourceforge.net/ask.html) versions of the AskUser module were in charge of coordinating the various questions that the AI might ask. More recently, concrete triggers call the modules that ask the more concrete questions. The AskUser module has taken on the role of asking speculative questions. Right now the EnCog module for English cognition calls the AskUser module, but eventually it may be the prerogative of the FreeWill volition module to embark upon episodes of asking many questions occurring to the emergent ConSciousness of the AI Mind.

### Search ###

The AskUser module enables the AI Mind to conduct a search for information. Instead of asking questions of a nearby or remote human user, an inquiring AI Mind could just as well conduct an Internet search for what it wants to know. The Win32Forth [http://aimind-i.com](http://aimind-i.com) program spawned from MindForth along a different branch of AiEvolution already has the ability to search the Web. A mentifex-class AI translated (ported) into Perl could reside on the Web and conduct searches on behalf of other persons, reasoning with Netizens to refine the search and communicating the results within a context of natural human language.

### Notes ###

Mind-designers and AI programmers should take note of a relatively new DeFault methodology employed in the AskUser module. First the word "ROBOTS" is a DeFault subject for any question to be asked. Then the subjects rotate among the concepts activated by the KbTraversal module, to provide some variety and even some surprise in the output of the AI Mind. Another DeFault is that the module will use the word "ANYTHING" as the direct object if the query-idea has failed to make the transformation from user input to speculative question. So instead of saying, "Do you need food?" the AI might ask, "Do you need anything?"

In our mind-design it is an arbitrary decision to have the lead-up to AskUser involve first the posing of a WhatAuxSDo question about a plural subject, then waiting for a response from the human user, and finally converting the human response into a query-idea for the asking of a question expecting a yes-or-no answer. We use a plural mystery subject like "unicorns" as the basis for asking questions (e.g., "What do unicorns do?") when we could just as well have seized upon any singular subject to ask a similar question, but we reserve the calling of WhoBe and WhatBe for cases involving a singular subject for good reasons. We want the AI Mind to start thinking in terms of asking "What is..." about a singular subject, and not plural subjects, so as to make progress in the area of classifying concepts into an ontology of things that exist in the world. If a human user makes the first mention of a unicorn in the singular, we want the AI to ask the WhatBe question, "What is a unicorn?" and not the WhatAuxSDo question, "What does a unicorn do?" For purposes of machine learning and machine reasoning, it is more valuable to ask what something is rather than what something does. Indeed, what something does is a sub-element under the topic of what something is.

### Discuss ###

  * http://groups.google.com/group/comp.ai.nat-lang

  * http://groups.google.com/group/comp.lang.forth

  * http://groups.google.com/group/comp.lang.javascript

  * http://www.ai-forum.org/topic.asp?forum_id=1&topic_id=8385

  * http://www.chatbots.org/ai_zone/viewthread/240/

### Resources ###

  * http://mind.sourceforge.net/ask.html

  * http://www.donbot.com/AskTheBots/

  * http://groups.google.com/group/comp.infosystems.search

### Wikipedia ###

  * http://en.wikipedia.org/wiki/Modularity_of_Mind
    * http://en.wikipedia.org/wiki/Language_module
      * http://en.wikipedia.org/wiki/Interrogative_mood
      * http://en.wikipedia.org/wiki/Question
        * http://en.wikipedia.org/wiki/Question_answering
          * http://en.wikipedia.org/wiki/Expert_system
          * http://en.wikipedia.org/wiki/Category:Information_retrieval
      * http://en.wikipedia.org/wiki/Word_order
    * http://en.wikipedia.org/wiki/Category:Computational_linguistics

### Memespace ###

[AiApp](http://cyborg.blogspot.com/2011/01/aiapp.html) AiEvolution [AiForum](http://www.ai-forum.org/topic.asp?forum_id=1&topic_id=8385) AiHq AiHasBeenSolved [AiMind](http://aimind-i.com) AiStandards AiTree BeVerb BrainTheory ChangeLog [ChatBots](http://www.chatbots.org/ai_zone/viewthread/240/) CognitiveArchitecture [CognitiveAtlas](http://cognitiveatlas.org) CognitiveChainReaction ConJoin ConSciousness CuriOsity yberneticEconomy [CybOrg](http://cyborg.blogspot.com) DeFault DisAmbiguation DoomsDay EmBodiment EmotiOn EnAdjective EnArticle
EnBoot EnGram EnPrep EnPronoun EnVocab ForthMindTextFile
FreeWill [FreshMeat](http://freshmeat.net/projects/ai) [HackerSpaces](http://hackerspaces.org/wiki/) HackerSpaces HardTakeoff IndustrialEspionage InFerence InStantiate InStinct IntelForth JavaScript JointStewardship JsAiManual KbRetro KbSearch KbTraversal KnowledgeBase LabNotes [LinuxAi](http://cyborg.blogspot.com/2009/11/linux.html) MachineLearning MainLoop [MakerBot](http://www.makerbot.com) MasPar MeanderingChain of Thought MemRistor MentiFex MentifexBashing MetEmPsychosis MfPj MileStones MindForth MindGrid MindMeld MindModule [MindRexx](http://mind.sourceforge.net/mindrexx.html) MotorOutput MovingWave [NegSvo](http://mind.sourceforge.net/negsvo.html) NounAct NounPhrase NumBer OldestLivingAiMind OmegaPoint OntoLogy OpenSource PriorArt ProsperityEngine PsiDamp PsiDecay PsychoSurgery QuIckening RecursiveSelfImprovement ReJuvenate [RentaCoder](http://www.rentacoder.com) RoadMap RoBot ScholarPedia [ScienceMuseum](http://cyborg.blogspot.com/2009/09/sciencemuseum.html) SeCurity SeedAi SelfReferentialThought SemanticMemory SensoryInput SeTi ShareWare [SiteSucker](http://www.sitesucker.us) SlashDot SloshOver SpeechAct SpreadAct SpreadingActivation StarTrek StrongAi SubConscious SuperComputer SuperIntelligence [TechnoRati](http://technorati.com) [TechnoSingularity](http://cyborg.blogspot.com/2009/08/singularity.html) TelePresence [TextBook](http://www.chatbots.org/book/ai4u/) ThInk TimeLine TransHumanism [TrustMetric](http://cyborg.blogspot.com/2009/10/trustmetric.html) TuringTest TwItter UseNet UserManual VerbPhrase VisRecog VpAi [WebCyc](http://mind.sourceforge.net/webcyc.html) WikiPedia [WikiReader](http://thewikireader.com) Win32Forth

### AI For You ###

Click to run

[![](http://farm1.static.flickr.com/51/179758367_f283f0d6e0_s.jpg)](http://www.scn.org/~mentifex/AiMind.html)

AI For You

**Table of Contents**
