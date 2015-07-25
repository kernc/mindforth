
```
( ki121129.F -- modification of ki121127.F German DeKi AI )
( May be named "DeKi.F" or any "Filename.F" you choose. )
( Rename any DeKi.F.txt as simply DeKi.F for Win32Forth. )
( http://home.planet.nl/~josv/w32for42_671.exe )
( http://prdownloads.sourceforge.net/win32forth/W32FOR42_671.zip?download )
( http://www.winzip.com/aboutzip.htm tells about WinZip. )
( Download and unzip W32FOR42_671.zip to run DeKi.F )
( http://code.google.com/p/mindforth )
( http://www.scn.org/~mentifex/DeKi.txt )
( http://www.scn.org/~mentifex/Dushka.html is Russian AI. )
( Run the AI with Win32Forth by issuing three commands: )
( win32for.exe [ENTER] )
( fload DeKi.F [ENTER] )
( MainLoop [ENTER]. )
( To halt the DeKi Mind, press the ESCAPE key at any time. )
( Ask or answer questions about the DeKiMind on Usenet. )
( http://groups.google.com/group/comp.ai.nat-lang )
( http://groups.google.com/group/comp.lang.forth )
( http://groups.google.com/group/de.comp.lang.forth )
( http://groups.google.com/group/de.sci.informatik.ki )
\ 15nov12A.F stubs in the VerbGen module for generating verbs.
\ ki121116.F copies 15nov2012A.F as the German Wotan AI Mind.
\ ki121117.F changes English names to Germanesque equivalents.
\ ki121118.F debugs AudMem & AudRecog to recognize verb-forms.
\ ki121119.F uses VerbGen to generate a needed German verb-form.
\ ki121120.F reorganizes the DeBoot German bootstrap sequence.
\ ki121121.F fixes DeBoot errors; uses parameters in KB talk.
\ ki121123.F uses negative logic to restrict output in VerbGen.
\ ki121124.F improves the question-asking and VerbGen modules.
\ ki121125.F improves assigning of "dba" parameter during input.
\ ki121126.F uses "audverb" to set "dba" for nouns after verbs.
\ ki121127.F does negation of German verbs in VerbPhrase module.
\ ki121129.F streamlines DeBoot; fixes bug in assigning "tqv".
DECIMAL  ( use decimal numbers )
variable abc  ( AudBuffer transfer character; 8nov2012 )
variable act 0 act ! ( activation level  )
variable actbase ( AudRecog discrimination activation base)
variable actran  ( PsiDecay holder of act-levels; 16may2011 )
variable adverbact 0 adverbact ! ( 29aug2008 adverb test )
variable adjcon  ( insert-adjective condition-flag; 16sep2011 )
variable aftjux  ( after-jux for negation of verb of being ) 
variable anset  ( Before vowel set article AN insertion ) 
variable atcd  ( "antecedent" for DePronoun; 17nov2012 )
variable aud  ( auditory recall-tag for activating engrams)
variable audbase  ( recall-vector for VerbGen;  8nov2012 )
variable audjuste ( NounPhrase motjuste aud to SpeechAct )
variable audme  ( tag to find "ME" in auditory memory )
variable audnum  ( de-globalizing the "num" variable; 8nov2012 )
variable audpsi  ( de-globalizing the "psi" variable )
variable audrec  ( 6may2009 replacing "psi" in AudRecog )
variable audrun 1 audrun ! ( counter of loops through AudRecog )
variable audstop  ( flag to stop SpeechAct after one word )
variable audverb  ( psi number of an input verb; 26nov2012 )
variable b01  ( buffer character 01 in OutBuffer; 12nov2012 )
variable b02  ( buffer character 02 in OutBuffer; 12nov2012 )
variable b03  ( buffer character 03 in OutBuffer; 12nov2012 )
variable b04  ( buffer character 04 in OutBuffer; 12nov2012 )
variable b05  ( buffer character 05 in OutBuffer; 12nov2012 )
variable b06  ( buffer character 06 in OutBuffer; 12nov2012 )
variable b07  ( buffer character 07 in OutBuffer; 12nov2012 )
variable b08  ( buffer character 08 in OutBuffer; 12nov2012 )
variable b09  ( buffer character 09 in OutBuffer; 12nov2012 )
variable b10  ( buffer character 10 in OutBuffer; 12nov2012 )
variable b11  ( buffer character 11 in OutBuffer; 12nov2012 )
variable b12  ( buffer character 12 in OutBuffer; 12nov2012 )
variable b13  ( buffer character 13 in OutBuffer; 12nov2012 )
variable b14  ( buffer character 14 in OutBuffer; 12nov2012 )
variable b15  ( buffer character 15 in OutBuffer; 12nov2012 )
variable b16  ( buffer character 16 in OutBuffer; 12nov2012 )
variable bday ( day of birth reveals oldest living AI Mind)
variable beflag 0 beflag ! ( 23apr2009 for InStantiate )
variable beg  1 beg ! ( "beginning" flag for word engrams )
variable bhour ( hour of birth for user interface display )
variable bias 5 bias ! ( Parser; newConcept: expected POS )
variable binc  ( OutBuffer "b" increment for VerbGen 12nov2012 )
variable bminute ( minute of birth: user interface display)
variable bmonth ( month of birth: user interface display )
variable bsec ( second of birth: user interface display)
variable byear ( MainLoop; TuringTest HCI -- year of birth)
variable c01  ( character in AudBuffer; 12nov2012 )
variable c02  ( character in AudBuffer; 12nov2012 )
variable c03  ( character in AudBuffer; 12nov2012 )
variable c04  ( character in AudBuffer; 12nov2012 )
variable c05  ( character in AudBuffer; 12nov2012 )
variable c06  ( character in AudBuffer; 12nov2012 )
variable c07  ( character in AudBuffer; 12nov2012 )
variable c08  ( character in AudBuffer; 12nov2012 )
variable c09  ( character in AudBuffer; 12nov2012 )
variable c10  ( character in AudBuffer; 12nov2012 )
variable c11  ( character in AudBuffer; 12nov2012 )
variable c12  ( character in AudBuffer; 12nov2012 )
variable c13  ( character in AudBuffer; 12nov2012 )
variable c14  ( character in AudBuffer; 12nov2012 )
variable c15  ( character in AudBuffer; 12nov2012 )
variable c16  ( character in AudBuffer; 12nov2012 )
variable caller  ( debug-identifier of calling module )
variable cns  2048 cns ! ( MindGrid size; doubled 3aug2012 )
variable coda  128 coda ! ( memory recycled in ReJuvenate)
variable cognum  ( grammatical number of cogpsi; 22oct2011 )
variable cogpsi  ( new noun being learned; 17oct2011 )
variable conj  ( OldConcept; ConJoin: conjunction )
variable ctu ( continuation-flag for "Aud" array phonemes )
variable dba ( case for nouns; person for verbs; 8nov2012 )
variable de8 ( DeVocab recall-vector "aud" in Rejuvenate )
variable defact ( default activation for NounPhrase; 9oct2011 )
variable defartcon ( set definite article condition )
variable dex ( holds concept-number in transfer to German 16nov2012 )
variable dirobj  ( indicates seeking for a direct object )
variable dnr 0 dnr ! ( German lexical concept number 16nov2012 ) 
variable dopsi  ( direct-object-psi to calculate "thotnum")
variable edge  0 edge ! ( Rejuvenate: edge-of-thought flag)
variable eot ( end-of-text for use in AudInput )
variable fex ( holds fiber-out concept up from Psi memory )
variable fin ( holds fiber-in concept for Psi array access)
variable firstword ( for identifying input of a query 19aug2011 )
variable flex1  ( "I" or "S" element of SpeechAct inflection )
variable flex2  ( "N" as part of "ING" SpeechAct inflection )
variable flex3  ( "G" as part of "ING" SpeechAct inflection )
variable fyi 0 fyi ! ( rotates through display modalities )
variable fyipsi  ( psi source-node in SpreadAct; 17oct2011 )
variable gencon ( VerbGen status flag; 19nov2012 )
variable ghost 0 ghost ! ( to switch from "a" to "the" )
variable glot 2 glot ! ( flag for which language to think in )
variable greet 640 greet ! ( greeting-trigger; 16oct2010 )
variable guspsi  ( concept-tag attached to taste-memories )
variable gusrec  ( for external recognition by GusRecog )
variable hipsi   ( "high-psi" tag on wavecrest concept )
variable hl ( possible standard instead of "glot"; 20aug2011 )
variable holdnum  ( transfer from subject to verb;  8nov2012 )
( I = Index in loops; does not require a fetch "@" )
variable img  ( visRecog: for future use as "image" )
variable indefartcon ( set indefinite article condition )
variable indefmust ( force saying of "A" or "AN"; 20oct2011 )
variable inert  0 inert ! ( marker of no recent interaction )
variable instnum  ( instantiation number for WhatBe questions )
variable IQ 1 IQ ! ( an invitation to code an IQ algorithm) 
variable jrt ( ReJuvenate "junior time" for memories moved)
variable jux  0 jux ! ( holds Psi # of a JUXtaposed word )
variable kbcon  ( flag for awaiting a yes-or-no answer 2jul2011 )
variable kbpsi  ( 20jan2008 an interim knowledge-base psi )
variable kbquiz 0 kbquiz !  ( flag to call kbSearch )
variable kbtv  0 kbtv !  ( KbTraversal trigger; 7aug2010 )
variable kbtqv  ( time of seq-concept found in KB; 7oct0211 )
variable kbyn  ( holds kbtv values for asking Y/N 24jun2011 ) 
variable kibosh  ( suppresses concepts failing to win selection )
variable krt ( Knowledge Representation time "t" for later)
variable lastpho  ( 24may2009 to avoid extra "S" on verbs )
variable lastword  0 lastword !  ( for zeroing "seq" tags.)
variable len  ( length, for avoiding non-words in AudInput)
variable lexact  ( testing a lexical "act" for DeReify )
variable lopsi  ( "low-psi" tag on just-crested concept )
variable lurk ( counter to activate initial thinking; 19sep2010 )
variable match  ( end-of-word flag for control ) 
variable memoire  ( instead of "motjuste" in kbSearch )
variable mfn  ( "masculine feminine neuter" gender flag )
variable mfnflag ( gender flag to cause a who-query; 17aug2010 )
variable midway 1 midway ! ( limit for searching backwards)
variable monopsi ( 26jul2002 For use in audRecog module )
variable moot  ( flag to prevent associations in DO-queries )
variable morphpsi ( for audRecog recognition of morphemes )
variable motjuste ( best word for inclusion in a thought )
variable nacpsi   ( 9may2009 de-globalized psi for NounAct)
variable negjux  ( flag for 12=NOT juxtaposed to a verb; 9oct2011 )
variable nen  0 nen ! ( English lexical concept number )
variable newpsi   ( for singular-nounstem assignments ) 
variable nlt  0 nlt !  ( not-later-than among time-points )
variable nounlock ( for a verb to lock onto a seq-nounl 8oct2011 )
variable nounval 0 nounval ! ( from NounPhrase to MounAct )
variable nphrnum 0 nphrnum ! ( NounPhrase number )
variable nphrpos 0 nphrpos ! ( for testing in DeCog; 17nov2012 )
variable num 0 num !  ( number-flag for the psi array )
variable numflag ( 4dec2009 for selection of verb-forms )
variable numsubj ( 13apr2010 for number of subject )
variable nwc    ( new-word-count for noun-stem recog )
variable objold  ( a test for optimizing slosh-over; 12oct2010 )
variable obstat ( Lets AudInput psi-damp a reentrant word.)
variable ocn  ( old-concept-number for EnVocab; 14oct2011 )
variable oldact ( show the source of spreading activations)
variable oldpos ( old part-of-speech for use with verbs )
variable oldpsi ( used in OldConcept to de-globalize "psi")
variable olfpsi ( concept-tag attached to smells in memory)
variable olfrec ( for external recognition by OlfRecog )
variable onset 0 onset ! ( of an auditory memory engram )
variable opt  ( option, for flushing out a part of speech )
variable ordo 0 ordo ! ( from JSAI; AudInput word-order )
variable pcn ( predicate concept number; 17jul2012 )
variable penultpho  ( 17may2009 next-to-last phoneme )
variable pho ( phoneme of input/output & internal reentry ) 
variable phodex  0 phodex ! ( pho-index for AudBuffer 14nov2012 )
variable pos  ( old- & newConcept; enVocab: part-of-speech)
variable pov  ( point-of-view: #35 internal; *42 external )
variable prc  ( provisional recognition in AudRecog; 18nov2012 )
variable pre ( previous concept associated with a concept )
variable precand  ( inviolate "pre" candidate from JSAI )
variable predflag ( indicates predicate nominative 11sep2010 )
variable predpos 0 predpos ! ( Predicate part of speech )
variable prejux  ( previous jux to carry NOT to verb 21jul2011 )
variable prepho   ( 17may2009 previous phoneme )
variable prepsi ( synaptic deglobalized "pre" in SpreadAct)
variable preset 0 preset ! ( for setting InStantiate "pre")
variable prevtag  ( from JSAI; for use in InStantiate )
variable prox1  ( first proximate concept of input cluster )
variable prox2  ( for determining association among engrams )
variable prox3  ( for ReActivate to impose unequal activation )
variable proxcon  ( flag to indicate usage of prox variables )
variable prsn  0 prsn ! ( 1st, 2nd, 3rd person )
variable psi ( identifier of a psi concept in Psi mindcore)
variable psi1 ( activation-level at each node of verb )
variable psi3 0 psi3 ! ( for VerbPhrase to find negation 25jun2011 ) 
variable psi8 ( tutorial dex in tutorial or diagnostics; 17nov2012 )
variable psibase ( winning psibase with winning actbase )
variable putdbav ( putative dba for verbs; 25nov2012 )
variable putnum  ( putative number for subj-verb agreement )
variable questype  ( oldConcept; Conjoin: "question-type" )
variable quiet 1 quiet ! ( status flag for auditory input )
variable quo ( 27dec2009 query-object for EnCog response )
variable quobj ( query-object for yes-or-no questions 24jun2011 )
variable qup ( 28dec2009 query-predicate if verb not given )
variable qusub  ( internal provisional query-subject; 3oct2010 )
variable quverb  ( query-verb for yes-or-no questions 24jun2011 )
variable recnum  ( recognized number of a recognized word 19jul2011 )
variable retropsi   ( for AudInput and Audmem noun-stems )
variable residuum 0 residuum ! ( activation after PsiDamp )
variable rjc  0 rjc ! ( rejuvenation counter for tracking )
variable rsvp 1000 rsvp ! ( user-response delay-counter)
variable rv ( "recall-vector" for diagnostic display )
variable scn  ( subject concept number; 17jul2012 )
variable seq  ( subSEQuent concept associated with another)
variable seqneed  ( noun/pronoun or verb needed as a "seq" )
variable seqpos  ( "seq" concept part-of-sppeech 1oct2011 )
variable seqpsi ( synaptic deglobalized "seq" in SpreadAct)
variable singflag  ( singularity flag for singular nouns )
variable snu ( subject-number as parameter for verb-selection )
variable spacegap  ( to add gap of one space in SpeechAct )
variable spike  ( 1aug2005: for potential use in SpreadAct)
variable spt  ( AudMem; AudInput: blank space time )
variable stemgap  ( for avoiding false audRecog stems )
variable stempsi  ( for singular noun-stem recognition )
variable subj     ( flag to supercharge subject-nouns )
variable subjectflag  ( 3dec2009 a default for NounPhrase )
variable subjnum ( for agreement with predicate nominative )
variable subjold ( old subject as default candidate 28sep2010 )
variable subjpsi  ( parameter to govern person of verb-forms )
variable sublen   ( length of audRecog subpsi word-stem )
variable subpsi ( for AudRecog of sub-component wordstems )
variable supsi    ( subject-psi for calculating "thotnum" )
variable svo2  ( second item among subj-verb-obj; 3sep2011 )
variable svo3  ( third item among subj-verb-obj; 28aug2011 )
variable t  0 t ! ( time incremented during AudMem storage)
variable t2s ( auditory text-to-speech index for SpeechAct)
variable tacpsi  ( concept-tag attached to tactile engrams)
variable tacrec   ( for external recognition by TacRecog )
variable tbev  ( time of be-verb for use with aftjux 27jul2011 )
variable tdzw ( time deutsches Zeitwort for negation 27nov2012 )
variable tkbn  ( time of KbRetro noun adjustment; 2jul2011 )
variable tkbv  ( time of KbRetro verb adjustment; 2jul2011 )
variable topic  ( topic for a question to be asked )
variable topicnum ( grammatical number of question "topic" )
variable tov 1 tov ! ( time-of-voice for keeping track )
variable tpeg  ( pegging the time-slice of a subject-noun )
variable tqv  ( tempus quod vide for specific psi instance )
variable trc  ( 20dec2009 tabula-rasa-counter like rjc )
variable tsday    ( for AudListen transcript-mode headers )
variable tseln  ( time of selection of noun;  8may2011 )
variable tselo  ( time of selection of object 30jul2011 )
variable tsels  ( time of selection of subj. 28jul2011 )
variable tselv  ( time of selection of verb;  8may2011 )
variable tshour   ( AudListen )
variable tsminute ( AudListen )
variable tsmonth  ( AudListen )
variable tsn  ( time of seqneed for InStantiate;  1jul2012 )
variable tssecond ( AudListen )
variable tsyear   ( AudListen )
variable tult     ( t penultimate, or time-minus-one )
variable unk  ( "unknown" variable for general use ) 
variable upnext  ( Flag lets new input de-crest previous. )
variable urpre ( original pre during call to other module )
variable urpsi ( original psi for use in psiDamp, etc. )
variable vacpsi  ( de-globalized psi for VerbAct; 27sep2010 )
\ variable vault 944 vault ! ( size of DeBoot; 18nov2012 )
variable vault 1176 vault ! ( size of DeBoot; 20nov2012 )
variable vbpsi   ( verb-psi for calculating "thotnum" )
variable verblock ( for subject-noun to lock onto seq-verb; 8oct2011 )
variable verbpsi  ( for transit into WhatAuxSVerb 13jun2011 )
variable verbval  ( transfer from VerbPhrase to VerbAct )
variable vispsi ( concept-tag attached to images in memory)
variable visrec   ( for external recognition by VisRecog )
variable vphract  ( verb phrase activation level 19jun2011 )
variable vphraud  ( holds aud-fetch for SpeechAct; 25jun2011 )
variable vpos     ( verb part of speech for inflections )
variable vrsn 20121129 vrsn ! ( version identifier; 29nov2012 )
variable whoflag   0 whoflag !   ( for InStantiate )
variable wordend  ( for singular noun-stem assignments )
variable yesorno 0 yesorno ! ( in conjunction w. KbSearch )
variable yncon ( statuscon to trigger yes-or-no query 2jul2011 )
variable ynverb  ( yes-or-no verb for AskUser; 24jun2011 )
variable zone  ( time-zone for "pre" and "seq" searches )


:  CHANNEL   ( size num -< name >- )
  CREATE   ( Returns address of newly named channel. )
  OVER     ( #r #c -- #r #c #r )
  ,        ( Stores number of rows from stack to array.)
  * CELLS  ( Feeds product of columns * rows to ALLOT.)
  ALLOT    ( Reserves given quantity of cells for array.)
  DOES>    ( member; row col -- a-addr )
  DUP @    ( row col pfa #rows )
  ROT *    ( row pfa col-index )
  ROT +    ( pfa index )
  1 +      ( because first cell has the number of rows.)
  CELLS +  ( from number of items to # of bytes in offset )
;


cns @  9  CHANNEL  psi{  ( Mindcore concept array "psi" )
cns @  9  CHANNEL   de{  ( German lexical arrray "de" ) 
cns @  6  CHANNEL  aud{  ( Auditory memory channel "aud" )


:  PsiClear  ( set Psi activations to zero; 26sep2010 )
  1   t @  1 +  DO
    0 I 1 psi{ !
  -1 +LOOP
; ( End of PsiClear )


:  TabulaRasa
  0 trc !  ( 20dec2009 tabula-rasa-counter like jrc )
  1 tov !
  BEGIN  cns @  1  DO
    0 I  trc @  psi{ !
  LOOP
  1  trc +!
  trc @  9  <  WHILE  \ Cover 9 columns 0-8; 29sep2011
  REPEAT
  0 trc !
  1 tov !
  BEGIN  cns @  1  DO
    0 I  trc @   de{ !
  LOOP
  1  trc +!
  trc @ 9 < WHILE  \ Cover #0 to #8, i.e. 9; 10nov2012
  REPEAT
  0 trc !
  1 tov !
  BEGIN  cns @  1  DO
    0 I  trc @  aud{ !
  LOOP
  1  trc +!
  trc @  6  <  WHILE
  REPEAT
  cns @  1  DO
    32   I  0   aud{ !
  LOOP
; ( End of TabulaRasa )


\ NounClear is a mechanism called by NounPhrase to set
\ activation on nouns and pronouns to zero just before
\ a pair of old and new noun-engrams is reduced even
\ further into negative activation by neural inhibition.
\ The purpose is to prevent the build-up of stray activations.
:  NounClear ( remove activation from all nouns ) \ 20dec2009
  midway @  cns @  DO     \  Loop backwards over time.
    I 5 psi{ @ 5 = I 5 psi{ @ 7 = OR IF \ pro(noun) 18aug2011
      I     1 psi{ @ 0 > IF \ avoid inhibited engrams; 26aug2011
        0 I 1 psi{ !  \ 20dec2009 Set noun to zero activation.
      THEN  \ end of test for positive activation; 26aug2011
    THEN              \ 20dec2009 End of test for pos=5 nouns.
  -1  +LOOP  \  End of backwards loop looking for pos=5 nouns.
; ( End of NounClear; return to NounPhrase; 18aug2011 )


:  VerbClear ( remove activation from all verbs )
  midway @  t @  DO
    I     5 psi{ @ 8 = IF
      I     1 psi{ @ 0 > IF \ avoid inhibited engrams; 26aug2011
        0 I 1 psi{ !
      THEN  \ end of test for positive activation; 26aug2011
    THEN
  -1  +LOOP
;  ( End of VerbClear )


:  VerbClip ( lower activation on all verbs )
  midway @  t @  DO
    I     5 psi{ @ 8 = IF
      I   1 psi{ @ 12 > IF  \ test; REMOVE? 25aug2010
      6 I 1 psi{ +!   \ test; 25aug2010
      THEN
    THEN
  -1  +LOOP
; ( End of VerbClip; return to AudInput )


:  PsiDecay ( let conceptual activations dwindle )
  fyi @ 2 > IF CR
    ."       PsiDecay called to reduce all "
    ." conceptual activations." CR
  THEN
  midway @  t @  DO
    I    1 psi{ @ 0 > IF \ avoid inhibited nodes; 9sep2010
      I  1 psi{ @ 40 > IF  34 actran ! THEN  \  4aug2011
      I  1 psi{ @ 50 > IF  35 actran ! THEN  \  4aug2011
      I  1 psi{ @ 60 > IF  36 actran ! THEN  \  4aug2011
      I  1 psi{ @ 70 > IF  37 actran ! THEN  \  4aug2011
      I  1 psi{ @ 80 > IF  38 actran ! THEN  \  4aug2011
      I  1 psi{ @ 90 > IF  39 actran ! THEN  \  4aug2011
    actran @ 0 > IF actran @ I 1 psi{ ! THEN  \ 16may2011
      0 actran !  \ Reset to zero for safety; 16may2011
        I  1 psi{ @  1 -        I  1  psi{  !
    THEN  \ end of test to skip inhibited nodes; 9sep2010
    I  1  psi{ @  0 < IF  1  I  1  psi{ +! THEN  \ 6sep2010
    I  0  psi{ @ 830 = IF  0 I  1  psi{  ! THEN  \ 830=DO
    I  0  psi{ @ 781 = IF  0 I  1  psi{  ! THEN  \ 781=WHAT
    I  0  psi{ @ 117 = IF  0 I  1  psi{  ! THEN  \ 117=THE
  -1  +LOOP
; ( http://code.google.com/p/mindforth/wiki/PsiDecay )


:  PsiDamp ( reduce activation of a concept )
  ( 33-48 = consciousness tier where concepts win selection. )
  ( 17-32 = subconscious where concepts remain available. )
  (  1-16 = noise tier below logical association threshold. )
  16 residuum !
  fyi @ 2 > IF CR
  ."     PsiDamp called for urpsi = " urpsi @ .
  ."  by module ID #" caller @ .
  caller @  42 = IF ." WhatAuxSDo " THEN
  caller @  51 = IF ." AuxVerb "    THEN
  caller @  62 = IF ." VerbPhrase " THEN
  caller @  66 = IF ." NounPhrase " THEN
  caller @ 104 = IF ." AudInput "   THEN
  caller @ 148 = IF ." Activate "   THEN
  caller @ 3535 = IF ." AudInput "  THEN
  caller @ 6967 = IF ." DeCog "     THEN \ test; 17nov2012
  caller @ 8766 = IF ." WhoBe "     THEN \ test; 26sep2010
  caller @ 8773 = IF ." WhatBe "    THEN \ changed; 25feb2011
  0 caller !
  THEN
  urpsi @ 791 = IF  \ if urpsi is 791=WHO; 10nov2012
    1 residuum !   \ deemphasize WHO; test; 25jul2010
  THEN  \ test; 25jul2010
  ( code to prevent psi-damping inhibited concepts; 6sep2010 )
  midway @  t @  DO
            I  0  psi{ @ urpsi @ = IF \ concept found; 6sep2010
            I  1  psi{ @ -1 > IF  \ positive act.? 16aug2011
 residuum @ I  1  psi{ !  \ psi-damp only high activations
      THEN  \ end of test for only positive act.; 6sep2010
    THEN  \ end of test for particular concept; 6sep2010
  -1 +LOOP
  0 residuum ! 
; ( http://code.google.com/p/mindforth/wiki/PsiDamp )


:  DeDamp ( deactivate German lexicon concepts; 18nov2012 )
  midway @  t @  DO
    0 I  1  de{ !   \ 16nov2012
  -1 +LOOP
;  ( End of DeDamp; 18nov2012 )


:  AudDamp ( deactivate auditory engrams )
  midway @  t @  DO
    0 I  1 aud{ !
  -1 +LOOP
;  ( End of AudDamp )


:  .psi ( show concepts in the Psi array )
  CR  ." Psi mindcore concepts"
  CR  ." time: psi act num jux pre pos seq dex "
  t @ 1+  midway @ DO
    I    0  psi{ @ 0 > IF
      CR I . ." : "
      I  0  psi{ @ . ." "  \ concept-number; 19nov2012
      I  1  psi{ @ . ." "  \ activation level 19nov2012
      I  2  psi{ @ . ." "  \ number; 19nov2012
      I  3  psi{ @ . ." "  \ jux-taposed tag; 19nov2012
      I  4  psi{ @ . ." "  \ pre-vious assoc. 19nov2012
      I  5  psi{ @ . ." "  \ pos part-of-speech 19nov2012
      I  6  psi{ @ . ." "  \ tqv IdeaPlex anchor 19nov2012
      I  7  psi{ @ . ." "  \ SUBseqUENT concept 19nov2012
      I  8  psi{ @ dex ! dex @ .  \ new "dex"; 16nov2012
      dex @ 0 > IF   \ 16nov2012
        ." to "
        I unk !
        0 aud !
        midway @ unk @  DO
          I   0 de{ @  dex @ = IF
            I 8 de{ @  aud  !  \ with dba; 10nov2012
            aud @ 0= NOT IF
              BEGIN
                aud @ 0 aud{ @ EMIT
                1 aud +!
                aud @ 0 aud{ @ 32 =
              UNTIL
              ."  "
            THEN
            0 aud !
          LEAVE  ( One engrammed word is enough. )
          THEN
        -1  +LOOP
      THEN
    THEN
  LOOP
  CR ." time: psi act num jux pre pos tqv seq dex "  0 unk !
  CR ." You may enter .psi or .de or .aud to view memory "
  ." engrams or "  \ Using ".de" above; 17nov2012
  CR ." MainLoop [ENTER] to erase all memories "
  ." and restart the Mind."
  CR
;  ( End of .psi post-Escape report )


:  .de ( show vocabulary in the German lexicon array )
  CR ." German lexical fibers"  \ 19nov2011
  CR ." t dnr act num mfn dba fex pos fin aud:" \ 16nov2012
  t @  1+  midway @  DO
    I  0  de{ @  0 > IF  ( display positive data 24nov2011 )
      CR I .  \ Show Index as t=time point; 24nov2011
      I 0 de{ @ . ." "  \ dnr; 16nov2012
      I 1 de{ @ . ." "  \ act; 24nov2011
      I 2 de{ @ . ." "  \ num; 24nov2011
      I 3 de{ @ . ." "  \ mfn; 24nov2011
      I 4 de{ @ . ." "  \ dba; 24nov2011
      I 5 de{ @ . ." "  \ fex; 24nov2011
      I 6 de{ @ . ." "  \ pos; 24nov2011
      I 7 de{ @ . ." "  \ fin; 24nov2011
      I 8 de{ @ aud !  aud @ . ."  to "  \ aud; 24nov2011
      BEGIN
        aud @ 0 aud{ @ EMIT  1 aud +!
        aud @ 0 aud{ @ 32 =
      UNTIL
      ."  "
      0 aud !
    THEN
  LOOP
  0 unk !
  CR ." t dnr act num mfn dba fex pos fin aud" CR  \ 16nov2012
  CR ." You may enter .psi or .de or .aud to view memory "
  ." engrams or "
  CR ." MainLoop [ENTER] to erase all memories "
  ." and restart the DeKi."  \ 19nov2011
  CR
;  ( End of .de post-Escape report; 19nov2011 )


:  .aud ( show engrams in the auditory memory array )
  CR ." Auditory memory nodes"
  CR  ."  t pho act pov beg ctu audpsi"
  t @  1+  1 DO           ( Show the entire Aud channel.)
    CR    I . ." "
    I 2 aud{ @ 123  =  IF
      ."     { "
    THEN
    I 0 aud{ @  33  <  IF
      ."  "  ( show a blank )
    ELSE
      I 0 aud{ @ EMIT ."  "
      I 1 aud{ @ .     ." "
      I 2 aud{ @ EMIT ."  "
      I 3 aud{ @ .     ." "
      I 4 aud{ @ .     ." "
      I 5 aud{ @ .
    THEN
    I 2 aud{ @ 125  =  IF
      ."     } "
    THEN
    I cns @ > IF QUIT THEN  \ safety measure; 26jul2010
  LOOP
  CR ." You may enter .psi or .de or .aud to view memory "
  ." engrams or "  \ Changing to ".de" above; 17nov2012
  CR ." MainLoop [ENTER] to erase all memories "
  ." and restart the Mind."
  CR
;  ( End of .aud post-Escape report )


:  .out ( show characters in the OutBuffer; 12nov2012 )
  CR ." AudBuffer word = " CR  \ 15nov2012
  c01 @ EMIT  c02 @ EMIT  c03 @ EMIT  c04 @ EMIT
  c05 @ EMIT  c06 @ EMIT  c07 @ EMIT  c08 @ EMIT
  c09 @ EMIT  c10 @ EMIT  c11 @ EMIT  c12 @ EMIT
  c13 @ EMIT  c14 @ EMIT  c15 @ EMIT  c16 @ EMIT
  CR ." OutBuffer word = " CR  \ 14nov2012
  b01 @ EMIT  b02 @ EMIT  b03 @ EMIT  b04 @ EMIT
  b05 @ EMIT  b06 @ EMIT  b07 @ EMIT  b08 @ EMIT
  b09 @ EMIT  b10 @ EMIT  b11 @ EMIT  b12 @ EMIT
  b13 @ EMIT  b14 @ EMIT  b15 @ EMIT  b16 @ EMIT
  CR ." 1234567890123456 " \ show right-justification
  CR  \ Return to left margin for Forth ok prompt.
;  ( End of OutBuffer report; 12nov2012 )


: .echo ( show what the robot just said )
  ( As on Usenet, user responds _below_ the AI output. )
  fyi @ 2 = IF
    CR ." Tutorial mode is now in effect. "
    ."  Enter input or wait for output."
  THEN
  CR  ." Wotan: "  \ drop English word; use Wotan; 19nov2012
    tov @ t @ = IF   \ 12jan2010 Test for equality.
      tov @ 1 - tov !  \ 12jan2010 Prevent infinite loops.
    THEN  \ 12jan2010 End of test for tov @ t equality.
    t @ tov @  DO
      I 0  aud{ @  0 =  IF
        ."  "
      ELSE
        I   2 aud{ @  42 = NOT IF
          I 0 aud{ @ EMIT
        THEN
      THEN
    LOOP
;  ( End of .echo )


: SpreadAct  ( spreading activation )
  PsiDecay  \ to differentiate among activations; 10aug2012
  prepsi @ 0 > IF  \ From NounAct or VerbAct; 30jun2012
    zone @ 7 -   zone @  DO
      I 0  psi{ @   prepsi @  =  IF  \ now prepsi; 15sep2010
\ CR ." SprAct: augmenting activation at time "  \ 10aug2012
\ I . ."  of prepsi " prepsi @ .  \ test; 10aug2012
             \  1   I  1 psi{ +!  \ C-ing outl 10aug2012
                8   I  1 psi{ +!  \ for queries; 10aug2012
        I zone  @  6 - > IF LEAVE THEN
      THEN
    -1  +LOOP
  THEN
  seqpsi @ 0 > IF  \ replacing seqsyn; 15sep2010
    fyi @ 3 = IF
      CR ." SprA seqpsi & spike = " seqpsi @ . spike @ . CR
    THEN
    zone @ 32 +   zone @  DO  \ Search past non-seq psi.
      I 0  psi{ @  seqpsi @  =  IF  \ replacement 15sep2010
        fyi @ 3 = IF
          CR ." SprA matching seqpsi w. spike = " \ 24sep2010
          seqpsi @ .  spike @ . CR  \ non-global 24sep2010
        THEN
        fyi @ 1 > IF
          pov @ 35 = IF
            0 psi8 !  \ flag-panel location of "dex"; 17nov2012
            fyi @ 3 = IF
              CR ." sprdAct: seqpsi = " seqpsi @ . CR \ 24sep2010
            THEN
            midway @ t @ DO
              I   0  psi{ @ fyipsi @ = IF  \ 17oct2011
                I 8  psi{ @   psi8 !  \ new "dex"; 16nov2012
                LEAVE
              THEN
            -1  +LOOP
            midway @ t @ DO
              I   0  de{ @    psi8 @ = IF  \ new "dex"; 16nov2012
                I 7  de{ @  rv !
                LEAVE
              THEN
            -1  +LOOP
            0 rv !
            midway @ t @ DO
              I   0  psi{ @  seqpsi @ = IF  \ 15sep2010
                I 8  psi{ @   psi8 !  \ new "dex"; 16nov2012
                LEAVE
              THEN
            -1  +LOOP
            midway @ t @ DO
              I   0  de{ @    psi8 @ = IF  \ "dex"; 16nov2012
                I 7  de{ @  rv !
                LEAVE
              THEN
            -1  +LOOP
            rv @ 0 > IF
              BEGIN
                rv @ 0 aud{ @ EMIT  1 rv +!
                rv @ 0 aud{ @ 32 =
              UNTIL
            THEN
            0 rv !
            ."  "
          THEN
        THEN   \ end of FYI=1;  2aug2011
        fyi @ 2 > IF
          pov @ 35 = IF
            CR
            0 psi8 !  \ new "dex"; 16nov2012
            midway @ t @ DO
              I   0  psi{ @   fyipsi @  =  IF  \ 17oct2011
                I 8  psi{ @   psi8 !  \ "dex"; 16nov2012
                LEAVE
              THEN
            -1  +LOOP
            midway @ t @ DO
              I   0  de{ @    psi8 @ = IF   \ "dex"; 16nov2012
                I 8  de{ @  rv !   \ with dba; 10nov2012
                LEAVE
              THEN
            -1  +LOOP
            rv @ 0 > IF
              BEGIN
                rv @ 0 aud{ @ EMIT  1 rv +!
                rv @ 0 aud{ @ 32 =
              UNTIL
            THEN
            0 rv !
            ."  #" fyipsi @ . ." act " oldact @ .  \ 17oct2011
            ." at i " I . ." sprA spike "
            spike @ . ." to seqpsi #" seqpsi @ . \ 20sep2010
            midway @ t @ DO
              I   0  psi{ @  seqpsi @ = IF  \ 15sep2010
                I 8  psi{ @   psi8 !  \ "dex"; 16nov2012
                LEAVE
              THEN
            -1  +LOOP
            midway @ t @ DO
              I   0  de{ @    psi8 @ = IF  \ "dex"; 16nov2012
                I 8  de{ @  rv !   \ with dba; 10nov2012
                LEAVE
              THEN
            -1  +LOOP
            rv @ 0 > IF
              BEGIN
                rv @ 0 aud{ @ EMIT  1 rv +!
                rv @ 0 aud{ @ 32 =
              UNTIL
            THEN
            0 rv !
            CR
            ."  at act " I 1 psi{ @ . ." yields "
          THEN
        THEN    \ end of FYI=2+  2aug2011
        fyi @ 3 = IF
          ." SprA: spiking seqpsi " spike @ . seqpsi @ .
        THEN
        subjectflag @ 1 = IF  \ onto verb-nodes; 18oct2010
        ( insert diagnostic code here to troubleshoot 5aug2011 )
          spike @ I 1 psi{ +!  ( add spike to seqpsi 15sep2010 )
        ELSE  \ in all other cases, e.g. dirobj; 25jun2011
        ( insert diagnostic code here to troubleshoot 5aug2011 )
          spike @ I 1 psi{  !  ( Xfer absolute act; 25jun2011 )
        THEN  \ end of test for subject-nodes; 18oct2010
        fyi @ 2 > IF
          pov @ 35 = IF
            I 1 psi{ @ .
            fyi @ 2 > IF
              ." and zone = " zone @ .
            THEN
          THEN
        THEN
        fyi @ 3 = IF
          I 1 psi{ @ . ." (lim = 63) for t=" I rv !
          BEGIN
            -1 rv +!
            rv @ 3 aud{ @ 1 =
          UNTIL
          rv @ .
          BEGIN
            rv @ 0 aud{ @ EMIT  1 rv +!
            rv @ 0 aud{ @ 32 =
          UNTIL
          ."  engram; in sprA spike = " spike @ .
          0 rv !
        THEN
        I zone  @  6 + > IF
          fyi @ 2 > IF
            CR ." executing LEAVE at zone = " zone @ .
          THEN
          LEAVE
        THEN
        LEAVE  \ After finding one seqpsi; 13oct2010
      THEN   \ end of test for matching Psi#; 8aug2011
    LOOP
  THEN
; ( http://code.google.com/p/mindforth/wiki/SpreadAct )


:  NounAct ( re-activate all recent nodes of a concept )
  0 unk !  \ reset before using in NounAct; 8aug2011
  28 nounval !  \ test; 1sep2011
  fyi @ 2 > IF CR  \ 5jan2010 Altering the next line:
  ."     Calling NounAct (not in AI4U). nacpsi = " nacpsi @ . CR
  THEN
  nacpsi @  0 >  IF
    fyi @ 2 > IF
      CR ."       NounAct calls SpreadAct to transfer "
      CR ." proportionate activation from each node of "
      CR ." concept #" psi @ .
    THEN
    midway @   t @  DO
      I 0 psi{ @ nacpsi @ = IF
      -3 unk +!  \ for decrementing spike over time; 8aug2011
         ( insert diagnostic code here; 7sep2011 )
         I      1 psi{ @ -1 > IF \ avoid inhibition; 3sep2011
           nounval @ I  1 psi{ !  \ 3sep2011
         THEN  ( http://greenarraychips.com )
            I  0 psi{ @  781 = IF  \ 781=WHAT; 10nov2012
          0 I  1 psi{ !
            THEN  ( http://www.calcentral.com/~forth/forth )
                  12 spike !  ( Aim for ample spikes.)
          I  4 psi{ @  prepsi !  ( for SpreadAct 15sep2010 )
          I  7 psi{ @  seqpsi !  ( for SpreadAct 12oct2011 )
          I           zone !     ( for use in SpreadAct )
          I  1 psi{ @  0 = IF  0 spike ! THEN
          I  1 psi{ @  5 > IF 12 spike ! THEN
          I  1 psi{ @ 10 > IF 24 spike ! THEN  \  3nov2010
          I  1 psi{ @ 15 > IF 26 spike ! THEN  \  3nov2010
          I  1 psi{ @ 20 > IF 28 spike ! THEN  \  3nov2010
          I  1 psi{ @ 25 > IF 30 spike ! THEN  \  4jun2011
          I  1 psi{ @ 30 > IF 32 spike ! THEN  \  4jun2011
          I  1 psi{ @ 35 > IF 34 spike ! THEN  \  4jun2011
          I  1 psi{ @ 40 > IF 36 spike ! THEN  \  4jun2011
          I  1 psi{ @ 45 > IF 38 spike ! THEN  \  4jun2011
          I  1 psi{ @ 50 > IF 40 spike ! THEN  \  4jun2011
          I  1 psi{ @ 55 > IF 42 spike ! THEN  \  4jun2011
          I  1 psi{ @ 60 > IF 44 spike ! THEN  \  4jun2011
        nacpsi @ fyipsi !   \ 17oct2011
          I  1 psi{ @ oldact !
          I  5 psi{ @ oldpos !
        seqpsi @  0 > IF  \ replacement; 15sep2010
          seqpsi @ 791 = IF  \ 791=WHO; 10nov2012
            1 spike !  \ not 24 act; 11aug2010
          THEN   \ end of experiment; 11aug2010
          ( insert diagnostic code here; 8aug2011 )
        unk @ -10 < IF -10 unk ! THEN  \ limit decrement 8aug2011
        unk @ spike +!  \ decrement spike; 8aug2011 
          7865 caller !
          SpreadAct  ( for spreading activation )
          0 caller !
          0 prepsi !  \ replacing presyn; 15sep2010
          0 seqpsi !  \ replacing seqsyn; 15sep2010
        THEN
        precand @ pre !
        0 oldpos !
        0 fyipsi !  \ 17oct2011
        0 oldact !
        0  pre !
      THEN
      0 spike !  \ reset for each new loop; 14oct2010
    -1  +LOOP
  THEN
  0 spike !
; ( http://code.google.com/p/mindforth/wiki/NounAct )


:  VerbAct ( re-activate all recent nodes of a verb )
  17 verbval !  \ lowering to promote warranted assoc; 27aug2011
  fyi @ 2 > IF CR
  ."     Calling verbAct (not in AI4U). psi = " psi @ . CR
  THEN
  vacpsi @  0 >  IF  \ if a vacpsi exists; 9nov2010
    fyi @ 2 > IF
      CR ."       VerbAct calls SpreadAct to transfer "
      CR ." proportionate activation from each node of "
      CR ." concept #" psi @ .
    THEN
    vacpsi @ fyipsi !  \ a replacement variable; 17oct2011
    midway @   t @ DO
      I 0 psi{ @ vacpsi @ = IF  \ deglobalized psi; 8oct2010
        fyi @ 2 > IF
          I 1 psi{ @ 8 > IF
            ." +"
          THEN
        THEN
            I  1 psi{ @  psi1 !
          I    1 psi{ @ -1 > IF \ avoid inhibited nodes; 9sep2010
            ( insert diagnostic code here; 27aug2011 )
            moot @ 0 = IF  \ deprive queries of tags; 20aug2011
              verbval @ I  1 psi{ +!  \ CUMULATIVE for slosh-over.
            THEN  \ end of test for a moot query input; 20aug2011
          THEN  \ end of test to skip inhibited nodes; 9sep2010
            I  0 psi{ @  781 = IF  \ 781=WHAT; 11nov2012
          0 I  1 psi{ !
            THEN
          I  4 psi{ @  prepsi !  ( for SpreadAct 15sep2010 )
          I  7 psi{ @  seqpsi !  ( for SpreadAct 12oct2011 )
          I           zone !     ( for use in SpreadAct )
          I  1 psi{ @  0 = IF  0 spike ! THEN
          I  1 psi{ @  0 > IF  1 spike ! THEN
          I  1 psi{ @  5 > IF  3 spike ! THEN
          I  1 psi{ @ 10 > IF  6 spike ! THEN
          I  1 psi{ @ 15 > IF  9 spike ! THEN
          I  1 psi{ @ 20 > IF 12 spike ! THEN
          I  1 psi{ @ 25 > IF 15 spike ! THEN
          I  1 psi{ @ 30 > IF 16 spike ! THEN
          I  1 psi{ @ 35 > IF 17 spike ! THEN
          I  1 psi{ @ 40 > IF 18 spike ! THEN
          I  1 psi{ @ 45 > IF 19 spike ! THEN
          I  1 psi{ @ 50 > IF 30 spike ! THEN
          I  1 psi{ @ 55 > IF 33 spike ! THEN
          I  1 psi{ @ 60 > IF 36 spike ! THEN
          I  1 psi{ @ 65 > IF 39 spike ! THEN
          I  1 psi{ @ 70 > IF 42 spike ! THEN
          I  1 psi{ @ 75 > IF 45 spike ! THEN
          I  1 psi{ @ 80 > IF 48 spike ! THEN
          I  1 psi{ @ 85 > IF 50 spike ! THEN
          I  1 psi{ @ 90 > IF 52 spike ! THEN
          I  1 psi{ @ 95 > IF 54 spike ! THEN
        vacpsi @ fyipsi !  \ a replacement variable; 17oct2011
          I  1 psi{ @ oldact !
          I  5 psi{ @ oldpos !
   fyi @ 2 = IF  \ In Tutorial mode show slosh-over; 17oct2010
     CR  ."    VerbAct calls SpreadAct with activation "
     spike @ . ." for Psi #" seqpsi @ . \ 18oct2010
   THEN  \  End of test for Tutorial mode; 17oct2010
        seqpsi @  0 > IF  \ replacement; 15sep2010
        ( insert diagnostic code here; 6aug2011 )
          5 spike +!  \ for sake of direct objects; 3sep2011
          8665 caller !
          SpreadAct  ( for spreading activation )
          0 caller !
          0 prepsi !  \ replacing presyn; 15sep2010
          0 seqpsi !  \ replacing seqsyn; 15sep2010
        THEN
        0 oldpos !
        0 fyipsi !  \ 17oct2011
        0 oldact !
        0  pre !
        0  seq !
      THEN
      ( perhaps reset spike to zero for each loop? 14oct2010 )
      0 spike !  \ reset to start each loop again; 14oct2010
    -1  +LOOP
  THEN
; ( http://code.google.com/p/mindforth/wiki/VerbAct )


:  ReActivate ( re-activate recent nodes of a concept )
  fyi @ 2 > IF CR
  ."     Calling ReActivate. psi = " psi @ . CR
  THEN
  0 spike !
  psi @  0 >  IF
    fyi @ 2 > IF
      CR ."       ReActivate calls SpreadAct to transfer "
      CR ." proportionate activation from each node of "
      CR ." concept #" psi @ .
    THEN
    midway @ tov @  DO  \ Omitting current input; 29may2011
      I 0 psi{ @ psi @ = IF
         pov @ 42 = IF  \ Only during "*" external POV; 7may2011
          moot @ 0 = IF  \ deprive queries of tags; 20aug2011
           I  1 psi{ @ 0 < IF  \ if inhibited; 29aug2011
             1 I  1 psi{ +!  \ reactivate only slightly; 29aug2011
               proxcon @ 1 = IF  \ if clustering input; 7sep2011
                 prox3 @ psi @ = IF   \ 7sep2011
                   I 7 psi{ @ prox2 @ = IF  \ seq; 12oct2011
                     40 I 1 psi{ !  \ extra act; 7sep2011
                   THEN  \ 7sep2011
                 THEN  \ 7sep2011
               THEN  \ end of proxcon test; 7sep2011
           ELSE   \ otherwise impose full reactivation; 29aug2011
             I      1 psi{ @ -1 > IF \ avoid inhibition; 3sep2011
               35 I 1 psi{ +!  \ Relative not absolute 12aug2011
               I 5 psi{ 8 = IF  \ Test for a verb; 28jun2012
                 16 I 1 psi{ +!  \ Accentuate verbs; 28jun2012
               THEN  \ End of test for verbs; 28jun2012
               proxcon @ 1 = IF  \ if clustering input; 7sep2011
                 prox2 @ psi @ = IF  \ 7sep2011
                 THEN  \ 7sep2011
                 prox3 @ psi @ = IF   \ 7sep2011
                   I 7 psi{ @ prox2 @ = IF  \ seq; 12oct2011
                     10 I 1 psi{ +!  \ extra act; 7sep2011
                   THEN  \ 7sep2011
                 THEN  \ 7sep2011
               THEN  \ end of proxcon test; 7sep2011
             THEN  ( http://www.ez-robot.com )
           THEN   \ end of test for inhibited concept; 29aug2011
          THEN  \ end of test for a moot query input; 20aug2011
         THEN   \  End of new test for external POV;  7may2011
            I  0 psi{ @ 781 = IF  \ 781=WHAT; 10nov2012
          0 I  1 psi{ !
            THEN
            I  0 psi{ @ 791 = IF  \ 791=WHO; 10nov2012
          0 I  1 psi{ !  \ As in InStantiate; 3may2011
            THEN  \ end of test for 791=WHO   10nov2012
            I  0 psi{ @ 830 = IF  \ 830=DO; 10nov2012
          0 I  1 psi{ !   \ 12jan2010 For what-do queries.
            THEN          \ End of 830=DO test; 10nov2012
                               1 spike !  \ 30jun2012
          I  1 psi{ @  0 = IF  0 spike ! THEN
          I  1 psi{ @  5 > IF  7 spike ! THEN
          I  1 psi{ @ 10 > IF  8 spike ! THEN
          I  1 psi{ @ 15 > IF  9 spike ! THEN
          I  1 psi{ @ 20 > IF 10 spike ! THEN
          I  1 psi{ @ 25 > IF 11 spike ! THEN
          I  1 psi{ @ 30 > IF 12 spike ! THEN
          I  1 psi{ @ 35 > IF 13 spike ! THEN
          I  1 psi{ @ 40 > IF 14 spike ! THEN
          I  1 psi{ @ 45 > IF 15 spike ! THEN
          I  1 psi{ @ 50 > IF 16 spike ! THEN
          I  1 psi{ @ 55 > IF 17 spike ! THEN
          I  1 psi{ @ 60 > IF 18 spike ! THEN
          I  4 psi{ @  prepsi !  ( for SpreadAct 30jun2012 )
          I  7 psi{ @  seqpsi !  ( for SpreadAct 30jun2012 )
          I           zone !     ( for SpreadAct 30jun2012 )
        148 caller !
        SpreadAct  ( for spreading activation 30jun2012 )
        0 oldpos !
        0 fyipsi !  \ 17oct2011
        0 oldact !
        0    pre !
        0 prepsi !
        0    seq !
        0 seqpsi !
        0   psi1 !
        1  spike !
      THEN
    -1  +LOOP
    0 caller !
    0 urpsi !
  THEN
; ( http://code.google.com/p/mindforth/wiki/ReActivate )


:  InNativate ( quasi-instantiate the DeBoot sequence )
( concept fiber psi )              psi @  t @  0 psi{ !
( Set "num" number flag )          num @  t @  2 psi{ !
( Set "jux" in case of negation )  jux @  t @  3 psi{ !
( Store PREvious associand. )      pre @  t @  4 psi{ !
( Store functional pos code. )     pos @  t @  5 psi{ !
( Store the "tqv" time-point. )    tqv @  t @  6 psi{ !
( Store the subSEQuent tag. )      seq @  t @  7 psi{ !
( Store the DE-transfer tag. )     dex @  t @  8 psi{ !
; ( http://code.google.com/p/mindforth )


:  OutBuffer  ( right-justifies a word in memory )
  ( may need expansion from 16 to 32 for long German words )
  32 b01 !  32 b02 !  32 b03 !  32 b04 !  32 b05 !
  32 b06 !  32 b07 !  32 b08 !  32 b09 !  32 b10 !
  32 b11 !  32 b12 !  32 b13 !  32 b14 !  32 b15 !
  32 b16 !
  c16 @ 32 > IF  \ if the AudBuffer is full; 14nov2012
    c16 @ b16 ! c15 @ b15 ! c14 @ b14 ! c13 @ b14 !
    c12 @ b12 ! c11 @ b11 ! c10 @ b10 @ c09 @ b09 !
    c08 @ b08 ! c07 @ b07 ! c06 @ c06 ! c05 ! b05 !
    c04 @ b04 ! c03 @ c03 ! c02 @ b02 ! c01 @ c01 !
    EXIT  \ abandon remainder of function; 13nov2012
  THEN \ end of transfer of 16-character word; 13nov2012
  c15 @ 32 > IF  \ word only 15 chars long? 14nov2012
    c15 @ b16 ! c14 @ b15 ! c13 @ b14 ! c12 @ b13 !
    c11 @ b12 ! c10 @ b11 ! c09 @ b10 ! c08 @ b09 !
    c07 @ b08 ! c06 @ b07 ! c05 @ b06 ! c04 @ b05 !
    c03 @ b04 ! c02 @ b03 ! c01 @ b02 ! EXIT
  THEN  \ transfer of a 15-character word; 13nov2012
  c14 @ 32 > IF
    c14 @ b16 !  c13 @ b15 !  c12 @ b14 !  c11 @ b13 !
    c10 @ b12 !  c09 @ b11 !  c08 @ b10 !  c07 @ b09 !
    c06 @ b08 !  c05 @ b07 !  c04 @ b06 !  c03 @ b05 !
    c02 @ b04 !  c01 @ b03 !  EXIT
  THEN
  c13 @ 32 > IF
    c13 @ b16 !  c12 @  b15 ! c11 @  b14 ! c10 @ b13 !
    c09 @ b12 !  c08 @  b11 ! c07 @  b10 ! c06 @ b09 !
    c05 @ b08 !  c04 @  b07 ! c03 @  b06 ! c02 @ b05 !
    c01 @ b04 !  EXIT
  THEN
  c12 @ 32 > IF
    c12 @ b16 !  c11 @ b15 !  c10 @ b14 !  c09 @ b13 !
    c08 @ b12 !  c07 @ b11 !  c06 @ b10 !  c05 @ b09 !
    c04 @ b08 !  c03 @ b07 !  c02 @ b06 !  c01 @ b05 !
    EXIT
  THEN
  c11 @ 32 > IF
    c11 @ b16 !  c10 @ b15 !  c09 @ b14 !  c08 @  b13 !
    c07 @ b12 !  c06 @ b11 !  c05 @ b10 !  c04 @  b09 !
    c03 @ b08 !  c02 @ b07 !  c01 @ b06 !  EXIT
  THEN
  c10 @ 32 > IF
    c10 @ b16 !  c09 @ b15 !  c08 @ b14 !  c07 @ b13 !
    c06 @ b12 !  c05 @ b11 !  c04 @ b10 !  c03 @ b09 !
    c02 @ b08 !  c01 @ b07 !  EXIT
  THEN
  c09 @ 32 > IF
    c09 @ b16 !  c08 @ b15 !  c07 @ b14 !  c06 @ b13 !
    c05 @ b12 !  c04 @ b11 !  c03 @ b10 !  c02 @ b09 !
    c01 @ b08 !  EXIT
  THEN
  c08 @ 32 > IF
    c08 @ b16 !  c07 @ b15 !  c06 @ b14 !  c05 @ b13 !
    c04 @ b12 !  c03 @ b11 !  c02 @ b10 !  c01 @ b09 !
    EXIT
  THEN
  c07 @ 32 > IF
    c07 @ b16 !  c06 @ b15 !  c05 @ b14 !  c04 @ b13 !
    c03 @ b12 !  c02 @ b11 !  c01 @ b10 !
    EXIT
  THEN
  c06 @ 32 > IF
    c06 @ b16 !  c05 @ b15 !  c04 @ b14 !  c03 @ b13 !
    c02 @ b12 !  c01 @ b11 !
    EXIT
  THEN
  c05 @ 32 > IF
    c05 @ b16 !  c04 @ b15 !  c03 @ b14 !  c02 @ b13 !
    c01 @ b12 !
    EXIT
  THEN
  c04 @ 32 > IF
    c04 @ b16 !  c03 @ b15 !  c02 @ b14 !  c01 @ b13 !
    EXIT
  THEN
  c03 @ 32 > IF
    c03 @ b16 !  c02 @ b15 !  c01 @ b14 !
    EXIT
  THEN
  c02 @ 32 > IF
    c02 @ b16 !  c01 @ b15 !
    EXIT
  THEN
  c01 @ 32 > IF
     c01 @ b16 !
     EXIT
  THEN
;  \ end of OutBuffer; return to AudBuffer or VerbGen.


:  AudBuffer  ( for transfer of words to OutBuffer; 12nov2012 )
  1 phodex +!  \ increment; 12nov2012
  phodex @  1 = IF  \ Erase any left-over old data;
    abc @ c01 !  \ fill in first item of new data.
    32 c02 ! 32 c03 ! 32 c04 ! 32 c05 ! 32 c06 !
    32 c07 ! 32 c08 ! 32 c09 ! 32 c10 ! 32 c11 !
    32 c12 ! 32 c13 ! 32 c14 ! 32 c15 ! 32 c16 !
  THEN  \ end of blanking out with 32=SPACE
  phodex @  2 = IF abc @ c02 !  THEN  \ 12nov2012
  phodex @  3 = IF abc @ c03 !  THEN  \ 12nov2012
  phodex @  4 = IF abc @ c04 !  THEN  \ 12nov2012
  phodex @  5 = IF abc @ c05 !  THEN  \ 12nov2012
  phodex @  6 = IF abc @ c06 !  THEN  \ 12nov2012
  phodex @  7 = IF abc @ c07 !  THEN  \ 12nov2012
  phodex @  8 = IF abc @ c08 !  THEN  \ 12nov2012
  phodex @  9 = IF abc @ c09 !  THEN  \ 12nov2012
  phodex @ 10 = IF abc @ c10 !  THEN  \ 12nov2012
  phodex @ 11 = IF abc @ c11 !  THEN  \ 12nov2012
  phodex @ 12 = IF abc @ c12 !  THEN  \ 12nov2012
  phodex @ 13 = IF abc @ c13 !  THEN  \ 12nov2012
  phodex @ 14 = IF abc @ c14 !  THEN  \ 12nov2012
  phodex @ 15 = IF abc @ c15 !  THEN  \ 12nov2012
  phodex @ 16 = IF abc @ c16 !  THEN  \ 12nov2012
  OutBuffer  \ right-justify each input word; 15nov2012
  0 abc !  \ reset for non-persistence; 14nov2012
;  \ end of AudBuffer; return to AudInput or VerbGen


:  InStantiate ( create a concept-fiber node )
  seqneed @ 0 = IF 5 seqneed ! THEN  \ test; 27jul2012
  precand @ 0 > IF precand @ pre ! THEN
  ordo @ 1 = IF  0 prevtag ! THEN
  firstword @ 830 = IF  \ DO or DOES; 10nov2012
    1 moot !  \ deprive queries of pre and seq tags; 19aug2011
  THEN  \ end of test for a DO-query; 19aug2011
  firstword @ 781 = firstword @ 791 = OR IF  \ 10nov2012
    1 proxcon !  \ set for 781=WHAT or 791=WHO; 10nov2012
  THEN
  lastword @ 1 = IF
    0 seq !
  THEN   ( http://home.iae.nl/users/mhx/i4faq.html )
  t @ vault @ > IF  \ Avoid the DeBoot vault; 19nov2012
    whoflag @ 1 = IF
      psi @ 800 = IF 800 beflag ! THEN  \ 10nov2012
      pos @ 5 = pos @ 7 = OR IF
        beflag @ seq !  \ Store verb as seq; 26nov2012
        0 beflag !
      THEN
    THEN
    psi @ 781 = IF  \ Special handling of 781=WHAT; 10nov2012
      1 indefartcon ! \ indefinite article condition 16apr2011
      0 act !      \ To suppress "WHAT" during answer.
    THEN           \ End of test for input of "WHAT"
    psi @ 791 = IF  \ Special handling of 791=WHO; 10nov2012
      1 defartcon ! \ Set definite article condition 16apr2011
      1 whoflag !
      0 act !      \ To suppress "WHO" during answer.
    THEN
    singflag @ 1 = IF
      pos @ 5 = IF
        1 num !
        0 singflag !
      THEN
    THEN
  \ psi @ 1 =  psi @ 83 = OR IF  \ "A" or "AN"; 6aug2011
    psi @  101 =  IF  \ EIN, EINE, EIN? 28nov2012
      1 singflag !  \ assume word is singular; 28nov2012
      0 act !
    THEN
  THEN   \ end of InStantiate t-test clause; 14jul2012
  pos @ 5 = IF  \ noun either external or internal; 6aug2011
    recnum @ 0 > IF   \ If positive recog-num; 6aug2022
      recnum @ num !  \ Override num(ber); 6aug2011
    \ 0 recnum !  \ reset for safety; 6aug2011; 14jul2012
    THEN  \ End of test for positive recog-num; 6aug2011
  THEN  \ End of test for a 5=pos noun; 6aug2011
  pov @ 42 = IF  \ If POV is external; 24jun2011
    num @ 0 = IF  \ if no num(ber) is assigned; 24jun2011
      putnum @ 0 > IF   \ if putative number is positive
        putnum @ num !  \ replace zero with putative num
      THEN  \ end of test for positive putnum; 24jun2011
    THEN   \ end of test for missing num-value; 24jun2011
    pos @ 8 = IF putnum @ num ! THEN \ test; 24jun2011
    pos @ 5 = IF psi @ quobj ! THEN  \ for AskUser; 6aug2011
  THEN  \ End of test for "*" external POV; 20aug2011
  pov @ 35 = IF  \ If POV is pound-sign internal; 3may2011
   num @ 0 = IF  \ if no num(ber) is assigned; 24jun2011
     putnum @ 0 > IF   \ if putative number is positive
       putnum @ num !  \ replace zero with putative num
       0 putnum !  \ zero for safety; test; 5aug2011
     THEN  \ end of test for positive putnum; 24jun2011
   THEN   \ end of test for missing num-value; 24jun2011
   pos @ 8 = IF putnum @ num ! THEN \ test; 24jun2011
    0 act !  \ 0 activation for ReEntry concepts; 26apr2011
  THEN  \ End of test for #internal POV;  7may2011
  pos @ 8 = NOT IF 0 jux ! THEN \ only negate verbs 27nov2012
  audnum @ num !  \ pass for storage; 19nov2012
  psi @ 701 = IF 1 num ! THEN  \ 701=ICH (I); 19nov2012
  psi @ 707 = IF 1 num ! THEN  \ 707=DU (you) 19nov2012
  psi @ 713 = IF 1 num ! THEN  \ 713=ER (he); 19nov2012
  psi @ 719 = IF 1 num ! THEN  \ 719=SIE she; 19nov2012
  psi @ 725 = IF 1 num ! THEN  \ 725=ES (it); 19nov2012
  psi @ 749 = IF 1 num ! THEN  \ 749=SIE you; 19nov2012
  psi @ 731 = IF 2 num ! THEN  \ 731=WIR (we) 19nov2012
  psi @ 737 = IF 2 num ! THEN  \ 737=IHR you; 19nov2012
  psi @ 743 = IF 2 num ! THEN  \ 743=SIE they 19nov2012
  psi @ 755 = IF 2 num ! THEN  \ 755=SIE you; 19nov2012
  prevtag @ pre !
  t @ vault @ < IF  0 pre ! THEN  \ for safety; 22sep2011
  ( concept fiber psi )             psi @  t @  0 psi{ !
  moot @ 0 = IF  \ deprive queries of tags; 20aug2011
  ( Set "act" activation level. )   act @  t @  1 psi{ +!
    pos @ 8 = IF  \ Re-using code; test for a verb; 28jun2012
      16 t @ 1 psi{ +!  \ Accentuate verbs; 28jun2012
    THEN  \ End of test for verbs; 28jun2012
  THEN  \ end of test for a moot query input; 20aug2011
  ( Set "num" number flag       )   num @  t @  2 psi{ !
  ( Store JUXtaposition tags. )     jux @  t @  3 psi{ !
  moot @ 0 = IF  \ deprive queries of tags; 19aug2011
  ( Store PREvious associand. )     pre @  t @  4 psi{ !
  THEN  \ end of test for a moot query input; 19aug2011
  ( Store functional pos code. )    pos @  t @  5 psi{ !
   seq @ 0 > IF  \ avoid spurious carry-over tqv; 1aug2012
    ( Store the "tqv" time-point. ) tqv @  t @  6 psi{ !
   THEN  \ only store "tqv" if there is a "seq"; 1aug2012
  moot @ 0 = IF  \ deprive queries of tags; 19aug2011
  ( Store the subSEQuent tag. )     seq @  t @  7 psi{ !
  THEN  \ end of test for a moot query input; 19aug2011
  ( Store the DE-xfer 16nov2012)    dex @  t @  8 psi{ !
  t @ vault @ < IF  \ store only during EnBoot; 29sep2011
  \ ( Store the "tqv" time-point. ) tqv @  t @  8 psi{ !
  THEN  \ otherwise store "tqv" retroactively; 29sep2011
  num @ instnum !
  pos @ 5 = IF num @ putnum ! THEN \ noun to verb; 24jun2011
  0 num !
  jux @ 250 = IF 0 jux ! THEN  \ reset after use; 10nov2012
  prejux @ 250 = IF  \ 250=NOT from OldConcept; 10nov2012
    250 jux !  \  set jux for next instantiand; 10nov2012
    0 prejux !  \ reset for safety; 21jul2011
  THEN  \  end of post-instantiation test; 21jul2011
  mfn @ 1 =  mfn @ 2 = OR IF  \ masc or fem; 17aug2010
    mfn @ mfnflag !  \   17aug2010
  THEN   \ 17aug2010
  mfn @ 0 = IF  0 mfnflag ! THEN  \ test; 25aug2010
  0 mfn !  \ Test code applies only to En array.
  0 preset !
  pos @ 5 = pos @ 7 = OR IF
    psi @ prevtag !
  THEN
  seqneed @ 8 = IF  \ if looking for a verb; 2oct2011
    pos @ 8 = IF  \ if part-of-speech is verb; 2oct2011
      psi @ seq !  \ verb has arrived; 2oct2011
      0 seqneed !  \ zero out after use; 2oct2011
      pos @ seqpos !  \ possibly for tqv; 2oct2011
    THEN  \ end of test for 8=pos verb; 2oct2011
      tsn @  t @ 2 - DO  \ look for noun needing seq; 1jul2012
      I 5 psi{ @ 5 = I 5 psi{ @ 7 = OR IF \ (pro)noun 2oct2011
        moot @ 0 = IF  \ deprive queries of tags; 5oct2011
          seq @ I 7 psi{ !  \ insert the seq; 12oct2011
          seqpos @ 8 = IF  \ a verb?  2oct2011
            t @   I 6 psi{ !  \ insert "tqv" value; 12oct2011
            t @   tqv !       \ assign "tqv" value;  2oct2011
          THEN  \ end of seqpos=verb test; 2oct2011
        THEN  \ end of test for a moot query input; 5oct2011
        LEAVE  \ insert only one seq; 2oct2011
      THEN  \ end of test for subject noun or pronoun 2oct2011
    -1 +LOOP   \ end of backwards loop; 2oct2011
  THEN  \ end of test for needing a verb; 2oct2011
  seqneed @ 5 = IF  \ if looking for a noun; 5oct2011
    pos @ 5 =  pos @ 7 = OR IF  \ if noun or pronoun; 5oct2011
      4 dba !  \ from RuAi: assuming acc. dir. obj.; 25nov2012
      psi @ seq !  \ because a (pro)noun has arrived; 5oct2011
      0 seqneed !  \ zero out after use; 5oct2011
      pos @ seqpos !  \ possibly for tqv; 5oct2011
    THEN  \ end of test for 5=pos noun or 7=pos pronoun; 5oct2011
    tsn @  t @ 2 -  DO  \ look for verb needing "seq"; 1jul2012
      I 5 psi{ @ 8 = IF  \ verb?  5oct2011
        moot @ 0 = IF  \ deprive queries of tags; 5oct2011
        \ t @ vault > IF  \ t>vault? 28nov2012
          t @ vault @ > IF  \ t>vault? 29nov2012
            seq @ I 7 psi{ !  \ insert the seq; 12oct2011
            seqpos @ 5 =  seqpos @ 7 = OR IF  \ 5oct2011
              t @   I 6 psi{ !  \ insert "tqv" 12oct2011
              t @   tqv !       \ assign "tqv"  5oct2011
            THEN  \ end of seqpos=(pro)noun test; 5oct2011
          THEN  \ end of test for t>vault; 28nov2012
        \ jux @ I 3 psi{ !  \ insert the jux; 27nov2012
        THEN  \ end of test for a moot query input; 5oct2011
        LEAVE  \ insert only one seq; 5oct2011
      THEN  \ end of test for a verb; 5oct2011
    -1 +LOOP   \ end of backwards loop; 5oct2011
  THEN  \ end of test for needing a noun; 5oct2011
  ordo @ 2 = IF  \  7sep2011
    psi @ prox2 !  \ 7sep2011
  THEN  \  7sep2011
  ordo @ 3 = IF  \  7sep2011
    psi @ prox3 !  \ 7sep2011
  THEN  \  7sep2011
  pos @ 5 =  pos @ 7 = OR IF  \ (pro)noun? 2oct2011
    8 seqneed !  \ need "8=verb" seq; 2oct2011
  THEN  \ end of test for a noun or a pronoun; 2oct2011
  pos @ 6 = IF  \ if preposition; 2oct2011
    5 seqneed !  \ need noun or pronoun; 2oct2011
  THEN ( http://home.hccnet.nl/a.w.m.van.der.horst/ciforth.html )
  pos @ 8 = IF  \ if verb then need noun as "seq"; 5oct2011
    5 seqneed !  \ seek noun or pronoun as "seq"; 5oct2011
  THEN  \  end of test for 8=verb; 5oct2011
  lastword @ 1 = IF  0 lastword ! THEN  \ for seqneed; 30jun2012
  0 dba !  \ from RuAi: reset for safety; 25nov2012
  0 recnum !  \ lest carry-over to other words; 19jul2011
  0 seq !
; ( http://code.google.com/p/mindforth/wiki/InStantiate )


:  DeVocab ( Deutsch Vocabulary node creation; 24nov2011 )
  ( German "dnr" number 16nov2012 ) dnr @  t @  0  de{ !
  ( Do not store the activation level; it is a transient.)
  ( Store "num" number tag. )       num @  t @  2  de{ !
  ( Store "mfn" gender tag. )       mfn @  t @  3  de{ !
  ( Store "dba" case; 24nov2011 )   dba @  t @  4  de{ !
  ( Store mindcore EXit tag. )      fex @  t @  5  de{ !
  ( Store part of speech "pos".)    pos @  t @  6  de{ !
  ( Store mindcore IN tag. )        fin @  t @  7  de{ !
  ( Store the auditory "aud" tag. ) aud @  t @  8  de{ !
  0 dba !  \ reset for safety; 24nov2011
; ( http://code.google.com/p/mindforth/wiki/EnVocab )


:  DeParser ( determine the part of speech; 17nov2012 )
  5 bias !
  35 act !  \ Activate lower than ReActivate; 29may2011
  pov @ 42 = IF  \ only during external input; 9oct2010
    act @ ordo @ - act !  \ reduce S-V-O act's; 9oct2010
  THEN  \ end of test for external POV; 9oct2010
  InStantiate  \ create a Psi concept node; 6nov2010
  pos @ 5 = IF  8 bias !  THEN
  pos @ 7 = IF  8 bias !  THEN
  pos @ 8 = IF  5 bias ! 0 singflag ! THEN  \ 4nov2011
; ( http://code.google.com/p/mindforth/wiki/EnParser )


:  DeReify ( express abstract concepts as real words )
  0 act !
  midway @  t   @  DO
          I   1 psi{ @  0 > IF
          I   1 psi{ @  lexact !
          I   2 psi{ @  num !
 lexact @ I   1  de{ !   \ 16nov2012
    num @ I   2  de{ !   \ 16nov2012
            0 lexact !
         THEN  ( http://home.vrweb.de/~stephan.becher/forth )
    0 dex !   \ 16nov2012
    0 act !
    0 lexact !
  -1  +LOOP
  0 act !
; ( http://code.google.com/p/mindforth/wiki/EnReify )


:  KbSearch ( knowledge base search )
  ordo @ 2 = IF
    NounAct  ( may need a "nacpsi" value )
    DeReify  \ changing to Germanesque name; 17nov2012
  THEN  ( http://www.ccreweb.org/software/kforth )
  ordo @ 3 = IF
    0 act !
    midway @ t  @ DO
      I     5 de{ @  8 = IF   \ Test part-of-speech.
        I   1 de{ @  act @ > IF  ( if en1 is higher )
          I 0 de{ @  memoire !  ( store psi-tag of word )
          I 1 de{ @  act !  ( to test for a higher en1 )
        THEN
      THEN
    -1 +LOOP
    yesorno @ 0 > IF
      memoire @ psi @ = IF
        1 yesorno +!
      ELSE
        0 yesorno !
      THEN
    THEN
    psi @ vacpsi !  \ deglobalizing; 27sep2010
    VerbAct
    0 vacpsi !  \ reset for safety; 27sep2010
    DeReify  \ changing to Germanesque name; 17nov2012
  THEN
  ordo @ 4 = IF
    0 act !
    0 memoire !
    midway @ t  @ DO
      I 5 de{ @ 5 = I 5 de{ @ 7 = OR IF
        I    1 de{ @  act @ > IF  ( if en1 is higher )
          I  0 de{ @  memoire !  ( store psi-tag of word )
          I  1 de{ @  act !  ( to test for a higher en1 )
        THEN
      THEN
    -1 +LOOP
    yesorno @ 0 > IF
      memoire @ psi @ = IF
        1 yesorno +!
      ELSE
        0 yesorno !
      THEN
    THEN  ( http://www.lifeai.com )
  THEN
  0 kbquiz !
  ordo @ 4 = IF 0 ordo ! THEN
; ( http://code.google.com/p/mindforth/wiki/KbSearch )


:  KbRetro  ( retroactive adjustment of knowledge base )
  oldpsi @ 432 = oldpsi @ 404 = OR IF  \ yes or no 10nov2012
    oldpsi @ 404 = IF  \ 404=NO; 10nov2012
      64  tkbn @  1 psi{ ! \ high noun activation 21jul2011
      64  tkbv @  1 psi{ ! \ set high activation? 2jul2011
      12  tkbv @  3 psi{ ! \ set 12=NOT jux flag; 2jul2011
    THEN  \ End of test for "No" answer; 2jul2011
    oldpsi @ 432 = IF  \ 432=YES; 10nov2012
      64  tkbv @  1 psi{ ! \ set high activation? 2jul2011
    THEN \ End of test for "Yes" answer; 2jul2011
  ELSE  \ if neither; 2jul2011
    0  tkbn @  4 psi{ ! \ delete pre-tag for noun;  2jul2011
    0  tkbn @  7 psi{ ! \ delete seq-tag for noun; 12oct2011
    0  tkbv @  4 psi{ ! \ delete pre-tag for verb;  2jul2011
    0  tkbv @  7 psi{ ! \ delete seq-tag for verb; 12oct2011
  THEN  ( http://retroforth.org )
  0 kbcon !  \ temporarily here turn off kbcon;  2jul2011
  0 tkbn !  \ reset for safety;  2jul2011
  0 tkbv !  \ reset for safety;  2jul2011
; ( http://code.google.com/p/mindforth/wiki/KbRetro )


:  OldConcept ( recognize a known word )
  28 act !  \ A value subject to optimization; 28sep2010
  midway @ t @ DO
    I 0 de{ @ oldpsi @ = IF
    I 2 de{ @    0 > IF
    I 2 de{ @  ocn ! THEN  \ "unk" is too global; 14jul2012
    I 3 de{ @    0 > IF
    I 3 de{ @  mfn ! THEN
  \ I 4 de{ @    0 > IF    \ Precaution from RuAi; 25nov2012
  \ I 4 de{ @  dba ! THEN  \ Not trustworthy for verbs 25nov
    I 5 de{ @    0 > IF
    I 5 de{ @  fex ! THEN
    I 6 de{ @    0 > IF
    I 6 de{ @  pos ! THEN
    I 7 de{ @    0 > IF
    I 7 de{ @  fin ! THEN
    LEAVE
    THEN  ( http://home.iae.nl/users/mhx/eforth.html )
  -1 +LOOP
  pos @ 8 = IF  \ verb? for WhatAuxSVerb 13jun2011
    numsubj @ unk !  \ assume agreement; 19jun2011
    3 dba !  \ 3rd person default before changes; 25nov2012    
    putdbav @ 0 > IF  \ positive putdbav? 25nov2012
      putdbav @ dba !  \ transfer; 25nov2012
      0 putdbav !  \ reset after use; 25nov2012
    THEN  \ end of test for putative dba; 25nov2012
    t @  tdzw !  \ for negational "jux"; 27nov2012
  THEN  \ end of test for verb \ 13jun2011
  oldpsi @ 800 = IF t @ tbev ! THEN \ 800=BE; 10nov2012
  pos @ 5 =  pos @ 7 =  OR IF  \ noun or pron.? 25nov2012
    1 dba !  \ default before changes; 25nov2012
    audverb @  0 > IF  \ preceded by a verb? 26nov2012
      audverb @  800 = NOT IF  \ except be-verbs; 26nov2012
        4 dba !  \ accusative direct object; 26nov2012
      THEN  \ 26nov2012
      0 audverb !  \ reset after use; 26nov2012
    THEN  \ end of test for positive audverb; 26nov2012
  THEN  \ end of test for noun or pronoun; 25nov2012
  oldpsi @ 701 = oldpsi @ 731 = OR IF 1 putdbav ! THEN
  oldpsi @ 707 = oldpsi @ 737 = OR IF 2 putdbav ! THEN
  subjectflag @ 1 = IF 1 dba ! THEN \ nom. subj. 25nov2012
  dirobj @ 1 = IF 4 dba ! THEN  \ acc. dir. obj. 25nov2012
  ( oldpsi found by AudRecog )   oldpsi @  t @  0 de{ !
  ( Add zero activation 28jul2011 )   0    t @  1 de{ +!
  ocn @ 0 > IF  \ from AudInput for old nouns; 14oct2011
  ( Store old-concept-number tag )  ocn @  t @  2 de{ !
    0 ocn !  \ reset to zero after use; 14oct2011
  THEN  \ leaving only one space in "2 en{" etc 8jul2012
  pcn @ 0 > IF  \ from NounPhrase predicate selection; 17jul2012
  ( Store pred-concept-number tag )  pcn @  t @  2 de{ !
    \ 0 pcn !  \ reset to zero after use; 17jul2012
  THEN  \ leaving one search-space in "2 en{" etc 17jul2012
  ( Store "mfn" gender tag. )       mfn @  t @  3 de{ !
  ( Store "dba" tag; 10nov2012 )    dba @  t @  4 de{ !
  ( Store mindcore EXit tag. )      fex @  t @  5 de{ !
  ( Store part of speech "pos".)    pos @  t @  6 de{ !
  ( Store mindcore IN tag. )        fin @  t @  7 de{ !
  ( Store the auditory "aud" tag. ) aud @  t @  8 de{ !
  pov @  35 = IF fex @ oldpsi ! THEN  ( internal pov )
  pov @  42 = IF fin @ oldpsi ! THEN  ( external pov )
  oldpsi @  dex !   \ 16nov2012
  oldpsi @ 250 = IF  \ 250=NICHT (not); 17nov2012
  \ tbev @ 0 > IF   \ if positive be-verb time; 27jul2011
  \ 250 tbev @  3 psi{ !  \ set verb "jux" to NOT 10nov2012
  \ 0 tbev !  \ reset for safety; 27jul2011
    tdzw @ 0 > IF
      250 tdzw @  3 psi{ !  \ set "jux" to NICHT; 27nov2012
      0 tdzw !  \ reset for safety; 27nov2012
    THEN  \ end of test for a positive tdzw; 27nov2012
  \ THEN  \ end of test for a positive tbev; 27jul2011
  \ 250 jux !  \ prepare negational jux; 27nov2012
  THEN  \ end of test for input of 250=NOT; 10nov2012
  oldpsi @ 781 = IF 8 act ! THEN  ( 781=WHAT; 10nov2012 )
  oldpsi @ 791 = IF 8 act ! THEN  ( 791=WHO; 10nov2012 )
  ordo @ 1 = IF
    oldpsi @ 830 = IF  ( 830=DO; 10nov2012 )
      1 kbquiz !
    THEN
  THEN
  oldpsi @ 830 = IF 0 act ! THEN  ( 830=DO; 10nov2012 )
  oldpsi @ 117 = IF 1 act ! THEN  ( 117=THE; 10nov2012 )
  kbcon @  0 > IF  \ if awaiting answer; 2jul2011
    KbRetro  \ retroactively adjust knowledge base;  2jul2011
  THEN  \  2jul2011
  oldpsi @ 250 = IF  \ 250=NOT; 10nov2012
    250 prejux !  \ set flag for verb; 10nov2012
    250 aftjux !  \ set flag for a be-verb; 10nov2012
  THEN  \ end of test for 250=NOT negation; 10nov2012
  oldpsi @ psi !
  DeParser  \ changing to a Germanesque name; 17nov2012
  fyi @ 2 > IF CR
  ."   from OldConcept "
  THEN
  pov @ 42 = IF  ( external pov )
    ReActivate
  THEN
  0 act !
  pov @ 35 = IF  ( internal pov )
    1 match !
  THEN
  pos @ 8 = IF psi @ quverb ! THEN  \ for yes-or-no; 24jun2011
  pos @ 8 = IF oldpsi @ audverb ! THEN  \ for "dba"; 26nov2012
  kbquiz @ 0 > IF
    1 yesorno !
    KbSearch
  THEN
  yesorno @ 0 > IF
    KbSearch
  THEN
  0 pos !  \ Reset no longer above but down here.
; ( http://code.google.com/p/mindforth/wiki/OldConcept )


:  NewConcept ( machine learning of new concepts )
  0 newpsi !
  1 dnr +!  \ increment the deutsch-nummer "dnr"; 17nov2012
  1 nwc +!
  dnr @ newpsi !  \ 17nov2012
  dnr @ stempsi !  \ 17nov2012
  dnr @ psi !  \ concept0number in Psi array;17nov2012
  dnr @ fex !  \ fiber-out; 17nov2012
  dnr @ fin !  \ fiber-in; 17nov2012
  bias @ pos !
  bias @ 8 = IF  \ 4nov2011
    putnum @ num !  \ 4nov2011
    0 putnum !    \ 4nov2011
    0 singflag !  \ prevent carry-over; 4nov2011
    3 dba !  \ default dba=3 third person; 25nov2012
    putdbav @ 0 > IF  \ positive putdbav? 25nov2012
      putdbav @ dba !  \ transfer; 25nov2012
      0 putdbav !  \ reset after use; 25nov2012
    THEN  \ 25nov2012
    b16 @ 69 = IF 1 dba ! THEN  \ 69=E 1st prsn; 25nov2012
    b15 @ 83 =  b16 @ 84 = AND IF 2 dba ! THEN \ 25nov2012
  THEN  \ 4nov2011
  bias @ 5 = IF  \ expecting a noun?  26nov2012
    1 dba !  \ default before changes; 26nov2012
    audverb @  0 > IF  \ preceded by a verb? 26nov2012
      audverb @  800 = NOT IF  \ except be-verbs; 26nov2012
        4 dba !  \ accusative direct object; 26nov2012
      THEN  \ 26nov2012
      0 audverb !  \ reset after use; 26nov2012
    THEN  \ end of test for positive audverb; 26nov2012
  THEN  \ end of test for expecting a noun; 26nov2012
  DeVocab  ( to create a German vocabulary node )
  0 dex !  \ 16nov2012
  0 fin !
  dnr @  dex !  \ 16nov2012
  DeParser  \ using a Germanesque name' 17nov2012
  pos @ 8 = IF dnr @ quverb ! THEN  \ for yes-or-no; 26nov2012
  pos @ 8 = IF psi @ audverb ! THEN  \ for "dba"; 26nov2012
  pos @ 5 = IF  \ if a new noun is encountered; 22oct2011
    dnr @ cogpsi !  \ hold onto new noun for WhatBe; 17nov2012
    instnum @ cognum !  \ keep track of the num(ber); 22oct2011
  THEN  \ end of test of "pos" part-of-speech; 22oct2011
  kbcon @  0 > IF  \ if awaiting answer; 2jul2011
    KbRetro  \ retroactively adjust knowledge base;  2jul2011
  THEN   ( http://www.gnu.org/software/gforth )
  0 pos !
  0 act !
;  \ end of NewConcept; return to AudInput; 25nov2012


\ The visual recognition module of MindForth AI for robots
\ when fully implemented will serve the purpose of letting
\ AI Minds dynamically describe what they see in real time
\ instead of fetching knowledge from the AI knowledge base.
:  VisRecog  ( identification of objects seen by a robot )
  svo3 @ 0 = IF  \ if no direct object is available;
    midway @  t @  DO  \ search for an automatic default
      I       0 de{ @  770 = IF  \ 770=NICHTS; 17nov2012
        I     8 de{ @  aud !  \ hold address for SpeechAct
        LEAVE  ( http://aimind-i.com )
      THEN  ( http://www.vicariousinc.com ) )
    -1 +LOOP \ end of looping through English lexical array
  THEN  ( http://opencv.willowgarage.com )
; ( http://code.google.com/p/mindforth/wiki/VisRecog )


:  AudRecog ( auditory recognition )
  0 audrec !
  0 psi !
  8 act !
  0 actbase !
  0 audpsi !  \ for safety; 18nov2012
  midway @  spt @ DO  ( reinstated in the German AI; 18nov2012 )
    I 0 aud{ @ pho @ = IF  \ If incoming pho matches stored aud0;
      I 1 aud{ @ 0 = IF    \ if matching engram has no activation;
        I 3 aud{ @ 1 = IF  \ if beg=1 on matching no-act aud engram;
       \ audrun @ 1 = IF   \ if comparing start of a word; 8may2010
         audrun @ 2 < IF   \ if comparing start of a word; 8may2010
          I 4 aud{ @ 1 = IF   \ If beg-aud has ctu=1 continuing,
            8 I 1+   1 aud{ !  \ activate the N-I-L character,
            0 audrec !
            I   5 aud{ @ 0 > IF   \ audpsi available? 18nov2012
              I 5 aud{ @ prc !  \ provisional recognition
            THEN  \ end of test for an early audpsi; 18nov2012
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
          I   5 aud{ @ 0 > IF   \ audpsi available? 18nov2012
            I 5 aud{ @ prc !  \ provisional recognition
          THEN  \ end of 2nd test for early audpsi; 18nov2012
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
              I   4 de{ @  0 > IF  \ from Russian AI; 25nov2012
                I 4 de{ @ dba !  \ verb-recognition; 25nov2012
              THEN  \  end of test for dba; 25nov2012
              I 1 aud{ @ actbase !  \ Winner is new actbase.
            THEN  \ End of test for act higher than actbase.
          ELSE  \ part of AudRecog code; 14jul2012
          \ 0 audrec !
            prc @ 0 = IF  0 audrec ! THEN  \ RuAi; 18nov2012
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
  audrec @ 0 =  prc @ 0 >  AND IF  \ 18nov2012
    prc @  audrec !  \ prov. recognition; 18nov2012
  THEN   \ end of test for no rec but provrec; 18nov2012
  audrec @ 0 = IF
      morphpsi @ audrec !
    sublen @ 0 > IF
      len @ sublen @ -  stemgap !
    THEN
    stemgap @ 0 < IF 0 stemgap ! THEN
    stemgap @ 1 > IF 0 subpsi ! THEN
    stemgap @ 1 > IF 0 morphpsi ! THEN
    stemgap @ 1 > IF 0 audrec ! THEN
  \ stemgap @ 3 > IF 0 morphpsi ! THEN  \ 25nov2012
  \ stemgap @ 3 > IF 0 audrec ! THEN    \ 25nov2012
  THEN
  subpsi @ morphpsi !
  0 psibase !
  0 subpsi !
  audrec @ 0 > IF
    stemgap @ 2 > IF
      0 audrec !
    THEN
  THEN   \  http://www.robotik-deutschland.de
  audrec @ 0 = IF  prc @ audrec ! THEN  \ prov rec. 18nov2012
  audrec @ audpsi !
  0 stemgap !  \ safety measure; 22sep2011
; ( http://code.google.com/p/mindforth/wiki/AudRecog )


:  AudMem ( auditory memory channel )
  t @ vault @ > IF
    pho @ 32 > IF
      AudRecog
      audpsi @ 0 = IF  \ from JavaScript Russian AI; 18nov2012
        prc @ 0 > IF prc @ audpsi !  THEN \ prov rec 18nov2012
      \ 0 prc !  \ reset in any case; 18nov2012
      THEN  \ end of test for no audpsi ultimate-tag 18nov2012
    THEN  ( ASCII 32 = SPACE-bar )
  THEN  ( http://pygmy.utoh.org/pygmyforth.html )
    t @ 1-  0 aud{ @  0 = IF  1 beg !  THEN
    t @ 1-  0 aud{ @ 32 = IF  1 beg !  THEN
    pho @  t @  0 aud{ !
    pov @  t @  2 aud{ !
    beg @  t @  3 aud{ !
    ctu @  t @  4 aud{ !
    audpsi @  t @  5 aud{ !  \ including prov rec; 18nov2012
    ctu @ 0 = IF
      audpsi @ 0 > IF
        audpsi @  t @  5 aud{ !
      THEN
      0 audpsi !
    THEN  ( http://home.earthlink.net/~gmayhak/M5_htm.htm )
    pov @ 42 = IF
      pho @ 83 = IF
        0 stempsi !
        wordend @ 1 = IF
            0 t @ 1- 4 aud{ !
        THEN
        0 newpsi !
      THEN
    THEN
    pho @ 32 = IF t @ spt !  THEN
  \ 0 prc !  \ reset prov rec for safety; 24nov2012
; ( http://code.google.com/p/mindforth/wiki/AudMem )


:  AudListen ( preparation for AudInput )
  t @  2 +  tsn !  \ time when awaiting input; test; 1jul2012
  rsvp @  1  DO
    KEY? IF
      KEY pho !
      0 inert !  \ User input cancels "inert" status; 16oct2011
      0 quiet !
      pho @  8 = IF 7 EMIT THEN
      pho @  9 = IF
         400 rsvp !  ( 23dec2009 From Supercomputer mind.frt )
        pho @ 13 = IF  1 lastword !  THEN
        fyi @ 0 = IF CR CR
          TIME&DATE  tsyear ! tsmonth ! tsday !
          tshour ! tsminute ! tssecond !
          ." Transcript of " vrsn @ . \ declare version; 17nov2012
          ." Wotan AI interview at "   \ emphasize name; 17nov2012
          tshour @ . tsminute @ . tssecond @ .
          ." o'clock on " tsday @ .
          tsmonth @  1 = IF ." January "   THEN
          tsmonth @  2 = IF ." February "  THEN
          tsmonth @  3 = IF ." March "     THEN
          tsmonth @  4 = IF ." April "     THEN
          tsmonth @  5 = IF ." May "       THEN
          tsmonth @  6 = IF ." June "      THEN
          tsmonth @  7 = IF ." July "      THEN
          tsmonth @  8 = IF ." August "    THEN
          tsmonth @  9 = IF ." September " THEN
          tsmonth @ 10 = IF ." October "   THEN
          tsmonth @ 11 = IF ." November "  THEN
          tsmonth @ 12 = IF ." December "  THEN
          tsyear @ . 8 EMIT 46 EMIT CR
        THEN
        1 fyi +!
        fyi @ 3 > IF 0 fyi ! THEN
        fyi @ 0 = IF CR ." Normal display mode. Tab 1 = "
          ." Transcript; 2 = Tutorial; 3 = Diagnostic." CR
        THEN
        fyi @ 2 = IF CR
          ."   Tutorial mode reveals the internal "
          ." thinking of the AI Mind." CR CR
        THEN
        fyi @ 3 = IF CR
          ." Diagnostic messages - ignore during input "
          ." until you press ENTER." CR
        THEN
        0  pho !
      THEN
      pho @ 27 = IF
        0 nounval !
        0 lopsi !   0 hipsi !
        CR
        CR ." User Command:  halt" 0 pho ! 0 rjc ! 0 fyi !
        CR ." You may enter .psi or .de or .aud to view "
        ." memory engrams, or " CR ." MainLoop [ENTER] "
        ." to erase memories and restart the Mind."
        CR ." Type 'bye' to quit Forth, EXIT to quit DOS."
        CR
        0 audpsi ! 0 newpsi ! 0 oldpsi ! 0 stempsi !
        1 audrun !     \ 26jul2010 In case AI is run again.
        0 defartcon !  \ 16apr2011 In case AI is run again.
        0 indefartcon ! \ 16apr2011 In case AI is run again.
        0 kbtv !       \ 28sep2010 In case AI is run again.
        0 mfn !        \ 25aug2010 In case AI is run again.
        0 mfnflag !    \ 23aug2010 In case AI is run again.
        0 motjuste !   \ 29aug2010 In case AI is run again.
        0 objold !     \ 12oct2010 In case AI is run again.
        0 ordo !       \ 21dec2009 In case AI is run again.
        0 prsn !       \ 29aug2010 In case AI is run again.
        0 psi1 !       \ 25aug2010 In case AI is run again.
        0 quo !        \ 27dec2009 In case AI is run again.
        0 qup !        \ 28dec2009 In case AI is run again.
        0 subjold !    \  9oct2010 In case AI is run again.
        0 subjpsi !    \  1jan2010 In case AI is run again.
        0 vphract !    \ 21jun2011 In case AI is run again.
        0 whoflag !    \ 23jul2010 In case AI is run again.
        QUIT
      THEN
      pho @ 0 > IF
        pho @ EMIT
      THEN
      pho @ DUP 96 > IF  \ convert input to UPPERCASE
        DUP 123 < IF
          32 -
        THEN
      THEN  pho !  \ save UPPERCASE as pho(neme) again.
      pho @ abc !  \ for transfer to AudBuffer; 12nov2012
      LEAVE
      ELSE
      ."  "
    THEN
    8  EMIT
  LOOP
  pho @ 0 > IF \ if user enters data; 19sep2010
    0 lurk !  \ reset; 19sep2010
  THEN   \ end of test for user entry; 19sep2010
  1 lurk +!   \ test; remove; 19sep2010
; ( http://code.google.com/p/mindforth/wiki/AudListen )


:  AudInput ( accept auditory input )
  0 match !
  0 upnext !
  0 urpsi !
  t @ nlt !
  pov @  42 = IF
    fyi @ 2 = IF
      ."     AudInput calls AudListen "
      ."  (Tab key will slow the AI down)." CR
    THEN
     t @ spt !
     t @ 8 >  IF  .echo  THEN  ( show output of AI )
     CR ." Mensch: "  \ 24nov2012
  THEN
  140 0 DO ( Accept a tweet of 140 characters from Twitter)
    pov @ 35 = IF  ( during internal re-entry )
      pho @ 13 = IF  \ if a CR is declared; 8may2010
        1 audrun !  \ Reset to one at CR end of input.
      THEN  \ end of test for a declared CR; 8may2010
      1 upnext +!
      upnext @ 1 = IF
        obstat @ 0 = IF
          kbpsi @ lopsi !
          0 kbpsi !
          lopsi @ urpsi !
          3535 caller !
          pho @ 64 > IF
            urpsi @ qup @ = IF
              urpsi @ vacpsi ! \ prep to deglobalize; 27sep2010
              urpsi @ psi ! VerbAct
              0 vacpsi !  \ reset for safety; 27sep2010
            THEN
          THEN
          hipsi @ lopsi !
          0 caller !
          0 urpsi !
          1 obstat !
        THEN
      THEN  \ AudInput; 14jul2012
      bias @ 5 = IF  \ If DeParser expects a noun; 17nov2012
        \ Here OutBuffer might be used to detect standard
        \ German indications of singular number, such as
        \ -HEIT -TUM -UNG etc.; 19nov2012
        pho @ 83 = IF  \ If "83=S";  6aug2011
          2 num !  \ Assign plural number; 6aug2011
          2 ocn !  \ Dislodgeable old-concept number; 14oct2011
        THEN  \ Only terminating "S" governs "num" 6aug2011
        pho @  0 > IF   \ Disregard empty pho; 6aug2011
          pho @  32 = NOT IF  \ Disregard SPACE; 6aug2011
            pho @  13 = NOT IF  \ Disregard CR; 6aug2011
              pho @ 83 = NOT IF \ If other than "S"; 6aug2011
               recnum @ 0 > IF  \ if recognized; 4nov2011
                recnum @ num !  \  transfer value; 14jul2012
                recnum @ ocn !  \  transfer value; 14jul2012
               ELSE  \ for non-S words w. no recnum; 16jul2012
                0 num !  \ default non-plural; 14jul2011
                0 ocn !  \ default non-plural; 14jul2012
               THEN  \ end of recognition-test; 4nov2011
              ELSE  \ if there is a recnum; 16jul2012
                recnum @ num !  \ transfer value; 16jul2012
                recnum @ ocn !  \ transfer value; 16jul2012
              THEN  \ If last letter is not "S"; 6aug2011
            THEN  \ End of test for carriage-return 6aug2011
          THEN  \  End of test for SPACE; 6aug2011
        THEN  \ End of test for empty pho; 6aug2011
      THEN  \ End of test for noun-expected; 6aug2011
    THEN  \ end of test for pov "35=#" internal reentry
    pov @ 42 = IF   ( during external input )
      AudListen
      pho @ 0 > IF  \ If a character comes in; 14nov2012
        AudBuffer  \ For external input; 14nov2012
      THEN  \ end of test for a positive "pho"; 14mov2012
      pho @ 0 > IF
        0 kbtv !
        1 upnext +!
        upnext @ 1 = IF
          hipsi @ urpsi !  \ What-do queries require
          hipsi @ lopsi ! \ Preventing a residuum lets
          0 caller !  \ SelfRef answer I DO NOT KNOW
          0 urpsi !  \ if no direct object is active.
        THEN
        400 rsvp !  ( give more time )
      THEN
      I 138 = IF
        rsvp @ 250 > IF 100 rsvp ! THEN
      THEN
      I 139 = IF
        pho @ 0 = IF
          rsvp @ 1 - rsvp !
          rsvp @ 2 < IF 400 rsvp ! THEN
        THEN
      THEN
      pho @ 32 = pho @ 13 = OR IF
        0 phodex !  \ Reset for AudBuffer; 14nov2012
        pho @ 13 = IF 10 EMIT THEN
        prepho @ 83 = IF
          0 t @ 1 - 4 aud{ !
          0 prepho !
        THEN
      THEN
      bias @ 5 = IF  \ If DeParser expects a noun; 17nov2012
        pho @ 83 = IF  \ If "S"
          2 num !  \ Assign plural number; 26may2011
        THEN  \ Only terminating "S" governs "num" 26may2011
        pho @  0 > IF   \ Disregard empty pho;  26may2011
          pho @  32 = NOT IF  \ Disregard SPACE; 26may2011
            pho @  13 = NOT IF  \ Disregard CR; 26may2011
              pho @ 83 = NOT IF \ If other than "S" 26may2011
                0 num !  \ Let "0" be default singular; 4nov2011
                singflag @ 1 = IF  \ article "a"? 4nov2011
                  1 num !  \ Assume singular number; 26may2011
                THEN  \ end of test to override default; 4nov2011
              THEN  \ If last letter is not "S"; 26may2011
            THEN  \ End of test for carriage-return 26may2011
          THEN  \  End of test for SPACE; 26may2011
        THEN  \ End of test for empty pho;  26may2011
      THEN  \ End of test for noun-expected; 26may2011
      bias @ 8 = IF  \ If DeParser expects a verb; 17nov2012
        b16 @ 69 = IF  \ final ASCII 69=E? 17nov2012
          1 num !  \ singular verb form; 17nov2012
          1 dba !  \ first person verb form; 17nov2012
          8 pos !  \ part of speech is 8=verb; 17nov2012
        THEN  \ end of test for final 69=E; 17nov2012
      THEN  \ End of test for verb-expected; 17nov2012
    THEN  \ End of test for external input
    pho @  0 > IF
      1 t +!
    THEN
    I 139 = IF  \ near end of input loop? 16oct2011
      1 inert +!  \  increment inert-flag by one; 16oct2011
    THEN  \ end of test for near-end of wait; 16oct2011
    pho @ 13 = IF  \ ASCII carriage-return CR; 26nov2012
       1 audrun !  \ Reset to one at CR end of input.
       1 beg !
      13 eot !
       1 lastword !
      32 pho !  10 EMIT  CR  \ 7sep2011
       0 prc !  \ provisional recognition; 26nov2012
       0 proxcon !  \ reset at end of input; 7sep2011
       1 quiet !
       0 seqneed !  \ test; 30jun2012
    THEN   ( http://www.inventio.co.uk )
    pho @ 27 =  IF
      CR ." AudInput: halt"  0 pho !  0 fyi !  0 nounval !
      CR ." You may enter .psi .de .aud to view memory "
      ." engrams, or " CR ." MainLoop [ENTER] to erase "
      ." memories and run the AI again."
      0 lopsi !  0 hipsi !
      0 audpsi ! 0 newpsi ! 0 oldpsi ! 0 stempsi !
      QUIT
    THEN
    pho @ 32 = IF
      prepho @ penultpho !
      1 audrun !  \ Reset to unity at end of a word.
      1 ordo +!
      audpsi @ urpsi !
      ordo @ 1 = IF audpsi @ firstword ! THEN  \ 19aug2011
      0 upnext !
      t @  spt !
      t @  1 - tult !
      0  tult @  4 aud{ !
      audpsi @  0 >  IF
        0 sublen !
        onset @ aud !
        0 onset !
  audpsi @  tult @  5 aud{ !
        pov @ 42 = IF
          tult @ 0 aud{ @ 83 = IF
       tult @ 1- 5 aud{ @ audpsi @ = NOT IF
              0  tult @ 1- 4 aud{ !
            THEN
   audpsi @  tult @ 1- 5 aud{ !
          THEN
        THEN
        audpsi @ hipsi !
        audpsi @ oldpsi !
        OldConcept
        eot @ 13 = IF
          35 pov !
        THEN
        0 psi !
        0 audpsi !
        0 aud !
      ELSE
        len @ 0 > IF
          onset @ aud !
          hipsi @ lopsi !
          1 wordend !
          NewConcept
          psi @ hipsi !
            dnr @  tult @  5 aud{ !  \ 17nov2012
     dnr @  tult @ 1- 5 aud{ !  \ 17nov2012
            dnr @ retropsi !  \ 17nov2012
        THEN
      THEN
      AudDamp
      0 len !
      0 aud !
      eot @ 13 = IF
        5 bias !
      THEN
      0 psi !
    THEN
    1 beg !
    1 ctu !
    spt @ 1 + onset !
      t @  onset @  = IF  1 beg !  ELSE  0 beg !  THEN
    pho @ 32 > IF
      1 len +!
      AudMem
    THEN
    eot @ 13 = IF
      5 bias !
      1 quiet !
    THEN
    eot @  0 > IF
      eot @ 14 = IF
        1 quiet !
        0 eot !
        0 pho !
        LEAVE
      THEN
      14 eot !
    THEN
    pho @ 0 > IF
      pho @ prepho !
    THEN
    0 pho !
  LOOP
  hipsi @ kbpsi !
  0 newpsi !
  0 wordend ! 
; ( http://code.google.com/p/mindforth/wiki/AudInput )


:  SensoryInput ( sensory input channels )
 ( SMELL  -- normal sensory stub for later implementation )
 ( VISION -- normal sensory stub for seed AI expansion )
 ( TOUCH  -- normal haptics stub for cybernetic organisms )
 ( TASTE  -- normal sensory stub for cyborg alife )
 ( SYNAESTHESIA -- an option in a multisensory AI )
     fyi @ 2 = IF
 ."   SensoryInput calls AudInput." CR
     THEN
   AudInput  ( for entry or reentry of phonemic ASCII )
 ( COMPASS  -- exotic sensory stub for use in robots )
 ( GEIGER   -- exotic: Geiger counter )
 ( GPS      -- exotic: Global Positioning System )
 ( INFRARED -- exotic )
 ( RADAR    -- exotic: RAdio Detection And Ranging )
 ( SONAR    -- exotic: SOund Navigation And Ranging )
 ( VSA      -- exotic: Voice Stress Analyzer lie detector )
 ( Wi-Fi    -- exotic: 802.11 wireless fidelity )
; ( http://code.google.com/p/mindforth/wiki/SensoryInput )


\ DeBoot the (Deutsch=German) bootstrap holds the innate
\ vocabulary of German words for the DeKi AI to think with.
\ Some words like "IHR" have multiple instantiations so that
\ the software may use linguistic parameters to find each one.
\ POS: 1=adj 2=adv 3=conj 4=interj 5=noun 6=prep 7=pron 8=verb
:  DeBoot ( German bootstrap of initial concepts )
  0 act ! 0 jux ! 35 pov ! 0 t ! t @ spt !
  ." clearing memory"
  CR ." There is no warranty for what this software does."
 ( IRRTUM -- "error" first word so any bug will announce itself )
    1 t !  73 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ I
    2 t !  82 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ R
    3 t !  82 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ R
    4 t !  84 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ T
    5 t !  85 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ U
    6 t !  77 pho !  0 beg !  0 ctu ! 523 audpsi ! AudMem \ M
523 dnr !   3 mfn !  1 dba ! 123 fex !  5 pos ! 523 fin !  1 aud !
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

( 1107: 525=KINDER  "children" noun; plural; 5dec2011 )
 1108 t !  75 pho !  1 beg !   1 ctu !   0 audpsi ! AudMem \ K
 1109 t !  73 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ I
 1110 t !  78 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ N
 1111 t !  68 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ D
 1112 t !  69 pho !  0 beg !   1 ctu !   0 audpsi ! AudMem \ E
 1113 t !  82 pho !  0 beg !   0 ctu ! 525 audpsi ! AudMem \ R
525 dnr !   0 mfn !  1 dba ! 525 fex ! 5 pos ! 525 fin ! 1108 aud !
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

( 1156: 848=SPIELT "plays" 2nd pers. sing; 28nov2012 )
 1157 t !  83 pho !  1 beg !  1 ctu !   0 audpsi ! AudMem \ S
 1158 t !  80 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ P
 1159 t !  73 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ I
 1160 t !  69 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ E
 1161 t !  76 pho !  0 beg !  1 ctu !   0 audpsi ! AudMem \ L
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
( Declaration of "vault" must reflect final DeBoot "t".)
  1 t +!
    t @  vault !
    t @  tov !
  1 t +!
    t @ nlt !  ( nlt may be basis for DAMP functions )
  900 dnr !  \ segregate parts of speech by century; 16nov2012
  5 bias !
  0 lurk !   \ prepare to auto-start thinking; 19sep2010
  0 num !
  0 mfn !  \ Prevent carry-over.
  0 mfnflag !  \ Prevent carry-over; 23aug2010
  0 nwc !
  0 pho !
  0 pre !  0 seq !
  0 putnum !  \ prevent carry-over;  4nov2011
; ( http://code.google.com/p/mindforth/wiki/EnBoot )


:  KbTraversal ( reactivate KB concepts )
  35 pov !
  kbtv @ 4 > IF  1 kbtv !  THEN
\ CR ." Knowledge base traversal activating " \ 25nov2012
  CR ." Time = " t @ . ." KbTraversal activates " \ 29nov2012
  kbtv @ 1 = IF
     1 kbyn !   \ for AskUser Y/N query subject; 24jun2011
    707 nacpsi ! \ 707=DU (you) activation-psi; 18nov2012
    707 qusub !  \ in case a query will be made; 10nov2012
    707 subjpsi !  \ a test to help WhoBe; 10nov2012
     1 subjnum !  \ for correct be-verb; 12oct2011
     2 prsn !     \ for correct be-verb; 12oct2011
    ." concept #707=DU (you)" CR  \ 25nov2012
    62 nounval !
    NounAct
    0 nacpsi !
  THEN
  kbtv @ 2 = IF  \ for use in ThInk module; 14oct2011
     2 kbyn !   \ for AskUser Y/N query subject; 24jun2011
    ." concept of ROBOTS" CR  ( 25nov2012 )
    571 subjpsi ! \ external tagging as subject; 23nov2012
    571 qusub !  \ in case a query will be made; 23nov2012
    0 nacpsi !
  THEN
  kbtv @ 3 = IF
     3 kbyn !   \ for AskUser Y/N query subject; 24jun2011
    701 nacpsi !  \ 701=ICH (I) activation-psi; 18nov2012
    ."  concept of 701=ICH " CR     ( 25nov2012 )
    701 qusub !  \ in case a query will be made; 10nov2012
    701 subjpsi ! \ external tagging as subject; 10nov2012
    NounAct
    0 nacpsi !
  THEN
  kbtv @ 4 = IF
     4 kbyn !   \ for AskUser Y/N query subject; 24jun2011
   533 nacpsi ! \ 533=GOTT (God) activation-psi; 23nov2012
    ." concept of GOD" CR   ( 25nov2012 )
    533 qusub !  \ in case a query will be made; 23nov2012
    533 subjpsi ! \ external tagging as subject; 23nov2012
    62 nounval !
    NounAct
    0 nacpsi !
  THEN  ( http://www.quartus.net )
  42 pov !
; ( http://code.google.com/p/mindforth/wiki/KbTraversal )


:  ReJuvenate ( recycle oldest memory spaces )
  fyi @ 2 = IF
    CLS
  THEN
  0 edge !
  CR 1 rjc +!
  ." Please wait as memories migrate in ReJuvenate cycle #"
  rjc @ . CR
  t @ 2 +  coda @ vault @ +  DO
    I  jrt !
    jrt @  coda @ -  jrt !
    edge @ 1 = IF
      I 0 psi{ @  jrt @  0 psi{ !  0 I 0 psi{ !
      I 1 psi{ @  jrt @  1 psi{ !  0 I 1 psi{ !
      I 2 psi{ @  jrt @  2 psi{ !  0 I 2 psi{ !
      I 3 psi{ @  jrt @  3 psi{ !  0 I 3 psi{ !
      I 4 psi{ @  jrt @  4 psi{ !  0 I 4 psi{ !
      I 5 psi{ @  jrt @  5 psi{ !  0 I 5 psi{ !
    \ Next line adjusts tqv by minus-coda; 14aug2012
      I 6 psi{ @ coda @ -  jrt @  6 psi{ !  0 I 6 psi{ !
      I 7 psi{ @  jrt @  7 psi{ !  0 I 7 psi{ !
      I 8 psi{ @  jrt @  8 psi{ !  0 I 8 psi{ !
    THEN
    edge @  1 =  IF
      de8 @  1 <  IF  0 de8 !  THEN  \ 17nov2012
      I 0 de{ @  jrt @  0 de{ !  0 I 0 de{ !
      I 1 de{ @  jrt @  1 de{ !  0 I 1 de{ !
      I 2 de{ @  jrt @  2 de{ !  0 I 2 de{ !
      I 3 de{ @  jrt @  3 de{ !  0 I 3 de{ !
      I 4 de{ @  jrt @  4 de{ !  0 I 4 de{ !
      I 5 de{ @  jrt @  5 de{ !  0 I 5 de{ !
      I 6 de{ @  jrt @  6 de{ !  0 I 6 de{ !
      I 7 de{ @  jrt @  7 de{ !  0 I 6 de{ !  \ 16nov2012
      I 8 de{ @  de8 !                        \ 17nov2012
          de8 @  vault @ < IF
          de8 @  jrt @  8 de{ !  0 I 8 de{ !  THEN
          de8 @  coda @  vault @ +  > IF      \ 16nov2012
          de8 @  coda @ -  jrt @ 8 de{ !      \ 16nov2012
          THEN               0 I 8 de{ !      \ 16nov2012
    THEN
    edge @  1 = IF
      I 0 aud{ @  jrt @  0 aud{ !
      I 1 aud{ @  jrt @  1 aud{ !
      I 2 aud{ @  jrt @  2 aud{ !
      I 3 aud{ @  jrt @  3 aud{ !
      I 4 aud{ @  jrt @  4 aud{ !
      I 5 aud{ @  jrt @  5 aud{ !
        fyi @ 1 > IF
                  jrt @  0 aud{ @ EMIT
        THEN
    THEN
    edge @ 0 = IF
     32 jrt @ 0 aud{ !
      0 jrt @ 1 aud{ !
            I 2 aud{ @ 123 = IF  1 edge !  THEN
      0 jrt @ 2 aud{ !
      0 jrt @ 3 aud{ !
      0 jrt @ 4 aud{ !
      0 jrt @ 5 aud{ !
      0 jrt @ 0 de{ !
      0 jrt @ 1 de{ !
      0 jrt @ 2 de{ !
      0 jrt @ 3 de{ !
      0 jrt @ 4 de{ !
      0 jrt @ 5 de{ !
      0 jrt @ 6 de{ !
      0 jrt @ 7 de{ !
      0 jrt @ 8 de{ !  
      0 jrt @ 0 psi{ !
      0 jrt @ 1 psi{ !
      0 jrt @ 2 psi{ !
      0 jrt @ 3 psi{ !
      0 jrt @ 4 psi{ !
      0 jrt @ 5 psi{ !
      0 jrt @ 6 psi{ !
      0 jrt @ 7 psi{ !
      0 jrt @ 8 psi{ !  \ for "tqv"; 12oct2011   
    THEN
  LOOP
  jrt @  t !
  cns @    t @  DO
   32  I 0  aud{ !
    0  I 1  aud{ !
    0  I 2  aud{ !
    0  I 3  aud{ !
    0  I 4  aud{ !
    0  I 5  aud{ !
    0  I 0   de{ !
    0  I 1   de{ !
    0  I 2   de{ !
    0  I 3   de{ !
    0  I 4   de{ !
    0  I 5   de{ !
    0  I 6   de{ !
    0  I 7   de{ !
    0  I 8   de{ !
    0  I 0  psi{ !
    0  I 1  psi{ !
    0  I 2  psi{ !
    0  I 3  psi{ !
    0  I 4  psi{ !
    0  I 5  psi{ !
    0  I 6  psi{ !
    0  I 7  psi{ !
    0  I 8  psi{ !
  LOOP
  t @ 32 - tov !  \ 12jan2010 Avoid truncating thoughts.
  CR CR ." End of ReJuvenate #" rjc @ .
\ ." in the AI Mind display for science museum exhibits."
  ." in the Wotan Supercomputer Artificial Intelligence."
  CR ." Tab key cycles through Normal, Transcript, "
   ." Tutorial, Diagnostic display-modes. "  CR
  1 kbtv +!
  kbtv @ 0 > IF
    CR ." For lack of human input, "
    ." ReJuvenate calls KbTraversal" CR
    KbTraversal
  THEN  ( http://ronware.org/reva )
  rsvp @ rjc @ - rsvp !
  rsvp @ 2 < IF 2 rsvp ! THEN  \ 23dec2009 Maintain speed.
; ( http://code.google.com/p/mindforth/wiki/ReJuvenate )


:  SpeechAct ( output of a word as text or sound )
  aud @ 0 = IF 1 aud ! THEN \ default to ERROR; 21jul2011
  fyi @ 2 = IF CR THEN
  0 audstop !   ( Initially false value of flag )
  0 pho !       ( Lest pho already be at 32 )
  aud @ onset !  ( onset of a word is its recall-vector )
  aud @ t2s !
  40  1  DO
    t2s @  0  aud{ @ pho !
    pho @ 32 = NOT IF
      pho @ EMIT  ( say or display "pho" )
      pho @ lastpho !
    THEN   \ End of test for pho=32 space-bar; 30aug2010 
    pho @ 32 = IF  \ but instead of a blank space; 30aug2010
      lastpho @ 83 = NOT IF \ not after "S"; 30aug2010
        flex1 @ 0 > IF  \ using shorter variable; 11sep2011
          flex1 @ pho !  \ append inflection; 11sep2011
          0 flex1 !  \ reset for safety; 11sep2011
        THEN  ( http://aimind-i.com )
        1 spacegap !
        0 vpos !
      THEN  \ End of test for previous "S"; 30aug2010
      pho @ EMIT  ( say or display "pho" )
      1 audstop !
    THEN  \ end of test for 32=space; 30aug2010
    35 pov !  ( internal point-of-view "#" like mindgrid )
    AudInput  ( for reentry of thought back into a mind )
    audstop @ 1 = IF
      spacegap @ 1 = IF
        32 pho !
        1 audrun ! \ resetting at end of internal word.
        AudInput
        0 spacegap !
      THEN  ( http://www.speechapi.com )
      LEAVE
    THEN  ( http://aigroup.narod.ru )
    t2s @  1+  t2s !
    t2s @  4 aud{ @ 0 = IF 32 pho ! THEN ( If end of word )
    match @ 1 = IF
      0 match !
      LEAVE
    THEN
  LOOP
  0 aud !  \ Avoid unwarranted carry-over of value; 11sep2011
  0 match !
  0 obstat !
; ( http://code.google.com/p/mindforth/wiki/SpeechAct )


:  SayYes ( to utter 4870=JA "yes" in response; 18nov2012 )
  midway @  t @  DO
    I       0 de{ @ 470 = IF  \ 3-digit; 18nov2012
      I     8 de{ @  aud !  \ with dba; 10nov2012
      LEAVE
    THEN  ( http://aimind-i.com )
  -1 +LOOP
  SpeechAct
  0 kbquiz !
  0 yesorno !
; ( http://code.google.com/p/mindforth )


:  DeArticle ( select "a" or "the" before a noun; 17nov2012 )
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
            I     8 de{ @  aud !  \ with dba; 10nov2012
            LEAVE
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


:  DeAdjective ( insert an adjective into a sentence )
  adjcon @ 1 = IF  \ activation spreads to an adjective?
    ( find and speak the most active adjective; 16sep2011 )
  THEN  ( http://www.colorforth.com )
; ( http://code.google.com/p/mindforth )


:  AuxVerb ( auxiliary Verb )
  subjnum @ 1 =  prsn @ 3 = AND IF  \ 19jul211
    midway @  t @  DO
      I       0 de{ @ 830 = IF  \ 830=DO; 10nov2012
        I     2 de{ @ 1 = IF  \ singular? 10nov2012
          I   4 de{ @ 3 = IF  \ 3rd person? 10nov2012
            I   8 de{ @  aud !  \ 10nov2012
            LEAVE
          THEN  \ end of test for third person; 10nov2012
        THEN  \ end ofbtest for num=1 singular; 10nov2012
      THEN  \ end of test for 830=DO; 10nov2012
    -1 +LOOP
    SpeechAct  \ Say word starting at "aud" value; 20jul2011
    830 urpsi !   \ 10nov2012
    51 caller !
    PsiDamp
    0 caller !
  ELSE  \ all other cases except 3rd prsn sing; 25jun2011
    midway @  t @  DO  \ may need parameters! 10nov2012
      I       0 de{ @  830 = IF  \ 830=DO; 10nov2012
        I     8 de{ @  aud !  \ 10nov2012
        LEAVE
      THEN
    -1 +LOOP
    SpeechAct
    fyi @ 2 > IF CR
      ."   from AuxVerb after speaking of DO, "
      ." psiDamping concept #830 DO"
    THEN
    830 urpsi !  \ 830=DO; 10nov2012
    51 caller !
    PsiDamp
    0 caller !
  THEN  \ end of test for both sing & 3rd prsn; 25jun2011
; ( http://code.google.com/p/mindforth/wiki/AuxVerb )


:  WhatAuxSVerb ( What DO Subjects Verb; 13jun2011 )
  midway @  t @  DO
    I       0 de{ @ 781 = IF  \ 781=WHAT  10nov2012
      I     8 de{ @  aud !   \ 10nov2012
      LEAVE
    THEN
  -1 +LOOP
  SpeechAct  \ Say word starting at "aud" value; 20jul2011
  781 urpsi !  \ 781=WHAT; 10nov2012
  PsiDamp
  AuxVerb  \ Say DOES or DO depending on num(ber) 20jul2011
  0 motjuste !
  midway @  t @  DO
    I       0 de{ @  topic @ = IF  \ 13jun2011
      I     8 de{ @ aud !  \ 10nov2012
      LEAVE
    THEN  ( http://sourceforge.net/projects/calforth )
  -1 +LOOP
  topic @ urpsi !  \ 14aug2011
  PsiDamp
  SpeechAct
  verbpsi @ 0 = IF 830 verbpsi ! THEN \ 830=DO DeFault 10nov2012
  verbpsi @ unk !  \ use a short "unk"; 28aug2011
  verbpsi @ 800 = IF  \ 800 cover AM IS ARE BE; 10nov2012
    830 verbpsi !  \ replace be-verbs with 830=DO; 10nov2012
  THEN \ end of default switching be-verb to 830=DO; 10nov2012
  midway @  t @  DO
    I       0 de{ @  verbpsi @ = IF  \ 13jun2011
      I     2 de{ @  2 = IF  \ as if infinitive; 13jun2011
        I     8 de{ @  aud !   \ 16nov2012
        LEAVE
      THEN  \ End of test for plural as if infinitive
    THEN
  -1 +LOOP
  aud @ 0 = IF  \ if no plural accept singular 14aug2011
    midway @  t @  DO  \ search English vocab; 14aug2011
      I       0 de{ @  verbpsi @ = IF  \ 14aug2011
        I   8 de{ @  aud !  \ for SpeechAct; 10nov2012
        LEAVE  \ one engram is enough; 14aug2011
      THEN  \ end of test for verbpsi; 14aug2011
    -1 +LOOP   \ end of backwards search loop; 14aug2011
  THEN  \ end of test for no engram found; 14aug2011
( http://www.intelligent-systems.com.ar/intsyst/proposedBrain.htm )
  SpeechAct
  verbpsi @ urpsi !  \ 13jun2011
  PsiDamp
; ( http://code.google.com/p/mindforth )


:  WhatAuxSDo ( What DO Subjects DO )
  topic @ 0 >  qusub @ 0 =  AND IF  \ no qusub? 23nov2012
    topic @  qusub !  \ suply a query-subject; 23nov2012
  THEN  \ end of test for topic but no qusub; 23nov2012
  midway @  t @  DO  \ Start question with "WAS" (what).
    I       0 de{ @ 781 = IF  \ 781=WAS (what); 25nov2012
      I     8 de{ @  aud !  \ 10nov2012
      LEAVE
    THEN
  -1 +LOOP
  SpeechAct
  781 urpsi !  \ 781=WAS (what) for PsiDamp; 15nov2012
  42 caller !
  PsiDamp
  0 caller !
  midway @  t @  DO  \ find form of 830=TUN (do); 25nov2012
    I       0 de{ @ 830 = IF  \ 830=DO; 10nov2012
      I     2 de{ @ subjnum @ = IF  \ number; 23nov2012
        I   4 de{ @ prsn @ = IF  \ person; 23nov2012
          I 8 de{ @  aud !  \ 10nov2012
          LEAVE
        THEN  \ end of test for person; 23nov2012
      THEN  \ end of test for number; 23nov2012
    THEN  \ end of search for 830=TUN (do); 23nov2012
  -1 +LOOP
  SpeechAct
  subjnum @ 1 = IF   \ for singular subject; 14oct2011
    topic @ motjuste !  \ test; 14oct2011
    0 ghost !  \ test; 14oct2011
    1 nphrnum !  \ required for "A"' 14oct2011
    1 indefartcon !  \ to say "A"; 14oct2011
    DeArticle  \ 17nov2012
  THEN  \ end of test for singular subject; 14oct2011
  midway @  t @  DO \ look for the query-subject; 23nov2012
    I       0 de{ @  topic @ = IF
      I     2 de{ @  subjnum @ = IF  \ agreement? 14oct2011
  \ For German, next line might accept 1 or 4 dba 23nov2012
        I   4 de{ @  1 = IF  \ dba=1 nominative? 21nov2012
          I   8 de{ @ aud !  \ 10nov2012
          LEAVE  \ only after finding match; 14oct2011
        THEN  \ end of test for nominativwe; 21nov2012
      THEN  \ end of grammatical-number test; 14oct2011
    THEN
  -1 +LOOP
  topic @ urpsi !   \ 14aug2011
  42 caller !
  PsiDamp
  SpeechAct
; ( http://code.google.com/p/mindforth/wiki/WhatAuxSDo )


:  WhoBe  ( for asking WER BIN/BIST/IST/SIND/SEID 25nov2012 )
  1 moot !  \ prevent associative tagging inside query; 24oct2011
  0 tqv !  \ prevent spurious carry-over values;  1aug2012
  topic @ 0 > IF topic @ qusub ! THEN  \ review; 30jul2011
  midway @  t @  DO  \ Say "WER" (who); 21nov2012
    I       0 de{ @ 791 = IF  ( 791=WHO; 10nov2012 )
      I     4 de{ @   1 = IF  ( nominative? 21nov2012 )
        I   8 de{ @  aud !  \ 10nov2012
        LEAVE
      THEN  \  end of test for dba=1 nominative; 21nov2012
    THEN
  -1 +LOOP  \ http://www.ki-profs.de
  SpeechAct
  8766 caller !  \ ASCII 87=W 66=B; test; 26sep2010
  55 urpsi !  \ Designate concept to be psi-damped; 19aug2010
  PsiDamp
  0 caller !  \ reset after use; 26sep2010
  qusub @ 701 = IF 1 prsn ! THEN \ 1st person "I" 10nov2012
  qusub @ 731 = IF 1 prsn ! THEN \ 1st person WE  10nov2012
  qusub @ 707 = IF 2 prsn ! THEN \ 2nd person YOU 10nov2012
  qusub @ 737 = IF 2 prsn ! THEN \ 2nd person YOU 10nov2012
  qusub @ 713 = IF 3 prsn ! THEN \ 3rd person HE  10nov2012
  qusub @ 719 = IF 3 prsn ! THEN \ 3rd person SHE 10nov2012
  qusub @ 725 = IF 3 prsn ! THEN \ 3rd person IT  10nov2012
  qusub @ 743 = IF 3 prsn ! THEN \ 3rd person THEY 10nov2012
  prsn @ 3 = IF  \ only for 3rd person; 1sep2010
    midway @  t @  DO  \ Say "IS" after "WHO"; 19aug2010
      I       0 de{ @ 800 = IF  ( 800=BE; 10nov2012 )
        I     2 de{ @ 1 = IF  ( singular? 10nov2012 )
          I   4 de{ @ 3 = IF  ( 3rd person? 10nov2012 )
            I 8 de{ @  aud !  \ 10nov2012
            LEAVE
          THEN  \ end of test for 3rd person "IS" 10nov2012
        THEN  \ end of test for singular; 10nov2012
      THEN  \ end of test for be-verb; 10nov2012
    -1 +LOOP
    SpeechAct   \ to say "IS"; 17aug2010
    0 mfn !  \ test; remove; 25aug2010
    0 mfnflag ! \ Reset after use; 19aug2010
  THEN  \ end of test for prsn=1; 1sep2010
  qusub @ 701 = IF  ( I; 10nov2012 )
    1 prsn !  \ first person; 1sep2010
    1 nphrnum !  \ singular; 1sep2010
    midway @  t @  DO
      I       0 de{ @ 800 = IF   ( 800=BE; 10nov2012 )
        I     2 de{ @ 1 = IF   ( singular? 10nov2012 )
          I   4 de{ @ 1 = IF   ( 1st person? 10nov2012 )
            I     8 de{ @  aud !  \ 10nov2012
            LEAVE
          THEN  \ end ofb test for first person; 10nov2012
        THEN  \ end of test for singular 800=BE; 10nov2012
      THEN  \ end of test for be-verb; 10nov2012
    -1 +LOOP
    SpeechAct   \ to say "AM"; 17oct2011
  THEN    \ 9aug2010
\ qusub @ 701 = IF  \ treat ME like 701=I; 10nov2012
\   midway @  t @  DO
\     I       0 de{ @ 800 = IF   ( 800=BE; 10nov2012 )
\       I     2 de{ @ 1 = IF   ( singular? 10nov2012 )
\         I   4 de{ @ 1 = IF   ( 1st person? 10nov2012 )
\           I     8 de{ @  aud !  \ 10nov2012
\           LEAVE
\         THEN  \ end of test for first person; 10nov2012
\       THEN  \ end of test for singular; 10nov2012
\     THEN   \ end of test for be-verb; 10nov2012
\   -1 +LOOP
\   SpeechAct  \ moved inside the IF-clause; 10aug2010
\ THEN    \ 9aug2010
  qusub @ 707 = IF  ( 707=YOU; 10nov2012 )
    2 prsn !  \ second person; 1sep2010
    midway @  t @  DO
      I       0 de{ @ 800 = IF  ( 800=BE; 10nov2012 )
        I     2 de{ @ 1 = IF  ( singular? 10nov2012 )
          I   4 de{ @ 2 = IF  ( 2nd person? 10nov2012 )
            I     8 de{ @  aud !  \ 10nov2012
            LEAVE
          THEN  \ end of test for 2nd person; 10nov2012
        THEN  \ end of test for singular; 10nov2012
      THEN  \ end of test for be-verb; 10nov2012
    -1 +LOOP
    SpeechAct   \ to say "ARE"; 10aug2010
  THEN    \ 9aug2010
  qusub @ 713 = IF  ( 713=HE; 10nov2012 )
    3 prsn !  \ third person; 1sep2010
    1 nphrnum !  \ singular; 1sep2010
    midway @  t @  DO
      I       0 de{ @ 800 = IF  ( 800=BE; 10nov2012 )
        I     2 de{ @ 1 = IF  ( singular? 10nov2012 )
          I   4 de{ @ 3 = IF  ( 3rd person? 10nov2012 )
            I 8 de{ @  aud !  \ 10nov2012
            LEAVE
          THEN  \ enmd of test for 3rd person; 10nov2012
        THEN  \ end of test for singular; 10nov2012
      THEN  \ end of test for be-verb; 10nov2012
    -1 +LOOP
  THEN  ( http://minforth.net.ms )
  midway @  t @  DO  \ search for who-query subject; 23aug2010
    I       0 de{ @  qusub @ = IF  \ if qusub found; 3oct2010
      I     4 de{ @  1 = IF  \ dba=1 nominative? 21nov2012
        I   8 de{ @  aud !  \ recall-tag; 10nov2012
        LEAVE   \ one exemplar is enough; 23aug2010
      THEN  \ end of test for dba=1 nominative qusub 21nov2012
    THEN   \ end of test for subject; 23aug2010
  -1 +LOOP  \ end of search-loop; 23aug2010
  SpeechAct  \ speak (WHO IS) qusub query-subject; 3oct2010
  0 moot !  \ end of not tagging query-concepts; 24oct2011
; ( http://code.google.com/p/mindforth )


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
    I       0 de{ @ 781 = IF  \ 781=WAS (what); 18nov2012
      I     8 de{ @  aud !  \ 10nov2012
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
      I       0 de{ @ 800 = IF  \ 800=BE; 10nov2012
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
      I       0 de{ @ 800 = IF  \ 800=BE; 23nov2012
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
      I       0 de{ @ 800 = IF  \ 800=BE; 10nov2012
        I     2 de{ @ 1 = IF    \ singular? 10nov2012
          I   4 de{ @ 3 = IF    \ 3rd pers? 23nov2012
            I     8 de{ @  aud !  \ 10nov2012
         \  1 topicnum !  \ If "IS" prevent "ARE"; 21jul2012
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
\ topicnum @ 2 =  prsn @ 2 =  OR IF  \ test; 19sep2010
  topicnum @ 2 =  IF  \ plural? 23nov2012
    midway @  t @  DO
      I       0 de{ @ 800 = IF  \ 800=BE; 10nov2012
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


:  AskUser  ( outputs questions of a speculative nature )
  kbyn  @ 0 = IF  \ insurance; 24jun2011
   571 qusub !    \ start with ROBOTS; 10nov2012
     3 prsn !     \ third person; 24jun2011
     2 numsubj !  \ plural; 24jun2011
     2 putnum !   \ plural for InStantiate; test; 5aug2011
     2 subjnum !  \ plural; 21jul2011
  THEN  \ end of test for no query-subject 24jun2011
  ynverb @ 0 = IF  \ only ask y/n question once; 24jun2011
   quverb @ ynverb !  \ isolate at start; 24jun2022
   nphrnum @ 2 = IF  \ if plural trigger; test; 24jun2011
    kbyn @ 1 = IF  \ from KbTraversal; 24jun2011
     707 qusub !  \ 707=YOU for yes-or-no query 10nov2012
       2 prsn !     \ YOU is second person; 24jun2011
       1 numsubj !  \ assume YOU is singular; 24jun2011
       1 subjnum !  \ assume YOU is singular; 21jul2011
    THEN  \ end of test for KbTraversal; 24jun2011
    kbyn @ 2 = IF  \ from KbTraversal; 24jun2011
    571 qusub !  \ use ROBOTS as a test item; 10nov2012
      3 prsn !     \ third person; 24jun2011
      2 numsubj !  \ plural; 24jun2011
      2 subjnum !  \ plural; 21jul2011
    THEN  \ end of test for KbTraversal; 24jun2011
    kbyn @ 3 = IF  \ from KbTraversal; 24jun2011
     701 qusub !  \ 701=I for yes-or-no query 10nov2012
       1 prsn !     \ I is first person; 24jun2011
       1 numsubj !  \ since I is singular; 24jun2011
       1 subjnum !  \ since "I" is singular; 21jul2011
    THEN  \ end of test for KbTraversal; 24jun2011
    kbyn @ 4 = IF  \ from KbTraversal; 24jun2011
     533 qusub !  \ 533=GOD for yes-or-no query 10nov2012
       3 prsn !     \ GOD is third person; 24jun2011
       1 numsubj !  \ GOD is singular; 24jun2011
       1 subjnum !  \ GOD is singular; 21jul2011
    THEN  \ end of test for KbTraversal; 24jun2011
     AuxVerb       \ to say DO or DOES; 24jun2011
     midway @  t @  DO  \ search English vocab; 24jun2011
       I       0 de{ @  qusub @ = IF  ( kbtv )
         I     8 de{ @  aud !  \ 10nov2012
         LEAVE
       THEN
     -1 +LOOP
     SpeechAct   \ to say the subject; 24jun2011
     t @ tkbn !  \ if engram is to be changed; 2jul2011
     qusub @ nacpsi !  \ transfer activand; 25jun2011
     62 nounval !  \ prime NounAct; 24jun2011
     NounAct  \ activate the query subject; 24jun2011
     midway @  t @  DO  \ search English vocab; 24jun2011
       I       0 de{ @  ynverb @ = IF  ( yes-or-no verb )
         I     2 de{ @  2 = IF  \ as if infinitive; 24jun2011
           I   8 de{ @  aud ! \ fetch recall-vector 10nov2012
           LEAVE  \ one engram is enough; 24jun2011
         THEN  \ end of test for plural as if infinitive
       THEN
     -1 +LOOP
     aud @ 0 = IF  \ if no plural accept singular 24jun2011
       midway @  t @  DO  \ search English vocab; 24jun2011
         I       0 de{ @  ynverb @ = IF  ( yes-or-no verb )
           I     2 de{ @  1 = IF  \ second choice; 24jun2011
             I   8 de{ @  aud !  \ fetch recall-vector
             LEAVE  \ one engram is enough; 24jun2011
           THEN  \ end of test for plural as if infinitive
         THEN
       -1 +LOOP
     THEN  \ end of test for no engram found; 24jun2011
     aud @ 0 = IF  \ if neither plural nor singular; 25aug2011
       midway @  t @  DO  \ search English vocab; 25aug2011
         I       0 de{ @  ynverb @ = IF  ( yes-or-no verb )
           I   8 de{ @  aud !  \ fetch recall-vector
           LEAVE  \ one engram is enough; 25aug2011
         THEN  \ end of test for any form at all; 25aug2011
       -1 +LOOP
     THEN  \ end of third test for no engram found; 25aug2011
     ynverb @ nacpsi !  \ transfer activand; 25jun2011
     62 verbval !  \ prime VerbAct;  2jul2011
     VerbAct  \ activate the query verb; 25jun2011
     SpeechAct   \ to say yes-or-no verb; 24jun2011
     t @ 1 - tkbv !  \ if engram is to be changed; 2jul2011
     quobj @ 0 =  quobj @ 586 = OR IF  \ nothing or ERROR
       711 quobj !  \ 711=ANYTHING by default; 10nov2012
     THEN  \ end of test for a query-object; 20jul2011
     midway @  t @  DO  \ search English vocab; 24jun2011
       I       0 de{ @  quobj @ = IF  ( query-object? )
         I     8 de{ @  aud !  \ 10nov2012
         LEAVE
       THEN
     -1 +LOOP
     aud @ 2 < IF  \ if zero or ERROR; 25aug2011
       midway @  t @  DO  \ search English vocab; 25aug2011
         I       0 de{ @  711 @ = IF  \ 711=ANYTHING; 10nov2012
           I     8 de{ @  aud !  \ 10nov2012
           LEAVE   \ 25aug2011
         THEN      \ 25aug2011
       -1 +LOOP    \ 25aug2011
     THEN          \ 25aug2011
     SpeechAct   \ to say query-object; 24jun2011
   THEN  \  end of test for a plural nphrnum; 24jun2011
   0 yncon !  \ because question has been asked;  2jul2011
   1 kbcon !  \ because waiting for answer;  2jul2011
   0 ynverb !  \ zero out; prevent repeat of query 24jun2011
  THEN  \ end of test for a positive ynverb; 24jun2011
   5 bias !  \ Restore expectation of noun; 24jun2011
; ( http://code.google.com/p/mindforth/wiki/AskUser )


:  DePronoun  \ For use with what-do-X-do queries.
  num @ 1 = IF  \ If antecedent num(ber) is singular.
    mfn @ 1 = IF  \ if masculine singular; 13apr2010
      midway @  t @  DO  \ Look backwards for 49=HE.
        I       0 de{ @  713 = IF  \ If 713=HE is found,
         713 motjuste !  \ "nen" concept #713 for "he".
          I     8 de{ @  aud !  \ Recall-vector for "he".
          LEAVE  \ Use the most recent engram of "he".
        THEN  \ End of search for 713=HE; 10-nov2012.
      -1 +LOOP  \ End of loop finding pronoun "he".
      SpeechAct \ Speak or display the pronoun "he".
    THEN  \ end of test for masculine gender-flag.
    mfn @ 2 = IF  \ if feminine singular.
      midway @  t @  DO  \ Look backwards for 80=SHE
        I       0 de{ @ 719 = IF  \ If 719=SHE is found,
         719 motjuste !  \ "nen" concept #719 for "she".
          I     8 de{ @  aud !  \ Recall-vector for "she".
          LEAVE  \ Use the most recent engram of "she".
        THEN  \ End of search for #719 "she".
      -1 +LOOP  \ End of loop finding pronoun "she"
      SpeechAct \ Speak or display the pronoun "she"
    THEN  \ end of test for feminine gender-flag.
    mfn @ 3 = IF  \ if neuter singular; 13apr2010
      midway @  t @  DO  \ Look backwards for 725=IT.
        I       0 de{ @ 725 = IF  \ If 725=IT is found,
         725 motjuste !  \ "nen" concept #725 for "it".
          I     8 de{ @  aud !  \ Recall-vector for "it".
          LEAVE  \ Use the most recent engram of "it".
        THEN  \ End of search for 725=IT; 10nov2012
      -1 +LOOP  \ End of loop finding pronoun "it".
      SpeechAct \ Speak or display the pronoun "it".
    THEN  \ end of test for neuter gender-flag.
    0 numsubj !  \ safety measure; 13apr2010
  THEN  \ End of test for singular num(ber)
  num @ 2 = IF  \ 30dec2009 If num(ber) of antecedent is plural
    ( code further conditions for "WE" or "YOU" )
    midway @  t @  DO  \ Look backwards for 743=THEY.
      I       0 de{ @ 743 = IF  \ If 743=THEY is found,
       743 motjuste !  \ "nen" concept #743 for "they".
        I     8 de{ @  aud !  \ Recall-vector for "they".
        LEAVE  \ Use the most recent engram of "they".
      THEN  \ End of search for 743=THEY; 10nov2012.
    -1 +LOOP  \ End of loop finding pronoun "they".
    SpeechAct \ Speak or display the pronoun "they".
  THEN  \ 30dec2009 End of test for plural num(ber)
; ( http://code.google.com/p/mindforth/wiki/EnPronoun )


:  NounPhrase ( select part of a thought )
  0 audjuste !  \ prevent carry-over; 20oct2011
  verblock @ 0 > IF  \ positive verbloc? 20oct2011
    verblock @ 6 psi{ @ nounlock !  \ test; 20oct2011
  THEN  \ end of test for a positive verblock; 20oct2011
  66 caller !  \ here and further down; 12oct2010
  objold @ urpsi !  \ here and further down; 12oct2010
  0 caller !  \ reset after use; 12oct2010
  0 urpsi !  \ reset for safety; 12oct2010
  DeReify ( move abstract Psi concepts to DeVocab reality )
  0 act !
  0 aud !
\ -64 defact !  \ for default comparisons with "50=I"; 9oct2011
 -64 defact !  \ for default comparisons with 701=ICH 29nov2012
  0 kibosh !  \ for de-activating non-selectees; 17aug2011
  0 motjuste !
  0 nphrnum !  \ prevent carry-overs; 11oct2011
  0 num !   \ without prejudice; 29aug2010
  0 prsn !  \ without prejudice; 29aug2010
  0 putnum !  \ prevent carry-over from previous; 4nov2011
  0 recnum !  \ prevent carry-over from previous; 4nov2011
  0 tpeg !  \ reset for safety; 28sep2011
  nounlock @ 0 > IF  \ already a nounlock? 19oct2011
    nounlock @ 2 de{ @  scn !  \ subject-concept-number 17jul2012
    nounlock @ 8 de{ @  audjuste !  \ tentatively; 10nov2012
  THEN  \ end of test for a positive nounlock; 19oct2011
  5 opt !
  35 pov !
  1 subjectflag !  ( 3dec2009 A default until countermanded )
  dirobj @ 1 = IF 0 subjectflag ! THEN  ( 3dec2009 anti-default )
  predflag @ 1 = IF 0 subjectflag ! THEN ( anti-default 8oct2010 )
  0 psi !
  midway @  t @  DO  \ examine Psi array for most active concept.
    I 5 psi{ @ 5 =  I 5 psi{ @ 7 = OR IF  \ POS; 12aug2011
      subjectflag @ 1 = IF  \  test; change; 26aug2011
        I 1 psi{ @  act @ >  I 6 psi{ 0 > AND IF  \ 6oct2011
          I 7 psi{ @  0 > IF  \ Testing for seq-concept; 12oct2011
            I  tsels ! \ retain time of subject; 11sep2011
            I  tseln ! \ retain time of motjuste; 11sep2011
            I 0 psi{ @  motjuste !  \ 12aug2011
            I 2 psi{ @  nphrnum !  \ NounPhrase num(ber); 6oct2011
            I 2 psi{ @  subjnum !  \ 11oct2011
            I 2 psi{ @  snu ! !  \ verb-select parameter 19nov2012
          THEN  \ end of test forb seq-concept; 19nov2012
          ( insert NPhr diagnostic code here; 11sep2011 )
          I 2 psi{ @ subjnum !   \ verbs in general; 12aug2011
          motjuste @ subjold !   \ keep oldsubject ready; 8oct
          I 2 psi{ @  putnum !   \ putative num for verb; 12aug2011
          I 5 psi{ @  nphrpos !  \ NounPhrase part-of-speech
          I   1 psi{ @  act @ > I 7 psi{ @ 0 > AND IF  \ 12oct2011
            I           tpeg !  \ peg the time-slice; 28sep2011
            I 7 psi{ @  svo2 !  \ hold seq; test; 12oct2011
            I 6 psi{ @  verblock ! \ tqv of seq-concept; 12oct2011
            midway @ t @  DO  \ inspect German lexicon; 19nov2012
              I       0 de{ @ motjuste @ = IF  \ same concept?
                I     2 de{ @  snu @ = IF  \ same subj. number?
                  I   4 de{ @ 1 = IF \ nom. for subj? 19nov2012
                    I 8 de{ @  audjuste ! \ avoid spurious
                  THEN  \ end of dba-test for nominative
                THEN  \ end of subject-number test; 19nov2012
              THEN  \ end of search of German lexicon; 19nov2012
            -1  +LOOP  \ end of German lexicon search; 19nov2012
            motjuste @ 701 = IF  \ guarantee "ICH"; 19nov2012
              midway @  t @  DO  \ search backwards; 25oct2011
                I     0 de{ @  701 = IF  \ 701=ICH; 19nov2012
                  I 4   de{ @  1 = IF  \ 1=nom. 19nov2012
                    I 8 de{ @  audjuste !  \ recall-vector
                    LEAVE  \ one I-engram is enough; 25oct2011
                  THEN  \ end of test for dba=1 nom. 19nov2012
                THEN  \ end of test for "701=ICH"; 19nov2012
              -1 +LOOP  \ end of 701=ICH search loop; 19nov2012
            THEN  \ end of test for "701=ICH"; 19nov2012
            motjuste @ 707 = IF  \ guarantee "YOU"; 10nov2012
              707 subjpsi !  \ for VerbGen' 24nov2012
              midway @  t @  DO  \ search backwards; 25oct2011
                I     0 de{ @  707 = IF  \ "707=YOU"; 10nov2012
                  I 4   de{ @  1 = IF  \ 1=nom. 19nov2012
                    I 8 de{ @  audjuste !  \ recall-vector
                    LEAVE  \ one I-engram is enough; 25oct2011
                  THEN  \ end of test for dba=1 nom. 19nov2012
                THEN  \ end of test for "707=YOU"; 10nov2012
              -1 +LOOP  \ end of 707=YOU search loop; 10nov2012
            THEN  \ end of test for "707=YOU"; 10nov2012
            I 1 psi{ @  act ! \ after passing seq-check; 28aug2011
          THEN  \ reinstating to prevent false motjuste; 6oct2011
        THEN  \ end of test for a higher activation; 26aug2011
      THEN  \ end of test for 1=subjectflag; test; 26aug2011
      subjectflag @ 0 = IF  \ i.e., dir.obj or pred.nom; 15oct2011
        I  1 psi{ @  act @ > IF  \ if higher; 12aug2011
          I          tseln ! \ retain time of motjuste;  8may2011
          I  0 psi{ @  motjuste !  \ 26aug2011
          ( insert NPhr diagnostic code here;  9sep2011 )
          nounlock @ 0 > IF  \ if positive nounlock exists; 8oct2011
            I  nounlock @ = IF  \ upon reaching engram; 8oct2011
               I 0 psi{ @ motjuste !  \ grab nounlock psi; 8oct2011
               I 2 psi{ @  nphrnum !  \ NounPhrase num(ber) 11oct2011
               I 2 de{ @  pcn !  \ predicate concept number 16jul2012
               I 8 de{ @  audjuste !  \ 10nov2012
               LEAVE  \ prevent usurpation of pre-ordained seq 8oct2011
            THEN  \ end of test for Index = nounlock; 8oct2011
          THEN  \ end of test for positive nounlock; 8oct2011
          I 2 psi{ @  nphrnum !  \ NounPhrase num(ber); 12aug2011
          I 2 psi{ @  putnum !   \ putative num for verb; 12aug2011
          I 5 psi{ @  nphrpos !  \ NounPhrase part-of-speech
          dirobj @ 1 = IF
            motjuste @ objold ! \ a test ICW slosh-over; 12oct2010
          THEN   ( http://christophe.lavarenne.free.fr/ff )
          I   1 psi{ @  act @ > IF  \ 26aug2011
            I 1 psi{ @  act !  \ 12aug2011
          THEN  \ 26aug2011
        THEN  \ end of test for a higher activation; 26aug2011
      THEN  \ end of test for 0=subjectflag; test; 26aug2011
    THEN  \ end of test for a noun or pronoun; 26aug2011
  -1 +LOOP  \ End of search for most active "motjuste"; 24nov2012
  subjectflag @ 1 = IF motjuste @ subjpsi ! THEN  \ 24nov2012
  midway @  t @  DO  \ search backwards; 12aug2011; 12sep2011
    I       0 de{ @  motjuste @ = IF  \ 12aug2011
      predflag @ 1 = IF  \ only for predicate nominatives;
       nounlock @ 0 = IF  \ in absence of nounlock; 19oct2011
        I   2 de{ @  subjnum @ = IF  \ agreement? 19sep2011
          I 8 de{ @  audjuste !  \ recall-vector; 10nov2012
          LEAVE  \ one auditory engram is enough; 12aug2011
        THEN ( http://practicalai.org )
       THEN  \ end of test for absence of nounlock; 19oct2011
      ELSE  \ for normal direct objects; 19sep2011
       verblock @ 0 = IF  \ if no verblock; test; 19oct2011
        I   8 de{ @  audjuste !  \ direct object; 10nov2012
        LEAVE  \ one auditory engram is enough; 19sep2011
       THEN  \ end of test for absence of nounlock; 19oct2011
      THEN  \ end of test for predicate nominative; 19sep2011
    THEN  \ end of test for match with motjuste; 12aug2011
  -1 +LOOP  \ end of backwards search loop; 12aug2011
 nounlock @ 0 = IF  \ if no nounlock override; 8oct2011
  act @ 20 < IF  \ if no subject of thought is found; 21aug2011
   subjectflag @ 1 = IF  \ default to "I" only as subject 17oct2011
    701 motjuste !  \ 701=I default concept of AI Mind; 10nov2012
    midway @  t @  DO  \
      I 0 psi{ @ 701 =  I 7 psi{ @ 0 > AND IF  \ 10nov2012
        I 1 psi{ @  defact @ > IF  \ if higher act found; 9oct2011
          I  tsels ! \ retain time of subject; 9oct2011
          I  tseln ! \ retain time of motjuste; 9oct2011
          I 6 psi{ @  verblock ! \ lock onto valid verb; 12oct2011
          I 1 psi{ @  defact ! \ dynamic metric; 9oct2011
        THEN  \ end of test for higher-act ego-concept; 9oct2011
      THEN  \ end of search for least-inhibited "50=I"; 9oct2011
    -1 +LOOP  \ End of loop finding "50=I"; 9oct2011
    701 subjpsi !   \ for use elsewhere; 10nov2012
    701 topic !     \ for question-asking modules; 10nov2012
     1 nphrnum !   \ for DeArticle and VerbPhrase; 17nov2012
     7 nphrpos !   \ prevent article "A" with "I";  6oct2011
     1 subjnum !   \ for use elsewhere; 16aug2011
     1 prsn !      \ for use elsewhere; 16aug2011
    midway @  t @  DO  \ Use parameters to find "I";  11nov2012
      I       0 de{ @  701 = IF  \ If 701=I is found; 16nov2012
        I     4 de{ @  1 = IF  \ parameter dba=1?     16nov2012
          I     8 de{ @  audjuste !  \ recall-vector; 16nov2012
          LEAVE  \ Use the most recent engram of "I"; 16aug2011
        THEN  \ end of search for nominative "I"; 11nov2012
      THEN  \ End of search for 701=I; 10nov2012
    -1 +LOOP  \ End of parameter-based search-loop; 11nov2012
   THEN  \ end of test for "I" to become subj. not obj. 17oct2011
  THEN  \ end of test for low activation warranting a default
 THEN  \ end of test for absence of pre-ordained nounlock; 8oct2011
  nounlock @ 0 > IF   \ must be dba=4 accusative? 29nov2012
    nounlock @ 8 de{ @ audjuste !  \ auditory recall-v; 11nov2012
    nounlock @ 0 de{ @ motjuste !  \ adjust for search; 29nov2012
    motjuste @ 701 = IF  \ 701=ICH (I)? 25nov23012
      midway @  t @  DO  \ Look for 701=ICH (I); 29nov2012
        I       0 de{ @ 701 = IF  \ 701=I found; 23nov2012
          predflag @ 1 = IF  \ pred. nom. needed? 29nov2012
            I     4 de{ @ 1 = IF  \ dba=1 ICH (I)? 29nov2012
              I     8 de{ @  audjuste !  \ ICH engram 29nov2012
              LEAVE  \ Use most recent engram of ICH; 29nov2012
              THEN  \ End of search for nom. ICH (I); 25nov2012
          THEN  \ end of test for "predflag"; 29nov2012
          I     4 de{ @ 4 = IF  \ dba=4 MICH (me)? 25nov2012
            I     8 de{ @  audjuste !  \ MICH engram 29nov2012
            LEAVE  \ Use most recent engram of MICH; 25nov2012
          THEN  \ end of test for dba=4 MICH (me) 25nov2012
        THEN  \ end of test for 701=ICH; 29nov2012
      -1 +LOOP  \ End of loop finding form of ICH; 29nov2012
    THEN  \ end of test for motjuste of 701=ICH (I); 29nov2012
    motjuste @ 707 = IF  \ if 707=YOU is needed; 10nov2012
      midway @  t @  DO  \ Look backwards for 56=YOU; 16aug2012
        I       0 de{ @ 707 = IF  \ If 707=DU found; 23nov2012
          I     8 de{ @  audjuste !  \ "YOU" engram 10nov2012
          LEAVE  \ Use most recent engram of "YOU"; 16aug2012
        THEN  \ End of search for #707 "YOU"; 23nov2012
      -1 +LOOP  \ End of loop finding word "YOU"; 16aug2012
    THEN  \ end of special override for 707=DICH; 29nov2012
  THEN  \  end of test for a positive nounlock; 16aug2012
  dirobj @ 1 = IF  \ When seeking direct object; 13jun2011
   nounlock @ 0 = IF  \ if no nounlock override; 8oct2011
    act @  20 < IF  \ If activation too low; 13jun2011
      WhatAuxSVerb  \ ask question for lack of dirobj 30jul2011
      EXIT  \ Abandon rest of NounPhrase; 13jun2011
    THEN  \ End of test for sufficient activation; 13jun2011
   THEN  \ end of test for a nounlock in play; 8oct2011
  THEN  \ End of test for direct object; 13jun2011
  \ The following code for the irregular English noun "child"
  \ serves as example code for the many German or Russian
  \ irregular nouns that a "DeKi" or "PyYm" AI must deal with.
  motjuste @ 112 = IF  \ irregular "112=CHILD"; 10nov2011
    nphrnum @ 2 < IF  \ if singular is needed; 10nov2011
      midway @  t @  DO  \ search backwards; 10nov2011
        I       0 de{ @  525 = IF  \ 525=CHILD; 11nov2012
          I     8 de{ @  audjuste !  \ for SpeechAct; 10nov2011
          LEAVE  \ one engram is enough; 10nov2011
        THEN  \ end of test for CHILD-engram; 10nov2011
      -1 +LOOP  \ end of search of En(glish) lexicon
    THEN  \ end of test for singular 525=CHILD; 11nov2012
    nphrnum @ 2 = IF  \ 10nov2011
      midway @  t @  DO  \ search backwards; 10nov2011
        I       0 de{ @  526 = IF  \ 526=CHILDREN; 11nov2012
          I     8 de{ @  audjuste !  \ for SpeechAct; 10nov2011
          LEAVE  \ one engram is enough; 10nov2011
        THEN  \ end of test for CHILDREN-engram; 10nov2011
      -1 +LOOP  \ end of search of En(glish) lexicon
    THEN  \ end of test for plural 526=CHILDREN; 11nov2012
  THEN  \ end of special handling of irregular 525=CHILD;
  motjuste @ 701 = IF  \ if 701=I selected; 10nov2012
    1 prsn !  \ first person; 29aug2010
    1 num !   \ singular; 29aug2010
    1 nphrnum !  \ singular; 30aug2010
  THEN  \ end of test for 50=I; 29aug2010
  DeDamp   \ morphing MindForth into Wotan; 18nov2012
  motjuste @  hipsi !
  0 anset !   ( Insert "AN" article before vowels. )
  whoflag @ 0 = IF  \ If not answering a who-is query; 23jul2010
  \ DeArticle    \ Give a chance, not an order; 17nov2012
    nphrnum @ 1 = IF  \ not default zero; 4nov2011
    \ DeArticle  \ for true singular; 17nov2012
    THEN  \ end of test for 1=singular; 4nov2011
    0 whoflag !  \ Here instead of at InStantiate; 23jul2010
  THEN  \ End of test for zero whoflag; 23jul2010
  whoflag @ 1 = IF  \ If answering a who-is query; 26aug2011
    DeArticle  \ answer with Is-a etc.; 17nov2012
    0 whoflag  \ zero out after use; 26aug2011
  THEN  \ end of whoflag test; 26aug2011
  num @ 1 = IF  \ If num(ber is singular; 10ap2010
    DePronoun   \ Prepare to substitute ER SIE ES; 17nov2012
  THEN   \ End of test of num(ber); 10apr2010
  motjuste @ 701 = NOT IF  \ if not 701=I; 10nov2012
    motjuste @ 707 = NOT IF  \ not 707=you; 10nov2012
      motjuste @ 731 = NOT IF  \ 731=WE; 10nov2012
        3 prsn !  \ not I YOU WE; 29aug2010
      THEN  \ end of test for 731=WE; 10nov2012
    THEN  \ end of test for 707=YOU; 10nov2012
  THEN  \ end of test for "not I" 29aug2010
  motjuste @ nacpsi !
  ( could use "subjectflag" for test below; 18oct2010 )
  dirobj @ 0 = IF  \ only let subjects call NounAct; 17oct2010
    NounAct
  THEN  \ end of test originating in JavaScript AI; 17oct2010
  0 nacpsi !
  0 nounval !
  66 caller !  \ test; 26sep2010
  motjuste @ urpsi !  \ test; 17oct2010
  PsiDamp  \ to prevent interference; 17oct2010
  0 caller !  \ reset after use; 26sep2010
  0 urpsi !  \ reset for safety; 24sep2010
  66 caller !  \ test; 12oct2010
  objold @ urpsi !  \ test; 12oct2010
  0 caller !  \ reset after use; 12oct2010
  0 urpsi !  \ reset for safety; 12oct2010
   -8 tsels @  1 psi{ ! \ Let subjects re-surface; 12oct2011
  predflag @ 1 = dirobj @ 1 = OR IF  \ test; 29may2011
    -16 tseln @  1 psi{ ! \ test; 12oct2011
  THEN  \ only inhibit predicate nominatives; 11sep2010
  predflag @ 1 = IF  \ helps for Is-a; 15sep2010
    DeArticle  \ say EIN or "DER"; 17nov2012
  THEN  \ end of test; 15sep2010
  audjuste @ aud !
  aud @ 0 > IF  \ avoid ERROR; 19sep2010
    SpeechAct  \ Display or speak the selected noun-phrase.
    0 anset !  \ Reset for safety; 21oct2011
  THEN   \ end of test for 0=aud ERROR; 19sep2010
  predflag @ 1 = dirobj @ 1 = OR IF  \ both; 23jun2011
    -32 t @ 1 -  1 psi{ ! \ inhibit new noun-node; 27sep2010
    -32 t @      1 psi{ ! \ AI is now robust enough; 5aug2011
  THEN  \ only inhibit predicate nominatives; 12sep2010
  -16 t @ 1 -    1 psi{ !  \ Even shallower; 12oct2011
  -16 t @        1 psi{ !  \ Even shallower; 12oct2011
  32 EMIT
  fyi @ 2 > IF CR
  ."   from NounPhrase "
  THEN
  motjuste @ topic !
  instnum @  topicnum !
  dirobj @ 1 = predflag @ 1 = OR IF  \ if set; 24sep2010
    66 caller !  \ test; 26seo2010
    motjuste @ urpsi !  \ prepare to psi-damp motjuste; 24sep
    PsiDamp  \ knock down activation of non-subject; 24sep2010
    0 caller !  \ test; 26sep2010
    0 urpsi !  \ reset for safety; 24sep2010
  THEN \ end of test for a non-subject (pro)noun; 24sep2010
  0 act !
  0 aftjux !  \ reset for safety; 27jul2011
  0 anset !   \ reset for safety; 21oct2011
  0 jux !     \ reset for safety; 27jul2011
  0 nounlock ! \ after causing selection of VPhr seq-noun 8oct2011 
  0 prejux !  \ reset for safety; 27jul2011
  0 psi  !
  0 psi3 !    \ reset for safety  27jul2011
; ( http://code.google.com/p/mindforth/wiki/NounPhrase )


:  ConJoin
  questype @  370 =  IF  \ 370=WHY; 10nov2012
    344    conj !  \ 344=BECAUSE; 10nov2012
  ELSE  302 conj !  \ 302=AND; 10nov2012
  THEN  ( http://www.taygeta.com/forth.html )
  midway @  t @  DO
    I       0 de{ @  conj @ = IF
      conj @  motjuste !
      I     8 de{ @  aud !  \ 10nov2012
      LEAVE
    THEN
  -1 +LOOP
  SpeechAct
  0 questype !
; ( http://code.google.com/p/mindforth/wiki/ConJoin )



:  VerbGen  ( verb-generation module; 19nov2012 )
  subjpsi @ 701 = IF 1 dba ! THEN  \ 1st pers. ICH; 18nov2012
  subjpsi @ 708 = IF 2 dba ! THEN  \ 2nd pers. DU;  18nov2012
  BEGIN   \ 19nov2012
   audbase @ 0 aud{ @ abc !  \ xfer to AudBufffer; 19nov2012
   AudBuffer  \ accumulate characters; 19nov2012
   audbase @ 4 aud{ @  ctu !  \ 19nov2012
   1 audbase +!   \ increment; 19nov2012
   ctu @ 0 =   \ 19nov2012
   UNTIL   \  19nov2012
   BEGIN  \ second loop uses OutBuffer; 19nov2012
     OutBuffer    \ 19nov2012
     35 pov !  \ 35=pound-sign internal; 19nov2012
     binc @ 1 = IF  \ b-increment? 23nov2012
       b01 @ 32 > IF  \ more than SPACE? 24nov2012
         b01 @ EMIT   \ display any character; 23nov2012
         b01 @ pho !  \ for AudInput; 23nov2012
         AudInput  \ for reentry; 23nov2012
       THEN  \ end of skipping 32=SPACE; 24nov2012
     THEN  \ end of test; 23nov2012
     binc @ 2 = IF  \ b-increment? 23nov2012
       b02 @ 32 > IF  \ more than SPACE? 24nov2012
         b02 @ EMIT   \ display any character; 23nov2012
         b02 @ pho !  \ for AudInput; 23nov2012
         AudInput  \ for reentry; 23nov2012
       THEN  \ end of skipping 32=SPACE; 24nov2012
     THEN  \ end of test; 23nov2012
     binc @ 3 = IF  \ b-increment? 23nov2012
       b03 @ 32 > IF  \ more than SPACE? 24nov2012
         b03 @ EMIT   \ display any character; 23nov2012
         b03 @ pho !  \ for AudInput; 23nov2012
         AudInput  \ for reentry; 23nov2012
       THEN  \ end of skipping 32=SPACE; 24nov2012
     THEN  \ end of test; 23nov2012
     binc @ 4 = IF  \ b-increment? 23nov2012
       b04 @ 32 > IF  \ more than SPACE? 24nov2012
         b04 @ EMIT   \ display any character; 23nov2012
         b04 @ pho !  \ for AudInput; 23nov2012
         AudInput  \ for reentry; 23nov2012
       THEN  \ end of skipping 32=SPACE; 24nov2012
     THEN  \ end of test; 23nov2012
     binc @ 5 = IF  \ b-increment? 23nov2012
       b05 @ 32 > IF  \ more than SPACE? 24nov2012
         b05 @ EMIT   \ display any character; 23nov2012
         b05 @ pho !  \ for AudInput; 23nov2012
         AudInput  \ for reentry; 23nov2012
       THEN  \ end of skipping 32=SPACE; 24nov2012
     THEN  \ end of test; 23nov2012
     binc @ 6 = IF  \ b-increment? 23nov2012
       b06 @ 32 > IF  \ more than SPACE? 24nov2012
         b06 @ EMIT   \ display any character; 23nov2012
         b06 @ pho !  \ for AudInput; 23nov2012
         AudInput  \ for reentry; 23nov2012
       THEN  \ end of skipping 32=SPACE; 24nov2012
     THEN  \ end of test; 23nov2012
     binc @ 7 = IF  \ b-increment? 23nov2012
       b07 @ 32 > IF  \ more than SPACE? 24nov2012
         b07 @ EMIT   \ display any character; 23nov2012
         b07 @ pho !  \ for AudInput; 23nov2012
         AudInput  \ for reentry; 23nov2012
       THEN  \ end of skipping 32=SPACE; 24nov2012
     THEN  \ end of test; 23nov2012
     binc @ 8 = IF  \ 22nov2012
       b08 @ 32 > IF  \ more than SPACE? 24nov2012
         b08 @ EMIT
         b08 @ pho !  \ for AudInput 22nov2012
         AudInput  \ for reentry; 22nov2012
       THEN  \ end of skipping 32=SPACE; 24nov2012
     THEN  \ test; 22nov2012
     binc @ 9 = IF  \ 12nov2012
       b09 @ 32 > IF  \ more than SPACE? 24nov2012
         b09 @ EMIT
         b09 @ pho !  \ for AudInput 22nov2012
         AudInput  \ for reentry; 22nov2012
       THEN  \ end of skipping 32=SPACE; 24nov2012
     THEN  \ test; 22nov2012
     binc @ 10 = IF  \ 12nov2012
       b10 @ 32 > IF  \ more than SPACE? 24nov2012
         b10 @ EMIT
         b10 @ pho !  \ for AudInput 22nov2012
         AudInput  \ for reentry; 22nov2012
       THEN  \ end of skipping 32=SPACE; 24nov2012
     THEN  \ test; 22nov2012
     binc @ 11 = IF  \ 19nov2012
       b11 @ 32 > IF  \ more than SPACE? 24nov2012
         b11 @ EMIT
         b11 @ pho !  \ for AudInput 19nov2012
         AudInput  \ for reentry; 19nov2012
       THEN  \ end of skipping 32=SPACE; 24nov2012
     THEN  \ test; 19nov2012
     binc @ 12 = IF  \ 19nov2012
       b12 @ 32 > IF  \ more than SPACE? 24nov2012
         b12 @ EMIT
         b12 @ pho !  \ for AudInput 19nov2012
         AudInput  \ for reentry; 19nov2012
       THEN  \ end of skipping 32=SPACE; 24nov2012
     THEN  \ test; 19nov2012
     binc @ 13 = IF  \ 19nov2012
       b13 @ 32 > IF  \ more than SPACE? 24nov2012
         b13 @ EMIT
         b13 @ pho !  \ for AudInput 19nov2012
         AudInput  \ for reentry; 19nov2012
       THEN  \ end of skipping 32=SPACE; 24nov2012
     THEN  \ test; 19nov2012
     binc @ 14 = IF  \ 19nov2012
       b14 @ 32 > IF  \ more than SPACE? 24nov2012
         b14 @ EMIT
         b14 @ pho !  \ for AudInput 19nov2012
         AudInput  \ for reentry; 19nov2012
       THEN  \ end of skipping 32=SPACE; 24nov2012
     THEN  \ test; 19nov2012
     binc @ 15 = IF  \ "b" increment; 22nov2012
       b15 @ 83 =  \ 83=S; 2nd person singular;  22nov2012
       b16 @ 84 =  \ 84=T; looking ahead to b16; 22nov2012
         AND NOT   \ if not -ST ending
       b15 @ 69 =  \ 69=E; 1st or 3rd pers. plur 22nov2012
       b16 @ 78 =  \ 78=N; looking ahead to b16; 22nov2012
         AND NOT   \ if not -EN ending
           AND IF  \ if not -ST and not -EN; 22nov2012
             b15 @ EMIT  \ 22nov2012
             b15 @ pho !  \ for AudInput; 22nov2012
            AudInput  \ for reentry; 22nov2012
           THEN  \ 22nov2012
     THEN  \ 22nov2012
     binc @ 16 = IF  \ 19nov2012
       b16 @ 69 = NOT  \ 69=E; 24nov2012
       b16 @ 78 = NOT  \ 78=N; 24nov2012
         AND  \ 24nov2012
       b16 @ 84 = NOT  \ 84=T; 24nov2012
         AND IF  \ 24nov2012
         b16 @ EMIT   \ 22nov2012
         b16 @ pho !  \ 22nov2012
         AudInput   \ 22nov2012
       THEN  \ end of rejection of E/N/T; 24nov2012
     THEN  \ test; 19nov2012
   1 binc +!  \ increment the b-increment; 19nov2012
   binc @  17 <    \ test; 19nov2012
   WHILE  \  test; 19nov2012
   REPEAT  \ 19nov2012
   binc @ 17 = IF  \ OutBuffer full? 19nov2012
     dba @ 1 = IF  \ 1st person? 19nov2012
       snu @ 1 = IF  \ singular? 19nov2012
         69 pho !  \ 69=E; 19nov2012
         pho @ EMIT  \ 22nov2012
         AudInput  \ for reentry; 19nov2012
       THEN  \  end of -E inflection; 22nov2012
       snu @ 2 = IF  \ plural? 22nov2012
         69 pho !  \ 69=E; 22nov2012
         pho @ EMIT  \ 22nov2012
         AudInput  \ for reentry; 22nov2012
         78 pho !  \ 78=N; 22nov2012
         pho @ EMIT  \ 22nov2012
         AudInput  \ for reentry; 22nov2012
       THEN  \ end of -EN inflection; 22nov2012
     THEN  \ end of test for dba=1;  19nov2012
     dba @ 2 = IF  \ 2nd person? 19nov2012
       snu @ 1 = IF  \ singular? 19nov2012
         83 pho !  \ 83=S; 19nov2012
         pho @ EMIT  \ 22nov2012
         AudInput  \ for reentry; 19nov2012
         84 pho !  \ 84=T; 19nov2012
         pho @ EMIT  \ 22nov2012
         AudInput  \ for reentry; 22nov2012
       THEN  \  end of -ST inflection; 22nov2012
       snu @ 2 = IF  \ plural? 22nov2012
         84 pho !  \ 84=T; 22nov2012
         pho @ EMIT  \ 22nov2012
         AudInput  \ for reentry; 22nov2012
       THEN  \ end of -T inflection; 22nov2012
     THEN  \ end of -T inflection; 22nov2012
     dba @ 3 = IF  \ 3rd person? 22nov2-12
       snu @ 1 = IF  \ singular? 22nov2012
         84 pho !  \ 84=T; 22nov2012
         pho @ EMIT  \ speak; 22nov2012
         AudInput  \ reentry; 22nov2012
       THEN  \ end of -T inflection; 22nov2012
       snu @ 2 = IF  \ plural? 22nov2012
         69 pho !  \ 69=E; 22nov2012
         pho @ EMIT  \ speak; 22nov2012
         AudInput  \ reentry; 22nov2012
         78 pho !  \ 78=N; 22nov2012
         pho @ EMIT  \ speak; 22nov2012
         AudInput  \ reentry; 22nov2012
       THEN  \ end of -EN inflection; 22nov2012
     THEN  \ end of test for third person; 22nov2012
     32 pho !  \ intervening space; 19nov2012
     AudInput  \ reentry 32=SPACE; 19nov2012
   THEN  \ 19nov2012
   32 c01 !  32 c02 !  32 c03 !  32 c04 !
   32 c05 !  32 c06 !  32 c07 !  32 c08 !
   32 c09 !  32 c10 !  32 c11 !  32 c12 !
   32 c13 !  32 c14 !  32 c15 !  32 c16 !
   0 binc !   \ reset after use; 19nov2012
   BEGIN  \ 19nov2012
     audbase @ 0 aud{ @ EMIT  \ 18nov2012
     audbase @ 0 aud{ @ abc !  \ for AudBuffer; 18nov2012
     AudBuffer   \ to transfer engrams; 18nov2012
     1 audbase +!  \ 19nov2012
     audbase @ 0 aud{ @ 32 =   \ 19nov2012
   UNTIL  \ 19nov2012
;  \ End of VerbGen module for verb-generation.


\ The VerbPhrase module aims for the following entelechy goals.
\ [ ] If no predicate nominative is known, detour into a question.
\ [ ] If no transitive verb is most active, default to verb of being.
\ [ ] If no direct object is found, detour into asking a question.
\ 7dec2009 If no verb is found for a noun, defer to SelfRef NOT-KNOW.
\ [ ] If a transitive verb is most active, try to find direct object.
\ [X] Find whatever verb is most active after a noun-phrase.
\ Verb-selection shifts from en{ array to psi{ array on 12aug2011.
:  VerbPhrase ( supervise verb syntax )
  verblock @ 0 > IF  \ positive verbloc? 20oct2011
    verblock @ 6 psi{ @ nounlock !  \ test; 20oct2011
  THEN  \ end of test for a positive verblock; 20oct2011
  0 subjectflag !  \ for only absolute SpreadAct; test; 4aug2011
  DeReify  \ changing to Germanesque name; 17nov2012
  0 act !
  0 aud !
  0 kibosh !  \ for de-activating non-selectees; 17aug2011
  0 motjuste !
  subjpsi @ 701 = subjpsi @ 731 = OR IF 1 dba ! THEN \ I or WE
  subjpsi @ 707 = subjpsi @ 737 = OR IF 2 dba ! THEN \ YOU
  subjpsi @ 713 = subjpsi @ 719 = OR IF 3 dba ! THEN \ HE; SHE
  subjpsi @ 725 = subjpsi @ 743 = OR IF 3 dba ! THEN \ IT THEY
  verblock @ 0 > IF  \ already a verblock? 20oct2011
    verblock @ 0 de{ @ verbpsi ! \ lexical verbpsi 13nov2012
    verblock @ 8 de{ @ audbase ! \ VerbGen parameter 13nov2012
    subjpsi @ 701 = subjpsi @ 731 = OR IF 1 prsn ! THEN \ I or WE
    subjpsi @ 707 = subjpsi @ 737 = OR IF 2 prsn ! THEN \ YOU
    subjpsi @ 713 = subjpsi @ 719 = OR IF 3 prsn ! THEN \ HE; SHE
    subjpsi @ 725 = subjpsi @ 743 = OR IF 3 prsn ! THEN \ IT THEY
    prsn @ dba !  \ parameter for VerbGen; 19nov2012
    0 vphraud !  \ until a known verb is found; 19nov2012
    midway @ t  @ DO  \ Search lexicon backwards; 19nov2012
    \ Following code accepts only a verb-form matching three
    \ requirements: [ ]same concept; [ ]num(ber); and [ ]person:
      I     0 de{ @  verbpsi @ = IF \ 1: same psi? 19nov2012
        I   2 de{ @  nphrnum @ = IF \ 2: same num? 19nov2012
          I 4 de{ @  prsn @ = IF    \ 3: same prsn? 19nov2012
            I 8 de{ @  vphraud !  \ tentatively; 19nov2012
          THEN  \ end of test for same person; 19nov2012
        THEN  \ end of test for correct number; 19nov2012
      THEN  \ end of parameter test; 19nov2012
    -1 +LOOP  \ end of loop searching lexicon; 19nov2012
    vphraud @ 0 = IF  \ as-if verb-search else-clause; 19nov2012
      1 gencon ! \ prevent usual call of VerbPhrase to SpeechAct
      0 phodex ! \ prevent carry-over values; 19nov2012
      verbpsi @ 0 = NOT IF  \ prevent unwarrnated call 19nov2012
        VerbGen  \ generate needed German verb-form; 19nov2012
      THEN  \ end of test for no selected verb; 19nov2012
    THEN  \ end of quasi-else-clause to call VerbGen; 19nov2012
  THEN  \ end of test for a positive verblock; 20oct2011
  8 opt !
  0 psi !
  0 vphract !  \ for validity of threshold-tests; 15aug2011
  0 vphraud !  \ prevent spurious carry-overs; 3oct2011
  adverbact 32 > IF
  \ ( EnAdverb )
    ( DeAdverb 25nov2012 )
  THEN  ( http://theforthsource.com )
  fyi @ 1 > IF CR
 ."   VerbPhrase preview with slosh-over indicated by + --"
    CR
    ."   Disparate verb-node activations slosh "  \ 7nov2010
    ." over onto candidate objects."  CR  ."    " \ 7nov2010
  THEN
 verblock @ 0 = IF  \ prevent false negations; 20oct2011
  midway @ t  @ DO  \ Search backwards through psi concepts.
    I     5 psi{ @  8 = IF  \  if 8=pos verb; 12aug2011
      I   1 psi{ @  act @ > IF  ( if psi1 is higher 12aug2011 )
        I          tselv ! \ retain time of winning verb; 8may2011
        tselv @  kibosh @  < IF  \ if different 17aug2011
        \ ."  KIBOSH = " kibosh @ .  \ 17aug2011
          0 kibosh @ 1 psi{ !  \ deactivate also-ran; 17aug2011
        THEN  \ end of comparison; 17aug2011
        I         kibosh ! \ time of predecessor cand 17aug2011
        I 0 psi{ @ motjuste !  ( store psi-tag of verb 12aug2011 )
        I 3 psi{ @ negjux !    ( record any "12=NOT"; 9oct2011 )
        ( insert diagnostic code here; 7sep2011 )
        verblock @ 0 > IF  \ if positive verblock exists; 8oct2011
          I  verblock @ = IF  \ upon reaching engram; 8oct2011
            I          tselv ! \ time of sel. of verb; 30jul2012
            I 0 psi{ @ motjuste !  \ grab verblock psi; 8oct2011
            64 act !  \ to pass threshold-test; 20oct2011
            I 3 psi{ @ negjux !  \ for negation of verb; 9oct2011
            I 8 de{ @  vphraud !  \ for SpeechAct; 10nov2012
            I 6 psi{ @ nounlock !  \ after verb grab seq; 12oct2011
            LEAVE  \ prevent usurpation of pre-ordained seq; 7oct2011
          THEN  \ end of test for Index = verblock;  8oct2011
        THEN  \ end of test for positive verblock; 8oct2011
        I 1 psi{ @ 0 > IF  \ positive activation; 12aug2011
          I 3 psi{ @ psi3 !  ( Check for negation; 25jun2011 )
         verblock @ 0 = IF  \ test; 20oct2011
          I 3 psi{ @ negjux !  ( be-verb negation;  9oct2011 )
         THEN  \ end of avoidance of false negation; 20oct2011
          I 6 psi{ @ tqv !  \ underailable qtv; 12oct2011
        THEN  \ end of test for positive activation; 27jul2011
        I 5 psi{ @ predpos ! ( Grab winning part of speech 12aug2011 )
        I  8 de{ @ vphraud ! ( auditory recall-vector 10nov2012 )
        I 1 psi{ @  act !  ( to test for a higher psi1 12aug2011 )
      THEN  ( http://win32forth.sourceforge.net )
    THEN  \ end of test for opt=8 verbs; 8sep2011
  -1 +LOOP  \ end of loop cycling back through psi concepts
 THEN  \ end of verblock-test to prevent false negations; 20oct2011
  verblock @ 0 > IF  \ if positive verblock exists; 20oct2011
    verblock @ 0 psi{ @ motjuste !  \ verblock override; 21oct2011
    verblock @ 3 psi{ @ negjux !  \ capture any "12=NOT"; 25oct2011
    verblock @ 8 de{ @ vphraud !  \ auditory recall-v; 16nov2012
    64 act !  \ prevent rejection of selection; 20oct2011
  THEN  \ end of test for positive verblock; 20oct2011
  tqv @  0 psi{ @  svo3 !  \ test; 29sep2011
  128  tqv @  1 psi{ !  \ accentuate tqv-seq; 29sep2011
  act @ vphract !  \ for threshold comparisons; 21jun2011
  act @ verbval !
  0 psi !
  fyi @ 2 > IF
    CR ."  VerbPhrase: motjuste = " motjuste @ .
    ." going into SPEECH."
    CR ."  VerbPhrase: aud = " aud @ .
    ." going into SPEECH."
  THEN
  motjuste @ 0 = IF
    nphrnum @ 1 = IF  \ 21jun2011
      mfnflag @ 0 > IF  \ if masc. or fem.; 30jul2011
        fyi @ 2 = IF ."   VPhr calls WhoBe" THEN \ 4jul2012
        WhoBe  \ ask WHO not WHAT; 30jul2011
        0 mfnflag !  \ reset after use; 30jul2011
        EXIT  \ abandon rest of VerbPhrase
      THEN  \ end of test for positive mfnflag; 30jul2011
      fyi @ 2 = IF ."   VPhr calls WhatBe" THEN \ 6jul2012
      WhatBe  \ for a what-is question; test; 21jun2011
      EXIT  \ abandon rest of VerbPhrase;  2jul2011
    THEN  \ 21jun2011
    nphrnum @ 2 = IF  \  2jul2011
      fyi @ 2 = IF ."   VPhr calls WhatAuxSDo" THEN \ 6jul2012
      WhatAuxSDo  \ what do Subjects do? 2jul2011
      1 yncon !  \ after input ask yes-or-no question
      EXIT  \ abandon rest of VerbPhrase;  2jul2011
    THEN  \ end of test for plural noun; 2jul2011
  THEN
  motjuste @ 0 > IF
    vphract @ 20 < IF  \ a test ICW WhoBe; 21jun2011
      nphrnum @ 1 = IF  \ 21jun2011
        mfnflag @ 0 > IF  \ if masc. or fem.; 30jul2011
          fyi @ 2 = IF ."   VerbPhr calls WhoBe" THEN \ 4jul2012
          WhoBe  \ ask WHO not WHAT; 30jul2011
          0 mfnflag !  \ reset after use; 30jul2011
          EXIT  \ abandon rest of VerbPhrase
        THEN  \ end of test for positive mfnflag; 30jul2011
        fyi @ 2 = IF ."   VerbPhr calls WhatBe" THEN \ 6jul2012
        WhatBe  \ for a what-is question; test; 21jun2011
        EXIT  \ abandon rest of VerbPhrase; 30jul2011
      THEN  \ 21jun2011
      nphrnum @ 2 = IF  \  2jul2011
        fyi @ 2 = IF ."   VPhr calls WASD" THEN \ 6jul2012
        WhatAuxSDo  \ what do Subjects do? 2jul2011
        1 yncon !  \ after input ask yes-or-no question
        EXIT  \ abandon rest of VerbPhrase;  2jul2011
      ELSE  \ if "nphrnum" neither 1 nor 2; 15aug2011
        EXIT  \ to avoid a spurious thought; 15aug2011
      THEN  \ end of test for plural noun; 2jul2011
    THEN   \ End of test of vphract; 21jun2011
    motjuste @  hipsi !
    motjuste @ 830 = IF  \ irregular 830=DO; 10nov2012
      subjnum @ 1 =  prsn @ 3 = AND IF  \ 5oct2011
        midway @  t @  DO  \ search backwards; 5oct2011
          I       0 de{ @ 830 = IF  \ 830=DO; 10nov2012
            I     2 de{ @ 1 = IF  \ singular? 10nov2012
              I   4 de{ @ 3 = IF  \ 3rd pers? 10nov2012
                I     8 de{ @  vphraud !  \ 10nov2012
                LEAVE  \ one engram is enough; 5oct2011
              THEN  \ end of test for third person 10nov2012
            THEN  \ end of test for singular; 10nov2012
          THEN  \ end of test for 830=DO; 10nov2012
        -1 +LOOP  \ end of search of En(glish) lexicon
      THEN  \  end of test for 3rd person singular; 5oct2011
    THEN  \ end of special handling of 59=DO; 5oct2011
    \ The following code for the irregular English verb
    \ "to have" serves as example code for the many German
    \ irregular verbs that a polyglot AI must deal with.
    motjuste @ 810 = IF  \ irregular 810=HAVE; 10nov2012
      subjnum @ 1 =  prsn @ 3 = AND IF  \ 13aug2011
        midway @  t @  DO  \ search backwards; 13aug2011
          I       0 de{ @ 810 = IF  \ 810=HAVE 10nov2012
            I     2 de{ @ 1 = IF  \ singular? 10nov2012
              I   4 de{ @ 3 = IF  \ 3rd pers? 10nov2012
                I     8 de{ @  vphraud !  \ 10nov2012
                LEAVE  \ one engram is enough; 13aug2011
              THEN  \ end of test for 3rd person; 10nov2012
            THEN  \ end of test for singular; 10nov2012
          THEN  \ end of test for HAS-engram; 13aug2011
        -1 +LOOP  \ end of search of En(glish) lexicon
      THEN  \  end of test for 3rd person singular; 13aug2011
    THEN  \ end of special handling of 70=HAVE; 13aug2011
    motjuste @ 800 = IF  \ present-tense be-verb? 10nov2012
      1 predflag !  \ for sake of NounPhrase; 26aug2011
    THEN  \ end of setting flag for predicate nom.; 29nov2012
    motjuste @ 800 = IF  \  800=BE; 10nov2012
      subjpsi @ 701 = IF  \ 701=I; 10nov2012
        midway @  t @  DO  \ search En(glish) array; 21aug2011
          I       0 de{ @ 800 = IF  \ 800=BE; 10nov2012
           800 motjuste !  ( Set verbform to "BE" 10nov2012 )
           800 urpsi !  ( parameter for PsiDamp 10nov2012 )
            I     2 de{ @ 1 = IF  \ singular? 10nov2012
              I   4 de{ @ 1 = IF  \ 1st pers? 10nov2012
                I     8 de{ @  vphraud ! \ SpeechAct 10nov2012
                LEAVE  \ recent "AM" is enough 12aug2011
              THEN  \ end of test for first person; 10nov2012
            THEN  \ end of test for singular; 10nov2012
          THEN  \ end of two-step test to say "AM"; 12aug2011
        -1 +LOOP  \ end of backwards loop; 12aug2011
      THEN  \ end of test for "50=I" subject-psi; 12aug2011
      subjpsi @ 707 = IF  ( 707=YOU; 10nov2012 )
        midway @  t @  DO               \ 8aug2011
          I    0 de{ @ 800 = IF    \ 800=BE 10nov2012
            I  2 de{ @ 1 = IF    \ singular? 10nov2012
             I 4 de{ @ 2 = IF    \ 2nd pers? 10nov2012
                I  8 de{ @  vphraud !  \ 10nov2012
                LEAVE                     \ 8aug2011
             THEN  \ end of test for 2nd person; 10nov2012
            THEN  \ end of test for singular; 10nov2012
          THEN   \ end of test for 800=BE: 10nov2012
        -1 +LOOP                      \ 8aug2011
      THEN  \ 8aug2011
    THEN  \  end of test for 58=BE; 13aug2011
    0 subjectflag !  \ for SpreadAct slosh-over; 18oct2010
    motjuste @ vacpsi !  \ prepare to deglobalize; 27sep2010
    motjuste @ verbpsi !  \ for WhatAuxSVerb; 13jun2011
    VerbAct
    0 vacpsi !  \ reset for safety; 27sep2010
    nphrnum @ 2 = NOT IF  \ if not plural; test; 30aug2010
      1 nphrnum !  \ default to singular; test; 30aug2010
    THEN  \ end of test for plural nphrnum; 30aug2010
    vphraud @ aud !  \ transfer just before call; 25jun2011
    gencon @ 0 = IF  \ if no call to VerbGen; 19nov2012
      SpeechAct  ( main call from VerbPhrase to SpeechAct )
    THEN  \ prevent speaking extra verb after VerbGen; 19nov2012
    0 gencon !  \ reset whether used or not; 19nov2012
      VerbClear  \ deactivate before inhibiting; 17aug2011
      -32 t @ 1 -  1 psi{ ! \ inhibit new verb-node; 3sep2011
      -32 t @      1 psi{ ! \ inhibit new verb-node; 3sep2011
      0 flex1 !  \ reset for safety; 11sep2011
      0 vphraud !  \ reset for safety; 25jun2011
      0 vpos !
    motjuste @ 800 = IF  \ may be redundant for German 29nov2012
      negjux @ 250 = IF  \ 250=NOT; 10nov2012
        midway @  t @  DO   \ Search de(eutsch) array; 29nov2012
          I       0 de{ @  250 = IF  \ Look for NICHT; 29nov2012
            I     8 de{ @  aud ! \ Auditory start-tag 10nov2012
            LEAVE   \ One instance of NICHT suffices; 29nov2012
          THEN   \ End of lexical test for 250=NICHT; 29nov2012
        -1 +LOOP \ End of loop searching for 250=NICHT 29nov2012
        SpeechAct  \ Say the word "NICHT"; 29nov2012
        0 aftjux !  \ reset for safety; 27jul2011
        0 negjux !  \ reset for safety;  9oct2011
        0 prejux !  \ reset for safety; 27jul2011
        0 jux !     \ reset for safety; 27jul2011
        0 psi3 !    \ reset for safety; 27jul2011
      THEN \ end of test for negated be-verb; 27jul2011
    THEN  \ end of test for be-verb; 27jul2011
    psi3 @ 250 =  negjux @ 250 = OR IF  \ 27nov2012
      midway @  t @  DO   \ Search de(utsch) array; 27nov2012
        I       0 de{ @  250 = IF  \ found NICHT? 27nov2012
          I     8 de{ @  aud ! \ Auditory start-tag 17nov2012
          LEAVE   \ One instance of NICHT suffices; 27nov2012
        THEN   \ End of lexical test for 250=NICHT; 27nov2012
      -1 +LOOP  \ End loop searching for 250=NICHT; 27nov2012
      SpeechAct  \ Say the word 250=NICHT; 27nov2012
    THEN  \ end of test for a negated verb; 27nov2012
  THEN  \ end of test for positive motjuste; 29aug2010
  10 act !
  motjuste @  urpsi !
  62 caller !
  PsiDamp  \ Necessary for chain of thought; 24oct2010
  0 caller !
  DeDamp  \ morphing MindForth into DeKi Wotan; 18nov2012
  \ Following lines inhibit old KB verb-node; 13jun2011
  -32 tselv @ 1 psi{ ! \ Shallow inhibition; 3sep2011
  0 tselv ! \ Reset tselv after use; 13jun2011
  32 EMIT
  subjpsi @ 701 = IF  \ only for subject 701=I; 10nov2012
    motjuste @ 820 = IF  \ only for verb 820=SEE; 10nov2012
      svo3 @ 0 = IF  \ if SEE has no direct object; 22sep2011
        VisRecog  \ a challenge for robot AI coders 22sep2011
        SpeechAct  \ say default from VisRecog; 22sep2011
        EXIT  \ abandon rest of VerbPhrase; 22sep2011
      THEN  \ end of test for direct object; 22sep2011
    THEN  \ end of test for "820=SEE"; 10nov2012
  THEN  ( http://code.google.com/p/robotbridgeware )
  motjuste @ 800 = IF 1 predflag ! \ 800=BE; 25nov2012
  ELSE   \ for transitive verbs; 25nov2012
    1 dirobj !  \ Declare seeking of a direct object; 25nov2012
  THEN \ end of test for be-verbs or else transitive; 25nov2012
  ( DeAdjective -- a possibility here; 18nov2012 )
  NounPhrase
  0 predflag !  \ reset for safety; 12sep2010
  motjuste @ 0 > IF motjuste @ dopsi ! THEN
  0 dirobj !
  0 negjux !  \ reset for safety; 9oct2011
  0 numflag !  \  3dec2009 Whether used here or in BeVerb.
  0 predflag !  \ Reset for safety; 26aug2011
  0 psi3 !  \ reset for safety; 27jul2011
  0 svo3 !  \ use once per thought; 9sep2011
  0 tqv !  \ reset for safety; 29sep2011
  0 verblock ! \ after causing selection of NPhr seq-verb; 8oct2011
; ( http://code.google.com/p/mindforth/wiki/VerbPhrase )


:  DeCog ( Deutsch Cognition -- thinking in German )
  0 moot !  \ may have been set in previous thought; 24oct2011
  0 morphpsi !
  0 psi !
  0 sublen !
  t @ tov !
  yncon @ 1 = IF  \ if flag set in VerbPhrase; 2jul2011
    AskUser  \ for a yes-or-no question; 2jul2011
    EXIT  \ abandon rest of DeCog; 17nov2012
  THEN  ( http://www.mpeforth.com )
  yesorno @ 0 > IF
    SayYes
    CR
    EXIT
  THEN   \  http://www.dfki.de 
  400 rsvp !   \ Give user time to respond. 23aug2010
  inert @ 10 > IF  \ if no input start thinking; 17oct2011
    cogpsi @ 0 > IF  \  17oct2011
      cogpsi @ topic !  \ for query-subject; 17oct2011
      cognum @ topicnum !  \ to select "IS" or "ARE"; 22oct2011
      fyi @ 2 = IF ."   DeCog calls WhatBe" THEN \ 17nov2012
      CR WhatBe  \ Ascribe output only to robot; 26jul2012
      0 cognum !  \ reset for safety; 22oct2011
      0 cogpsi !  \ reset for safety; 17oct2011
      EXIT  \ abandon the rest of DeCog; 17nov2012
    THEN  \ 17oct2011
    kbtv @ 1 = IF  \ in cycle of KbTraversal; 17oct2011
    707 topic !   \ 707=YOU as topic of question; 10nov2012
      7 nphrpos !  \ pronoun "YOU" part-of-speech; 21oct2011
      2 prsn !     \ parameter second-person YOU; 17oct2011
      1 subjnum !  \ singular YOU as a parameter; 17oct2011
      IQ @ 1 = IF  \ borrowing IQ as a control; 17oct2011
        fyi @ 2 = IF ."   DeCog calls WhoBe" THEN \ 17nov2012
        CR WhoBe  \ Ascribe output only to robot; 26jul2012
        0 inert !  \ reset to resume counting; 17oct2011
        2 IQ !  \ to ask a different question; 17oct2011
        1000 rsvp !  \ AI waits for an answer; 19oct2011
        EXIT  \ only output one thought per cycle; 17oct2011
      THEN  \ end of re-purposed IQ-test; 17oct2011
      IQ @ 2 = IF  \ to ask a different question; 17oct2011
        fyi @ 2 = IF ."   EnC calls WhatBe" THEN \ 6jul2012
        CR WhatBe  \ Ascribe output only to robot; 26jul2012
        0 inert ! \ reset to resume counting; 17oct2011
        3 IQ !  \ to ask a different question; 17oct2011
        1000 rsvp !  \ AI waits for an answer; 19oct2011
        EXIT  \ only output one thought per cycle; 17oct2011
      THEN  \ end of IQ-test; 17oct2011
      IQ @ 3 = IF  \ to ask a different question; 17oct2011
        fyi @ 2 = IF ."   EnC-kbtv1 calls WASD" THEN \ 6jul2012
        CR WhatAuxSDo  \ Ascribe output only to robot; 26jul2012
        0 inert ! \ reset to resume counting; 17oct2011
        1 IQ !  \ to ask a different question; 17oct2011
        1000 rsvp !  \ AI waits for an answer; 19oct2011
        EXIT  \ only output one thought per cycle; 17oct2011
      THEN  \ end of IQ-test; 17oct2011
    THEN  \ end of #1 test of rotating "kbtv"; 17oct2011
    kbtv @ 2 = IF  \ in rotation of KbTraversal; 17oct2011
      571 topic !  \ let 571=ROBOT be subject; 10nov2012
      5 nphrpos !  \ noun part-of-speech; 17oct2011
      3 prsn !  \ parameter needed for AuxVerb; 17oct2011
      IQ @ 1 = IF  \ borrowing IQ as a control; 17oct2011
        1 indefmust !  \ for "A ROBOT"; 20oct2011
        1 subjnum !  \ for singular "ROBOT"; 17oct2011
        fyi @ 2 = IF ."   DeCog calls WhatBe" THEN \ 17nov2012
        CR WhatBe  \ Ascribe output only to robot; 26jul2012
        0 indefmust !  \ reset for safety; 20oct2011
        0 inert !  \ reset to resume counting; 17oct2011
        2 IQ !  \ to ask a different question; 17oct2011
        1000 rsvp !  \ AI waits for an answer; 19oct2011
        EXIT  \ only output one thought per cycle; 17oct2011
      THEN  \ end of re-purposed IQ-test; 17oct2011
      IQ @ 2 = IF  \ borrowing IQ as a control; 17oct2011
        1 subjnum !  \ for singular "ROBOT"; 17oct2011
        fyi @ 2 = IF ."   EnC-kbtv2 calls WASD" THEN \ 6jul2012
        CR WhatAuxSDo  \ Ascribe output only to robot; 26jul2012
        0 inert !  \ reset to resume counting; 17oct2011
        3 IQ !  \ to ask a different question; 17oct2011
        1000 rsvp !  \ AI waits for an answer; 19oct2011
        EXIT  \ only output one thought per cycle; 17oct2011
      THEN  \ end of re-purposed IQ-test; 17oct2011
      IQ @ 3 = IF  \ borrowing IQ as a control; 17oct2011
        2 subjnum !  \ for plural "ROBOTS"; 17oct2011
        fyi @ 2 = IF ."  DeCog-kbtv2 calls WASD" THEN \ 17nov2012
        CR WhatAuxSDo  \ Ascribe output only to robot; 26jul2012
        0 inert !  \ reset to resume counting; 17oct2011
        1 IQ !  \ to ask a different question; 17oct2011
        1000 rsvp !  \ AI waits for an answer; 19oct2011
        EXIT  \ only output one thought per cycle; 17oct2011
      THEN  \ end of re-purposed IQ-test; 17oct2011
    THEN  \ end of #2 test of rotating "kbtv"; 17oct2011
    kbtv @ 3 = IF  \ in rotation of KbTraversal; 17oct2011
     701 topic !  \ 701=I; 10nov2012
      7 nphrpos !  \ pronoun "I" part-of-speech; 21oct2011
      1 prsn !     \ parameter first-person I; 17oct2011
      1 subjnum !  \ singular I as a parameter; 17oct2011
      IQ @ 1 = IF  \ borrowing IQ as a control; 17oct2011
        fyi @ 2 = IF ."   DeCog calls WhoBe" THEN \ 17nov2012
        CR WhoBe  \ Ascribe output only to robot; 26jul2012
        0 inert !  \ reset to resume counting; 17oct2011
        2 IQ !  \ to ask a different question; 17oct2011
        1000 rsvp !  \ AI waits for an answer; 19oct2011
        EXIT  \ only output one thought per cycle; 17oct2011
      THEN  \ end of re-purposed IQ-test; 17oct2011
      IQ @ 2 = IF  \ to ask a different question; 17oct2011
        fyi @ 2 = IF ."  EnC-kbtv3 calls WhatBe" THEN \ 6jul2012
        CR WhatBe  \ Ascribe output only to robot; 26jul2012
        0 inert ! \ reset to resume counting; 17oct2011
        3 IQ !  \ to ask a different question; 17oct2011
        1000 rsvp !  \ AI waits for an answer; 19oct2011
        EXIT  \ only output one thought per cycle; 17oct2011
      THEN  \ end of IQ-test; 17oct2011
      IQ @ 3 = IF  \ to ask a different question; 17oct2011
        fyi @ 2 = IF ."  DeCog-kbtv3 calls WASD" THEN \ 17nov2012
        CR WhatAuxSDo  \ Ascribe output only to robot; 26jul2012
        0 inert ! \ reset to resume counting; 17oct2011
        1 IQ !  \ to ask a different question; 17oct2011
        1000 rsvp !  \ AI waits for an answer; 19oct2011
        EXIT  \ only output one thought per cycle; 17oct2011
      THEN  \ end of IQ-test; 17oct2011
    THEN  \ end of #3 test of rotating "kbtv"; 17oct2011
    kbtv @ 4 = IF  \ in rotation of KbTraversal; 17oct2011
      533 topic !  \ 533=GOD for AI theology discussion; 10nov2012
      3 prsn !     \ parameter third-person GOD; 17oct2011
      1 subjnum !  \ singular GOD as a parameter; 17oct2011
      IQ @ 1 = IF  \ borrowing IQ as a control; 17oct2011
        fyi @ 2 = IF ."   DeCog calls WhoBe" THEN \ 17nov2012
        CR WhoBe  \ Ascribe output only to robot; 26jul2012
        0 inert !  \ reset to resume counting; 17oct2011
        2 IQ !  \ to ask a different question; 17oct2011
        1000 rsvp !  \ AI waits for an answer; 19oct2011
        EXIT  \ only output one thought per cycle; 17oct2011
      THEN  \ end of re-purposed IQ-test; 17oct2011
      IQ @ 2 = IF  \ to ask a different question; 17oct2011
        fyi @ 2 = IF ."   EnC-kbtv4 calls WhatBe" THEN \ 6jul2012
        CR WhatBe  \ Ascribe output only to robot; 26jul2012
        0 inert ! \ reset to resume counting; 17oct2011
        3 IQ !  \ to ask a different question; 17oct2011
        1000 rsvp !  \ AI waits for an answer; 19oct2011
        EXIT  \ only output one thought per cycle; 17oct2011
      THEN  \ end of IQ-test; 17oct2011
      IQ @ 3 = IF  \ to ask a different question; 17oct2011
        fyi @ 2 = IF ."   EnC-kbtv4 calls WASD" THEN \ 6jul2012
        CR WhatAuxSDo  \ Ascribe output only to robot; 26jul2012
        0 inert ! \ reset to resume counting; 17oct2011
        1 IQ !  \ to ask a different question; 17oct2011
        1000 rsvp !  \ AI waits for an answer; 19oct2011
        EXIT  \ only output one thought per cycle; 17oct2011
      THEN  \ end of IQ-test; 17oct2011
    THEN  \ end of #4 test of rotating "kbtv"; 17oct2011
  THEN  \ end of arbitrary delay before initiating thought
  ( exceptional think was above; normal thinking below here )
\ CR ." Robot: "
  CR ." Wotan: "   \ 23nov2012
  123  t @  2 aud{ !
  t @ tov !  \ 12jan2010 "{" marks start of thought.
  NounPhrase  \ First of two Chomskyan bifurcations.
  VerbPhrase  \ Second of two Chomskyan bifurcations.
  0 nphrnum ! \ Reset intersyntactic variable; 11oct2011
  0 pcn !  \ Reset for safety; 17jul2012
  0 prox2 !  \ Reset after use; 7sep2011
  0 prox3 !  \ Reset after use; 7sep2011
  0 proxcon !  \ Reset after use; 7sep2011
  0 putnum !  \ reset for safety;  4nov2011
  0 quo !          \ 5jan2010 Reset after use.
  5 bias !
  0 qup !   \ 10jan2010 Must be at zero to be used again.
  PsiDecay  \ Reduce activation after each thought; 4aug2011
; ( http://code.google.com/p/mindforth/wiki/EnCog )


:  ThInk ( calls DeCog to think in German; 17nov2012 )
  0 ordo !
  35 pov !  \ internal ASCII 35=# point-of-view; 16oct2011
  glot @ 2 = IF  \ upon input of multiple German words;
    DeCog  ( think in Deutsch -- German;  20jul2011 )
  THEN  \ end of test for language-choice in polyglot AI
  fyi @ 1 = IF CR THEN
  0 ordo !
  rjc @ 1 < IF  \ if AI on but not yet ReJuvenated; 19sep2010
    lurk @ greet @ > IF  \ if limit exceeded; 19sep2010
      100 rsvp !  \ slow down the display; 19sep2010
      -1 lurk ! \ reset for safety; 19sep2010
      kbtv @ 4 > IF  1 kbtv !  THEN  \ test; 19sep2010
      1 kbtv +!  \ cycle through values; 19sep2010
      KbTraversal  \ if no input, begin thinking; 19sep2010
    THEN  ( http://www.forth.com )
  THEN  \ end of test of ReJuvenation-count (rjc); 19sep2010
; ( http://code.google.com/p/mindforth/wiki/ThInk )


:  MotorOutput ( stub for autonomous control of robots )
   7 EMIT
 ( MOVE_FORWARD   )
 ( MOVE_BACKWARDS )
 ( STOP_MOTION    )
 ( TURN_LEFT      )
 ( TURN_RIGHT     )
; ( http://code.google.com/p/mindforth/wiki/MotorOutput )


:  TuringTest ( Human-Computer Interaction )
  fyi @ 0 = IF CLS CR CR CR CR CR CR CR
    t @ 476 < IF CR  \ "vault" after SEE and NOTHING; 22sep2011
      ." There is no warranty for MindForth AI for robots."
    ELSE CR
    THEN
  THEN
  fyi @ 1 = NOT IF CR THEN
  ."  "
  fyi @ 1 = NOT IF CR THEN
  fyi @ 0 = IF
    CR
    ." Artificial intelligence alive and thinking since "
    bday @ .
    bmonth @  1 = IF ." January "   THEN
    bmonth @  2 = IF ." February "  THEN
    bmonth @  3 = IF ." March "     THEN
    bmonth @  4 = IF ." April "     THEN
    bmonth @  5 = IF ." May "       THEN
    bmonth @  6 = IF ." June "      THEN
    bmonth @  7 = IF ." July "      THEN
    bmonth @  8 = IF ." August "    THEN
    bmonth @  9 = IF ." September " THEN
    bmonth @ 10 = IF ." October "   THEN
    bmonth @ 11 = IF ." November "  THEN
    bmonth @ 12 = IF ." December "  THEN
    byear @ . 8 EMIT 46 EMIT CR
  THEN
  fyi @ 1 = NOT IF
    ." Time = " t @ . 8 EMIT 46 EMIT
    ." KB-Traversal ID = " kbtv @ .
    8 EMIT 46 EMIT
    ."  IQ = " IQ @ . 8 EMIT 46 EMIT
    ."  Cyc = " rjc @ . ." delay = " rsvp @ . 8 EMIT 46 EMIT
    CR ." ENTER a positive or negative Subj-Verb-Obj "
    ." unpunctuated sentence."
    CR
  THEN
  fyi @ 0 = IF CR
   ." Display-mode is normal. Press Tab for other modes; "
   ." ESC to exit."
    CR
  THEN
  fyi @ 3 = IF CR
    ." Diagnostic messages - ignore during input "
    ." before pressing ENTER."
  THEN
  42 pov !
; ( http://code.google.com/p/mindforth/wiki/TuringTest )


:  SeCurity ( new wiki-page name for SECURITY module )
  fyi @ 2 = IF CR
  ."   SeCurity calls HCI TuringTest module."
  THEN
  TuringTest
  t @ cns @ 64 - > IF
    fyi @ 2 = IF CR
    ."   SeCurity module calls ReJuvenate."
    THEN
    ReJuvenate
  THEN
  t @  cns @ > IF \ Use midway only for larger Minds 13aug2012
    t @ cns @ - midway !  ( for limit on searches; 13aug2012 )
    ELSE  \ If the CNS memory has a small capacity 13aug2012
    1 midway ! \ Avoid any "array boundary problem"; 13aug2012
  THEN \ Future code may let an AI itself set midway 13aug2012
  0 quiet !
; ( http://code.google.com/p/mindforth/wiki/SeCurity )


:  MainLoop  ( may be called by individual name of DeKi )
  TIME&DATE byear ! bmonth ! bday ! bhour ! bminute ! bsec !
  TabulaRasa
  DeBoot ( call the German vocabulary bootstrap; 16nov2012 )
  BEGIN
    SeCurity
    fyi @ 2 = IF CR
    ." MainLoop calls the SensoryInput module." CR
    THEN
    SensoryInput
  ( EmotiOn )
    fyi @ 2 = IF CR CR   \ create gap; 6jul2012
    ." MainLoop calls the ThInk mind-module." CR
    THEN
    ThInk
  ( FreeWill )
  ( MotorOutput )
  AGAIN
; ( http://code.google.com/p/mindforth/wiki/MainLoop )


:  Wotan  ( Call MainLoop if not called by user. )
  MainLoop
```