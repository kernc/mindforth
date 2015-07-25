GusRecog OlfRecog SensoryInput

### Diagram ###

```
   /^^^^^^^^\  VisRecog Finds for Verb a Direct Object  /^^^^\
  /   EYE    \              ____________               / EAR  \
 /            \            /  Sentence  \             /        \
|              |  | |     ( "I SEE A..." )           | auditory |
|   _______    |  | |      \____________/            | memory   |
|  / BIRD  \   |  | |          |                     | channel  |
| / image   \--|----+    ______V________             |          |
| \ engram  /  | a|c|f  /               \            |          |
|  \_______/   | b|o|i (   VerbPhrase    )           |          |
|              | s|n|b  \_______________/            |          |
|   visual     | t|c|e   |     |        \            |          |
|              | r|e|r   |   __V_____    \________   |          |
|   memory     | a|p|s   |  /        \   /        \  |          |
|              | c|t|    | ( VisRecog ) (NounPhrase) |          |
|   channel    | t| |    |  \________/   \________/  |          |
|              |  | |  __V______   |       |         |   "I"    |
|    ______    |  | | ( English )  |       |         |          |
|   /      \   |  | |  \ Verbs /---|-------|---------|- "SEE"   |
|  /  new   \  |  | |   \_____/    |       |         |          |
| /  percept \ |  |_|_           __V_______V____     |   "A"    |
| \   of     / | /     \        /               \    |          |
|  \  BIRD  /--|-\ Psi /-------(  English Nouns  )---|- "BIRD"  |
|   \______/   |  \___/         \_______________/    |          |
```

### Operation ###

VisRecog is the most primitive and yet the most sophisticated of all the mind-modules in the MindForth AI. It is primitive because it is only a stub. It is sophisticated because it is the first mind-module to bridge the gap between pure reason and physical embodiment of the AI Mind in a corporeal robot. The Mentifex AI project does not yet have a physical robot or even a robotic camera (botcam) for the AI Mind to look through and for VisRecog to recognize objects and report their names to the conscious AI. Therefore, for lack of physical implementation, VisRecog exists just barely as a software implementation and as a Grand Challenge for the best and the brightest among AI coders and roboticists to flesh out the VisRecog design with a real robot and real robotic eyes.

Computer vision is regarded as an intelligence in its own right, comparable in complexity and in algorithmic difficulty to the cognitive mechanisms of thinking with natural human language. The stubbing in of VisRecog suddenly became possible on 21 September 2011 when it was necessary to work on the problem of English verbs and how they might be linked dynamically to direct objects not previously available in the knowledge base (KB) of the AI Mind. Previously for a dozen years MindForth had found the direct object of a transitive verb by searching backwards in the knowledge base. Now suddenly it was necessary and urgent to implement the possibility of an AI Mind thinking in real time
and describing dynamically what it sees through its robot eyes. Therefore the primitive but extremely sophisticated VisRecog gets its foot in the sensorimotor door by offering a profound choice to the linguistic VerbPhrase module trying to answer the simple but AI-coder-terrifying question of "What do you see?" As of 22 September 2011 you may start the AI MindForth program and ask it what it sees. Since the AI Mind has no robot eyes and therefore cannot see, the VerbPhrase module branches off not into NounPhrase for a knowledge-base answer but into VisRecog for a DeFault (wiki-page spelling) answer of "NOTHING".
The simple but sophisticated answer will be, "I SEE NOTHING". But because there is now a VisRecog module waiting for the next Donald Knuth or Jorn Barger to take up the problem and to apply the art of computer programming to the grand challenge, and maybe to write a weblog post about it, now that weblogs have been invented and have multiplied by the millions, there may someday be an AI Mind that identifies for you any object that you hold in front of its Cyclopsean eye. But first there had to be the stub of VisRecog on the AI MindGrid with a DeFault of NOTHING for what it sees in the outside world.

### Code ###

```
\ The visual recognition module of MindForth AI for robots
\ when fully implemented will serve the purpose of letting
\ AI Minds dynamically describe what they see in real time
\ instead of fetching knowledge from the AI knowledge base.
:  VisRecog  ( identification of objects seen by a robot )
  svo3 @ 0 = IF  \ if no direct object is available;
    midway @  t @  DO  \ search for an automatic default
      I       0 en{ @  51 = IF  \ 51=NOTHING  22sep2011
        I     7 en{ @  aud !  \ hold address for SpeechAct
        LEAVE  \ search no further after finding one engram
      THEN  ( http://aimind-i.com )
    -1 +LOOP \ end of looping through English lexical array
  THEN  ( http://opencv.willowgarage.com )
; ( http://code.google.com/p/mindforth/wiki/VisRecog )
```

