MileStones SuperIntelligence ThInk
### Theory ###

The Mentifex AI Minds began to incorporate [inference](http://www.amazon.com/dp/B00FKJY1WY) in December of 2012, when it became clear that the AI could use two facts to create a third fact as a logical [inference](http://www.amazon.com/dp/B00FKJY1WY) by replacing the subject of a general statement ("Birds have wings") with the subject of a specific statement ("An eagle is a bird") to create a silent [inference](http://www.amazon.com/dp/B00FKJY1WY): "Eagles have wings."

### Algorithm ###

MindForth uses the input of a BeVerb statement ("Boys are kids") to trigger the calling of the [InFerence](http://www.amazon.com/dp/B00FKJY1WY) module, which then changes the knowledge-base idea "Kids make robots" by replacing the general subject "Kids" with the specific subject "Boys" to infer, "Boys make robots."

### Code ###

```
: InFerence ( create silent triples for machine reasoning )
  CR ." InFer: subjnom prednom = " \ test; 18dec2012
  subjnom @ . prednom @ . CR \ test; 18dec2012
  midway @ t @ DO \ search IdeaPlex to infer facts; 18dec2012
    I 0 psi{ @ prednom @ = IF \ KB data? 18dec2012
      I 4 en{ @ 1 = IF \ nominative? 18dec2012
        seqverb @ 0 = IF \ only once; 18dec2012
          I 6 psi{ @ seqtqv ! \ transfer; 18dec2012
          I 7 psi{ @ seqverb ! \ transfer; 18dec2012
          seqverb @ seq ! \ test; 18dec2012
        THEN \ end of test for not-yet-declared; 18dec2012
        CR ." InFer: t psi seqverb = " \ test; 18dec2012
        I . prednom @ . seqverb @ . \ 18dec2012
      \ LEAVE \ at first make only one inference; 18dec2012
      THEN \ end of test for nominative; 18dec2012
    THEN \ end of test for finding prednom facts; 18dec2012
  -1 +LOOP \ end of backwards loop; 18dec2012
  1 t +! \ increment time "t" by one for a gap; 18dec2012
  1 t +! \ increment time to create an inference; 18dec2012
  subjnom @ t @ 0 psi{ ! \ subj of inference; 18dec2012
          5 t @ 5 psi{ ! \ pos=5 noun; 18dec2012
      \ 999 t @ 6 psi{ ! \ test; remove; 18dec2012
   t @ 1 + t @ 6 psi{ ! \ psi6=tqv; 18dec2012 
  CR ." InferB: storing seqverb = " seqverb @ . \ 18dec2012 
  seqverb @ t @ 7 psi{ ! \ seq is the verb; 18dec2012
  subjnom @ t @ 8 psi{ ! \ enx; 18dec2012
  1 t +! \ increment t for storage of verb; 18dec2012
  seqverb @ t @ 0 psi{ ! \ verb of inference; 18dec2012
  subjnom @ t @ 4 psi{ ! \ pre of verb; 18dec2012
          8 t @ 5 psi{ ! \ pos=8 verb; 18dec2012
        seqtqv @ 7 psi{ @ t @ 7 psi{ ! \ seq 18dec2012
  seqverb @ t @ 8 psi{ ! \ enx; 18dec2012 
  1 t +! \ increment t to store direct object; 18dec2012
  seqtqv @ 7 psi{ @ t @ 0 psi{ ! \ dir. obj 18dec2012
  seqtqv @ 7 psi{ @ t @ 8 psi{ ! \ enx 18dec2012 
  1 t +! \ increment time "t" for an ending gap; 18dec2012
  0 becon ! \ reset after use; 18dec2012
  0 prednom ! \ reset after use; 18dec2012
  0 seqtqv ! \ reset after use; 18dec2012
  0 subjnom ! \ reset after use; 18dec2012
\ QUIT \ test; remove; 18dec2012
; ( http://code.google.com/p/mindforth/wiki/InFerence )
```

### Report ###

```
 [the innate knowledge base KB about kids:]
583 : 528 -7 2 0 0 5 588 835 528 to KIDS
588 : 835 15 2 0 72 8 595 571 835 to MAKE
595 : 571 23 2 0 835 5 0 0 571 to ROBOTS
602 : 571 0 2 0 0 5 473 74 571 to ROBOTS
607 : 849 0 2 0 571 8 610 701 849 to NEED
610 : 701 0 1 0 849 7 0 0 701 to ME
  [three words of human input come in:]
617 : 589 16 1 0 0 5 621 800 589 to BOYS
621 : 800 0 1 0 589 8 626 528 800 to ARE
626 : 528 -15 2 0 589 5 0 0 528 to KIDS
  [AI creates an inference about boys:]
628 : 589 6 0 0 0 5 629 835 589 to BOYS
629 : 835 15 0 0 589 8 0 571 835 to MAKE
630 : 571 12 0 0 0 0 0 0 571 to ROBOTS
636 : 528 -13 2 0 0 5 641 835 528 to
641 : 835 -31 0 0 528 8 649 571 835 to MAKE
649 : 571 -15 2 0 528 5 0 0 571 to ROBOTS
time: psi act num jux pre pos tqv seq enx
```

### AI in German ###

[![](http://ecx.images-amazon.com/images/I/41IxawpIOEL._AA160_.jpg)](http://www.amazon.com/dp/B00GX2B8F0)

also uses inference. See chapter 18 in the free preview.

### Logic ###

Now that the [InFerence](http://www.amazon.com/dp/B00FKJY1WY) module exists, it may be expanded to incorporate logical operations such as if-then conditions.

### Superintelligence ###

Once the AI Minds like [MindForth](http://www.nlg-wiki.org/systems/Mind.Forth) in English, [Wotan](http://www.nlg-wiki.org/systems/Wotan) in German, and [Dushka](http://www.nlg-wiki.org/systems/Dushka) in Russian start to employ complex logic in the modules for [inference](http://www.amazon.com/dp/B00FKJY1WY), a speed-up and a smarten-up may begin to occur, culminating in SuperIntelligence.

### Wikipedia ###
  * http://en.wikipedia.org/wiki/Automated_reasoning
  * http://en.wikipedia.org/wiki/Inference_engine
  * http://en.wikipedia.org/wiki/Is-a
  * http://en.wikipedia.org/wiki/Logic
  * http://en.wikipedia.org/wiki/Reasoning
  * http://en.wikipedia.org/wiki/Syllogism

### Inference e-book -- click to read free preview ###

[![](http://ecx.images-amazon.com/images/I/419aG1Q4I9L._AA278_PIkin4,BottomRight,-51,22_AA300_SH20_OU15_.jpg)](http://www.amazon.com/dp/B00FKJY1WY)