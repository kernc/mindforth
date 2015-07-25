EnBoot UnterTan WortSchatz

### Diagram ###

```
  /^^^^^^^^^^^\ Each Syntax Needs Bootstrap Words /^^^^^^^^^^^\
 /   EYE       \                                 /    EAR      \
|               |CONCEPTS                       |   _________   |
|               |   | | |     ______________    |  /DeBoot   \  |
|   _______     |   | | |    /              \   | / German    \ |
|  /old    \!!!!|!!!| | |   / English syntax \  | \ bootstrap / |
| / image   \---|---+ | |   \ (needs EnBoot) /  |  \"vault"  /  |
| \ recog   /   |  k| | |    \______________/   |   \_______/   |
|  \_______/    |  l| | |     ______________    |oldest memories|
|               |  e| |l|    /              \   |to be forgotten|
|               |  i| |e|   / Russian syntax \  |               |
|   visual      |  d| |u|   \ (needs RuBoot) /  |newest memories|
|               |  e| |t|    \______________/   |to be recycled |
|   memory      |  r|m|e|           _______     |periodically by|
|               |   |a| |          /       \    |backwards shift|
|   channel     |   |c| |         / German  \---|--------------\|
|               |   |h| |         \ syntax  /   |              ||
|               |   |e| |          \_______/    |              ||
|   _______     |   |n| |              |        |   _________  ||
|  /new    \    |   |_|_|_           __V____    |  /"kleider"\ ||
| / percept \   |  / Psi  \---------/ De    \---|-/ "machen"  \||
| \ engram  /---|-/concepts\ reify / lexicon \  | \ "leute"   / |
|  \_______/    | \________/-------\_________/--|--\_________/  |
```


### Purpose ###

