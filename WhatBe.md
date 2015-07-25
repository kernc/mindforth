WhatAuxSDo WhatAuxSVerb WhoBe

### Purpose ###

The WhatBe module serves an obvious purpose and several not-so-obvious purposes. Obviously, the module serves to ask a simple question like, "What is truth?", but WhatBe also plays a role in machine learning, logical reasoning with InFerence, and in demonstrating an AI in such settings as schools and museums.

### Learning ###

When the AI has a subject in mind but knows nothing about that subject, WhatBe steps forward to ask human users what the subject is, if the subject is singular. If the subject is plural, the AI will instead call WhatAuxSDo to ask, "What do the subjects do?" This difference in triggering the two types of question is intentional on the part of the mind-designer. When we ask what a singular subject "is" -- as opposed to what it "does" -- we hope to learn what kind of thing the subject is and how we can categorize it in the grand scheme of things, or the OntoLogy of beings in existence. When we ask instead what subjects do in the plural, we are asking for information generally true of a particular class or category of subjects. As the AI learns more and more general attributes of ontological categories, the AI becomes better able to make a logical InFerence about any new single subject belonging to the class or category.

### Inference ###

If the AI Mind uses WhatBe to ask something like, "What is an eagle?" and the AI already knowns that birds have wings, a human being might answer that "An eagle is a bird" and give the AI the opportunity to make an InFerence indicated by AskUser putting the question, "Does an eagle have wings?"

### Code from English MindForth Robot AI ###

