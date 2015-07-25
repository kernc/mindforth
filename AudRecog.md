AudBuffer AudInput AudMem

### Diagram ###

```
   /^^^^^^^^^\  Auditory Recognition of "c-a-t-s"  /^^^^^^^^^\
  /    EYE    \ REACTIVATED                       /   EAR     \
 /             \ CONCEPTS                        /"CATS"=input \
|   _______     |   | | |    SEMANTIC MEMORY    |               |
|  /old    \!!!!|!!!| | |                       |  C     match! |
| / image   \---|-----+ |             ___       |  -A    match! |
| \ fetch   /   |   |c| |            /   \      |    R    stop  |
|  \_______/    |   |a| |           /     \     |     S   drop  |
|               |   |t| |          / Old-  \    |               |
|  visual       |   |s| |         ( Concept )   |  C     match! |
|               |  e| | |          \       /    |  -A    match! |
|  memory       |  a| | |          /\     /!!!!!|!!!!T   match! |
|               |  t| | |   ______/  \___/------|-----S  recog! |
|  reactivation |   | |f|  /      \             |               |
|               |   | |i| (EnParser)            |  C     match! |
|  channel      |   | |s|  \______/             |  -A    match! |
|   _______     |   | |h|      |                |  --T   match! |
|  /old    \    |   |_|_|     _V_________       |  ---S   busy  |
| / image   \   |  /     \   /           \      |      U  drop  |
| \ store   /---|--\ Psi /--( InStantiate )     |       P drop  |
|  \_______/    |   \___/    \___________/      |               |
```

### Code from MindForth ###

```

:  AudRecog ( auditory recognition )
  0 audrec !
  0 psi !
  8 act !
  0 actbase !
  midway @  spt @ DO
    I 0 aud{ @ pho @ = IF  \ If incoming pho matches stored aud0;
      I 1 aud{ @ 0 = IF    \ if matching engram has no activation;
        I 3 aud{ @ 1 = IF  \ if beg=1 on matching no-act aud engram;
       \ audrun @ 1 = IF   \ if comparing start of a word; 8may2010
         audrun @ 2 < IF   \ if comparing start of a word; 8may2010
          I 4 aud{ @ 1 = IF   \ If beg-aud has ctu=1 continuing,
            8 I 1+   1 aud{ !  \ activate the N-I-L character,
            0 audrec !
            I   5 aud{ @ 0 > IF   \ audpsi available? 27dec2012
              I 5 aud{ @ prc !  \ provisional recognition 27dec2012
            THEN  \ end of test for an early audpsi; 27dec2012
          ELSE
            len @ 1 = IF
              I 5 aud{ @  monopsi !
            THEN  \ End of test for one char length.
          THEN   \ end of test for continuation of beg-aud
         THEN  \ end of test for audrun=1 start of word.
        THEN   \ end of test for a beg(inning) non-active aud0
      THEN   \ end of test for matching aud0 with no activation
      I 1 aud{ @ 0 > IF  \ If matching aud0 has activation,
        0 audrec !       \ Zero out any previous audrec.
        I 4 aud{ @ 1 = IF  \ If act-match aud0 has ctu=1 continuing,
          2 act +!           \ Increment act for discrimination.
          0 audrec !         \ because match-up is not complete.
          act @ I 1+   1 aud{ ! \ Increment for discrimination.
        THEN  \ end of test for active-match aud0 continuation
        I 4 aud{ @ 0 = IF  \ If ctu=0 indicates end of word
          len @ 2 = IF  \ If len(gth) is only two characters.
            I 1 aud{ @ 7 > IF  \ testing for eight (8).
              I 5 aud{ @ psibase !  \ Assume a match.
            THEN  \  End of test for act=8 or positive.
          THEN   \ End of test for two-letter words.
        THEN   \ End of test in AudRecog for end of word.
        I 1 aud{ @ 8 > IF  \ If activation higher than initial
          8 actbase !  \ Since act is > 8 anyway; 8may2010
          I 4 aud{ @ 0 = IF  \ If matching word-engram now ends,
            I 1 aud{ @ actbase @ > IF  \ Testing for high act.
              I 5 aud{ @ audrec !  \ Fetch the potential tag
              I 5 aud{ @ subpsi !  \ Seize a potential stem.
              len @ sublen !    \ Hold length of word-stem.
              I 5 aud{ @ psibase !  \ Hold onto winner.
              I 2 psi{ @ recnum !   \ recognized number 19jul2011
              I   4 en{ @  0 > IF  \ from German AI; 27dec2012
                I 4 en{ @ dba !  \ verb-recognition; 27dec2012
              THEN  \  end of test for dba; 27nov20122012
              I 1 aud{ @ actbase !  \ Winner is new actbase.
            THEN  \ End of test for act higher than actbase.
          ELSE  \ part of AudRecog code; 14jul2012
            0 audrec !
            monopsi @ 0 > IF
              monopsi @ audrec !
              0 monopsi !
            THEN  ( http://code.google.com/p/reda4 )
          THEN  \ End of test for final char that has a psi-tag.
        THEN  \  End of test for engram-activation above eight.
      THEN  \ End of test for matching aud0 with activation.
    THEN  \ End of test for a character matching "pho".
    I midway @ = IF  \ If a loop reaches midway; 8may2010
      1 audrun +!  \ Increment audrun beyond unity; 8may2010
    THEN   \ End of test for loop reaching midway; 8may2010
  -1 +LOOP
  0 act !
  0 actbase !
  psibase @ 0 > IF
     psibase @  audrec !
  THEN
  audrec @ 0 = IF
    monopsi @ 0 > IF
      len @ 2 < IF
        monopsi @ audrec !
      THEN
      0 monopsi !
   audrec @ 0 = IF
        psibase @ 0 > IF
          psibase @ audrec !
        THEN
      THEN
    THEN
  THEN
  audrec @ 0 = IF
      morphpsi @ audrec !
    sublen @ 0 > IF
      len @ sublen @ -  stemgap !
    THEN
    stemgap @ 0 < IF 0 stemgap ! THEN
    stemgap @ 1 > IF 0 subpsi ! THEN
    stemgap @ 1 > IF 0 morphpsi ! THEN
    stemgap @ 1 > IF 0 audrec ! THEN
  THEN
  subpsi @ morphpsi !
  0 psibase !
  0 subpsi !
  audrec @ 0 > IF
    stemgap @ 2 > IF
      0 audrec !
    THEN
  THEN
  audrec @ audpsi !
  0 stemgap !  \ safety measure; 22sep2011
; ( http://code.google.com/p/mindforth/wiki/AudRecog )
```

