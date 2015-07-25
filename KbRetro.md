AskUser KbSearch KbTraversal

### Diagram ###

```
   /^^^^^^^^^\  KbRetro handles yes-or-no answers  /^^^^^^^^^\
  /   EYE     \  QUERY-IDEA      _________        /   EAR     \
 /             \   |c| | | |    / KbRetro \      /             \
|   _______     |  |a| | | |   /           \    |  Y            |
|  /old    \    |  |t| | | |  /   affirm    \   |   E           |
| / image   \   |  |s| | | |  | query-idea  |---|----S          |
| \ fetch   /   |  | | | | |  |             |   |               |
|  \_______/    | d| |N|h| |  |attach 12=NOT|   |  N            |
|               | o| |O|a| |  |  jux-flag   |---|---O           |
|  visual       |  | |T|v| |  |             |   |               |
|               |  | | |e| |  |             |   |  M            |
|  memory       |  | | | | |  |   remove    |   |   A           |
|               |  | | | |w|  | associative |   |    Y          |
|  reactivation |  | | | |i|  |   tags      |   |     B         |
|               |  | | | |n|  |   from      |---|------E        |
|  channel      |  | | | |g|  |   query     |   |               |
|   _______     |  | | | |s|  |   idea      |---|-(no response) |
|  /old    \    |  |_|_|_|_|_  \___________/    |               |
| / image   \   | /   Psi    \                  |               |
| \ store   /---|-\ Concepts /                  |               |
|  \_______/    |  \________/                   |               |
```

### Operation ###

The KbRetro module accepts answers from a human user when the AI Mind has asked a question expecting a yes-or-no answer. There are actually four possible responses to such a question: yes; no; maybe (and the like); or no answer at all. As in the diagram above, if the AI asks "Do cats have wings?" and the human user answers "No", the KbRetro module retroactively adjusts the knowledge base (KB) by imposing the value of twelve ("12") for "NOT" on the "jux" (juxtapositon) flag of the query-verb in the Psi conceptual memory and leaves the associations among concepts in the query-idea unchanged. The word "CATS" is still associated with the verb "HAVE" and onwards, but negationally, to the concept of "WINGS". The AI will remember, "Cats do not have wings." On the other hand, if the answer is "yes", the associations in the query-idea will remain unchanged and the AI will think, "Cats have wings." If the human user gives an answer like "Maybe" or in fact any answer other than "Yes" or "No", the KbRetro software removes the associative tags from the query-idea and the AI will not know anything about cats having wings. The same happens if the response is no answer at all, because the query-idea has been neither confirmed nor denied.

### Code ###

```
:  KbRetro  ( retroactive adjustment of knowledge base )
  oldpsi @ 27 =  oldpsi @ 32 =  OR IF  \ yes or no 2jul2011
  \ CR ."  KbRetro: answer is " oldpsi @ .  \ 2jul2011
    oldpsi @ 27 = IF  \ 27=NO; 2jul2011
      64  tkbn @  1 psi{ ! \ high noun activation 21jul2011
      64  tkbv @  1 psi{ ! \ set high activation? 2jul2011
      12  tkbv @  3 psi{ ! \ set 12=NOT jux flag; 2jul2011
  \ CR ."  KbRetro: answer is No "  \ 2jul2011
    THEN  \ End of test for "No" answer; 2jul2011
    oldpsi @ 32 = IF  \ 32=YES; 2jul2011
      64  tkbv @  1 psi{ ! \ set high activation? 2jul2011
  \ CR ."  KbRetro: answer is Yes "  \ 2jul2011
    THEN \ End of test for "Yes" answer; 2jul2011
  ELSE  \ if neither; 2jul2011
    0  tkbn @  4 psi{ ! \ delete pre-tag for noun; 2jul2011
    0  tkbn @  6 psi{ ! \ delete seq-tag for noun; 2jul2011
    0  tkbv @  4 psi{ ! \ delete pre-tag for verb; 2jul2011
    0  tkbv @  6 psi{ ! \ delete seq-tag for verb; 2jul2011
  \ CR ."  KbRetro: answer is neither Yes nor No "
  THEN  \ 2jul2011
  0 kbcon !  \ temporarily here turn off kbcon;  2jul2011
  0 tkbn !  \ reset for safety;  2jul2011
  0 tkbv !  \ reset for safety;  2jul2011
;  ( End of KbRetro; return to OldConcept; 2jul2011 )
```

### Demo ###

Users may demonstrate or "demo" the function of the KbRetro module by provoking the AI Mind to ask a yes-or-no query after the input of an unknown plural noun, like "unicorns". First the AI may ask, "What do unicorns do?" If the user answers something like, "Unicorns fight battles", the AI AskUser module may then turn the answer into a question like, "Do robots fight battles?" Users may answer these questions with the four possibilities of yes, no, maybe, or nothing in order to see how the KbRetro module works. In the Diagnostic mode of the JavaScript AiMind.html program, the values of the "jux" flag and of the "pre" and "seq" flags are visible. Likewise in MindForth the AI can be stopped and the ".psi" report can be run to make the flag-panels of the Psi concept array visible. The AI may also behave differently after each answer, perhaps making the negational statement after a "No" answer or moving on to another topic if the answer is not "Yes" or "No".