```
:  WhatBe ( what AM/IS/ARE Subjects ) \ 10oct2011
  1 moot !  \ prevent storage of spurious ideas; 24oct2011
  0 tqv !  \ prevent spurious carry-over values;  1aug2012
  qusub @ 0 = IF  \ for a new word like "energy"; 8aug2012
    subjnum @ 0 = IF  \ in absence of num(ber) data; 8aug2012
      3 prsn !  \ to say "IS"; 8aug2012
    THEN  \ end of test for "qusub"; 8aug2012
  THEN  \ end of test for "subjnum"; 8aug2012
  topic @ qusub ! \ THEN  \ 2nd choice; 10oct2011
  qusub @ 701 = IF 1 prsn ! THEN  \ 1st person "I"; 10nov2012
  qusub @ 707 = IF 2 prsn ! THEN  \ 2nd person YOU; 10nov2012
  midway @  t @  DO
    I       0 en{ @ 781 = IF  \ 781=WHAT;  10nov2012
      I     8 en{ @  aud !  \ 10nov2012
      LEAVE
    THEN
  -1 +LOOP
  SpeechAct
  fyi @ 2 > IF CR
    ."   from WhatBe after speaking of WHAT, "  \ 25feb2011
    ." psiDamping concept #781"
  THEN
  8773 caller !  \ ASCII 87=W 73=I; test; 26sep2010
  781 urpsi !  \ 781=WHAT for PsiDamp; 10nov2012
  PsiDamp
  0 caller !
  subjnum @ 2 <  topicnum @ 2 < OR IF  \ not plural? 4nov2011
    prsn @ 1 = IF  \ 1st person singular; 21aug2011
      midway @  t @  DO   \ 21aug2011
        I       0 en{ @ 800 = IF  \ 800=BE; 10nov2012
          I     2 en{ @ 1 = IF  \ singular?; 10nov2012
            I   4 en{ @ 1 = IF  \ 1st person?; 10nov2012
              I     8 en{ @  aud !  \ 10nov2012
              1 topicnum !  \ If "AM" prevent "ARE"; 26jul2012
              LEAVE  \ 21aug2011
            THEN  \ end of test for first person; 10nov2012
          THEN  \ end of test for singular; 10nov2012
        THEN     \ 21aug2011
      -1 +LOOP   \ 21aug2011
      SpeechAct  \ 21aug2011
    THEN  \ end of test for first person singular; 21aug2011
    prsn @ 3 = IF  \ 3rd person singular; 19sep2010
      midway @  t @  DO
        I       0 en{ @ 800 = IF  \ 800=BE; 10nov2012
          I     2 en{ @ 1 = IF    \ singular? 10nov2012
            I   4 en{ @ 3 = IF    \ 3rd pers? 26dec2012
              I     8 en{ @  aud !  \ 10nov2012
              1 topicnum !  \ If "IS" prevent "ARE" 21jul2012
              1 indefmust !  \ to say "IS A"; 20oct2011
              LEAVE
            THEN  \ end of test for 3rd person; 10nov2012
          THEN  \ end of test for singualr; 10nov2012
        THEN  ( http://isforth.com )
      -1 +LOOP
      SpeechAct
      fyi @ 2 > IF CR
      ."   from WhatBe after speaking of IS, " \ 25feb2011
      ." psiDamping concept #800"
      THEN
      8773 caller !  \ ASCII 87=W 73=I; test; 26sep2010
      800 urpsi !  \ 10nov2012
      PsiDamp
      0 caller !
      0 motjuste !
    THEN  \ end of test for 3rd person singular; 19sep2010
  THEN
  topicnum @ 2 =  prsn @ 2 =  OR IF  \ test; 19sep2010
    midway @  t @  DO
      I       0 en{ @ 800 = IF  \ 800=BE; 10nov2012
        I     2 en{ @ 2 = IF  \ plural? 10nov2012
          I     8 en{ @  aud !  \ 10nov2012
          LEAVE
        THEN  \ end of test for plural "ARE"; 10nov2012
      THEN  \ end of test for be-verb
    -1 +LOOP
    SpeechAct
    fyi @ 2 > IF CR
      ."   from WhatBe after speaking of ARE, " \ 25feb2011
      ." psiDamping concept #800"
    THEN
    8773 caller !  \ ASCII 87=W 73=I; test; 26sep2010
    800 urpsi !  \ 10nov2012
    PsiDamp
    0 caller !  \ test; 26sep2010
    0 motjuste !
    0 subjpsi !  \ reset for safety' 17oct2011
    0 topicnum !
  THEN
  topicnum @ 2 = NOT IF  \ if singular; 21jun2011
    prsn @ 3 = IF  \ 3rd person singular; 21jun2011
      topicnum @ 1 = IF  \ not zero; 4nov2011
        EnArticle  \ chance for "A" or "THE"; 21jun2011
      THEN  \ end of test for 1=singular; 4nov2011
    THEN   \ end of test for 3rd person; 21jun2011
  THEN   \ end of test for singular; 21jun2011
  midway @  t @  DO
    I       0 en{ @  qusub @ = IF  \ 10oct2011
      I     4 en{ @  1 = IF  \ nominative?  1jan2013
        I   8 en{ @ aud !  \ 10nov2012
        LEAVE
      THEN  \ end of test for dba=1 nominative; 1jan2013
    THEN
  -1 +LOOP
  motjuste @ urpsi !
  8773 caller !  \ ASCII 87=W 73=I; test; 26sep2010
  PsiDamp
  0 caller !  \ test; 26sep2010
  aud @ 0 > IF  \ avoid #zero ERROR; \ 19sep2010
    SpeechAct
  THEN  \ end of test to avoid ERROR; 19sep2010
  0 cogpsi !  \ let another new word call WhatBe; 17oct2011
  0 indefmust !  \ reset for safety; 20oct2011
  0 moot !  \ resume associative tagging; 24oct2011
  0 qusub !  \ zero out for safety; 10oct2011
  0 subjpsi !  \ reset for safety; 17oct2011
  0 topic !  \ reset for safety; 18oct2011
  0 whoflag !  \ Prevent EnArticle; 6oct2011
; ( http://code.google.com/p/mindforth )
```

### Code from German Wotan Supercomputer AI ###