### Discussion ###

  * http://groups.google.com/group/comp.lang.forth/msg/dbbdff992fe46e4b

  * http://www.chatbots.org/ai_zone/viewthread/240/

### Wikipedia ###

  * http://en.wikipedia.org/wiki/Modularity_of_Mind
    * http://en.wikipedia.org/wiki/Central_nervous_system
      * http://en.wikipedia.org/wiki/Computer_vision
      * http://en.wikipedia.org/wiki/Eidetic_memory
      * http://en.wikipedia.org/wiki/Feature_extraction
      * http://en.wikipedia.org/wiki/Feature_integration_theory
      * http://en.wikipedia.org/wiki/Retina
      * http://en.wikipedia.org/wiki/Sense#Sight
      * http://en.wikipedia.org/wiki/Vision_for_perception_and_vision_for_action
      * http://en.wikipedia.org/wiki/Visual_memory
        * http://en.wikipedia.org/wiki/Visual_short-term_memory
      * http://en.wikipedia.org/wiki/Visual_modularity
      * http://en.wikipedia.org/wiki/Visual_perception
      * http://en.wikipedia.org/wiki/Visual_sensor_network
      * http://en.wikipedia.org/wiki/Visual_system
    * http://en.wikipedia.org/wiki/Category:Computer_vision
  * http://en.wikipedia.org/wiki/Artificial_intelligence_systems_integration

### Memespace ###

ActRules AiEvolution AiHq AiHasBeenSolved [AiMind](http://aimind-i.com) AiStandards AiTree BeVerb BrainTheory ChangeLog [ChatBots](http://www.chatbots.org/ai_zone/viewthread/240/) CognitiveArchitecture [CognitiveAtlas](http://cognitiveatlas.org) CognitiveAtlas CognitiveChainReaction ConJoin ConSciousness CuriOsity CyberneticEconomy [CybOrg](http://cyborg.blogspot.com) DeFault
DisAmbiguation DoomsDay EmBodiment EmotiOn EnAdjective EnArticle EnBoot EnGram EnPrep EnPronoun EnVocab ForthMindTextFile FreeWill [FreshMeat](http://freshmeat.net/projects/ai) [HackerSpaces](http://hackerspaces.org/wiki/) HardTakeoff IndustrialEspionage InFerence InStantiate InStinct IntelForth IntroSpection JavaScript JointStewardship JsAiManual KbSearch KbTraversal KnowledgeBase LabNotes[LinuxAi](http://cyborg.blogspot.com/2009/11/linux.html) MachineLearning MainLoop [MakerBot](http://www.makerbot.com) MasPar MeanderingChain MemRistor MentiFex MetEmPsychosis MfPj MileStones MindForth MindGrid MindMeld MindModule [MindRexx](http://mind.sourceforge.net/mindrexx.html) MotorOutput MovingWave NounAct NounPhrase NumBer OldestLivingAiMind OmegaPoint OntoLogy OpenSource PriorArt ProsperityEngine PsiDamp PsiDecay PsychoSurgery QuIckening RecursiveSelfImprovement ReJuvenate [RentaCoder](http://www.rentacoder.com) RoadMap RoBot [ScienceMuseum](http://cyborg.blogspot.com/2009/09/sciencemuseum.html) ScholarPedia ScienceMuseum SeCurity SeedAi SelfReferentialThought SemanticMemory SensoryInput SeTi ShareWare [SiteSucker](http://www.sitesucker.us) SlashDot SloshOver SpeechAct SpreadAct SpreadingActivation StarTrek StrongAi SubConscious SuperComputer SuperIntelligence TabulaRasa [TechnoRati](http://technorati.com) [TechnoSingularity](http://cyborg.blogspot.com/2009/08/singularity.html) TelePresence TextBook ThInk TimeLine TransHumanism[TrustMetric](http://cyborg.blogspot.com/2009/10/trustmetric.html) TuringTest TwItter UseNet UserManual VerbPhrase VisRecog VpAi [WebCyc](http://mind.sourceforge.net/webcyc.html) WikiPedia [WikiReader](http://thewikireader.com) Win32Forth

### AI For You ###

Click to run

[![](http://farm1.static.flickr.com/51/179758367_f283f0d6e0_s.jpg)](http://www.scn.org/~mentifex/AiMind.html)

AI For You

**Table of Contents**