### Import ###

The function of KbRetro is significant for several reasons.
It is one of the first enhancements of the AI Mind to show
sophisticated, human-like thinking. It shows the interdependence
of various parts of the AI Mind, because all the mind-modules
must cooperate to preserve the negationality of any idea
negated by human users with trustworthy authority.

### Discussion ###

http://groups.google.com/group/comp.lang.forth

http://groups.google.com/group/comp.lang.javascript

### Resources ###

http://groups.google.com/group/comp.ai.nat-lang

http://groups.google.com/group/sci.logic

### Wikipedia ###

  * http://en.wikipedia.org/wiki/Modularity_of_Mind
    * http://en.wikipedia.org/wiki/Language_module
      * http://en.wikipedia.org/wiki/Double_negative
      * http://en.wikipedia.org/wiki/Double_negative_elimination
      * http://en.wikipedia.org/wiki/Negation
      * http://en.wikipedia.org/wiki/Negation_normal_form
    * http://en.wikipedia.org/wiki/Logic
      * http://en.wikipedia.org/wiki/First-order_logic
      * http://en.wikipedia.org/wiki/If_and_only_if
      * http://en.wikipedia.org/wiki/Logical_conjunction
      * http://en.wikipedia.org/wiki/Logical_disjunction
      * http://en.wikipedia.org/wiki/Reasoning
      * http://en.wikipedia.org/wiki/Automated_reasoning
      * http://en.wikipedia.org/wiki/Syllogism
    * http://en.wikipedia.org/wiki/Category:Computational_linguistics

### Memespace ###
[AiApp](http://cyborg.blogspot.com/2011/01/aiapp.html) AiEvolution AiHq AiHasBeenSolved [AiMind](http://aimind-i.com) AiStandards AiTree BeVerb BrainTheory ChangeLog [ChatBots](http://www.chatbots.org/ai_zone/viewthread/240/) CognitiveArchitecture [CognitiveAtlas](http://cognitiveatlas.org) CognitiveAtlas CognitiveChainReaction ConJoin ConSciousness CuriOsity yberneticEconomy [CybOrg](http://cyborg.blogspot.com) DeFault DisAmbiguation DoomsDay EmBodiment EmotiOn EnAdjective EnArticle EnBoot nGram EnPrep EnPronoun EnVocab ForthMindTextFile [ForthWorks](http://forthworks.com) FreeWill [FreshMeat](http://freshmeat.net/projects/ai) [HackerSpaces](http://hackerspaces.org/wiki/) HardTakeoff IndustrialEspionage InFerence InStantiate InStinct IntelForth JavaScript JointStewardship JsAiManual KbSearch KbTraversal nowledgeBase LabNotes [LinuxAi](http://cyborg.blogspot.com/2009/11/linux.html) MachineLearning MainLoop [MakerBot](http://www.makerbot.com) MasPar MeanderingChain of Thought MemRistor MentiFex MentifexBashing etEmPsychosis MfPj MileStones MindForth MindGrid MindMeld MindModule [MindRexx](http://mind.sourceforge.net/mindrexx.html) MotorOutput MovingWave [NegSvo](http://mind.sourceforge.net/negsvo.html) NounAct NounPhrase NumBer OldestLivingAiMind OmegaPoint OntoLogy penSource PriorArt ProsperityEngine PsiDamp PsiDecay PsychoSurgery uIckening RecursiveSelfImprovement ReJuvenate [RentaCoder](http://www.rentacoder.com) [RetroForth](http://retroforth.org) RoadMap RoBot [ScienceMuseum](http://cyborg.blogspot.com/2009/09/sciencemuseum.html) ScholarPedia ScienceMuseum SeCurity SeedAi SelfReferentialThought emanticMemory SensoryInput SeTi ShareWare [SiteSucker](http://www.sitesucker.us) SlashDot SloshOver SpeechAct SpreadAct SpreadingActivation StarTrek StrongAi SubConscious SuperComputer SuperIntelligence TabulaRasa [TechnoRati](http://technorati.com) [TechnoSingularity](http://cyborg.blogspot.com/2009/08/singularity.html) TelePresence TextBook ThInk TimeLine TransHumanism [TrustMetric](http://cyborg.blogspot.com/2009/10/trustmetric.html) TuringTest TwItter UseNet UserManual VerbPhrase VisRecog VpAi [WebCyc](http://mind.sourceforge.net/webcyc.html) WikiPedia [WikiReader](http://thewikireader.com) Win32Forth

### AI For You ###

Click to run

[![](http://farm1.static.flickr.com/51/179758367_f283f0d6e0_s.jpg)](http://www.scn.org/~mentifex/AiMind.html)

AI For You

**Table of Contents**