```
:  WhatBe ( WAS IST/SIND und so weiter ) \ 8mar2012
  1 moot !  \ prevent storage of spurious ideas; 24oct2011
  0 tqv !  \ prevent spurious carry-over values;  1aug2012
  qusub @ 0 = IF  \ for a new word like "energy"; 8aug2012
    subjnum @ 0 = IF  \ in absence of num(ber) data; 8aug2012
      3 prsn !  \ to say "IST" (is); 6mar2013
    THEN  \ end of test for "qusub"; 8aug2012
  THEN  \ end of test for "subjnum"; 8aug2012
  topic @ qusub ! \ THEN  \ 2nd choice; 10oct2011
  qusub @ 701 = IF 1 prsn ! THEN  \ 1st person ICH  6mar2012
  qusub @ 707 = IF 2 prsn ! THEN  \ 2nd person DU;  6mar2013
  midway @  t @  DO
    I       0 de{ @ 781 = IF  \ 781=WAS (what); 18nov2012
      I     8 de{ @  aud !  \ 10nov2012
      LEAVE  \ one instance is enough;  6mar2013
    THEN
  -1 +LOOP
  SpeechAct  \ say the word "WAS" (what);  6mar2013
  fyi @ 2 > IF CR
    ."   from WhatBe after speaking of WAS, "  \  6mar2012
    ." psiDamping concept #781"
  THEN
  8773 caller !  \ ASCII 87=W 73=I; test; 26sep2010
  781 urpsi !  \ 781=WAS (what) for PsiDamp;  6mar2013
  PsiDamp
  0 caller !
  subjnum @ 2 <  topicnum @ 2 < OR IF  \ not plural? 4nov2011
   prsn @ 1 = IF  \ 1st person singular; 21aug2011
    midway @  t @  DO   \ 21aug2011
      I       0 de{ @ 800 = IF  \ 800=SEIN (be);  6mar2013
        I     2 de{ @ 1 = IF  \ singular?; 10nov2012
          I   4 de{ @ 1 = IF  \ 1st person?; 10nov2012
            I     8 de{ @  aud !  \ 10nov2012
            1 topicnum !  \ If "AM" prevent "ARE"; 26jul2012
            LEAVE  \ 21aug2011
          THEN  \ end of test for first person; 10nov2012
        THEN  \ end of test for singular; 10nov2012
      THEN     \ 21aug2011
    -1 +LOOP   \ 21aug2011
    SpeechAct  \ 21aug2011
   THEN  \ end of test for first person singular; 21aug2011
   prsn @ 2 = IF  \ 2nd person singular? 23nov2012
    midway @  t @  DO   \ 23nov2012
      I       0 de{ @ 800 = IF  \ 800=SEIN (be);  6mar2013
        I     2 de{ @ 1 = IF  \ singular?; 23nov2012
          I   4 de{ @ 2 = IF  \ 2nd person?; 23nov2012
            I     8 de{ @  aud !  \ 23nov2012
            LEAVE  \ one engram is enough; 23nov2012
          THEN  \ end of test for 2nd person; 23nov2012
        THEN  \ end of test for singular; 23nov2012
      THEN  \ end of test for 800=SEIN (be); 23nov2012
    -1 +LOOP   \ end of loop; 23nov2012
    SpeechAct  \ speak the be-verb; 23nov2012
   THEN  \ end of test for 2nd person singular; 23nov2012
   prsn @ 3 = IF  \ 3rd person singular; 19sep2010
    midway @  t @  DO
      I       0 de{ @ 800 = IF  \ 800=SEIN (be); 6mar2013
        I     2 de{ @ 1 = IF    \ singular? 10nov2012
          I   4 de{ @ 3 = IF    \ 3rd pers? 23nov2012
            I     8 de{ @  aud !  \ 10nov2012
         \  1 topicnum !  \ If "IS" prevent "ARE"; 21jul2012
            1 indefmust !  \ to say "IST EIN" ("is a")
            LEAVE
          THEN  \ end of test for 3rd person; 10nov2012
        THEN  \ end of test for singular; 10nov2012
      THEN
    -1 +LOOP
    SpeechAct  \ say "IST" ("is");  6mar2013
    fyi @ 2 > IF CR
      ."   from WhatBe after speaking of IST, " \ 6mar2013
      ." psiDamping concept #800"
    THEN
    8773 caller !  \ ASCII 87=W 73=I; test; 26sep2010
    800 urpsi !  \ 10nov2012
    PsiDamp
    0 caller !
    0 motjuste !
   THEN  \ end of test for 3rd person singular; 19sep2010
  THEN
\ topicnum @ 2 =  prsn @ 2 =  OR IF  \ test; 19sep2010
  topicnum @ 2 =  IF  \ plural? 23nov2012
    midway @  t @  DO
      I       0 de{ @ 800 = IF  \ 800=SEIN ("be"); 6mar2013
        I     2 de{ @ 2 = IF  \ plural? 10nov2012
          I   4 de{ @ prsn @ = IF  \ 23nov2012
            I 8 de{ @  aud !  \ 10nov2012
            LEAVE
          THEN  \ end of person-test; 23nov2012
        THEN  \ end of test for plural; 23nov2012
      THEN  \ end of test for be-verb
    -1 +LOOP
    SpeechAct
    fyi @ 2 > IF CR
      ."   from WhatBe after speaking of ARE, " \ 25feb2011
      ." psiDamping concept #800"
    THEN
    8773 caller !  \ ASCII 87=W 73=I; test; 26sep2010
    800 urpsi !  \ 10nov2012
    PsiDamp
    0 caller !  \ test; 26sep2010
    0 motjuste !
    0 subjpsi !  \ reset for safety' 17oct2011
    0 topicnum !
  THEN
  topicnum @ 2 = NOT IF  \ if singular; 21jun2011
    prsn @ 3 = IF  \ 3rd person singular; 21jun2011
     topicnum @ 1 = IF  \ not zero; 4nov2011
      DeArticle  \ chance for EIN or "DER"; 17nov2012
     THEN  \ end of test for 1=singular; 4nov2011
    THEN   \ end of test for 3rd person; 21jun2011
  THEN   \ end of test for singular; 21jun2011
  midway @  t @  DO
    I       0 de{ @  qusub @ = IF  \ 10oct2011
      I     8 de{ @ aud !  \ 10nov2012
      LEAVE
    THEN
  -1 +LOOP
  motjuste @ urpsi !
  8773 caller !  \ ASCII 87=W 73=I; test; 26sep2010
  PsiDamp
  0 caller !  \ test; 26sep2010
  aud @ 0 > IF  \ avoid #zero ERROR; \ 19sep2010
    SpeechAct
  THEN  \ end of test to avoid ERROR; 19sep2010
  0 cogpsi !  \ let another new word call WhatBe; 17oct2011
  0 indefmust !  \ reset for safety; 20oct2011
  0 moot !  \ resume associative tagging; 24oct2011
  0 qusub !  \ zero out for safety; 10oct2011
  0 subjpsi !  \ reset for safety; 17oct2011
  0 topic !  \ reset for safety; 18oct2011
  0 whoflag !  \ Prevent DeArticle; 17nov2012
; ( http://code.google.com/p/mindforth )
```