### Function ###

Within the AudRecog comparator there are both functions and considerations. The functions are what the comparator does, and the considerations are guidelines that we mindmakers must keep in mind as we program the functions into the comparator.

One consideration is that we will use the time-variable "midway" to limit backwards searches for word-recognition to an arbitrary length of most recent time, that is, not all the way back to the moment when the artificial mind began its artificial life -- except when the AI must summon all its resources and powers of thought, including an exhaustive search of all possible associations among all the thoughts and perceptions that the AI has ever experienced. Then, and only then, will the AI dwell on a save-the-world problem with infinite patience and with unlimited access to all memories. Meanwhile, until Armageddon or Goetterdaemmerung, we code an AI that looks back recently enough to find quick associations.

Another consideration is that, if the comparator finds multiple engrams of a known word in Aud, the most recent engram should be good enough for the purposes of pattern recognition.

A further consideration is that, if the most recent word-match is found, the search may be called off for more distant matches lying further back in time.

Another consideration is that we want the comparator to be completely robust and bug-free, so that we may safely program other parts of the Robot AI Mind, and so that other people may confidently port the comparator without worrying about bugs.

Another consideration is that we want to "aud-damp" the Aud array after each word-recognition, so that no left-over activation may interfere with fresh attempts to recognize words.

The AudRecog comparator is called over and over again by the auditory Memory (AudMem) just before each auditory engram is stored in the array of the auditory memory channel.

### Purpose ###

The AudRecog auditory recognition module has two main tests.

The first test looks to see if an incoming pho(neme) matches a stored aud0 engram in a search backwards in time.

In AI more advanced than the original 26.Nov.1994 Mind.Rexx, we want the comparator to recognize morphemic sub-matches, that is, partial phonemic strings like the "pre" in the word unpremeditated -- a substring which may or may not supremely affect the meaning of the circumambient word, depending on whether or not the morpheme is accidentally or adventitiously contained within the word being heard.

For all matches, only "beg=1" initial phonemes will get their act(ivation) level raised by an arbitrary incremental value.

The second test checks to see if a given stored phoneme has a positive activation, which indicates a potential match.

Then a string-effect sequence passes the activation on to the next-in-line character, so that, on the next pass, once again a match will cause the activation to be strung further along.

The AudRecog function is at the heart of the Robot AI Mind and it has been quite difficult to program in each language. A good homework assignment for a computer science class or AI textbook would be to port the audRecog comparator module into a given programming language; or to improve the AudRecog algorithm to make it faster or more powerful; or to make the audRecog module capable of learning how to improve itself; or to implement auditory recognition for specific hardware devoted to auditory pattern recognition in physical robots.

The comparator in MindForth is an improvement upon 26.Nov.1994 MindRexx, which recognized only complete, entire English words. The MindForth comparator is designed and coded in such a way as eventually to permit subtleties and gradations of verbal recognition, so that the artificial Mind will gradually become better and better at recognizing a morpheme that meaningfully inhabits a word.

### JavaScript ###

https://github.com/zzmp/juliusjs -- JuliusJS -- is a port of the "Large Vocabulary Continuous Speech Recognition Engine Julius" to JavaScript. If the AI Mind in JavaScript were to be converted to using acoustic phonemes instead of keyboard characters for input, all things pertinent to storage of phonemes in memory and production of phonemes for SpeechAct would also have to be changed.


### SeeAlso ###

http://aihub.net/artificial-intelligence-lab-projects

http://mind.sourceforge.net/audrecog.html

http://www.nlg-wiki.org/systems/Mind.Forth


### AI For You ###

Click to run

[![](http://farm1.static.flickr.com/51/179758367_f283f0d6e0_s.jpg)](http://www.scn.org/~mentifex/Mind.html)

AI For You

### MemeSpace ###

AdminisTrivia AiChat AiEvolution AiHasBeenSolved AiTree BrainTheory CognitiveChainReaction ConSciousness EnTelEchy ForthMindTextFile GenerationOfThought InFerence JavaScript KbSearch KbTraversal KnowledgeBase MachineLearning MasPar MeanderingChain MileStones MindGrid MindModule MindRexx MovingWave NaturalLanguageProcessing OldestLivingAiMind PortingOfCode QuIckening RecursiveSelfImprovement RoadMap RoBot ScienceMuseums SeedAi SelfReferentialThought SpreadingActivation SubConscious SuperComputer SuperIntelligence TechnologicalSingularity TimeLine UserManual