The purpose of the German bootstrap "DeBoot" module is to load a basic German vocabulary or WortSchatz into the [German AI](http://ai.neocities.org) at the start of each session of running the AI software. Some artificial intelligence enthusiasts may object that an AI should learn all its vocabulary from experience with the world, as human babies do. Although such a way of learning is preferable to having an innate vocabulary, the AI software will first need to become far more sophisticated before it is powerful enough to function as a _tabula rasa_ or blank slate that is genetically able to learn what it needs to know. [MindForth](http://www.nlg-wiki.org/systems/Mind.Forth) and the [German AI program](http://ai.neocities.org/DeKi.txt) need the innate bootstrap vocabulary to function as a proof-of-concept AI that can primitively think and learn.

### Inclusion ###

```
  CR ." There is no warranty for what this software does."
 ( IRRTUM -- "error" first word so any bug will announce itself )
    1 t !  73 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ I
    2 t !  82 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ R
    3 t !  82 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ R
    4 t !  84 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ T
    5 t !  85 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ U
    6 t !  77 pho !  0 beg !  0 ctu ! 523 audpsi ! AudMem \ M
523 dnr !   3 mfn !  1 dba ! 523 fex !  5 pos ! 523 fin !  1 aud !
523 psi !   1 num !  0 pre !  0 seq ! 523 dex ! DeVocab InNativate

  ( 7: 205=ABER "however" adverb;  2dec2011 )
    8 t !  65 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ A
    9 t !  66 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ B
   10 t !  69 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ E
   11 t !  82 pho !  0 beg !  0 ctu ! 205 audpsi ! AudMem \ R
205 dnr !   0 mfn ! 0 dba ! 205 fex ! 2 pos ! 205 fin ! 8 aud !
205 psi !   0 num !  0 pre !  0 seq ! 205 dex ! DeVocab InNativate

 ( 12: 210=AUCH adverb "also" 24nov2011 )
   13 t !  65 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ A
   14 t !  85 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ U
   15 t !  67 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ C
   16 t !  72 pho !  0 beg !  0 ctu ! 210 audpsi ! AudMem \ H
210 dnr !   0 mfn ! 0 dba ! 210 fex ! 2 pos ! 210 fin ! 13 aud !
210 psi !   0 num !  0 pre !  0 seq ! 210 dex ! DeVocab InNativate

 ( 17: 410=BITTE  "please" interjection for HCI; 26nov2011 )
   18 t !  66 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ B
   19 t !  73 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ I
   20 t !  84 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ T
   21 t !  84 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ T
   22 t !  69 pho !  0 beg !  0 ctu ! 410 audpsi ! AudMem \ E
410 dnr !   0 mfn !  0 dba ! 410 fex ! 4 pos ! 410 fin ! 18 aud !
410 psi !   0 num !  0 pre !  0 seq ! 410 dex ! DeVocab InNativate

 ( 23: 420=DANKE  "thanks" interjection; for HCI; 26nov2011 )
   24 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
   25 t !  65 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ A
   26 t !  78 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ N
   27 t !  75 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ K
   28 t !  69 pho !  0 beg !  0 ctu ! 420 audpsi ! AudMem \ E
420 dnr !   0 mfn ! 0 dba ! 420 fex ! 4 pos ! 420 fin ! 24 aud !
420 psi !   0 num !  0 pre !  0 seq ! 420 dex ! DeVocab InNativate

 ( 29: 745=DAS  "that" pronoun; 26nov2011 )
   30 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
   31 t !  65 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ A
   32 t !  83 pho !  0 beg !  0 ctu ! 745 audpsi ! AudMem \ S
745 dnr !   3 mfn ! 1 dba ! 745 fex ! 7 pos ! 745 fin ! 30 aud !
745 psi !   0 num !  0 pre !  0 seq ! 745 dex ! DeVocab InNativate

 ( 33: 310=DASS  "that" conjunction; 26nov2011 )
   34 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
   35 t !  65 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ A
   36 t !  83 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ S
   37 t !  83 pho !  0 beg !  0 ctu ! 310 audpsi ! AudMem \ S
310 dnr !   0 mfn ! 0 dba ! 310 fex ! 3 pos ! 310 fin ! 34 aud !
310 psi !   0 num !  0 pre !  0 seq ! 310 dex ! DeVocab InNativate

 ( 38: 344=DENN "because"  conj. see also 384=WEIL; 20nov2012 )
   39 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
   40 t !  69 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ E
   41 t !  78 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ N
   42 t !  78 pho !  0 beg !  0 ctu ! 344 audpsi ! AudMem \ N
344 dnr !   0 mfn ! 0 dba ! 344 fex ! 3 pos ! 344 fin ! 39 aud !
344 psi !   0 num !  0 pre !  0 seq ! 344 dex ! DeVocab InNativate

  ( 117 DER DIE DAS DIE subject to search by parameter 18nov2012 )

 ( 43: 117=DER  "the" article; nom. masc. sing. 18nov2012 )
   44 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
   45 t !  69 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ E
   46 t !  82 pho !  0 beg !  0 ctu ! 117 audpsi ! AudMem \ R
117 dnr !   1 mfn ! 1 dba ! 117 fex ! 1 pos ! 117 fin ! 44 aud !
117 psi !   1 num !  0 pre !  0 seq ! 117 dex ! DeVocab InNativate

 ( 47: 117=DIE  "the" article; nom. fem. sing. 18nov2012 )
   48 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
   49 t !  73 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ I
   50 t !  69 pho !  0 beg !  0 ctu ! 117 audpsi ! AudMem \ E
117 dnr !   2 mfn ! 1 dba ! 117 fex ! 1 pos ! 117 fin ! 48 aud !
117 psi !   1 num !  0 pre !  0 seq ! 117 dex ! DeVocab InNativate

 ( 51: 117=DAS  "the" article; nom. neuter. sing. 18nov2012 )
   52 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
   53 t !  65 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ A
   54 t !  83 pho !  0 beg !  0 ctu ! 117 audpsi ! AudMem \ S
117 dnr !   3 mfn ! 1 dba ! 117 fex ! 1 pos ! 117 fin ! 52 aud !
117 psi !   1 num !  0 pre !  0 seq ! 117 dex ! DeVocab InNativate

 ( 55: 117=DIE  "the" article; nom. plural; 18nov2012 )
   56 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
   57 t !  73 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ I
   58 t !  69 pho !  0 beg !  0 ctu ! 117 audpsi ! AudMem \ E
117 dnr !   0 mfn ! 1 dba ! 117 fex ! 1 pos ! 117 fin ! 56 aud !
117 psi !   2 num !  0 pre !  0 seq ! 117 dex ! DeVocab InNativate

( 117 DES DER DES DER 18nov2012 )

 ( 59: 117=DES  "the" article; gen. masc. sing. 18nov2012 )
   60 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
   61 t !  69 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ E
   62 t !  83 pho !  0 beg !  0 ctu ! 117 audpsi ! AudMem \ S
117 dnr !   1 mfn ! 2 dba ! 117 fex ! 1 pos ! 117 fin ! 60 aud !
117 psi !   1 num !  0 pre !  0 seq ! 117 dex ! DeVocab InNativate

 ( 63: 117=DER  "the" article; gen. fem. sing. 18nov2012 )
   64 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
   65 t !  69 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ E
   66 t !  82 pho !  0 beg !  0 ctu ! 117 audpsi ! AudMem \ R
117 dnr !   2 mfn ! 2 dba ! 117 fex ! 1 pos ! 117 fin ! 64 aud !
117 psi !   1 num !  0 pre !  0 seq ! 117 dex ! DeVocab InNativate

 ( 67: 117=DES  "the" article; gen. neut. sing. 18nov2012 )
   68 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
   69 t !  69 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ E
   70 t !  83 pho !  0 beg !  0 ctu ! 117 audpsi ! AudMem \ S
117 dnr !   3 mfn ! 2 dba ! 117 fex ! 1 pos ! 117 fin ! 68 aud !
117 psi !   1 num !  0 pre !  0 seq ! 117 dex ! DeVocab InNativate

 ( 71: 117=DER  "the" article; gen. plural; 18nov2012 )
   72 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
   73 t !  69 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ E
   74 t !  82 pho !  0 beg !  0 ctu ! 117 audpsi ! AudMem \ R
117 dnr !   0 mfn ! 2 dba ! 117 fex ! 1 pos ! 117 fin ! 72 aud !
117 psi !   2 num !  0 pre !  0 seq ! 117 dex ! DeVocab InNativate

( 117 DEM DER DEM DEN 18nov2012 )

 ( 75: 117=DEM  "the" article; dat. masc. sing. 18nov2012 )
   76 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
   77 t !  69 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ E
   78 t !  77 pho !  0 beg !  0 ctu ! 117 audpsi ! AudMem \ M
117 dnr !   1 mfn ! 3 dba ! 117 fex ! 1 pos ! 117 fin ! 76 aud !
117 psi !   1 num !  0 pre !  0 seq ! 117 dex ! DeVocab InNativate

 ( 79: 117=DER  "the" article; dat. fem. sing. 18nov2012 )
   80 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
   81 t !  69 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ E
   82 t !  82 pho !  0 beg !  0 ctu ! 117 audpsi ! AudMem \ R
117 dnr !   2 mfn ! 3 dba ! 117 fex ! 1 pos ! 117 fin ! 80 aud !
117 psi !   1 num !  0 pre !  0 seq ! 117 dex ! DeVocab InNativate

 ( 83: 117=DEM  "the" article; dat. neut. sing. 18nov2012 )
   84 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
   85 t !  69 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ E
   86 t !  77 pho !  0 beg !  0 ctu ! 117 audpsi ! AudMem \ M
117 dnr !   3 mfn ! 3 dba ! 117 fex ! 1 pos ! 117 fin ! 84 aud !
117 psi !   1 num !  0 pre !  0 seq ! 117 dex ! DeVocab InNativate

 ( 87: 117=DEN  "the" article; dat. plural 18nov2012 )
   88 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
   89 t !  69 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ E
   90 t !  78 pho !  0 beg !  0 ctu ! 117 audpsi ! AudMem \ N
117 dnr !   0 mfn ! 3 dba ! 117 fex ! 1 pos ! 117 fin ! 88 aud !
117 psi !   2 num !  0 pre !  0 seq ! 117 dex ! DeVocab InNativate

( 117 DEN DIE DAS DIE 18nov2012 )

 ( 91: 117=DEN  "the" article; masc. acc. sing. 18nov2012 )
   92 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
   93 t !  69 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ E
   94 t !  78 pho !  0 beg !  0 ctu ! 117 audpsi ! AudMem \ N
117 dnr !   1 mfn ! 4 dba ! 117 fex ! 1 pos ! 117 fin ! 92 aud !
117 psi !   1 num !  0 pre !  0 seq ! 117 dex ! DeVocab InNativate

 ( 95: 117=DIE  "the" article; acc. fem. sing. 18nov2012 )
   96 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
   97 t !  73 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ I
   98 t !  69 pho !  0 beg !  0 ctu ! 117 audpsi ! AudMem \ E
117 dnr !   2 mfn ! 4 dba ! 117 fex ! 1 pos ! 117 fin ! 96 aud !
117 psi !   1 num !  0 pre !  0 seq ! 117 dex ! DeVocab InNativate

 ( 99: 117=DAS  "the" article; acc. neuter. sing. 18nov2012 )
  100 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
  101 t !  65 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ A
  102 t !  83 pho !  0 beg !  0 ctu ! 117 audpsi ! AudMem \ S
117 dnr !   3 mfn ! 4 dba ! 117 fex ! 1 pos ! 117 fin ! 100 aud !
117 psi !   1 num !  0 pre !  0 seq ! 117 dex ! DeVocab InNativate

( 103: 117=DIE  "the" article; acc. plural; 18nov2012 )
  104 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
  105 t !  73 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ I
  106 t !  69 pho !  0 beg !  0 ctu ! 117 audpsi ! AudMem \ E
117 dnr !   0 mfn ! 4 dba ! 117 fex ! 1 pos ! 117 fin ! 104 aud !
117 psi !   2 num !  0 pre !  0 seq ! 117 dex ! DeVocab InNativate

( 107: 507=DEUTSCH  "German" noun; the language; 1dec2011 )
  108 t !  68 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ D
  109 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  110 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  111 t !  84 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ T
  112 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  113 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  114 t !  72 pho !  0 beg !   0 ctu ! 507 audpsi ! AudMem \ H
507 dnr !   3 mfn !  1 dba ! 507 fex ! 5 pos ! 507 fin ! 108 aud !
507 psi !   0 num !  0 pre !   0 seq ! 507 dex ! DeVocab InNativate

( 115: 747=DIES  "this" pronoun; dba nom. 1dec2011 )
  116 t !  68 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ D
  117 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  118 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  119 t !  83 pho !  0 beg !   0 ctu ! 747 audpsi ! AudMem \ S
747 dnr !   3 mfn !  1 dba ! 747 fex ! 7 pos ! 747 fin ! 116 aud !
747 psi !   1 num !  0 pre !   0 seq ! 747 dex ! DeVocab InNativate

( 120: 509=DING  "thing" noun; singular; 1dec2011 )
  121 t !  68 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ D
  122 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  123 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  124 t !  71 pho !  0 beg !   0 ctu ! 509 audpsi ! AudMem \ G
509 dnr !   3 mfn !  1 dba ! 509 fex ! 5 pos ! 509 fin ! 121 aud !
509 psi !   1 num !  0 pre !   0 seq ! 509 dex ! DeVocab InNativate

( 125: 509=DINGE "things" noun; plural 1dec2011 )
  126 t !  68 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ D
  127 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  128 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  129 t !  71 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ G
  130 t !  69 pho !  0 beg !   0 ctu ! 509 audpsi ! AudMem \ E
509 dnr !   3 mfn !  1 dba ! 509 fex ! 5 pos ! 509 fin ! 126 aud !
509 psi !   2 num !  0 pre !   0 seq ! 509 dex ! DeVocab InNativate

( 131: 220=DOCH "indeed" adverb  26nov2011 )
  132 t !  68 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ D
  133 t !  79 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ O
  134 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  135 t !  72 pho !  0 beg !   0 ctu ! 220 audpsi ! AudMem \ H
220 dnr !   0 mfn !  0 dba ! 220 fex ! 2 pos ! 220 fin ! 132 aud !
220 psi !   0 num !  0 pre !   0 seq ! 220 dex ! DeVocab InNativate

( 136: 707=DU  "you" pronoun, familiar, dba nom; 17nov2012 )
  137 t !  68 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ D
  138 t !  85 pho !  0 beg !   0 ctu ! 707 audpsi ! AudMem \ U
707 dnr !   0 mfn !  1 dba ! 707 fex ! 7 pos ! 701 fin ! 137 aud !
707 psi !   1 num !  0 pre !   0 seq ! 707 dex ! DeVocab InNativate

( 139: 707=DEINER genitive "of you" 17nov2012 )
  140 t !  68 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ D
  141 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  142 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  143 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  144 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  145 t !  82 pho !  0 beg !   0 ctu ! 707 audpsi ! AudMem \ R
707 dnr !   0 mfn !  2 dba ! 707 fex !  7 pos ! 701 fin ! 140 aud !
707 psi !   1 num !  0 pre !   0 seq ! 707 dex ! DeVocab InNativate

( 146: 707=DIR  "you" pronoun; familiar; dba dat. 1dec2011 )
  147 t !  68 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ D
  148 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  149 t !  82 pho !  0 beg !   0 ctu ! 707 audpsi ! AudMem \ R
707 dnr !   0 mfn !  3 dba ! 707 fex ! 7 pos ! 701 fin ! 147 aud !
707 psi !   1 num !  0 pre !   0 seq ! 707 dex ! DeVocab InNativate

( 150: 707=DICH  "you" pronoun, familiar, dba acc. 17nov2012 )
  151 t !  68 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ D
  152 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  153 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  154 t !  72 pho !  0 beg !   0 ctu ! 707 audpsi ! AudMem \ H
707 dnr !   0 mfn !  4 dba ! 707 fex ! 7 pos ! 701 fin ! 151 aud !
707 psi !   1 num !  0 pre !   0 seq ! 707 dex ! DeVocab InNativate

( 101  EIN EINE EIN subject to search by parameters; 18nov2012 )

( 155: 101=EIN  "a" article; dba nom. masc. sing. 18nov2012 )
  156 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  157 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  158 t !  78 pho !  0 beg !   0 ctu ! 101 audpsi ! AudMem \ N
101 dnr !   1 mfn !  1 dba ! 101 fex ! 1 pos ! 101 fin ! 156 aud !
101 psi !   1 num !  0 pre !   0 seq ! 101 dex ! DeVocab InNativate

( 159: 101=EINE  "a" article; dba nom. fem. sing. 18nov2012 )
  160 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  161 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  162 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  163 t !  69 pho !  0 beg !   0 ctu ! 101 audpsi ! AudMem \ E
101 dnr !   2 mfn !  1 dba ! 101 fex ! 1 pos ! 101 fin ! 160 aud !
101 psi !   1 num !  0 pre !   0 seq ! 101 dex ! DeVocab InNativate

( 164: 101 EIN  "a" article; dba nom. neuter. sing. 18nov2012 )
  165 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  166 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  167 t !  78 pho !  0 beg !   0 ctu ! 101 audpsi ! AudMem \ N
101 dnr !   3 mfn !  1 dba ! 101 fex ! 1 pos ! 101 fin ! 165 aud !
101 psi !   1 num !  0 pre !   0 seq ! 101 dex ! DeVocab InNativate

( 101 EINES EINER EINES searchable by parameter 20nov2012 )

( 168: 101=EINES  "of a" article; dba gen. masc. sing. 18nov2012 )
  169 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  170 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  171 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  172 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  173 t !  83 pho !  0 beg !   0 ctu ! 101 audpsi ! AudMem \ S
101 dnr !   1 mfn !  2 dba ! 101 fex ! 1 pos ! 101 fin ! 169 aud !
101 psi !   1 num !  0 pre !   0 seq ! 101 dex ! DeVocab InNativate

( 174: 101=EINER  "of a" article; dba gen. fem. sing. 18nov2012 )
  175 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  176 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  177 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  178 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  179 t !  82 pho !  0 beg !   0 ctu ! 101 audpsi ! AudMem \ R
101 dnr !   2 mfn !  2 dba ! 101 fex ! 1 pos ! 101 fin ! 175 aud !
101 psi !   1 num !  0 pre !   0 seq ! 101 dex ! DeVocab InNativate

( 180: 101=EINES  "of a" article; dba gen. neuter sing. 18nov2012 )
  181 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  182 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  183 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  184 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  185 t !  83 pho !  0 beg !   0 ctu ! 101 audpsi ! AudMem \ S
101 dnr !   3 mfn !  2 dba ! 101 fex ! 1 pos ! 101 fin ! 181 aud !
101 psi !   1 num !  0 pre !   0 seq ! 101 dex ! DeVocab InNativate

( 186: 101=EINEM EINER EINEM subject to search by parameter 18nov2012 )

( 187: 101=EINEM  "to a" article; dba dat. masc. sing. 18nov2012 )
  188 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  189 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  190 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  191 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  192 t !  77 pho !  0 beg !   0 ctu ! 101 audpsi ! AudMem \ M
101 dnr !   1 mfn !  3 dba ! 101 fex ! 1 pos ! 101 fin ! 188 aud !
101 psi !   1 num !  0 pre !   0 seq ! 101 dex ! DeVocab InNativate

( 193: 101=EINER  "to a" article; dba dat. fem. sing. 18nov2012 )
  194 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  195 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  196 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  197 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  198 t !  82 pho !  0 beg !   0 ctu ! 101 audpsi ! AudMem \ R
101 dnr !   2 mfn !  3 dba ! 101 fex ! 1 pos ! 101 fin ! 194 aud !
101 psi !   1 num !  0 pre !   0 seq ! 101 dex ! DeVocab InNativate

( 199: 101=EINEM  "to a" article; dba dat. neut. sing. 18nov2012 )
  200 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  201 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  202 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  203 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  204 t !  77 pho !  0 beg !   0 ctu ! 101 audpsi ! AudMem \ M
101 dnr !   3 mfn !  3 dba ! 101 fex ! 1 pos ! 101 fin ! 200 aud !
101 psi !   1 num !  0 pre !   0 seq ! 101 dex ! DeVocab InNativate

( 205: 101=EINEN  "a" article; dba acc. masc. sing. 18nov2012 )
  206 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  207 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  208 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  209 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  210 t !  78 pho !  0 beg !   0 ctu ! 101 audpsi ! AudMem \ N
101 dnr !   1 mfn !  4 dba ! 101 fex ! 1 pos  ! 101 fin ! 206 aud !
101 psi !   1 num !  0 pre !   0 seq ! 101 dex ! DeVocab InNativate

( 211: 101=EINE  "a" article; dba acc. fem. sing. 18nov2012 )
  212 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  213 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  214 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  215 t !  69 pho !  0 beg !   0 ctu ! 101 audpsi ! AudMem \ E
101 dnr !   2 mfn !  4 dba ! 101 fex ! 1 pos  ! 101 fin ! 212 aud !
101 psi !   1 num !  0 pre !   0 seq ! 101 dex ! DeVocab InNativate

( 216: 101=EIN  "a" article; dba acc. neuter. sing. 18nov2012 )
  217 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  218 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  219 t !  78 pho !  0 beg !   0 ctu ! 101 audpsi ! AudMem \ N
101 dnr !   3 mfn !  4 dba ! 101 fex ! 1 pos  ! 101 fin ! 217 aud !
101 psi !   1 num !  0 pre !   0 seq ! 101 dex ! DeVocab InNativate

( 220: 751=EINS "one" pronoun dba nom. neut. sing. 1dec2011 )
  221 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  222 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  223 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  224 t !  83 pho !  0 beg !   0 ctu ! 751 audpsi ! AudMem \ S
751 dnr !   3 mfn !  1 dba ! 751 fex ! 7 pos  ! 751 fin ! 221 aud !
751 psi !   1 num !  0 pre !   0 seq ! 751 dex ! DeVocab InNativate

( 225: 512=ELTERN  "parents" noun; plural; 27nov2011 )
  226 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  227 t !  76 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ L
  228 t !  84 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ T
  229 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  230 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  231 t !  78 pho !  0 beg !   0 ctu ! 512 audpsi ! AudMem \ N
512 dnr !   0 mfn !  0 dba ! 512 fex ! 5 pos ! 512 fin ! 226 aud !
512 psi !   2 num !  0 pre !   0 seq ! 512 dex ! DeVocab InNativate

( 232: 513=ENGLISCH  "English" noun; the English; 2dec2011 )
  233 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  234 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  235 t !  71 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ G
  236 t !  76 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ L
  237 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  238 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  239 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  240 t !  72 pho !  0 beg !   0 ctu ! 513 audpsi ! AudMem \ H
513 dnr !   3 mfn !  1 dba ! 513 fex ! 5 pos ! 513 fin ! 233 aud !
513 psi !   0 num !  0 pre !   0 seq ! 513 dex ! DeVocab InNativate

( 241: 713=ER  "he, it"  pronoun; dba nominative; 17nov2012 )
  242 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  243 t !  82 pho !  0 beg !   0 ctu ! 713 audpsi ! AudMem \ R
713 dnr !   1 mfn !  1 dba ! 713 fex ! 7 pos ! 713 fin ! 242 aud !
713 psi !   1 num !  0 pre !   0 seq ! 713 dex ! DeVocab InNativate

( 244: 713=SEINER genitive masculine "of him"; 17nov2012 )
  245 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  246 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  247 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  248 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  249 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  250 t !  82 pho !  0 beg !   0 ctu ! 713 audpsi ! AudMem \ R
713 dnr !   1 mfn !  2 dba ! 713 fex ! 7 pos ! 713 fin ! 245 aud !
713 psi !   1 num !  0 pre !   0 seq ! 713 dex ! DeVocab InNativate

( 251:  713=IHM  "to him" pronoun; dative masc. 17nov2012 )
  252 t ! 73 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ I
  253 t ! 72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  254 t ! 77 pho !  0 beg !   0 ctu ! 713 audpsi ! AudMem \ M
 713 dnr !  1 mfn ! 3 dba ! 713 fex ! 7 pos ! 713 fin ! 252 aud !
 713 psi !  1 num ! 0 pre !   0 seq ! 713 dex ! DeVocab InNativate

( 255: 713=IHN  "him" pronoun; masc. acc. sing. 17nov2012 )
  256 t ! 73 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ I
  257 t ! 72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  258 t ! 78 pho !  0 beg !   0 ctu ! 713 audpsi ! AudMem \ N
 713 dnr !  1 mfn ! 4 dba ! 713 fex !  7 pos ! 713 fin ! 256 aud !
 713 psi !  1 num !  0 pre !  0 seq ! 713 dex ! DeVocab InNativate

( 259: 725=ES  "it" pronoun; dba nominative; 17nov2012 )
  260 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  261 t !  83 pho !  0 beg !   0 ctu ! 725 audpsi ! AudMem \ S
725 dnr !   3 mfn !  1 dba ! 725 fex ! 7 pos ! 725 fin ! 260 aud !
725 psi !   1 num !  0 pre !   0 seq ! 725 dex ! DeVocab InNativate

( 262 725=SEINER genitive neuter "of it"; 17nov2012 )
  263 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  264 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  265 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  266 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  267 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  268 t !  82 pho !  0 beg !   0 ctu ! 725 audpsi ! AudMem \ R
725 dnr !   3 mfn !  2 dba ! 725 fex ! 7 pos ! 725 fin ! 263 aud !
725 psi !   1 num !  0 pre !   0 seq ! 725 dex ! DeVocab InNativate

( 269: 725=IHM  "to it" pronoun; dative neuter; 17nov2012 )
  270 t ! 73 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ I
  271 t ! 72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  272 t ! 77 pho !  0 beg !   0 ctu ! 725 audpsi ! AudMem \ M
 725 dnr !  3 mfn ! 3 dba ! 725 fex !  7 pos ! 725 fin ! 270 aud !
 725 psi !  1 num ! 0 pre !   0 seq ! 725 dex ! DeVocab InNativate

( 273 725=ES  "it" pronoun; dba accusative; 17nov2012 )
  274 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  275 t !  83 pho !  0 beg !   0 ctu ! 725 audpsi ! AudMem \ S
725 dnr !   3 mfn !  4 dba ! 725 fex ! 7 pos ! 725 fin ! 274 aud !
725 psi !   1 num !  0 pre !   0 seq ! 725 dex ! DeVocab InNativate

( 276: 755=ETWAS  "something" pronoun; 28nov2011 )
  277 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  278 t !  84 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ T
  279 t !  87 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ W
  280 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  281 t !  83 pho !  0 beg !   0 ctu ! 755 audpsi ! AudMem \ S
755 dnr !   3 mfn !  4 dba ! 755 fex ! 7 pos ! 755 fin ! 277 aud !
755 psi !   1 num !  0 pre !   0 seq ! 755 dex ! DeVocab InNativate

( 282: 515=FRAU  "woman" noun; singular; 27nov2011 )
  283 t !  70 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ F
  284 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  285 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  286 t !  85 pho !  0 beg !   0 ctu ! 515 audpsi ! AudMem \ U
515 dnr !   2 mfn !  1 dba ! 515 fex ! 5 pos ! 515 fin ! 283 aud !
515 psi !   1 num !  0 pre !   0 seq ! 515 dex ! DeVocab InNativate

( 287: 515=FRAUEN  "women" noun; plural; 2dec2011 )
  288 t !  70 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ F
  289 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  290 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  291 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  292 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  293 t !  78 pho !  0 beg !   0 ctu ! 515 audpsi ! AudMem \ N
515 dnr !   2 mfn !  1 dba ! 515 fex ! 5 pos ! 515 fin ! 288 aud !
515 psi !   2 num !  0 pre !   0 seq ! 515 dex ! DeVocab InNativate

( 294:  517=FREUND  "friend" noun; singular; 27nov2011 )
  295 t !  70 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ F
  296 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  297 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  298 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  299 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  300 t !  68 pho !  0 beg !   0 ctu ! 517 audpsi ! AudMem \ D
517 dnr !   1 mfn !  1 dba ! 517 fex ! 5 pos ! 517 fin ! 295 aud !
517 psi !   1 num !  0 pre !   0 seq ! 517 dex ! DeVocab InNativate

( 301: 517=FREUNDE  "friends" noun; plural; 27nov2011 )
  302 t !  70 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ F
  303 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  304 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  305 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  306 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  307 t !  68 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ D
  308 t !  69 pho !  0 beg !   0 ctu ! 517 audpsi ! AudMem \ E
517 dnr !   0 mfn !  1 dba ! 517 fex ! 5 pos ! 517 fin ! 302 aud !
517 psi !   2 num !  0 pre !   0 seq ! 517 dex ! DeVocab InNativate

( 309: 519=FREUNDIN  "friend" noun; fem. singular; 2dec2011 )
  310 t !  70 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ F
  311 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  312 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  313 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  314 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  315 t !  68 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ D
  316 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  317 t !  78 pho !  0 beg !   0 ctu ! 519 audpsi ! AudMem \ N
519 dnr !   2 mfn !  1 dba ! 519 fex ! 5 pos ! 519 fin ! 310 aud !
519 psi !   1 num !  0 pre !   0 seq ! 519 dex ! DeVocab InNativate

( 318: 519=FREUNDINNEN  "friends" noun; plural; 2dec2011 )
  319 t !  70 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ F
  320 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  321 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  322 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  323 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  324 t !  68 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ D
  325 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  326 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  327 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  328 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  329 t !  78 pho !  0 beg !   0 ctu ! 519 audpsi ! AudMem \ N
519 dnr !   2 mfn !  1 dba ! 519 fex ! 5 pos ! 519 fin ! 319 aud !
519 psi !   2 num !  0 pre !   0 seq ! 519 dex ! DeVocab InNativate

( 330: 640=FUER  "for" prep. with dba accusative; 26nov2011 )
  331 t !  70 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ F
  332 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  333 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  334 t !  82 pho !  0 beg !   0 ctu ! 640 audpsi ! AudMem \ R
640 dnr !   0 mfn !  0 dba ! 640 fex ! 6 pos ! 640 fin ! 331 aud !
640 psi !   0 num !  0 pre !   0 seq ! 640 dex ! DeVocab InNativate

( 335 440=GELL  "right?" interjection; 27nov2011 )
  336 t !  71 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ G
  337 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  338 t !  76 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ L
  339 t !  76 pho !  0 beg !   0 ctu ! 640 audpsi ! AudMem \ L
440 dnr !   0 mfn !  0 dba ! 440 fex ! 4 pos ! 440 fin ! 336 aud !
440 psi !   0 num !  0 pre !   0 seq ! 440 dex ! DeVocab InNativate

( 340: 228=GENUG "enough" adverb; 28nov2011 )
  341 t !  71 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ G
  342 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  343 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  344 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  345 t !  71 pho !  0 beg !   0 ctu ! 228 audpsi ! AudMem \ G
228 dnr !   0 mfn !  0 dba ! 228 fex ! 2 pos ! 228 fin ! 341 aud !
228 psi !   0 num !  0 pre !   0 seq ! 228 dex ! DeVocab InNativate

( 346: 758=GENUG "enough" pronoun; 28nov2011 )
  347 t !  71 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ G
  348 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  349 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  350 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  351 t !  71 pho !  0 beg !   0 ctu ! 758 audpsi ! AudMem \ G
758 dnr !   3 mfn !  1 dba ! 758 fex ! 7 pos ! 758 fin ! 347 aud !
758 psi !   0 num !  0 pre !   0 seq ! 758 dex ! DeVocab InNativate

( 352: 230=GERN  "gladly" adverb  26nov2011 )
  353 t !  71 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ G
  354 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  355 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  356 t !  78 pho !  0 beg !   0 ctu ! 230 audpsi ! AudMem \ N
230 dnr !   0 mfn !  0 dba ! 230 fex ! 2 pos ! 230 fin ! 353 aud !
230 psi !   0 num !  0 pre !   0 seq ! 230 dex ! DeVocab InNativate

( 357: 140=GUT  "good" adjective; frequent' 5dec2011 )
  358 t !  71 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ G
  359 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  360 t !  84 pho !  0 beg !   0 ctu ! 140 audpsi ! AudMem \ T
140 dnr !   0 mfn !  0 dba ! 140 fex ! 1 pos ! 140 fin ! 358 aud !
140 psi !   0 num !  0 pre !   0 seq ! 140 dex ! DeVocab InNativate

( 361: 810=HABEN  "have" irregular verb; 3dec2011 )
  362 t !  72 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ H
  363 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  364 t !  66 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ B
  365 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  366 t !  78 pho !  0 beg !   0 ctu ! 810 audpsi ! AudMem \ N
810 dnr !   0 mfn !  0 dba ! 810 fex ! 8 pos ! 810 fin ! 362 aud !
810 psi !   0 num !  0 pre !   0 seq ! 810 dex ! DeVocab InNativate

( 367: 810=HABE "have" verb; irreg; 1st pers. sing. 20nov2012 )
  368 t !  72 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ H
  369 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  370 t !  66 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ B
  371 t !  69 pho !  0 beg !   0 ctu ! 810 audpsi ! AudMem \ E
810 dnr !   0 mfn !  1 dba ! 810 fex ! 8 pos ! 810 fin ! 368 aud !
810 psi !   1 num !  0 pre !   0 seq ! 810 dex ! DeVocab InNativate

( 372 810 HAST "have" verb; irreg; 2nd pers. sing. 20nov2012 )
  373 t !  72 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ H
  374 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  375 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  376 t !  84 pho !  0 beg !   0 ctu ! 810 audpsi ! AudMem \ T
810 dnr !   0 mfn !  2 dba ! 810 fex ! 8 pos ! 810 fin ! 373 aud !
810 psi !   1 num !  0 pre !   0 seq ! 810 dex ! DeVocab InNativate

( 377: 810=HAT  "has" verb; irreg; 3rd pers. sing. 20nov2012 )
  378 t !  72 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ H
  379 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  380 t !  84 pho !  0 beg !   0 ctu ! 810 audpsi ! AudMem \ T
810 dnr !   0 mfn !  3 dba ! 810 fex ! 8 pos ! 810 fin ! 378 aud !
810 psi !   1 num !  0 pre !   0 seq ! 810 dex ! DeVocab InNativate

( 381: 450=HALLO  "hello" interjection for HCI; 27nov2011 )
  382 t !  72 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ H
  383 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  384 t !  76 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ L
  385 t !  76 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ L
  386 t !  79 pho !  0 beg !   0 ctu ! 450 audpsi ! AudMem \ O
450 dnr !   0 mfn !  0 dba ! 450 fex ! 4 pos ! 450 fin ! 382 aud !
450 psi !   0 num !  0 pre !   0 seq ! 450 dex ! DeVocab InNativate

( 387: 895=HELFEN "help" irregular verb; takes dative; 20nov2012 )
  388 t !  72 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ H
  389 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  390 t !  76 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ L
  391 t !  70 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ F
  393 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  393 t !  78 pho !  0 beg !   0 ctu ! 895 audpsi ! AudMem \ N
895 dnr !   0 mfn !  0 dba ! 895 fex ! 8 pos ! 895 fin ! 388 aud !
895 psi !   0 num !  0 pre !   0 seq ! 895 dex ! DeVocab InNativate

( 394: 701=ICH "I" pronoun; for SelfReferential thought; 19nov2012 )
  395 t ! 73 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ I
  396 t ! 67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  397 t ! 72 pho !  0 beg !   0 ctu ! 701 audpsi ! AudMem \ H
 701 dnr ! 0 mfn !  1 dba ! 701 fex !  7 pos ! 707 fin ! 395 aud !
 701 psi ! 1 num !  0 pre !   0 seq ! 701 dex ! DeVocab InNativate

( 398: 701=MEINER  "of me" pronoun; sing. dba genitive; 17nov2012 )
  399 t !  77 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ M
  400 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  401 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  402 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  403 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  404 t !  82 pho !  0 beg !   0 ctu ! 701 audpsi ! AudMem \ R
701 dnr !   0 mfn !  2 dba ! 701 fex ! 7 pos ! 707 fin ! 399 aud !
701 psi !   1 num !  0 pre !   0 seq ! 701 dex ! DeVocab InNativate

( 405: 701=MIR  "to me" pronoun; sing. dba dative; 17nov2012 )
  406 t !  77 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ M
  407 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  408 t !  82 pho !  0 beg !   0 ctu ! 701 audpsi ! AudMem \ R
701 dnr !   0 mfn !  3 dba ! 701 fex ! 7 pos ! 707 fin ! 406 aud !
701 psi !   1 num !  0 pre !   0 seq ! 701 dex ! DeVocab InNativate

( 409: 701=MICH  "me" pronoun; sing. dba accusative; 17nov2012 )
  410 t !  77 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ M
  411 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  412 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  413 t !  72 pho !  0 beg !   0 ctu ! 701 audpsi ! AudMem \ H
701 dnr !   0 mfn !  4 dba ! 701 fex ! 7 pos ! 707 fin ! 410 aud !
701 psi !   1 num !  0 pre !   0 seq ! 701 dex ! DeVocab InNativate

( 414: 737=IHR  "you" pronoun; nom. familiar plural; 17nov2012 )
  415 t !  73 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ I
  416 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  417 t !  82 pho !  0 beg !   0 ctu ! 737 audpsi ! AudMem \ R
737 dnr !   0 mfn !  1 dba ! 737 fex ! 1 pos ! 731 fin ! 415 aud !
737 psi !   2 num !  0 pre !   0 seq ! 737 dex ! DeVocab InNativate

( 418: 737=EUER  "of you" fam. pl. prounoun; dba genitive; 17nov2012 )
  419 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  420 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  421 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  422 t !  82 pho !  0 beg !   0 ctu ! 737 audpsi ! AudMem \ R
737 dnr !   0 mfn !  2 dba ! 737 fex ! 7 pos ! 731 fin ! 419 aud !
737 psi !   2 num !  0 pre !   0 seq ! 737 dex ! DeVocab InNativate

( 423: 737=EUCH  "to you" fam. pl. pronoun; dba dative; 17nov2012 )
  424 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  425 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  426 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  427 t !  72 pho !  0 beg !   0 ctu ! 737 audpsi ! AudMem \ H
737 dnr !   0 mfn !  3 dba ! 737 fex ! 7 pos ! 731 fin ! 424 aud !
737 psi !   2 num !  0 pre !   0 seq ! 737 dex ! DeVocab InNativate

( 428: 737=EUCH  "you" fam. pl. pronoun; dba acc. 17nov2012 )
  429 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
  430 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  431 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  432 t !  72 pho !  0 beg !   0 ctu ! 737 audpsi ! AudMem \ H
737 dnr !   0 mfn !  4 dba ! 737 fex ! 7 pos ! 731 fin ! 429 aud !
737 psi !   2 num !  0 pre !   0 seq ! 737 dex ! DeVocab InNativate

( 433: 470=JA  "yes" interjection; for HCI and KbRetro )
  434 t !  74 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ J
  435 t !  65 pho !  0 beg !   0 ctu ! 450 audpsi ! AudMem \ A
470 dnr !   0 mfn !  0 dba ! 470 fex ! 4 pos ! 470 fin ! 434 aud !
470 psi !   0 num !  0 pre !  0 seq ! 470 dex ! DeVocab InNativate

( 436: 760=JEMAND  "somebody" pronoun; nom. singular; 5dec2011 )
  437 t !  74 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ J
  438 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  439 t !  77 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ M
  440 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  441 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  442 t !  68 pho !  0 beg !   0 ctu ! 760 audpsi ! AudMem \ D
760 dnr !   0 mfn !  1 dba ! 760 fex ! 7 pos ! 760 fin ! 437 aud !
760 psi !   1 num !  0 pre !   0 seq ! 760 dex ! DeVocab InNativate

( 443: 837=KENNEN  "know" verb; multiple audpsi: 25nov2012 )
  444 t !  75 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ K
  445 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  446 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  447 t !  78 pho !  0 beg !   1 ctu ! 837 audpsi ! AudMem \ N
  448 t !  69 pho !  0 beg !   1 ctu ! 837 audpsi ! AudMem \ E
  449 t !  78 pho !  0 beg !   0 ctu ! 837 audpsi ! AudMem \ N
837 dnr !   0 mfn !  0 dba ! 837 fex ! 8 pos ! 837 fin ! 444 aud !
837 psi !   0 num !  0 pre !   0 seq ! 837 dex ! DeVocab InNativate

( 450: 525=KIND  "child" noun; nom. neuter singular; 5dec2011 )
  451 t !  75 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ K
  452 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  453 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  454 t !  68 pho !  0 beg !   0 ctu ! 525 audpsi ! AudMem \ D
525 dnr !   3 mfn !  1 dba ! 525 fex ! 5 pos ! 525 fin ! 451 aud !
525 psi !   1 num !  0 pre !   0 seq ! 525 dex ! DeVocab InNativate

( 455: 525=KINDER  "children" noun; plural; 5dec2011 )
  456 t !  75 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ K
  457 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  458 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  459 t !  68 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ D
  460 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  461 t !  82 pho !  0 beg !   0 ctu ! 525 audpsi ! AudMem \ R
525 dnr !   0 mfn !  1 dba ! 525 fex ! 5 pos ! 525 fin ! 456 aud !
525 psi !   2 num !  0 pre !   0 seq ! 525 dex ! DeVocab InNativate

( 462: 587=LEUTE  "people" noun; plural; 20nov2012 )
  463 t !  76 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ L
  464 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  465 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  466 t !  84 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ T
  467 t !  69 pho !  0 beg !   0 ctu ! 587 audpsi ! AudMem \ E
587 dnr !   0 mfn !  1 dba ! 587 fex ! 5 pos ! 587 fin ! 463 aud !
587 psi !   2 num !  0 pre !   0 seq ! 587 dex ! DeVocab InNativate

( 468: 838=MACHEN useful verb for "make" or "do"; 20nov2012 )
  469 t !  77 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ M
  470 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  471 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  472 t !  72 pho !  0 beg !   1 ctu ! 838 audpsi ! AudMem \ H
  473 t !  69 pho !  0 beg !   1 ctu ! 838 audpsi ! AudMem \ E
  474 t !  78 pho !  0 beg !   0 ctu ! 838 audpsi ! AudMem \ N
838 dnr !   0 mfn !  0 dba ! 838 fex ! 8 pos ! 838 fin ! 469 aud !
838 psi !   0 num !  0 pre !   0 seq ! 838 dex ! DeVocab InNativate

( 475: 531=MAEDCHEN  "girl" noun; singular 27nov2011 )
  476 t !  77 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ M
  477 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  478 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  479 t !  68 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ D
  480 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  481 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  482 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  483 t !  78 pho !  0 beg !   0 ctu ! 531 audpsi ! AudMem \ N
531 dnr !   3 mfn !  1 dba ! 531 fex ! 5 pos ! 531 fin ! 476 aud !
531 psi !   1 num !  0 pre !   0 seq ! 531 dex ! DeVocab InNativate

( 484: 531=MAEDCHEN  "girls" noun; plural; 5dec2011 )
  485 t !  77 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ M
  486 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  487 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  488 t !  68 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ D
  489 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  490 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  491 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  492 t !  78 pho !  0 beg !   0 ctu ! 531 audpsi ! AudMem \ N
531 dnr !   0 mfn !  1 dba ! 531 fex ! 5 pos ! 531 fin ! 485 aud !
531 psi !   2 num !  0 pre !   0 seq ! 531 dex ! DeVocab InNativate

( 493: 733=MAN -- a person; singular pronoun; 20nov2012 )
  494 t !  77 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ M
  495 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  496 t !  78 pho !  0 beg !   0 ctu ! 101 audpsi ! AudMem \ N
733 dnr !   1 mfn !  1 dba ! 733 fex ! 7 pos ! 733 fin ! 494 aud !
733 psi !   1 num !  0 pre !   0 seq ! 733 dex ! DeVocab InNativate

( 497: 543=MANN  "man" noun; masc. singular; nom. 23nov2012 )
  498 t !  77 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ M
  499 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  500 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  501 t !  78 pho !  0 beg !   0 ctu ! 543 audpsi ! AudMem \ N
543 dnr !   1 mfn !  1 dba ! 543 fex ! 5 pos ! 543 fin ! 498 aud !
543 psi !   1 num !  0 pre !   0 seq ! 543 dex ! DeVocab InNativate

( 502:543=MANNES  "of man" noun; masc. singular; genitive 23nov2012 )
  503 t !  77 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ M
  504 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  505 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  506 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  507 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  508 t !  83 pho !  0 beg !   0 ctu ! 543 audpsi ! AudMem \ S
543 dnr !   1 mfn !  2 dba ! 543 fex ! 5 pos ! 543 fin ! 503 aud !
543 psi !   1 num !  0 pre !   0 seq ! 543 dex ! DeVocab InNativate

( 509 543=MAENNER  "men" noun; plural; nom. 23nov2012 )
  510 t !  77 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ M
  511 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  512 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  513 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  514 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  515 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  516 t !  82 pho !  0 beg !   0 ctu ! 543 audpsi ! AudMem \ R
543 dnr !   1 mfn !  1 dba ! 543 fex ! 5 pos ! 543 fin ! 510 aud !
543 psi !   2 num !  0 pre !  0 seq ! 543 dex ! DeVocab InNativate

( 517: 535=MENSCH  "human being" noun; singular; 27nov2011 )
  518 t !  77 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ M
  519 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  520 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  521 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  522 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  523 t !  72 pho !  0 beg !   0 ctu ! 535 audpsi ! AudMem \ H
535 dnr !   1 mfn !  1 dba ! 535 fex ! 5 pos ! 535 fin ! 518 aud !
535 psi !   1 num !  0 pre !   0 seq ! 535 dex ! DeVocab InNativate

( 524: 535=MENSCHEN "of human being" noun; masc. gen. sing. 5dec2011 )
  525 t !  77 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ M
  526 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  527 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  528 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  529 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  530 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  531 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  532 t !  78 pho !  0 beg !   0 ctu ! 535 audpsi ! AudMem \ N
535 dnr !   1 mfn !  2 dba ! 535 fex ! 5 pos ! 535 fin ! 525 aud !
535 psi !   1 num !  0 pre !   0 seq ! 535 dex ! DeVocab InNativate

( 533: 535=MENSCHEN "to human being" noun; masc. dat. sing. 5dec2011 )
  534 t !  77 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ M
  535 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  536 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  537 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  538 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  539 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  540 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  541 t !  78 pho !  0 beg !   0 ctu ! 535 audpsi ! AudMem \ N
535 dnr !   1 mfn !  3 dba ! 535 fex ! 5 pos ! 535 fin ! 534 aud !
535 psi !   1 num !  0 pre !   0 seq ! 535 dex ! DeVocab InNativate

( 542: 535=MENSCHEN "human being" noun; masc. acc. sing. 5dec2011 )
  543 t !  77 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ M
  544 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  545 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  546 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  547 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  548 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  549 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  550 t !  78 pho !  0 beg !   0 ctu ! 535 audpsi ! AudMem \ N
535 dnr !   1 mfn !  4 dba ! 535 fex ! 5 pos ! 535 fin ! 543 aud !
535 psi !   1 num !  0 pre !   0 seq ! 535 dex ! DeVocab InNativate

( 551: 535 MENSCHEN  "human beings" noun; nom. plural; 5dec2011 )
  552 t !  77 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ M
  553 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  554 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  555 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  556 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  557 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  558 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  559 t !  78 pho !  0 beg !   0 ctu ! 535 audpsi ! AudMem \ N
535 dnr !   0 mfn !  1 dba ! 535 fex ! 5 pos ! 535 fin ! 552 aud !
535 psi !   2 num !  0 pre !  0 seq ! 535 dex ! DeVocab InNativate

( 560: 480=NEIN  "no" interjection; for HCI and KbRetro; 5dec2011 )
  561 t !  78 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ N
  562 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  563 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  564 t !  78 pho !  0 beg !   0 ctu ! 480 audpsi ! AudMem \ N
480 dnr !   0 mfn !  0 dba ! 480 fex ! 4 pos ! 480 fin ! 561 aud !
480 psi !   0 num !  0 pre !   0 seq ! 480 dex ! DeVocab InNativate

( 565: 250=NICHT  "not"  adverb for negation; 26nov2011 )
  566 t !  78 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ N
  567 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  568 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  569 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  570 t !  84 pho !  0 beg !   0 ctu ! 250 audpsi ! AudMem \ T
250 dnr !   0 mfn !  0 dba ! 250 fex ! 2 pos ! 250 fin ! 566 aud !
250 psi !   0 num !  0 pre !   0 seq ! 250 dex ! DeVocab InNativate

( 571: 770=NICHTS  "nothing" pronoun; 26nov2011 )
  572 t !  78 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ N
  573 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  574 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  575 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  576 t !  84 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ T
  577 t !  83 pho !  0 beg !   0 ctu ! 770 audpsi ! AudMem \ S
770 dnr !   3 mfn !  1 dba ! 770 fex ! 7 pos ! 770 fin ! 572 aud !
770 psi !   1 num !  0 pre !   0 seq ! 770 dex ! DeVocab InNativate

( 578: 775=NIEMAND  "nobody" pronoun; nom. singular; 5dec2011 )
  579 t !  78 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ N
  580 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  581 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  582 t !  77 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ M
  583 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  584 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  585 t !  68 pho !  0 beg !   0 ctu ! 775 audpsi ! AudMem \ D
775 dnr !   1 mfn !  1 dba ! 775 fex ! 7 pos ! 775 fin ! 579 aud !
775 psi !   1 num !  0 pre !   0 seq ! 775 dex ! DeVocab InNativate

( 586: 258=NUR  "only" adverb; 2dec2011 )
  587 t !  78 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ N
  588 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  589 t !  82 pho !  0 beg !   0 ctu ! 258 audpsi ! AudMem \ R
258 dnr !   0 mfn !  0 dba ! 258 fex ! 2 pos ! 258 fin ! 587 aud !
258 psi !   0 num !  0 pre !   0 seq ! 258 dex ! DeVocab InNativate

( 590: 330=OB  "whether"  conj. 26nov2011 )
  591 t !  79 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ O
  592 t !  66 pho !  0 beg !   0 ctu ! 330 audpsi ! AudMem \ B
330 dnr !   0 mfn !  0 dba ! 330 fex ! 3 pos ! 330 fin ! 591 aud !
330 psi !   0 num !  0 pre !   0 seq ! 330 dex ! DeVocab InNativate

( 593: 340=ODER  "or" conj. 26nov2011 )
  594 t !  79 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ O
  595 t !  68 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ D
  596 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  597 t !  82 pho !  0 beg !   0 ctu ! 340 audpsi ! AudMem \ R
340 dnr !   0 mfn !  0 dba ! 340 fex ! 3 pos ! 340 fin ! 594 aud !
340 psi !   0 num !  0 pre !   0 seq ! 340 dex ! DeVocab InNativate

( 598: 537=PERSON  "person" noun; singular; 27nov2011 )
  599 t !  80 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ P
  600 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  601 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  602 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  603 t !  79 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ O
  604 t !  78 pho !  0 beg !   0 ctu ! 537 audpsi ! AudMem \ N
537 dnr !   2 mfn !  1 dba ! 537 fex ! 5 pos ! 537 fin ! 599 aud !
537 psi !   1 num !  0 pre !   0 seq ! 537 dex ! DeVocab InNativate

( 605: 537=PERSONEN  "persons" noun; plural; 27nov2011 )
  606 t !  80 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ P
  607 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  608 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  609 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  610 t !  79 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ O
  611 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  612 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  613 t !  78 pho !  0 beg !   0 ctu ! 537 audpsi ! AudMem \ N
537 dnr !   0 mfn !  1 dba ! 537 fex ! 5 pos ! 537 fin ! 606 aud !
537 psi !   2 num !  0 pre !   0 seq ! 537 dex ! DeVocab InNativate

( 614: 571=ROBOTER  "robot" noun; masc. singular; 23nov2012 )
  615 t !  82 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ R
  616 t !  79 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ O
  617 t !  66 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ B
  618 t !  79 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ O
  619 t !  84 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ T
  620 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  621 t !  82 pho !  0 beg !   0 ctu ! 571 audpsi ! AudMem \ R
571 dnr !   1 mfn !  1 dba ! 571 fex ! 5 pos ! 571 fin ! 615 aud !
571 psi !   1 num !  0 pre !  0 seq ! 571 dex ! DeVocab InNativate

( 622: 571=ROBOTER  "robots" noun; plural; 23nov2012 )
  623 t !  82 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ R
  624 t !  79 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ O
  625 t !  66 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ B
  626 t !  79 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ O
  627 t !  84 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ T
  628 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  629 t !  82 pho !  0 beg !   0 ctu ! 571 audpsi ! AudMem \ R
571 dnr !   0 mfn !  1 dba ! 571 fex ! 5 pos ! 571 fin ! 623 aud !
571 psi !   2 num !  0 pre !   0 seq ! 571 dex ! DeVocab InNativate

( 630: 557=SACHE  "thing" noun; singular; 23nov2012 )
  631 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  632 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  633 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  634 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  635 t !  69 pho !  0 beg !   0 ctu ! 557 audpsi ! AudMem \ E
557 dnr !   2 mfn !  1 dba ! 557 fex ! 5 pos ! 557 fin ! 631 aud !
557 psi !   1 num !  0 pre !   0 seq ! 557 dex ! DeVocab InNativate

( 636: 557=SACHEN  "things" noun; plural; 23nov2012 )
  637 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  638 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  639 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  640 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  641 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  642 t !  78 pho !  0 beg !   0 ctu ! 557 audpsi ! AudMem \ N
557 dnr !   0 mfn !  1 dba ! 557 fex ! 5 pos ! 557 fin ! 637 aud !
557 psi !   2 num !  0 pre !   0 seq ! 557 dex ! DeVocab InNativate

( 643: 564=SCHACH  "chess" noun for AI; singular; 20nov2012 )
  644 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  645 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  646 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  647 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  648 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  649 t !  72 pho !  0 beg !   0 ctu ! 564 audpsi ! AudMem \ H
564 dnr !   2 mfn !  1 dba ! 564 fex ! 5 pos ! 564 fin ! 644 aud !
564 psi !   1 num !  0 pre !   0 seq ! 564 dex ! DeVocab InNativate

( 650: 260=SCHON "already" adverb; frequent; 23nov2012 )
  651 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  652 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  653 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  654 t !  79 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ O
  655 t !  78 pho !  0 beg !   0 ctu ! 260 audpsi ! AudMem \ N
260 dnr !   0 mfn !  0 dba ! 260 fex ! 2 pos ! 260 fin ! 651 aud !
260 psi !   0 num !  0 pre !   0 seq ! 260 dex ! DeVocab InNativate

( 656: 840=SEHEN  "see" verb; needed for VisRecog; 27nov2011 )
  657 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  658 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  659 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  660 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  661 t !  78 pho !  0 beg !   0 ctu ! 840 audpsi ! AudMem \ N
840 dnr !   0 mfn !  0 dba ! 840 fex ! 8 pos ! 840 fin ! 657 aud !
840 psi !   0 num !  0 pre !   0 seq ! 840 dex ! DeVocab InNativate

( 662: 840=SIEHST "see" verb; irreg. 2nd pers. sing. 20nov2012 )
  663 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  664 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  665 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  666 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  667 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  668 t !  84 pho !  0 beg !   0 ctu ! 840 audpsi ! AudMem \ T
840 dnr !   0 mfn !  2 dba ! 840 fex ! 8 pos ! 840 fin ! 663 aud !
840 psi !   1 num !  0 pre !   0 seq ! 840 dex ! DeVocab InNativate

( 669: 840=SIEHT  "sees" verb; irreg. 3rd pers. sing. 20nov2012 )
  670 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  671 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  672 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  673 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  674 t !  84 pho !  0 beg !   0 ctu ! 840 audpsi ! AudMem \ T
840 dnr !   0 mfn !  3 dba ! 840 fex ! 8 pos ! 840 fin ! 670 aud !
840 psi !   1 num !  0 pre !   0 seq ! 840 dex ! DeVocab InNativate

( 675: 800=SEIN  "be" verb; infinitive; irregular; 18nov2012 )
  676 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  677 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  678 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  679 t !  78 pho !  0 beg !   0 ctu ! 800 audpsi ! AudMem \ N
800 dnr !   0 mfn !  0 dba ! 800 fex ! 8 pos ! 800 fin ! 676 aud !
800 psi !   0 num !  0 pre !   0 seq ! 800 dex ! DeVocab InNativate

( 680: 800=BIN  "am" verb irreg. 1st pers. sing. 18nov2012 )
  681 t !  66 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ B
  682 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  683 t !  78 pho !  0 beg !   0 ctu ! 800 audpsi ! AudMem \ N
800 dnr !   0 mfn !  1 dba ! 800 fex ! 8 pos ! 800 fin ! 681 aud !
800 psi !   1 num !  0 pre !   0 seq ! 800 dex ! DeVocab InNativate

( 684: 800=BIST "are" verb irreg. 2nd pers. sing. 23nov2012 )
  685 t !  66 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ B
  686 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  687 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  688 t !  84 pho !  0 beg !   0 ctu ! 800 audpsi ! AudMem \ T
800 dnr !   0 mfn !  2 dba ! 800 fex ! 8 pos ! 800 fin ! 685 aud !
800 psi !   1 num !  0 pre !   0 seq ! 800 dex ! DeVocab InNativate

( 689: 800=IST  "is" verb irreg; 3rd pers. sing. 18nov2012 )
  690 t !  73 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ I
  691 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  692 t !  84 pho !  0 beg !   0 ctu ! 800 audpsi ! AudMem \ T
800 dnr !   0 mfn !  3 dba ! 800 fex ! 8 pos ! 800 fin ! 690 aud !
800 psi !   1 num !  0 pre !   0 seq ! 800 dex ! DeVocab InNativate

( 693: 800=SIND "are" verb irreg. 1st pers. plur. 18nov2012 )
  694 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  695 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  696 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  697 t !  68 pho !  0 beg !   0 ctu ! 800 audpsi ! AudMem \ D
800 dnr !   0 mfn !  1 dba ! 800 fex ! 8 pos ! 800 fin ! 694 aud !
800 psi !   2 num !  0 pre !   0 seq ! 800 dex ! DeVocab InNativate

( 698: 800=SEID  "are" verb irreg. 2nd pers. plur. 18nov2012 )
  699 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  700 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  701 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  702 t !  68 pho !  0 beg !   0 ctu ! 800 audpsi ! AudMem \ D
800 dnr !   0 mfn !  2 dba ! 800 fex ! 8 pos ! 800 fin ! 699 aud !
800 psi !   2 num !  0 pre !   0 seq ! 800 dex ! DeVocab InNativate

( 703: 800=SIND "are" verb irreg. 3rd pers. plur. 18nov2012 )
  704 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  705 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  706 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  707 t !  68 pho !  0 beg !   0 ctu ! 800 audpsi ! AudMem \ D
800 dnr !   0 mfn !  3 dba ! 800 fex ! 8 pos ! 800 fin ! 704 aud !
800 psi !   2 num !  0 pre !   0 seq ! 800 dex ! DeVocab InNativate

( 708: 800=SIND "are" verb irreg; 2nd pers. sing. 18nov2012 )
\  709 t !  83 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ S
\  710 t !  73 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ I
\  711 t !  78 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ N
\  712 t !  68 pho !  0 beg !  0 ctu ! 800 audpsi ! AudMem \ D
\ 800 dnr !  0 mfn !  2 dba ! 800 fex ! 8 pos ! 800 fin ! 709 aud !
\ 800 psi !  1 num !  0 pre !  0 seq ! 800 dex ! DeVocab InNativate

( 713: 800=SIND "are" verb irreg. 2nd pers. plur. 18nov2012 )
\  714 t !  83 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ S
\  715 t !  73 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ I
\  716 t !  78 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ N
\  717 t !  68 pho !  0 beg !  0 ctu ! 800 audpsi ! AudMem \ D
\ 800 dnr !  0 mfn !  2 dba ! 800 fex ! 8 pos ! 800 fin ! 714 aud !
\ 800 psi !  2 num !  0 pre !  0 seq ! 800 dex ! DeVocab InNativate

( 718: 719=SIE  nominative "she" 17nov2012 )
  719 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  720 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  721 t !  69 pho !  0 beg !   0 ctu ! 719 audpsi ! AudMem \ E
719 dnr !   2 mfn !  1 dba ! 719 fex ! 7 pos ! 719 fin ! 719 aud !
719 psi !   1 num !  0 pre !  0 seq ! 719 dex ! DeVocab InNativate

( 722: 719=IHRER  "of her" pronoun; fem. sing. genitive  17nov2012 )
  723 t !  73 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ I
  724 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  725 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  726 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  727 t !  82 pho !  0 beg !   0 ctu ! 719 audpsi ! AudMem \ R
719 dnr !   2 mfn !  2 dba ! 719 fex ! 7 pos ! 719 fin ! 723 aud !
719 psi !   1 num !  0 pre !   0 seq ! 719 dex ! DeVocab InNativate

( 728: 719=IHR  "to her" pronoun; fem. sing. dba dative; 17nov2012 )
  729 t !  73 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ I
  730 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  731 t !  82 pho !  0 beg !   0 ctu ! 719 audpsi ! AudMem \ R
719 dnr !   2 mfn !  3 dba ! 719 fex ! 1 pos ! 719 fin ! 729 aud !
719 psi !   1 num !  0 pre !   0 seq ! 719 dex ! DeVocab InNativate

( 732: 719=SIE  accusative "her"; 17nov2012 )
  733 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  734 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  735 t !  69 pho !  0 beg !   0 ctu ! 719 audpsi ! AudMem \ E
719 dnr !   2 mfn !  4 dba ! 719 fex ! 7 pos ! 719 fin ! 733 aud !
719 psi !   1 num !  0 pre !   0 seq ! 719 dex ! DeVocab InNativate

( 736: 743=SIE  nominative "they"; 17nov2012 )
  737 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  738 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  739 t !  69 pho !  0 beg !   0 ctu ! 743 audpsi ! AudMem \ E
743 dnr !   0 mfn !  1 dba ! 743 fex ! 7 pos ! 743 fin ! 737 aud !
743 psi !   2 num !  0 pre !   0 seq ! 743 dex ! DeVocab InNativate

( 740: 743=IHRER  "of them" pronoun; genitive plural; 17nov2012 )
  741 t !  73 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ I
  742 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  743 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  744 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  745 t !  82 pho !  0 beg !   0 ctu ! 743 audpsi ! AudMem \ R
743 dnr !   0 mfn !  2 dba ! 743 fex ! 7 pos ! 743 fin ! 741 aud !
743 psi !   2 num !  0 pre !   0 seq ! 743 dex ! DeVocab InNativate

( 746: 743=IHNEN  "to them" pronoun; dative plural; 17nov2012 )
  747 t !  73 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ I
  748 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  749 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  750 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  751 t !  78 pho !  0 beg !   0 ctu ! 743 audpsi ! AudMem \ N
743 dnr !   0 mfn !  3 dba ! 743 fex ! 7 pos ! 743 fin ! 747 aud !
743 psi !   2 num !  0 pre !   0 seq ! 743 dex ! DeVocab InNativate

( 752: 743=SIE  accusative plural "them"; 17nov2012 )
  753 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  754 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  755 t !  69 pho !  0 beg !   0 ctu ! 743 audpsi ! AudMem \ E
743 dnr !   0 mfn !  4 dba ! 743 fex ! 7 pos ! 743 fin ! 753 aud !
743 psi !   2 num !  0 pre !   0 seq ! 743 dex ! DeVocab InNativate

( 756: 749=SIE  nominative singular formal "you"; 17nov2012 )
  757 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  758 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  759 t !  69 pho !  0 beg !   0 ctu ! 749 audpsi ! AudMem \ E
749 dnr !   0 mfn !  1 dba ! 749 fex ! 7 pos ! 701 fin ! 757 aud !
749 psi !   1 num !  0 pre !   0 seq ! 749 dex ! DeVocab InNativate

( 760: 749=IHRER  "of you" pronoun; formal gen. sing. 17nov2012 )
  761 t !  73 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ I
  762 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  763 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  764 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  765 t !  82 pho !  0 beg !   0 ctu ! 749 audpsi ! AudMem \ R
749 dnr !   0 mfn !  2 dba ! 749 fex ! 7 pos ! 701 fin ! 761 aud !
749 psi !   1 num !  0 pre !   0 seq ! 749 dex ! DeVocab InNativate

( 766: 749=IHNEN  "to you" pronoun; sing. formal dative; 17nov2012 )
  767 t !  73 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ I
  768 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  769 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  770 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  771 t !  78 pho !  0 beg !   0 ctu ! 749 audpsi ! AudMem \ N
749 dnr !   0 mfn !  3 dba ! 749 fex ! 7 pos ! 701 fin ! 767 aud !
749 psi !   1 num !  0 pre !   0 seq ! 749 dex ! DeVocab InNativate

( 772: 749=SIE  accusative singular formal "you"; 17nov2012 )
  773 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  774 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  775 t !  69 pho !  0 beg !   0 ctu ! 749 audpsi ! AudMem \ E
749 dnr !   0 mfn !  4 dba ! 749 fex ! 7 pos ! 701 fin ! 773 aud !
749 psi !   1 num !  0 pre !   0 seq ! 749 dex ! DeVocab InNativate

( 776: 755=SIE  nominative plural formal "you"; 17nov2012 )
  777 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  778 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  779 t !  69 pho !  0 beg !   0 ctu ! 755 audpsi ! AudMem \ E
755 dnr !   0 mfn !  1 dba ! 755 fex ! 7 pos ! 731 fin ! 777 aud !
755 psi !   2 num !  0 pre !   0 seq ! 755 dex ! DeVocab InNativate

( 780: 755=IHRER  "of you" pronoun; formal gen. plural; 17nov2012 )
  781 t !  73 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ I
  782 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  783 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  784 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  785 t !  82 pho !  0 beg !   0 ctu ! 755 audpsi ! AudMem \ R
755 dnr !   0 mfn !  2 dba ! 755 fex ! 7 pos ! 731 fin ! 781 aud !
755 psi !   2 num !  0 pre !   0 seq ! 755 dex ! DeVocab InNativate

( 786: 755=IHNEN  plural formal dative "to you"; 17nov2012 )
  787 t !  73 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ I
  788 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  789 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  790 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  791 t !  78 pho !  0 beg !   0 ctu ! 755 audpsi ! AudMem \ N
755 dnr !   0 mfn !  3 dba ! 755 fex ! 7 pos ! 731 fin ! 787 aud !
755 psi !   2 num !  0 pre !   0 seq ! 755 dex ! DeVocab InNativate

( 792: 755=SIE  accusative plural formal  "you"; 17nov2012 )
  793 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  794 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  795 t !  69 pho !  0 beg !   0 ctu ! 755 audpsi ! AudMem \ E
755 dnr !   0 mfn !  4 dba ! 755 fex ! 7 pos ! 731 fin ! 793 aud !
755 psi !   2 num !  0 pre !   0 seq ! 755 dex ! DeVocab InNativate

( 796: 264=SO  "so, thus" adverb, frequent; 4dec2011 )
  797 t !  83 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ S
  798 t !  79 pho !  0 beg !  0 ctu ! 264 audpsi ! AudMem \ O
264 dnr !   0 mfn !  0 dba ! 264 fex ! 2 pos ! 264 fin ! 797 aud !
264 psi !   0 num !  0 pre !  0 seq ! 264 dex ! DeVocab InNativate

( 799: 266=SONST  "otherwise" adverb useful for logic; 4dec2011 )
  800 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  801 t !  79 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ O
  802 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  803 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  804 t !  84 pho !  0 beg !   0 ctu ! 266 audpsi ! AudMem \ T
266 dnr !   0 mfn !  0 dba ! 266 fex ! 2 pos ! 266 fin ! 800 aud !
266 psi !   0 num !  0 pre !   0 seq ! 266 dex ! DeVocab InNativate

( 805: 268=SOWIESO  "generally" adverb, idiomatically valuable )
  806 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  807 t !  79 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ O
  808 t !  87 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ W
  809 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  810 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  811 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  812 t !  79 pho !  0 beg !   0 ctu ! 268 audpsi ! AudMem \ O
268 dnr !   0 mfn !  0 dba ! 268 fex ! 2 pos ! 268 fin ! 806 aud !
268 psi !   0 num !  0 pre !   0 seq ! 268 dex ! DeVocab InNativate

( 813: 860=SPRECHEN  "speak" verb; irregular; 27nov2011 )
  814 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  815 t !  80 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ P
  816 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  817 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  818 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  819 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  820 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  821 t !  78 pho !  0 beg !   0 ctu ! 860 audpsi ! AudMem \ N
860 dnr !   0 mfn !  0 dba ! 860 fex ! 8 pos ! 860 fin ! 814 aud !
860 psi !   0 num !  0 pre !   0 seq ! 860 dex ! DeVocab InNativate

( 822:  860=SPRECHE  "speak" verb; irreg; 1st pers. sing. 22dec2011 )
  823 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  824 t !  80 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ P
  825 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  826 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  827 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  828 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  829 t !  69 pho !  0 beg !   0 ctu ! 860 audpsi ! AudMem \ E
860 dnr !   0 mfn !  1 dba ! 860 fex ! 8 pos ! 860 fin ! 823 aud !
860 psi !   1 num !  0 pre !   0 seq ! 860 dex ! DeVocab InNativate

( 830: 860=SPRICHST  "speak" verb; irreg. 2nd pers. sing. 22dec2011 )
  831 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  832 t !  80 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ P
  833 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  834 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  835 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  836 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  837 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  838 t !  84 pho !  0 beg !   0 ctu ! 860 audpsi ! AudMem \ T
860 dnr !   0 mfn !  2 dba ! 860 fex ! 8 pos ! 860 fin ! 831 aud !
860 psi !   1 num !  0 pre !   0 seq ! 860 dex ! DeVocab InNativate

( 839: 860=SPRICHT   "speaks" verb; irreg. 3rd pers. sing; 14dec2011 )
  840 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
  841 t !  80 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ P
  842 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  843 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  844 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  845 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  846 t !  84 pho !  0 beg !   0 ctu ! 860 audpsi ! AudMem \ T
860 dnr !   0 mfn !  3 dba ! 860 fex ! 8 pos ! 860 fin ! 840 aud !
860 psi !   1 num !  0 pre !   0 seq ! 860 dex ! DeVocab InNativate

( 847: 546=TIER  "animal" noun; singular; 27nov2011 )
  848 t !  84 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ T
  849 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  850 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  851 t !  82 pho !  0 beg !   0 ctu ! 546 audpsi ! AudMem \ R
546 dnr !   3 mfn !  1 dba ! 546 fex ! 5 pos ! 546 fin ! 848 aud !
546 psi !   1 num !  0 pre !   0 seq ! 546 dex ! DeVocab InNativate

( 852: 546=TIERE  "animals" noun; plural; 27nov2011 )
  853 t !  84 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ T
  854 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  855 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  856 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  857 t !  69 pho !  0 beg !   0 ctu ! 546 audpsi ! AudMem \ E
546 dnr !   0 mfn !  1 dba ! 546 fex ! 5 pos ! 546 fin ! 853 aud !
546 psi !   2 num !  0 pre !   0 seq ! 546 dex ! DeVocab InNativate

( 858: 830=TUN  "do" verb; irregular; infinitive; 20nov2012 )
  859 t !  84 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ T
  860 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  861 t !  78 pho !  0 beg !   0 ctu ! 830 audpsi ! AudMem \ N
830 dnr !   0 mfn !  0 dba ! 830 fex ! 8 pos ! 830 fin ! 859 aud !
830 psi !   0 num !  0 pre !   0 seq ! 830 dex ! DeVocab InNativate

( 862: 830=TUE  "do" verb; irreg; 1st pers. sing. 20nov2012 )
  863 t !  84 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ T
  864 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  865 t !  69 pho !  0 beg !   0 ctu ! 830 audpsi ! AudMem \ E
830 dnr !   0 mfn !  1 dba ! 830 fex ! 8 pos ! 830 fin ! 863 aud !
830 psi !   1 num !  0 pre !   0 seq ! 830 dex ! DeVocab InNativate

( 866: 830=TUST  "do" verb; irreg; 2nd pers. sing. 20nov2012 )
  867 t !  84 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ T
  868 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  869 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  870 t !  84 pho !  0 beg !   0 ctu ! 830 audpsi ! AudMem \ T
830 dnr !   0 mfn !  2 dba ! 830 fex ! 8 pos ! 830 fin ! 867 aud !
830 psi !   1 num !  0 pre !   0 seq ! 830 dex ! DeVocab InNativate

( 871: 830=TUT  "do" verb; irreg; 3rd pers. sing. 20nov2012 )
  872 t !  84 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ T
  873 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  874 t !  84 pho !  0 beg !   0 ctu ! 830 audpsi ! AudMem \ T
830 dnr !   0 mfn !  3 dba ! 830 fex ! 8 pos ! 830 fin ! 872 aud !
830 psi !   1 num !  0 pre !   0 seq ! 830 dex ! DeVocab InNativate

( 875: 830=TUN  "do" verb; irreg; 1st pers. plural; 20nov2012 )
  876 t !  84 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ T
  877 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  878 t !  78 pho !  0 beg !   0 ctu ! 830 audpsi ! AudMem \ N
830 dnr !   0 mfn !  1 dba ! 830 fex ! 8 pos ! 830 fin ! 876 aud !
830 psi !   2 num !  0 pre !   0 seq ! 830 dex ! DeVocab InNativate

( 879: 830=TUT  "do" verb; irreg; 2nd pers. plural. 20nov2012 )
  880 t !  84 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ T
  881 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  882 t !  84 pho !  0 beg !   0 ctu ! 830 audpsi ! AudMem \ T
830 dnr !   0 mfn !  2 dba ! 830 fex ! 8 pos ! 830 fin ! 880 aud !
830 psi !   2 num !  0 pre !   0 seq ! 830 dex ! DeVocab InNativate

( 883: 830=TUN  "do" verb; irreg; 3rd pers. plural; 20nov2012 )
  884 t !  84 pho !  1 beg !   1 ctu !  0 audpsi ! AudMem \ T
  885 t !  85 pho !  0 beg !   1 ctu !  0 audpsi ! AudMem \ U
  886 t !  78 pho !  0 beg !   0 ctu ! 830 audpsi ! AudMem \ N
830 dnr !   0 mfn !  3 dba ! 830 fex ! 8 pos ! 830 fin ! 884 aud !
830 psi !   2 num !  0 pre !   0 seq ! 830 dex ! DeVocab InNativate

( 887: 830=TUN  "do" verb; polite irreg; 2nd pers. sing; 20nov2012 )
\  888 t !  84 pho !  1 beg !  1 ctu !  0 audpsi ! AudMem \ T
\  889 t !  85 pho !  0 beg !  1 ctu !  0 audpsi ! AudMem \ U
\  890 t !  78 pho !  0 beg !  0 ctu ! 830 audpsi ! AudMem \ N
\ 830 dnr !   0 mfn !  2 dba ! 830 fex ! 8 pos ! 830 fin ! 888 aud !
\ 830 psi !   1 num !  0 pre !  0 seq ! 830 dex ! DeVocab InNativate

( 891: 830=TUN  "do" verb; polite irreg; 2nd pers. plural 20nov2012 )
\  892 t !  84 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ T
\  893 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
\  894 t !  78 pho !  0 beg !   0 ctu ! 830 audpsi ! AudMem \ N
\ 830 dnr !   0 mfn !  2 dba ! 830 fex ! 8 pos ! 830 fin ! 892 aud !
\ 830 psi !   2 num !  0 pre !   0 seq ! 830 dex ! DeVocab InNativate

( 895: 350=UM  "in order to" conj. 26nov2011 )
  896 t !  85 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ U
  897 t !  77 pho !  0 beg !   0 ctu ! 350 audpsi ! AudMem \ M
350 dnr !   0 mfn !  0 dba ! 350 fex ! 3 pos ! 350 fin ! 896 aud !
350 psi !   0 num !  0 pre !   0 seq ! 350 dex ! DeVocab InNativate

( 898: 360=UND  "and" conjunction; 20nov2012 )
  899 t !  85 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ U
  900 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  901 t !  68 pho !  0 beg !   0 ctu ! 360 audpsi ! AudMem \ D
360 dnr !   0 mfn !  0 dba ! 360 fex ! 3 pos ! 360 fin ! 899 aud !
360 psi !   0 num !  0 pre !   0 seq ! 360 dex ! DeVocab InNativate

( 902: 878=VERSTEHEN "understand"; verb; 24nov2012 )
  903 t !  86 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ V
  904 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  905 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  906 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  907 t !  84 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ T
  908 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  909 t !  72 pho !  0 beg !   1 ctu ! 878 audpsi ! AudMem \ H
  910 t !  69 pho !  0 beg !   1 ctu ! 878 audpsi ! AudMem \ E
  911 t !  78 pho !  0 beg !   0 ctu ! 878 audpsi ! AudMem \ N
878 dnr !   0 mfn !  0 dba ! 878 fex ! 8 pos ! 878 fin ! 903 aud !
878 psi !   0 num !  0 pre !  0 seq ! 878 dex ! DeVocab InNativate

( 912: 270=VIELLEICHT  "maybe, perhaps" adverb for KbRetro )
  913 t !  86 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ V
  914 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  915 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  916 t !  76 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ L
  917 t !  76 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ L
  918 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  919 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  920 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
  921 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
  922 t !  84 pho !  0 beg !   0 ctu ! 270 audpsi ! AudMem \ T
270 dnr !   0 mfn !  0 dba ! 270 fex ! 2 pos ! 270 fin ! 913 aud !
270 psi !   0 num !  0 pre !   0 seq ! 270 dex ! DeVocab InNativate

( 923: 280=WARUM  "why" adverb, essential for reasoning; 20nov2012 )
  924 t !  87 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ W
  925 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  926 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  927 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  928 t !  77 pho !  0 beg !   0 ctu ! 280 audpsi ! AudMem \ M
280 dnr !   0 mfn !  0 dba ! 280 fex ! 2 pos ! 280 fin ! 924 aud !
280 psi !   0 num !  0 pre !   0 seq ! 280 dex ! DeVocab InNativate

( 929: 370=WARUM  "why" conjunction, essential for reasoning )
  930 t !  87 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ W
  931 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  933 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  934 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
  935 t !  77 pho !  0 beg !   0 ctu ! 370 audpsi ! AudMem \ M
370 dnr !   0 mfn !  0 dba ! 370 fex ! 3 pos ! 370 fin ! 930 aud !
370 psi !   0 num !  0 pre !   0 seq ! 370 dex ! DeVocab InNativate

( 935: 781=WAS  "what" pronoun; 18nov2012 )
  936 t !  87 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ W
  937 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
  938 t !  83 pho !  0 beg !   0 ctu ! 781 audpsi ! AudMem \ S
781 dnr !   3 mfn !  1 dba ! 781 fex ! 7 pos ! 781 fin ! 936 aud !
781 psi !   1 num !  0 pre !   0 seq ! 781 dex ! DeVocab InNativate

( 939: 384=WEIL non-standard "because" see also 344=DENN 20nov2012 )
  940 t !  87 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ W
  941 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  942 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  943 t !  76 pho !  0 beg !   0 ctu ! 384 audpsi ! AudMem \ L
384 dnr !   0 mfn !  0 dba ! 384 fex ! 3 pos ! 384 fin ! 940 aud !
384 psi !   0 num !  0 pre !   0 seq ! 384 dex ! DeVocab InNativate

( 944: 390=WENN  "if" conj. essential for logic; 26nov2011 )
  945 t !  87 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ W
  946 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  947 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  948 t !  78 pho !  0 beg !   0 ctu ! 390 audpsi ! AudMem \ N
390 dnr !   0 mfn !  0 dba ! 390 fex ! 3 pos ! 390 fin ! 945 aud !
390 psi !   0 num !  0 pre !   0 seq ! 390 dex ! DeVocab InNativate

( 949: 791=WER "who" pronoun; dba nominative; 26nov2011 )
  950 t !  87 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ W
  951 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  952 t !  82 pho !  0 beg !   0 ctu ! 791 audpsi ! AudMem \ R
791 dnr !   0 mfn !  1 dba ! 791 fex ! 1 pos ! 791 fin ! 950 aud !
791 psi !   1 num !  0 pre !   0 seq ! 791 dex ! DeVocab InNativate

( 953: 791=WESSEN  "whose" pronoun; dba genitive; 20nov2012 )
  954 t !  87 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ W
  955 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  956 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  957 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  958 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  959 t !  78 pho !  0 beg !   0 ctu ! 791 audpsi ! AudMem \ R
791 dnr !   0 mfn !  2 dba ! 791 fex ! 1 pos ! 791 fin ! 954 aud !
791 psi !   1 num !  0 pre !   0 seq ! 791 dex ! DeVocab InNativate

( 960: 791=WEM "to whom" interrogative pronoun; dba dative 20nov2012 )
  961 t !  87 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ W
  962 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  963 t !  77 pho !  0 beg !   0 ctu ! 791 audpsi ! AudMem \ M
791 dnr !   0 mfn !  3 dba ! 791 fex ! 1 pos ! 791 fin ! 961 aud !
791 psi !   1 num !  0 pre !   0 seq ! 791 dex ! DeVocab InNativate

( 964: 791=WEN "whom" interrogative pronoun dba accusative 20nov2012 )
  965 t !  87 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ W
  966 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  967 t !  78 pho !  0 beg !   0 ctu ! 791 audpsi ! AudMem \ N
791 dnr !   0 mfn !  4 dba ! 791 fex ! 1 pos ! 791 fin ! 965 aud !
791 psi !   1 num !  0 pre !   0 seq ! 791 dex ! DeVocab InNativate

( 968: 880=WERDEN  "become" verb; irregular; 27nov2011 )
  969 t !  87 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ W
  970 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  971 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
  972 t !  68 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ D
  973 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  974 t !  78 pho !  0 beg !   0 ctu ! 880 audpsi ! AudMem \ N
880 dnr !   0 mfn !  0 dba ! 880 fex ! 8 pos ! 880 fin ! 969 aud !
880 psi !   0 num !  0 pre !  0 seq ! 880 dex ! DeVocab InNativate

( 975: 731=WIR  "we" pronoun; nom. familiar plural; 20nov2012 )
  976 t !  87 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ W
  977 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  978 t !  82 pho !  0 beg !   0 ctu ! 731 audpsi ! AudMem \ R
731 dnr !   0 mfn !  1 dba ! 731 fex ! 1 pos ! 737 fin ! 976 aud !
731 psi !   2 num !  0 pre !   0 seq ! 731 dex ! DeVocab InNativate

( 979: 731=UNSER  "of us" fam. pl. prounoun; dba genitive; 20nov2012 )
  980 t !  85 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ U
  981 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  982 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  983 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  984 t !  82 pho !  0 beg !   0 ctu ! 731 audpsi ! AudMem \ R
731 dnr !   0 mfn !  2 dba ! 731 fex ! 7 pos ! 737 fin ! 980 aud !
731 psi !   2 num !  0 pre !   0 seq ! 731 dex ! DeVocab InNativate

( 985: 731=UNS  "to us" pronoun; plural dative  20nov2012 )
  986 t ! 85 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ U
  987 t ! 78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  988 t ! 83 pho !  0 beg !   0 ctu ! 731 audpsi ! AudMem \ S
 731 dnr ! 0 mfn !  3 dba ! 731 fex ! 7 pos ! 737 fin ! 986 aud !
 731 psi ! 2 num !  0 pre !   0 seq ! 731 dex ! DeVocab InNativate

( 989: 731=UNS  "us" pronoun; plural acc.  20nov2012 )
  990 t ! 85 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ U
  991 t ! 78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
  992 t ! 83 pho !  0 beg !   0 ctu ! 713 audpsi ! AudMem \ S
 731 dnr ! 0 mfn !  4 dba ! 731 fex !  7 pos ! 737 fin ! 990 aud !
 731 psi ! 2 num !  0 pre !   0 seq ! 731 dex ! DeVocab InNativate

( 993: 890=WISSEN  "know" verb; irregular; 27nov2011 )
  994 t !  87 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ W
  995 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
  996 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  997 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
  998 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
  999 t !  78 pho !  0 beg !   0 ctu ! 890 audpsi ! AudMem \ N
890 dnr !   0 mfn !  0 dba ! 890 fex ! 8 pos ! 890 fin ! 994 aud !
890 psi !   0 num !  0 pre !   0 seq ! 890 dex ! DeVocab InNativate

( 1000: 890=WEISS "know" verb irreg. 1st pers. sing. 14dec2011 )
 1001 t !  87 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ W
 1002 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
 1003 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
 1004 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
 1005 t !  83 pho !  0 beg !   0 ctu ! 890 audpsi ! AudMem \ S
890 dnr !   0 mfn !  1 dba ! 890 fex ! 8 pos ! 890 fin ! 1001 aud !
890 psi !   1 num !  0 pre !   0 seq ! 890 dex ! DeVocab InNativate

( 1006: 890=WEISST "know" verb irreg. 2nd pers. sing. 14dec2011 )
 1007 t !  87 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ W
 1008 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
 1009 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
 1010 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
 1011 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
 1012 t !  84 pho !  0 beg !   0 ctu ! 890 audpsi ! AudMem \ T
890 dnr !   0 mfn !  2 dba ! 890 fex ! 8 pos ! 890 fin ! 1007 aud !
890 psi !   1 num !  0 pre !   0 seq ! 890 dex ! DeVocab InNativate

( 1013: 890=WEISS "know" verb irreg. 3rd pers. sing. 14dec2011 )
 1014 t !  87 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ W
 1015 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
 1016 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
 1017 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
 1018 t !  83 pho !  0 beg !   0 ctu ! 890 audpsi ! AudMem \ S
890 dnr !   0 mfn !  3 dba ! 890 fex ! 8 pos ! 890 fin ! 1014 aud !
890 psi !   1 num !  0 pre !   0 seq ! 890 dex ! DeVocab InNativate

( 1019: 290=WOHL  "probably" adverb; idiomatically valuable )
 1020 t !  87 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ W
 1021 t !  79 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ O
 1022 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
 1023 t !  76 pho !  0 beg !   0 ctu ! 290 audpsi ! AudMem \ L
290 dnr !   0 mfn !  0 dba ! 290 fex ! 2 pos ! 290 fin ! 1020 aud !
290 psi !   0 num !  0 pre !   0 seq ! 290 dex ! DeVocab InNativate

( 1024: 596=ZEUG  "stuff" noun; neuter; 14dec2011 )
 1025 t !  90 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ Z
 1026 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
 1027 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
 1028 t !  71 pho !  0 beg !   0 ctu ! 596 audpsi ! AudMem \ G
596 dnr !   3 mfn !  1 dba ! 596 fex ! 5 pos ! 596 fin ! 1025 aud !
596 psi !   1 num !  0 pre !   0 seq ! 596 dex ! DeVocab InNativate

( 1029: 691=ZU  "to" infinitive; 26nov2011 )
 1030 t !  90 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ Z
 1031 t !  85 pho !  0 beg !   0 ctu ! 691 audpsi ! AudMem \ U
691 dnr !   3 mfn !  4 dba ! 691 fex ! 6 pos  ! 691 fin ! 1030 aud !
691 psi !   1 num !  0 pre !   0 seq ! 691 dex ! DeVocab InNativate

( 1032: 701=ICH "I" pronoun; for SelfReferential thought; 19nov2012 )
 1033 t ! 73 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ I
 1034 t ! 67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
 1035 t ! 72 pho !  0 beg !   0 ctu ! 701 audpsi ! AudMem \ H
 701 dnr ! 0 mfn !  1 dba ! 701 fex !  7 pos ! 707 fin ! 1033 aud !
 701 psi ! 1 num !  0 pre ! 1039 tqv ! 800 seq ! 701 dex !
 DeVocab InNativate 0 jux !    0 tqv ! \ reset 28nov2012

( 1036: 800=BIN  "am" verb irreg. 1st pers. sing. 18nov2012 )
 1037 t !  66 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ B
 1038 t !  73 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ I
 1039 t !  78 pho !  0 beg !  0 ctu ! 800 audpsi ! AudMem \ N
800 dnr !   0 mfn ! 1 dba ! 800 fex ! 8 pos ! 800 fin ! 1037 aud !
800 psi !   1 num !  0 pre ! 1045 tqv ! 591 seq ! 800 dex !
 DeVocab InNativate  0 jux !    0 tqv ! \ reset 28nov2012

( 1040: 591=WOTAN  noun; name of the German AI; 27nov2011 )
 1041 t !  87 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ W
 1042 t !  79 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ O
 1043 t !  84 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ T
 1044 t !  65 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ A
 1045 t !  78 pho !  0 beg !  0 ctu ! 591 audpsi ! AudMem \ N
591 dnr !   1 mfn ! 1 dba ! 591 fex ! 5 pos ! 591 fin ! 1041 aud !
591 psi !   1 num !  0 pre !  0 seq ! 591 dex ! DeVocab InNativate

( 1046: 701=ICH "I" pronoun; for SelfReferential thought; 19nov2012 )
 1047 t ! 73 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ I
 1048 t ! 67 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ C
 1049 t ! 72 pho !  0 beg !  0 ctu ! 701 audpsi ! AudMem \ H
 1050 dnr ! 0 mfn !  1 dba ! 701 fex !  7 pos ! 707 fin ! 1047 aud !
 1051 psi ! 1 num !  0 pre ! 1055 tqv ! 800 seq ! 701 dex !
 DeVocab InNativate  0 jux !    0 tqv ! \ reset 28nov2012

( 1052: 800=BIN  "am" verb irreg. 1st pers. sing. 18nov2012 )
 1053 t !  66 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ B
 1054 t !  73 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ I
 1055 t !  78 pho !  0 beg !  0 ctu ! 800 audpsi ! AudMem \ N
800 dnr !   0 mfn ! 1 dba ! 800 fex ! 8 pos ! 800 fin ! 1053 aud !
800 psi !   1 num !  0 pre ! 1067 tqv ! 537 seq ! 800 dex !
 DeVocab InNativate  0 jux !    0 tqv ! \ reset 28nov2012

( 1056: 101=EINE  "a" article; dba nom. fem. sing. 18nov2012 )
 1057 t !  69 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ E
 1058 t !  73 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ I
 1059 t !  78 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ N
 1060 t !  69 pho !  0 beg !  0 ctu ! 101 audpsi ! AudMem \ E
101 dnr !   2 mfn ! 1 dba ! 101 fex ! 1 pos ! 101 fin ! 1057 aud !
101 psi !   1 num !  0 pre !  0 seq ! 101 dex ! DeVocab InNativate

( 1061: 537=PERSON  "person" noun; singular; 27nov2011 )
 1062 t !  80 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ P
 1063 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
 1064 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
 1065 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
 1066 t !  79 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ O
 1067 t !  78 pho !  0 beg !   0 ctu ! 537 audpsi ! AudMem \ N
537 dnr !   2 mfn !  1 dba ! 537 fex ! 5 pos ! 537 fin ! 1062 aud !
537 psi !   1 num !  0 pre !   0 seq ! 537 dex ! DeVocab InNativate

( 1068: 701=ICH "I" pronoun; for SelfReferential thought; 19nov2012 )
 1069 t ! 73 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ I
 1070 t ! 67 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ C
 1071 t ! 72 pho !  0 beg !  0 ctu ! 701 audpsi ! AudMem \ H
 701 dnr ! 0 mfn !  1 dba ! 701 fex !  7 pos ! 707 fin ! 1069 aud !
 701 psi ! 1 num !  0 pre ! 1079 tqv ! 860 seq ! 701 dex !
 DeVocab InNativate 0 jux !    0 tqv ! \ reset 28nov2012

( 1072: 860=SPRECHE  "speak" verb; irreg; 1st pers. sing. 21nov2012 )
 1073 t !  83 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ S
 1074 t !  80 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ P
 1075 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
 1076 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
 1077 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
 1078 t !  72 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ H
 1079 t !  69 pho !  0 beg !   0 ctu ! 860 audpsi ! AudMem \ E
860 dnr !   0 mfn !  1 dba ! 860 fex ! 8 pos ! 860 fin ! 1073 aud !
860 psi !   1 num !  0 pre ! 1087 tqv ! 507 seq ! 860 dex !
 DeVocab InNativate  0 jux !    0 tqv ! \ reset 28nov2012

( 1080: 507=DEUTSCH  "German" noun; the language; 1dec2011 )
 1081 t !  68 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ D
 1082 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
 1083 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
 1084 t !  84 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ T
 1085 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
 1086 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
 1087 t !  72 pho !  0 beg !   0 ctu ! 507 audpsi ! AudMem \ H
507 dnr !   3 mfn !  4 dba ! 507 fex ! 5 pos ! 507 fin ! 1081 aud !
507 psi !   1 num !  0 pre !   0 seq ! 507 dex ! DeVocab InNativate

( 1088: 707=DU  "you" pronoun, familiar, dba nom; 17nov2012 )
 1089 t !  68 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ D
 1090 t !  85 pho !  0 beg !  0 ctu ! 707 audpsi ! AudMem \ U
707 dnr !   0 mfn ! 1 dba ! 707 fex ! 7 pos ! 701 fin ! 1089 aud !
707 psi !   1 num !  0 pre ! 1095 tqv ! 800 seq ! 707 dex !
 DeVocab InNativate  0 jux !    0 tqv ! \ reset 28nov2012

( 1091: 800=BIST "are" verb irreg. 2nd pers. sing. 18nov2012 )
 1092 t !  66 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ B
 1093 t !  73 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ I
 1094 t !  83 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ S
 1095 t !  84 pho !  0 beg !  0 ctu ! 800 audpsi ! AudMem \ T
800 dnr !   0 mfn ! 2 dba ! 800 fex ! 8 pos ! 800 fin ! 1092 aud !
800 psi !   1 num !  0 pre ! 1106 tqv ! 535 seq ! 800 dex !
 DeVocab InNativate  0 jux !    0 tqv ! \ reset 28nov2012

( 1096: 101=EIN  "a" article; dba nom. masc. sing. 18nov2012 )
 1097 t !  69 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ E
 1098 t !  73 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ I
 1099 t !  78 pho !  0 beg !  0 ctu ! 101 audpsi ! AudMem \ N
101 dnr !   1 mfn ! 1 dba ! 101 fex ! 1 pos ! 101 fin ! 1097 aud !
101 psi !   1 num !  0 pre !  0 seq ! 101 dex ! DeVocab InNativate

( 1100: 535=MENSCH  "human being" noun; singular; 21nov2012 )
 1101 t !  77 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ M
 1102 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
 1103 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
 1104 t !  83 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ S
 1105 t !  67 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ C
 1106 t !  72 pho !  0 beg !   0 ctu ! 535 audpsi ! AudMem \ H
535 dnr !   1 mfn !  1 dba ! 535 fex ! 5 pos ! 535 fin ! 1101 aud !
535 psi !   1 num !  0 pre !  0 seq ! 535 dex ! DeVocab InNativate

( 1107: 525=KINDER  "children" noun; plural; 5dec2011; 11mar2013 )
 1108 t !  75 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ K
 1109 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
 1110 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
 1111 t !  68 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ D
 1112 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
 1113 t !  82 pho !  0 beg !   0 ctu ! 525 audpsi ! AudMem \ R
525 dnr !   3 mfn !  1 dba ! 525 fex ! 5 pos ! 525 fin ! 1108 aud !
525 psi !   2 num !  0 pre ! 1120 tqv ! 838 seq ! 525 dex !
 DeVocab InNativate  0 jux !    0 tqv ! \ reset 28nov2012

( 1114: 838=MACHEN  "do, make" verb; 27nov2011 )
 1115 t !  77 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ M
 1116 t !  65 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ A
 1117 t !  67 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ C
 1118 t !  72 pho !  0 beg !  1 ctu ! 838 audpsi ! AudMem \ H
 1119 t !  69 pho !  0 beg !  1 ctu ! 838 audpsi ! AudMem \ E
 1120 t !  78 pho !  0 beg !  0 ctu ! 838 audpsi ! AudMem \ N
838 dnr !   0 mfn !  3 dba ! 838 fex ! 8 pos ! 838 fin ! 1115 aud !
838 psi !   2 num !  0 pre ! 1128 tqv ! 571 seq ! 838 dex !
 DeVocab InNativate  0 jux !    0 tqv ! \ reset 28nov2012

( 1121: 571=ROBOTER  "robots" noun; plural; 23nov2012 )
 1122 t !  82 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ R
 1123 t !  79 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ O
 1124 t !  66 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ B
 1125 t !  79 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ O
 1126 t !  84 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ T
 1127 t !  69 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ E
 1128 t !  82 pho !  0 beg !  0 ctu ! 571 audpsi ! AudMem \ R
571 dnr !   0 mfn !  1 dba ! 571 fex ! 5 pos ! 571 fin ! 1122 aud !
571 psi !   2 num !  0 pre !  0 seq ! 571 dex ! DeVocab InNativate

( 1129: 571=ROBOTER  "robots" noun; plural; 23nov2012 )
 1130 t !  82 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ R
 1131 t !  79 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ O
 1132 t !  66 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ B
 1133 t !  79 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ O
 1134 t !  84 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ T
 1135 t !  69 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ E
 1136 t !  82 pho !  0 beg !  0 ctu ! 571 audpsi ! AudMem \ R
571 dnr !   0 mfn !  1 dba ! 571 fex ! 5 pos ! 571 fin ! 1130 aud !
571 psi !   2 num !  0 pre ! 1145 tqv ! 849 seq ! 571 dex !
 DeVocab InNativate  0 jux !    0 tqv ! \ reset 28nov2012

( 1137: 849=BRAUCHEN  "need" verb; 23nov2012 )
 1138 t !  66 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ B
 1139 t !  82 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ R
 1140 t !  65 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ A
 1141 t !  85 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ U
 1142 t !  67 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ C
 1143 t !  72 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ H
 1144 t !  69 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ E
 1145 t !  78 pho !  0 beg !  0 ctu ! 849 audpsi ! AudMem \ N
849 dnr !   0 mfn !  3 dba ! 849 fex ! 8 pos ! 849 fin ! 1138 aud !
849 psi !   2 num ! 571 pre ! 1150 tqv ! 701 seq ! 849 dex !
 DeVocab InNativate   0 jux !    0 tqv ! \ reset 28nov2012

( 1146: 701=MICH  "me" pronoun; sing. dba accusative; 25nov2012 )
 1147 t !  77 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ M
 1148 t !  73 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ I
 1149 t !  67 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ C
 1150 t !  72 pho !  0 beg !  0 ctu ! 701 audpsi ! AudMem \ H
701 dnr !   0 mfn ! 4 dba ! 701 fex ! 7 pos ! 707 fin ! 1147 aud !
701 psi !   1 num ! 849 pre !  0 seq ! 701 dex ! DeVocab InNativate

( 1151: 533=GOTT  "God" noun; singular; 23nov2012 )
 1152 t !  71 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ G
 1153 t !  79 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ O
 1154 t !  84 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ T
 1155 t !  84 pho !  0 beg !  0 ctu ! 533 audpsi ! AudMem \ T
533 dnr !   1 mfn !  1 dba ! 533 fex ! 5 pos ! 533 fin ! 1152 aud !
533 psi !   1 num !  0 pre ! 1162 tqv ! 848 seq ! 533 dex !
 DeVocab InNativate  0 jux !    0 tqv ! \ reset 28nov2012

( 1156: 848=SPIELT "plays" 2nd pers. sing; 26jan2013 )
 1157 t !  83 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ S
 1158 t !  80 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ P
 1159 t !  73 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ I
 1160 t !  69 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ E
 1161 t !  76 pho !  0 beg !  1 ctu ! 848 audpsi ! AudMem \ L
 1162 t !  84 pho !  0 beg !  0 ctu ! 848 audpsi ! AudMem \ T
848 dnr ! 0 mfn ! 3 dba ! 250 jux ! 848 fex ! 8 pos ! 848 fin ! 1157 aud !
848 psi ! 1 num ! 533 pre ! 1176 tqv ! 577 seq ! 848 dex !
 DeVocab InNativate 0 jux !    0 tqv ! \ reset 28nov2012

( 1163: 250=NICHT  "not"  adverb for negation; 21nov2012 )
 1164 t !  78 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ N
 1165 t !  73 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ I
 1166 t !  67 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ C
 1167 t !  72 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ H
 1168 t !  84 pho !  0 beg !  0 ctu ! 250 audpsi ! AudMem \ T
250 dnr !   0 mfn !  0 dba ! 250 fex ! 2 pos ! 250 fin ! 1164 aud !
250 psi !   0 num !  0 pre !  0 seq ! 250 dex ! DeVocab InNativate

( 1169: 577=WUERFEL  "dice" noun; plural; 21nov2012 )
 1170 t !  87 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ W
 1171 t !  85 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ U
 1172 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
 1173 t !  82 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ R
 1174 t !  70 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ F
 1175 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
 1176 t !  76 pho !  0 beg !   0 ctu ! 577 audpsi ! AudMem \ L
577 dnr !   0 mfn !  4 dba ! 577 fex ! 5 pos ! 577 fin ! 1170 aud !
577 psi !   2 num ! 848 pre !  0 seq ! 577 dex ! DeVocab InNativate

( 1177 543=MAENNER  "men" noun; plural; nom. 31jan2013 )
 1178 t !  77 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ M
 1179 t !  65 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ A
 1180 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
 1181 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
 1182 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
 1183 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
 1184 t !  82 pho !  0 beg !   0 ctu ! 543 audpsi ! AudMem \ R
543 dnr !   1 mfn !  1 dba ! 543 fex ! 5 pos ! 543 fin ! 1178 aud !
543 psi !   2 num !  0 pre ! 1193 tqv ! 888 seq ! 543 dex !
DeVocab InNativate   0 jux !    0 tqv ! \ reset 26jan2013

( 1185: 888=ARBEITEN  "work" verb; 26jan2013 )
 1186 t !  65 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ A
 1187 t !  82 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ R
 1188 t !  66 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ B
 1189 t !  69 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ E
 1190 t !  73 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ I
 1191 t !  84 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ T
 1192 t !  69 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ E
 1193 t !  78 pho !  0 beg !  0 ctu ! 888 audpsi ! AudMem \ N
888 dnr !   0 mfn !  3 dba ! 888 fex ! 8 pos ! 888 fin ! 1186 aud !
888 psi !   2 num ! 543 pre ! 0 tqv ! 0 seq ! 888 dex !
 DeVocab InNativate   0 jux ! 0 tqv ! \ reset 26jan2013

( 1194: 515=FRAUEN  "women" noun; plural; 31jan2013 )
 1195 t !  70 pho !  1 beg !    1 ctu !   0 audpsi ! AudMem \ F
 1196 t !  82 pho !  0 beg !    1 ctu !   0 audpsi ! AudMem \ R
 1197 t !  65 pho !  0 beg !    1 ctu !   0 audpsi ! AudMem \ A
 1198 t !  85 pho !  0 beg !    1 ctu !   0 audpsi ! AudMem \ U
 1199 t !  69 pho !  0 beg !    1 ctu !   0 audpsi ! AudMem \ E
 1200 t !  78 pho !  0 beg !    0 ctu ! 515 audpsi ! AudMem \ N
515 dnr !   2 mfn !  1 dba !  515 fex ! 5 pos ! 515 fin ! 1195 aud !
515 psi !   2 num !  0 pre ! 1206 tqv ! 810 seq ! 515 dex !
DeVocab InNativate   0 jux ! 0 tqv ! \ reset 26jan2013

( 1201: 810=HABEN  "have" irregular verb; 31jan2013 )
 1202 t !  72 pho !   1 beg !    1 ctu !   0 audpsi ! AudMem \ H
 1203 t !  65 pho !   0 beg !    1 ctu !   0 audpsi ! AudMem \ A
 1204 t !  66 pho !   0 beg !    1 ctu !   0 audpsi ! AudMem \ B
 1205 t !  69 pho !   0 beg !    1 ctu !   0 audpsi ! AudMem \ E
 1206 t !  78 pho !   0 beg !    0 ctu ! 810 audpsi ! AudMem \ N
810 dnr !   0 mfn !   3 dba !  810 fex ! 8 pos ! 810 fin ! 1202 aud !
810 psi !   2 num ! 515 pre ! 1215 tqv ! 525 seq ! 810 dex !
DeVocab InNativate  0 jux !    0 tqv ! \ reset 26jan2013

( 1207: 101=EIN  "a" article; dba acc. neuter. sing. 26jan2013 )
 1208 t !  69 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ E
 1209 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
 1210 t !  78 pho !  0 beg !   0 ctu ! 101 audpsi ! AudMem \ N
101 dnr !   3 mfn !  4 dba ! 101 fex ! 1 pos  ! 101 fin ! 1208 aud !
101 psi !   1 num !  0 pre !   0 seq ! 101 dex ! DeVocab InNativate

( 1211: 525=KIND  "child" noun; acc. neuter singular; 26jan2013 )
 1212 t !  75 pho !   1 beg !   1 ctu !   0 audpsi ! AudMem \ K
 1213 t !  73 pho !   0 beg !   1 ctu !   0 audpsi ! AudMem \ I
 1214 t !  78 pho !   0 beg !   1 ctu !   0 audpsi ! AudMem \ N
 1215 t !  68 pho !   0 beg !   0 ctu ! 525 audpsi ! AudMem \ D
525 dnr !   3 mfn !   4 dba ! 525 fex ! 5 pos ! 525 fin ! 1212 aud !
525 psi !   1 num ! 810 pre !   0 seq ! 525 dex ! DeVocab InNativate
```

### Rationale ###

The German-speaking artificial intelligence DeKi contains just
enough German words to demonstrate and engage in four kinds of thought:
  1. positive transitive ideas ("Kleider machen Leute");
  1. negated transitive ideas ("Roboter essen nicht Fleisch");
  1. positive be-verb statements ("Ich bin Wotan");
  1. negated be-verb statements ("Der Mann ist nicht ein Spion").

Some of the German words are included as examples of parts of speech which the AI Mind may not yet use for thinking, but which are likely to be needed in due course as the AI is enlarged and improved. Other words are included for testing purposes and for their potential in the areas of machine reasoning and logic.

Although these words have been selected from German word frequency lists found on the Internet, the innate vocabulary of the AI Mind
is not automatically a list of the most frequent German words. The primitive AI may not be ready to make use of some very frequent words on the one hand, and on the other hand the AI may contain words like "ROBOTER" which may be relatively rare but germane to the science of artificial intelligence.

### Evolution ###

The vocabulary of the German-speaking artificial intelligence Wotan may be expected to increase and grow in several ways. Initially the AI programmers will add new words as needed for the implementation of new AI functionality. Human users will teach the AI new words during each session of running the AI software, but the AI will not remember words taught to it from session to session, unless an AI Mind installation is made to store files of knowledge gained, or unless the AI coders and maintainers notice important words which ought to be added to the innate vocabulary of the AI. Eventually there should be an attempt automatically to include the entire German lexicon in every session of running the AI Mind. At that point, the AI will comprehend user input much better and without the confusion that results when the AI does not know, for example, whether an incoming word is a noun or an adjective.

### Expansion ###

Expanding the DeBoot sequence involves various considerations.
  * Recalculating the time "t" values;
  * Re-designating the "aud" values;
  * Entering the correct ASCII character numbers;
  * Changing the declared "vault" value;
  * Entering new data for vault-dependent code;
  * Incrementing value of "den" at end of DeBoot.


### Resources ###

  * http://ai.neocities.org

  * http://ai.neocities.org/DeKi.txt

  * http://ai.neocities.org/untertan.html

  * http://de.wikipedia.org/wiki/Cyc

  * http://groups.google.com/group/de.sci.informatik.ki

  * http://home.planet.nl/~josv/w32for42_671.exe

  * http://mind.sourceforge.net/enboot.html

  * http://prdownloads.sourceforge.net/win32forth/W32FOR42_671.zip?download

  * http://store.kagi.com/cgi-bin/store.cgi?storeID=AMP_Live¤cy=USD

  * http://www.amazon.com/dp/B00GX2B8F0

  * http://www.amazon.de/dp/B00GX2B8F0

  * http://www.amazon.de/exec/obidos/ASIN/0595259227/

  * http://www.dfki.de

  * http://www.nlg-wiki.org/systems/Wotan

  * http://www.ofai.at

  * http://www.ranks.nl/stopwords/german.html

### Memespace ###

[AiApp](http://cyborg.blogspot.com/2011/01/aiapp.html) [AiForum](http://www.ai-forum.org/topic.asp?forum_id=1&topic_id=8385) [AiMind](http://ai.neocities.org/AiMind.html) AskUser BrainTheory ChangeLog [ChatBots](http://www.chatbots.org/ai_zone/viewthread/240/) CognitiveArchitecture
[CognitiveAtlas](http://cognitiveatlas.org) CognitiveAtlas ConSciousness [CybOrg](http://cyborg.blogspot.com) DeFault [DeKiManual](http://ai.neocities.org/untertan.html) DfKi DisAmbiguation EnBoot [GermanAi](http://ai.neocities.org) [HackerSpaces](http://hackerspaces.org/wiki/) InFerence IntelForth KbRetro KbSearch [LinuxAi](http://cyborg.blogspot.com/2009/11/linux.html) MainLoop [MakerBot](http://www.makerbot.com) MasPar MfPj NumBer OpenCog ReJuvenate [RentaCoder](http://www.rentacoder.com) [RussianAi](http://ai.neocities.org/Dushka.html) [ScienceMuseum](http://cyborg.blogspot.com/2009/09/sciencemuseum.html)
SensoryInput [SiteSucker](http://www.sitesucker.us) SpeechAct [SpeechApi](http://www.speechapi.com) SpreadAct SpreadingActivation [StopWords](http://solartz.de/649/deutsche-stopwords.htm) StrongAi SubConscious SuperComputer SuperIntelligence [TechnoRati](http://technorati.com) [TechnoSingularity](http://cyborg.blogspot.com/2009/08/singularity.html)
[TextBook](http://www.chatbots.org/book/ai4u/) [TrustMetric](http://cyborg.blogspot.com/2009/10/trustmetric.html) UnterTan VisRecog [WikiReader](http://thewikireader.com)

### AI in German ###

Click to read

[![](http://ecx.images-amazon.com/images/I/41IxawpIOEL._AA160_.jpg)](http://www.amazon.com/dp/B00GX2B8F0)

AI in German

**Table of Contents**