### Function ###

The WhatBe module functions by receiving one ParaMeter after another from a calling module, such as VerbPhrase or DeCog. The parameters are used to ask the what-be question properly in the natural language of the AI, which could be English or German or Russian.

### DeBug ###

Typical Forth code for DeBug includes:

```
:  WhatBe ( what AM/IS/ARE Subjects ) \ 10oct2011
  1 moot !  \ prevent storage of spurious ideas; 24oct2011
\ CR ." WhatBe: topic qusub subjnum nphrnum cognum = " \ 22oct2011
\ topic @ . qusub @ .  subjnum @ . nphrnum @ . cognum @ . \ 22oct
\ subjpsi @ 0 > IF subjpsi @ qusub ! THEN  \ 1st choice; 10oct2011
\ qusub @ 0 = IF  \ if still no qusub, try "topic"; 10oct2011
  \  topic @ 0 > IF
  topic @ qusub ! \ THEN  \ 2nd choice; 10oct2011
\ THEN  \  end of test for unfilled "qusub"; 10oct2011
  subjpsi @ 50 = IF 1 prsn ! THEN  \ 1st person "I"; 10oct2011
  subjpsi @ 56 = IF 2 prsn ! THEN  \ 2nd person YOU; 19sep2010
```

Typical JavaScript code for DeBug includes:

```
function WhatBe() {  // what AM/IS/ARE Subjects; 18oct2011
  moot = 1;  // prevent storage of spurious ideas; 24oct2011
  qusub = topic;  // 18oct2011
 
   alert("WhatBe: qusub subjnum cognum = "+qusub+" "+subjnum+" "+cognum); 
// 27oct2011
 
  for (i = t; i>midway; i--) {  // 19jun2011
    enLexicon[i].enExam();  // 19jun2011
    if (en0 == 54) {  // 54=WHAT  5jul2011
    aud = en7; // 19jun2011
    break;  // 19jun2011
    }  // 19jun2011
  }  // end of search loop; 19jun2011
  SpeechAct();  // 19jun2011
```

### Person ###

A false value for the "prsn" variable may be carried over into WhatBe, tripping a test that causes the module to say "WHAT AM" instead of "WHAT IS" or "WHAT ARE". Some new experimental code tests for the lack of positive "num(ber)" values and sets "prsn" to a DeFault value of "3" for third person, so that WhatBe will tend to say "WHAT IS" instead of "WHAT AM" for a word like "energy".

### Extension ###

AI coders may embrace and extend the WhatBe mind-module by giving it the ability to search the Internet for answers above and beyond the knowledge of specific human users.