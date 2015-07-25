AskUser EnArticle ParaMeter

## Calling by parameter ##

When a search-loop is trying to find a German noun, such as the direct object of a query in AskUser, it makes sense to call DeArticle from the same nested depth of the search which is using each ParaMeter to find the German noun. When the search reveals the case and number of the noun being found, these parameters can be passed along with a call to DeArticle. Since a "LEAVE" statement terminates the loop, there will not be mulitple calls to DeArticle resulting in a kind of stuttering in German.

## Code from German DeKi.txt ##

```
:  DeArticle ( select "EIN" or "DER" before a noun; 3feb2013 )
\ CR ." DeArt: subjnum indefartcon defartcon = " \ test 3mar2013
\ subjnum @ . indefartcon @ . defartcon @ .  \ test; 3mar2013
  indefmust @ 1 = IF  \ if required to say "A(N)"; 20oct2011
    midway @  t @  DO  \ search backwards in time; 20oct2011
      I       0 de{ @  101 = IF  \ 101=A found?  8nov2012
        I     8 de{ @  aud !  \ save auditory recall-vector
        LEAVE  \ one instance is enough; 20oct2011
      THEN  \ end of test for "101=A" engram; 8nov2012
    -1 +LOOP  \ end of backwards loop; 20oct2011
    SpeechAct  \ pronounce the requred article; 20oct2011
    0 indefmust !  \ reset for safety; 20oct2011
    EXIT  \ abandon rest of DeArticle; 20oct2011; 17nov2012
  THEN  \ end of test for a required "A(N); 20oct2011
  nphrpos @ 7 = NOT IF
    quobjnum @ 1 = IF   \  4feb2012
      1 nphrnum !  \  4feb2012
      1 indefartcon !  \ 4feb2012
    \ 0  quobjnum !  \ reset after use;  4feb2012
    \ 0  quobjnum !  \ Commenting out on 4mar2013
    THEN  \  4feb2012
    nphrnum @  1 = IF
      motjuste @ ghost @ = IF  \
        0 indefartcon !  \ do not say "A"; 15oct2011
        1 defartcon !    \ say "THE"; 15oct2011
      THEN  \
      motjuste @ ghost @ = NOT IF
        subjnum @ 1 = IF  \ if singular subject; 13sep2011
          verbpsi @ 800 = IF  \ AM or IS; 10nov0212
            1 indefartcon !  \ indefinite article; 13sep2011
          THEN  \ end of test for "AM" or "IS"; 13sep2011
        THEN  \ 13sep2011
        indefartcon @  1 = IF  \ from WHAT-query; 16apr2011
          0 defartcon !  \ avoid "A THE"; 6oct2011
          anset @ 0 = IF ( If no vowel is next )
            midway @  t @  DO
              I       0 de{ @ 101 = IF  \ 101=A? 8nov2012
                I     8 de{ @  aud !  \ 10nov2012
                LEAVE
              THEN
            -1 +LOOP
          THEN  ( End of test for absence of a vowel )
          anset @ 0 > IF  ( If anset-flag is positive )
            midway @  t @  DO
              I       0 de{ @ 102 = IF  \ 102=AN? 8nov2012
                I     8 de{ @  aud !  \ 10nov2012
                LEAVE
              THEN
            -1 +LOOP
          THEN  ( End of test for a vowel coming next )
          1 numflag ! \ With "A" assume singular number.
          SpeechAct
          0 indefartcon !  \ Reset; 16apr2011
        THEN  \ End of test for positive indefartcon; 16apr2011
        0 indefartcon !  \ Reset for safety; 6oct2011
      THEN
      motjuste @ ghost @ = IF
       defartcon @  1 = IF  \ from WH0-query; 16apr2011
        midway @  t @  DO
          I       0 de{ @ 117 = IF  \ If 117=THE found; 10nov2012
            I     2 de{ @ quobjnum @ = IF  \ number?  4mar2013
              I   4 de{ @ dbacon @ = IF  \ acc. dba?  4mar2013
                I 8 de{ @  aud !  \ auditory engram 4mar2012
              THEN  \ end of dba-test;  4mar2013
              LEAVE  \ one engram suffices;  5mar2013
            THEN  \ end of number-test;  4mar2012
          THEN
        -1 +LOOP
        SpeechAct
        0 defartcon !  \ Reset; 16apr2011
       THEN  \ End of test for positive defartcon; 16apr2011
      THEN
    THEN
  THEN
  dirobj @ 1 = IF
    motjuste @ ghost !
  THEN   ( http://thebeez.home.xs4all.nl/4tH )
  0 whoflag !  \ call DeArticle only once; 17nov2012
; ( http://code.google.com/p/mindforth/wiki/EnArticle )
```