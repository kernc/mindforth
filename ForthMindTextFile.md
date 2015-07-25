### MindForth ###

```
( 18aug11A.F -- modification of 17augl1A.F MindForth )
( Released under GNU General Public License V2 )
( http://gpl-violations.org -- see NYT Sun.26.SEP.2010. )
( May be ported to new language and app store marketed. )
( May be named "Mind.F" or any "Filename.F" you choose. )
( Rename any Mind.F.txt as simply Mind.F for Win32Forth. )
( http://www.winzip.com/aboutzip.htm tells about WinZip. )
( Download and unzip W32FOR42_671.zip to run MindForth. )
( Run the AI with Win32Forth by issuing three commands: )
( win32for.exe [ENTER] )
( fload Mind.f [ENTER] )
( MainLoop [ENTER]. )
( To halt the AI Mind, press the ESCAPE key at any time. )
( Ask or answer questions about MindForth AI on Usenet. )
( http://groups.google.com/group/comp.lang.forth/topics )
( http://www.scn.org/~mentifex/mindforth.txt Win32Forth )
( http://www.scn.org/~mentifex/mind.frt 32/64-bit iForth )
( http://code.google.com/p/mindforth/wiki/UserManual )
( http://code.google.com/p/mindforth/wiki/ChangeLog data )
\  7nov10A.F psi-damps be-verbs to reduce stray activation.
\  9nov10A.F is 7nov10A.F with diagnostics commented out.
\ 25feb11A.F removes obsolete query-flags and query code.
\ 15apr11A.F improves WHO-query and WHAT-query responses.
\ 25apr11A.F sets zero act(ivation) for ReEntry concepts.
\  3may11A.F coordinates InStantiate and ReActivate "WHO".
\  7may11A.F inhibits transitive verbs after thinking them.
\  8may11A.F improves VerbPhrase use of inflectional "S".
\ 16may11A.F uses differential instead of linear PsiDecay.
\ 26may11A.F assumes plural number if noun ends in "S".
\ 29may11A.F answers questions from knowledge base (KB).
\  1jun11A.F was abandoned after code veered into disarray.
\  6jun11A.F gives valid answers to knowledge base queries.
\ 12jun11A.F introduces WhatAuxSVerb to ask user questions.
\ 19jun11A.F calls WhatBe if no verb is found for a subject.
\ 23jun11A.F has AskUser begin asking yes-or-no questions.
\ 24jun11A.F converts KbTraversal concepts to query-subjects.
\ 25jun11A.F in VerbPhrase eliminates need for NegSvo module.
\ 25jun11B.F organizes AuxVerb module for use with negation.
\  2jul11A.F introduces KbRetro to adjust the knowledge base.
\ 19jul11A.F uses recnum to recognize CHESS as singular noun.
\ 20jul11A.F removes obsolete NegSvo in favor of VerbPhrase.
\ 21jul11A.F uses diagnostic messages to debug negation code.
\ 21jul11B.F uses prejux to carry NOT over onto verb engram.
\ 27jul11A.F introduces "aftjux" for negation of be-verbs.
\ 28jul11A.F introduces "tsels" for inhibition of subjects.
\ 29jul11A.F adjusts activations for negation of be-verbs.
\ 30jul11A.F streamlines the EnCog English cognition module.
\  2aug11A.F troubleshoots EnBoot with diagnostic messages.
\  2aug11B.F instantiates AM, IS, & ARE as psi "58=BE" verbs.
\  4aug11A.F debugs spurious-predicate-nominative problem.
\  4aug11B.F puts cumulative SpreadAct spikes only on verbs.
\  5aug11A.F in VerbPhrase removes redundant NOT negation.
\  5aug11B.F adjusts activation-levels for direct objects.
\  6aug11A.F assigns number for both input and re-entry.
\  6aug11B.F improves the function of the AskUser module.
\  7aug11A.F repatriates BeVerb into the VerbPhrase module.
\  8aug11A.F disregards Psi number during EnReify transfer.
\ 10aug11A.F is before removal of diagnostic messages.
\ 10aug11B.F in VerbAct converts "AM IS ARE" to "58=BE".
\ 11aug11A.F uses new variables "notjux" and "skipseq".
\ 12aug11A.F uses diagnostic messages for radical change.
\ 12aug11B.F shifts NLP generation from en{ to psi{ array.
\ 13aug11A.F prepares for English or German irregular verbs.
\ 14aug11A.F psi-damps 58=BE after thinking AM or IS or ARE.
\ 15aug11A.F improves threshold-test branching in VerbPhrase.
\ 16aug11A.F defaults to self-concept I if no noun is active.
\ 16aug11B.F has two-step be-verb substitution in VerbPhrase.
\ 17aug11A.F eliminates activation on non-selected concepts.
\ 18aug11A.F clears stray activation on nouns with NounClear.
DECIMAL  ( use decimal numbers )
variable act 0 act ! ( activation level  )
variable actbase ( AudRecog discrimination activation base)
variable actran  ( PsiDecay holder of act-levels; 16may2011 )
variable adverbact 0 adverbact ! ( 29aug2008 adverb test )
variable aftjux  ( after-jux for negation of verb of being )
variable alsoran  ( NounPhrase non-winner to be psi-damped )
variable anset  ( Before vowel set article AN insertion )
variable areflag ( 10dec2009 SelfRef answers "what are?" )
variable atcd  ( 30dec2009 "antecedent" for EnPronoun )
variable aud  ( auditory recall-tag for activating engrams)
variable audjuste ( NounPhrase motjuste aud to SpeechAct )
variable audme  ( tag to find "ME" in auditory memory )
variable audpsi  ( de-globalizing the "psi" variable )
variable audrec  ( 6may2009 replacing "psi" in AudRecog )
variable audrun 1 audrun ! ( counter of loops through AudRecog )
variable audstop  ( flag to stop SpeechAct after one word )
variable bday ( day of birth reveals oldest living AI Mind)
variable beact  ( for discrimination during BeVerb; 8aug2010 )
variable beflag 0 beflag ! ( 23apr2009 for InStantiate )
variable beg  1 beg ! ( "beginning" flag for word engrams )
variable bhour ( hour of birth for user interface display )
variable bias 5 bias ! ( Parser; newConcept: expected POS )
variable bminute ( minute of birth: user interface display)
variable bmonth ( month of birth: user interface display )
variable bsec ( second of birth: user interface display) 
variable byear ( MainLoop; TuringTest HCI -- year of birth)
variable caller  ( debug-identifier of calling module )
variable cns  1024 cns !  ( "central nervous system" size )
variable coda  128 coda !  ( memory recycled in ReJuvenate)
variable cogpsi  ( cognition psi source-node in SpreadAct )
variable conj  ( OldConcept; ConJoin: conjunction )
variable ctu ( continuation-flag for "Aud" array phonemes )
variable defartcon ( set definite article condition )
variable detour  ( abort-flag if knowledge is insufficient)
variable dirobj  ( indicates seeking for a direct object )
\ variable doesflag ( 13dec2009 SelfRef answers "What does? )
\ variable doflag  ( 13dec2009 SelfRef answers "What do...? )
variable dopsi  ( direct-object-psi to calculate "thotnum")
variable dunno  ( 13dec2009 Flag for EnCog to call SelfRef )
variable dunnoobject ( 5jan2010 EnCog what-do-X-verb flag )
variable dunnoverb   ( 5jan2010 EnCog what-do-X-do flag )
variable edge  0 edge ! ( Rejuvenate: edge-of-thought flag)
variable en7 ( EnVocab recall-vector "aud" in Rejuvenate )
variable enx ( holds concept-number in transfer to English)
variable eot ( end-of-text for use in AudInput ) 
variable fex ( holds fiber-out concept up from Psi memory )
variable fin ( holds fiber-in concept for Psi array access)
variable fyi 0 fyi ! ( rotates through display modalities )
variable ghost 0 ghost ! ( to switch from "a" to "the" )
variable glot 1 glot ! ( flag for which language to think in )
variable greet 420 greet ! ( greeting-trigger; 8oct2010 )
variable guspsi  ( concept-tag attached to taste-memories )
variable gusrec  ( for external recognition by GusRecog )
variable hipsi   ( "high-psi" tag on wavecrest concept )
( I = Index in loops; does not require a fetch "@" )
variable img  ( visRecog: for future use as "image" )
variable indefartcon ( set indefinite article condition )
variable inflex1  ( inflection from VerbPhrase to SpeechAct )
variable instnum  ( instantiation number for whatIs/Be )
variable IQ 6 IQ ! ( an invitation to code an IQ algorithm)
variable isflag   ( 7dec2009 To detect input of "IS" )
variable jrt ( ReJuvenate "junior time" for memories moved)
variable jux  0 jux ! ( holds Psi # of a JUXtaposed word )
variable kbcon  ( flag for awaiting a yes-or-no answer 2jul2011 )
variable kbpsi  ( 20jan2008 an interim knowledge-base psi )
variable kbquiz 0 kbquiz !  ( flag to call kbSearch )
variable kbtv  0 kbtv !  ( KbTraversal trigger; 7aug2010 )
variable kbyn  ( holds kbtv values for asking Y/N 24jun2011 )
variable kibosh  ( suppresses concepts failing to win selection )
variable krt ( Knowledge Representation time "t" for later)
variable lastpho  ( 24may2009 to avoid extra "S" on verbs )
variable lastword  0 lastword !  ( for zeroing "seq" tags.)
variable len  ( length, for avoiding non-words in AudInput)
variable lexact  ( testing a lexical "act" for EnReify )
variable lopsi  ( "low-psi" tag on just-crested concept )
variable lurk ( counter to activate initial thinking; 19sep2010 )
variable match  ( end-of-word flag for control )
variable maxbeact ( to prevent BeVerb from calling AskUser )
variable memoire  ( instead of "motjuste" in kbSearch )
variable mfn  ( "masculine feminine neuter" gender flag )
variable mfnflag ( gender flag to cause a who-query; 17aug2010 )
variable midway 1 midway ! ( limit for searching backwards)
variable monopsi ( 26jul2002 For use in audRecog module )
variable morphpsi ( for audRecog recognition of morphemes )
variable motjuste ( best word for inclusion in a thought )
variable nacpsi   ( 9may2009 de-globalized psi for NounAct)
variable nen  0 nen ! ( English lexical concept number )
variable newpsi   ( for singular-nounstem assignments ) 
variable nlt  0 nlt !  ( not-later-than among time-points )
variable notjux  ( flag for 12=NOT juxtaposed to a verb; 11aug2011 )
variable nounval 0 nounval ! ( from NounPhrase to MounAct )
variable nphrnum 0 nphrnum ! ( NounPhrase number )
variable nphrpos 0 nphrpos ! ( for testing in EnCog )
variable num 0 num !  ( number-flag for the psi array )
variable numflag ( 4dec2009 for selection of verb-forms )
variable numsubj ( 13apr2010 for number of subject )
variable nwc    ( new-word-count for noun-stem recog )
variable objold  ( a test for optimizing slosh-over; 12oct2010 )
variable obstat ( Lets AudInput psi-damp a reentrant word.)
variable oldact ( show the source of spreading activations)
variable oldpos ( old part-of-speech for use with verbs )
variable oldpsi ( used in OldConcept to de-globalize "psi")
variable olfpsi ( concept-tag attached to smells in memory)
variable olfrec ( for external recognition by OlfRecog )
variable onset 0 onset ! ( of an auditory memory engram )
variable opt  ( option, for flushing out a part of speech )
variable ordo 0 ordo ! ( from JSAI; AudInput word-order )
variable penultpho  ( 17may2009 next-to-last phoneme )
variable pho ( phoneme of input/output & internal reentry )
variable pos  ( old- & newConcept; enVocab: part-of-speech)
variable posflag  ( AskUser discriminand; 9aug2010 )
variable pov  ( point-of-view: #35 internal; *42 external )
variable pre ( previous concept associated with a concept )
variable precand  ( inviolate "pre" candidate from JSAI )
variable predflag ( indicates predicate nominative 11sep2010 )
variable predpos 0 predpos ! ( Predicate part of speech )
variable prejux  ( previous jux to carry NOT to verb 21jul2011 )
variable prepho   ( 17may2009 previous phoneme )
variable prepsi ( synaptic deglobalized "pre" in SpreadAct)
variable preset 0 preset ! ( for setting InStantiate "pre")
variable prevtag  ( from JSAI; for use in InStantiate )
variable prsn  0 prsn ! ( 1st, 2nd, 3rd person )
variable psi ( identifier of a psi concept in Psi mindcore)
variable psi1 ( activation-level at each node of verb )
variable psi3 0 psi3 ! ( for VerbPhrase to find negation 25jun2011 )
variable psi7 ( tutorial enx in tutorial or diagnostics )
variable psibase ( winning psibase with winning actbase )
variable putnum  ( putative number for subj-verb agreement )
variable questype  ( oldConcept; Conjoin: "question-type" )
variable quiet 1 quiet ! ( status flag for auditory input )
variable quo ( 27dec2009 query-object for EnCog response )
variable quobj ( query-object for yes-or-no questions 24jun2011 )
variable qup ( 28dec2009 query-predicate if verb not given )
variable qus ( 27dec2009 query-subject for EnCog response )
variable quset ( 3jan2010 query-set flag from OldC to EnCog )
variable qusub  ( internal provisional query-subject; 3oct2010 )
variable qutop ( query-topic to maintain chain of thought 26jul2010 )
variable quverb  ( query-verb for yes-or-no questions 24jun2011 )
variable recnum  ( recognized number of a recognized word 19jul2011 )
variable recon 0 recon ! ( reconnaissance flag for Q & A )
variable reject 0 reject ! ( used in sentence-generation )
variable retropsi   ( for AudInput and Audmem noun-stems )
variable residuum 0 residuum ! ( activation after PsiDamp )
variable rjc  0 rjc ! ( rejuvenation counter for tracking )
variable rsvp 1000 rsvp ! ( user-response delay-counter)
variable rv ( "recall-vector" for diagnostic display )
variable seq  ( subSEQuent concept associated with another)
variable seqpsi ( synaptic deglobalized "seq" in SpreadAct)
variable singflag  ( singularity flag for singular nouns )
variable skipseq  ( possible replacement for lackseq 30jul2011 )
variable sknlp  ( 8jan2010 SelfRef "skip NLP" for EnCog )
variable spacegap  ( to add gap of one space in SpeechAct )
variable spike  ( 1aug2005: for potential use in SpreadAct)
variable spt  ( AudMem; AudInput: blank space time )
variable stemgap  ( for avoiding false audRecog stems )
variable stempsi  ( for singular noun-stem recognition )
variable subj     ( flag to supercharge subject-nouns )
variable subjectflag  ( 3dec2009 a default for NounPhrase )
variable subjnum ( for agreement with predicate nominative )
variable subjold ( old subject as default candidate 28sep2010 )
variable subjpsi  ( For Predicate to correct beVerb choice)
variable sublen   ( length of audRecog subpsi word-stem )
variable subpsi ( for AudRecog of sub-component wordstems )
variable supsi    ( subject-psi for calculating "thotnum" )
variable t  0 t ! ( time incremented during AudMem storage)
variable t2s ( auditory text-to-speech index for SpeechAct)
variable tacpsi  ( concept-tag attached to tactile engrams)
variable tacrec   ( for external recognition by TacRecog )
variable tbev  ( time of be-verb for use with aftjux 27jul2011 )
variable tdy  ( 27dec2009 "temporary duty" of NLP modules )
variable tkbn  ( time of KbRetro noun adjustment; 2jul2011 )
variable tkbv  ( time of KbRetro verb adjustment; 2jul2011 )
variable topic  ( topic for a question to be asked )
variable topicnum ( grammatical number of question "topic")
variable tov 1 tov ! ( time-of-voice for keeping track )
variable trc  ( 20dec2009 tabula-rasa-counter like rjc )
variable tsday    ( for AudListen transcript-mode headers )
variable tseln  ( time of selection of noun;  8may2011 )
variable tselo  ( time of selection of object 30jul2011 )
variable tsels  ( time of selection of subj. 28jul2011 )
variable tselv  ( time of selection of verb;  8may2011 )
variable tshour   ( AudListen )
variable tsminute ( AudListen )
variable tsmonth  ( AudListen )
variable tssecond ( AudListen )
variable tsyear   ( AudListen )
variable tult     ( t penultimate, or time-minus-one )
variable unk  ( "unknown" variable for general use )
variable unkflag  ( 7dec2009 for NewConcept to pass to SelfRef )
variable upnext  ( Flag lets new input de-crest previous. )
variable urpre ( original pre during call to other module )
variable urpsi ( original psi for use in psiDamp, etc. )
variable vacpsi  ( de-globalized psi for VerbAct; 27sep2010 ) 
variable vault 439 vault ! ( size of EnBoot; 21jul2011 )
variable vbpsi   ( verb-psi for calculating "thotnum" )
variable verbpsi  ( for transit into WhatAuxSVerb 13jun2011 )
variable verbval  ( transfer from VerbPhrase to VerbAct )
variable vispsi ( concept-tag attached to images in memory)
variable visrec   ( for external recognition by VisRecog )
variable vphract  ( verb phrase activation level 19jun2011 )
variable vphraud  ( holds aud-fetch for SpeechAct; 25jun2011 )
variable vpos     ( verb part of speech for inflections )
variable vrsn 20110818 vrsn ! ( version identifier; 18aug2011 )
variable whatdoflag ( 21jan2010 for what-do query response )
variable whereflag 0 whereflag ! ( for InStantiate )
variable whoflag   0 whoflag !   ( for InStantiate )
variable whomark  ( InStantiate: for sake of qutopl 26jul2010 )
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


cns @  8  CHANNEL  psi{  ( Mindcore concept array "psi" )
cns @  8  CHANNEL   en{  ( English lexicon array "en" )
cns @  6  CHANNEL  aud{  ( Auditory memory channel "aud" )


:  PsiClear  ( set Psi activations to zero; 26sep2010 )
\ CR ." PsiClear called by " caller @ .  \ test; 7may2011
  1   t @  1 +  DO
    0 I 1 psi{ !
  -1 +LOOP
;  ( End of PsiClear )


:  TabulaRasa
  0 trc !  ( 20dec2009 tabula-rasa-counter like jrc )
  1 tov !
  BEGIN  cns @  1  DO
    0 I  trc @  psi{ !
  LOOP
  1  trc +!
  trc @  8  <  WHILE
  REPEAT
  0 trc !
  1 tov !
  BEGIN  cns @  1  DO
    0 I  trc @   en{ !
  LOOP
  1  trc +!
  trc @ 8 < WHILE  \ Cover #0 to #7, i.e. 8
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
;  ( End of TabulaRasa )


\ SubjectClear is a mechanism to help SelfRef and EnCog in
\ answering "what-do" questions. A subject noun is deactivated
\ so that slosh-over activation may identify an answer.
:  SubjectClear ( remove activation from a subject ) \ 19jan2010
  CR ." SubjectClear runs " \ test; remove; 15sep2010
  midway @  cns @  DO     \  Loop backwards over time.
    I     0 psi{ @ qus @ = IF  \ Look for qus query-subject
      0 I 1 psi{ !    \ 19jan2010 Set subject to zero activation.
    THEN              \ 19jan2010 End of test for query-subject
  -1  +LOOP  \  End of backwards loop looking for query-subject
;  ( End of SubjectClear )


\ NounClear is a mechanism called by NounPhrase to set
\ activation on nouns and pronouns to zero just before
\ a pair of old and new noun-engrams is reduced even
\ further into negative activation by neural inhibition.
\ The purpose is to prevent the build-up of stray activations.
:  NounClear ( remove activation from all nouns ) \ 20dec2009
  midway @  cns @  DO     \  Loop backwards over time.
  \ I     5 psi{ @ 5 = IF  \ 20dec2009 Look for noun pos.
    I 5 psi{ @ 5 = I 5 psi{ @ 7 = OR IF \ pro(noun) 18aug2011
      0 I 1 psi{ !    \ 20dec2009 Set noun to zero activation.
    THEN              \ 20dec2009 End of test for pos=5 nouns.
  -1  +LOOP  \  End of backwards loop looking for pos=5 nouns.
;  ( End of NounClear; return to NounPhrase; 18aug2011 )


:  VerbClear ( remove activation from all verbs )
  midway @  t @  DO
    I     5 psi{ @ 8 = IF
      0 I 1 psi{ !
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
;  ( End of VerbClip; return to AudInput )


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
    I  0  psi{ @ 59 = IF  0  I  1  psi{  ! THEN  \ 59=DO
    I  0  psi{ @ 54 = IF  0  I  1  psi{  ! THEN  \ 54=WHAT
    I  0  psi{ @  7 = IF  0  I  1  psi{  ! THEN  \  7=THE
  -1  +LOOP
;  ( End of PsiDecay )


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
  caller @ 6967 = IF ." EnCog "     THEN \ test; 26sep2010
  caller @ 8766 = IF ." WhoBe "     THEN \ test; 26sep2010
  caller @ 8773 = IF ." WhatBe "    THEN \ changed; 25feb2011
  0 caller !
  THEN
  urpsi @ 57 = IF  58 urpsi ! THEN  \ 57=AM;  14aug2011
  urpsi @ 66 = IF  58 urpsi ! THEN  \ 66=IS;  14aug2011
  urpsi @ 67 = IF  58 urpsi ! THEN  \ 67=ARE; 14aug2011
  urpsi @ 55 = IF  \ if urpsi is 55=WHO
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
;  ( End of PsiDamp )


:  EnDamp ( deactivate English lexicon concepts )
  midway @  t @  DO
    0 I  1  en{ !
  -1 +LOOP
;  ( End of EnDamp )


:  AudDamp ( deactivate auditory engrams )
  midway @  t @  DO
    0 I  1 aud{ !
  -1 +LOOP
;  ( End of AudDamp )


:  .psi ( show concepts in the Psi array )
  CR  ." Psi mindcore concepts"
  CR  ." time: psi act num jux pre pos seq enx "
  t @ 1+  midway @ DO
    I    0  psi{ @ 0 > IF
      CR I . ." : "
      I  0  psi{ @ . ." "
      I  1  psi{ @ . ." "
      I  2  psi{ @ . ." "
      I  3  psi{ @ . ." "
      I  4  psi{ @ . ." "
      I  5  psi{ @ . ." "
      I  6  psi{ @ . ." "
      I  7  psi{ @ enx ! enx @ .
      enx @ 0 > IF
        ." to "
        I unk !
        0 aud !
        midway @ unk @  DO
          I   0 en{ @  enx @ = IF
            I 7 en{ @  aud  !
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
  CR ." time: psi act num jux pre pos seq enx "  0 unk !
  CR ." You may enter .psi or .en or .aud to view memory "
  ." engrams or "
  CR ." MainLoop [ENTER] to erase all memories "
  ." and restart the Mind."
  CR
;  ( End of .psi post-Escape report )


:  .en ( show vocabulary in the English lexicon array )
  CR ." English lexical fibers"
  CR ." t nen act num mfn fex pos fin aud:" \ 13apr2010
  t @  1+  midway @  DO
    I  0  en{ @  unk !
    unk @  0 > IF ( display positive data )
      CR I . unk @ . ." "
      I 1 en{ @ . ." "
      I 2 en{ @ . ." "
      I 3 en{ @ . ." "
      I 4 en{ @ . ." "
      I 5 en{ @ . ." "
      I 6 en{ @ . ." "
      I 7 en{ @ aud !  aud @ . ."  to "
      BEGIN
        aud @ 0 aud{ @ EMIT  1 aud +!
        aud @ 0 aud{ @ 32 =
      UNTIL
      ."  "
      0 aud !
    THEN
  LOOP
  0 unk !
  CR ." t nen act num mfn fex pos fin aud" CR
  CR ." You may enter .psi or .en or .aud to view memory "
  ." engrams or "
  CR ." MainLoop [ENTER] to erase all memories "
  ." and restart the Mind."
  CR
;  ( End of .en post-Escape report )


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
  CR ." You may enter .psi or .en or .aud to view memory "
  ." engrams or "
  CR ." MainLoop [ENTER] to erase all memories "
  ." and restart the Mind."
  CR
;  ( End of .aud post-Escape report )


: .echo ( show what the robot just said )
  ( As on Usenet, user responds _below_ the AI output. )
  fyi @ 2 = IF
    CR ." Tutorial mode is now in effect. "
    ."  Enter input or wait for output."
  THEN
  CR  ." Robot: "
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
  pre @ 0 > IF
    zone @ 7 -   zone @  DO
      I 0  psi{ @   prepsi @  =  IF  \ now prepsi; 15sep2010
                1   I  1 psi{ +!
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
            0 psi7 !
            fyi @ 3 = IF
              CR ." sprdAct: seqpsi = " seqpsi @ . CR \ 24sep2010
            THEN
            midway @ t @ DO
              I   0  psi{ @ cogpsi @ = IF
                I 7  psi{ @   psi7 !
                LEAVE
              THEN
            -1  +LOOP
            midway @ t @ DO
              I   0  en{ @    psi7 @ = IF
                I 7  en{ @  rv !
                LEAVE
              THEN
            -1  +LOOP
            0 rv !
            midway @ t @ DO
              I   0  psi{ @  seqpsi @ = IF  \ 15sep2010
                I 7  psi{ @   psi7 !
                LEAVE
              THEN
            -1  +LOOP
            midway @ t @ DO
              I   0  en{ @    psi7 @ = IF
                I 7  en{ @  rv !
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
            0 psi7 !
            midway @ t @ DO
              I   0  psi{ @   cogpsi @  =  IF
                I 7  psi{ @   psi7 !
                LEAVE
              THEN
            -1  +LOOP
            midway @ t @ DO
              I   0  en{ @    psi7 @ = IF
                I 7  en{ @  rv !
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
            ."  #" cogpsi @ . ." act " oldact @ .
            ." at i " I . ." sprA spike "
            spike @ . ." to seqpsi #" seqpsi @ . \ 20sep2010
            midway @ t @ DO
              I   0  psi{ @  seqpsi @ = IF  \ 15sep2010
                I 7  psi{ @   psi7 !
                LEAVE
              THEN
            -1  +LOOP
            midway @ t @ DO
              I   0  en{ @    psi7 @ = IF
                I 7  en{ @  rv !
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
        I           1 psi{ @ -1 > IF \ avoid inhibition;
          subjectflag @ 1 = IF  \ onto verb-nodes; 18oct2010
          ( insert diagnostic code here to troubleshoot 5aug2011 )
            spike @ I 1 psi{ +!  ( add spike to seqpsi 15sep2010 )
          ELSE  \ in all other cases, e.g. dirobj; 25jun2011
          ( insert diagnostic code here to troubleshoot 5aug2011 )
            spike @ I 1 psi{  !  ( Xfer absolute act; 25jun2011 )
          THEN  \ end of test for subject-nodes; 18oct2010
        THEN  \ end of test to skip inhibited nodes; 9sep2010
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
;  ( End of SpreadAct; return to NounAct, VerbAct or ReActivate )


:  NounAct ( re-activate all recent nodes of a concept )
  0 unk !  \ reset before using in NounAct; 8aug2011
  26 nounval !  \ decremend; test; remove; 8aug2011
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
      ( insert diagnostic code here; 8aug2011 )
     \ 26   I  1 psi{ !  \ trying revert to 4aug; 6aug2011
  nounval @ I  1 psi{ !  \ whether integer or variable; 8aug2011
            I  0 psi{ @  54 = IF
          0 I  1 psi{ !
              PsiDecay  \ await active subject; 24sep2010
              PsiDecay  \ commenting out 1 of 2 29jul2011
            THEN
                  12 spike !  ( Aim for ample spikes.)
          I  4 psi{ @  prepsi !  ( for SpreadAct 15sep2010 )
          I  6 psi{ @  seqpsi !  ( for SpreadAct 15sep2010 )
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
        nacpsi @ cogpsi !
          I  1 psi{ @ oldact !
          I  5 psi{ @ oldpos !
        seqpsi @  0 > IF  \ replacement; 15sep2010
          seqpsi @ 55 = IF  \ 55=WHO; 15sep2010
            1 spike !  \ not 24 act; 11aug2010
          THEN   \ end of experiment; 11aug2010
          ( insert diagnostic code here; 8aug2011 )
        unk @ -10 < IF -10 unk ! THEN  \ limit decrement 8aug2011
        unk @ spike +!  \ decrement spike; 8aug2011
          7865 caller !
          SpreadAct  ( for spreading activation )
          -1 spike +!  \ to let recent engrams win; 8aug2011
          0 caller !
          0 prepsi !  \ replacing presyn; 15sep2010
          0 seqpsi !  \ replacing seqsyn; 15sep2010
        THEN
        precand @ pre !
        0 oldpos !
        0 cogpsi !
        0 oldact !
        0  pre !
      THEN
      0 spike !  \ reset for each new loop; 14oct2010
    -1  +LOOP
  THEN
  0 spike !
;  ( End of NounAct )


:  VerbAct ( re-activate all recent nodes of a verb )
  28 verbval !  \ trying revert to 5aug; 6aug2011
  fyi @ 2 > IF CR
  ."     Calling verbAct (not in AI4U). psi = " psi @ . CR
  THEN
  vacpsi @  0 >  IF  \ if a vacpsi exists; 9nov2010
    fyi @ 2 > IF
      CR ."       VerbAct calls SpreadAct to transfer "
      CR ." proportionate activation from each node of "
      CR ." concept #" psi @ .
    THEN
    vacpsi @ 57 = vacpsi @ 66 = OR vacpsi @ 67 = OR IF \ 10aug2011
      58 vacpsi !  \ convert to 58=BE to find seqpsi; 10aug2011
    THEN  \ end of test to switch AM IS ARE to 58=BE; 10aug2011
    vacpsi @ cogpsi !  \ deglobalizing from psi; 27sep2010
    midway @   t @ DO
      I 0 psi{ @ vacpsi @ = IF  \ deglobalized psi; 8oct2010
        fyi @ 2 > IF
          I 1 psi{ @ 8 > IF
            ." +"
          THEN
        THEN
            I  1 psi{ @  psi1 !
          I    1 psi{ @ -1 > IF \ avoid inhibited nodes; 9sep2010
          ( insert diagnostic code here; 6aug2011 )
   verbval @ I  1 psi{ +!  \ CUMULATIVE for slosh-over; 14oct2010
          THEN  \ end of test to skip inhibited nodes; 9sep2010
            I  0 psi{ @  54 = IF
          0 I  1 psi{ !
            THEN
          I  4 psi{ @  prepsi !  ( for SpreadAct 15sep2010 )
          I  6 psi{ @  seqpsi !  ( for SpreadAct 15sep2010 )
          I           zone !     ( for use in SpreadAct )
          I  1 psi{ @  0 = IF  0 spike ! THEN
          I  1 psi{ @  0 > IF  1 spike ! THEN
          I  1 psi{ @  5 > IF  3 spike ! THEN  \  2nov2010
          I  1 psi{ @ 10 > IF  6 spike ! THEN
          I  1 psi{ @ 15 > IF  9 spike ! THEN
          I  1 psi{ @ 20 > IF 12 spike ! THEN
          I  1 psi{ @ 25 > IF 15 spike ! THEN
          I  1 psi{ @ 30 > IF 16 spike ! THEN  \ 4aug2011
          I  1 psi{ @ 35 > IF 17 spike ! THEN  \ 4aug2011
          I  1 psi{ @ 40 > IF 18 spike ! THEN  \ 4aug2011
          I  1 psi{ @ 45 > IF 19 spike ! THEN  \  4aug2011
          I  1 psi{ @ 50 > IF 30 spike ! THEN
          I  1 psi{ @ 55 > IF 33 spike ! THEN
          I  1 psi{ @ 60 > IF 36 spike ! THEN
          I  1 psi{ @ 65 > IF 39 spike ! THEN  \  2nov2010
          I  1 psi{ @ 70 > IF 42 spike ! THEN  \  2nov2010
          I  1 psi{ @ 75 > IF 45 spike ! THEN  \  2nov2010
          I  1 psi{ @ 80 > IF 48 spike ! THEN  \  2nov2010
          I  1 psi{ @ 85 > IF 50 spike ! THEN  \  9nov2010
          I  1 psi{ @ 90 > IF 52 spike ! THEN  \  9nov2010
          I  1 psi{ @ 95 > IF 54 spike ! THEN  \  9nov2010
        vacpsi @ cogpsi !  \ deglobalizing; 27sep2010
          I  1 psi{ @ oldact !
          I  5 psi{ @ oldpos !
 fyi @ 2 = IF  \ In Tutorial mode show slosh-over; 17oct2010
   CR  ."    VerbAct calls SpreadAct with activation " \ 18oct
   spike @ . ." for Psi #" seqpsi @ . \ 18oct2010
 THEN  \  End of test for Tutorial mode; 17oct2010
        seqpsi @  0 > IF  \ replacement; 15sep2010
        ( insert diagnostic code here; 6aug2011 )
          8665 caller !
          SpreadAct  ( for spreading activation )
          0 caller !
          0 prepsi !  \ replacing presyn; 15sep2010
          0 seqpsi !  \ replacing seqsyn; 15sep2010
        THEN
        0 oldpos !
        0 cogpsi !
        0 oldact !
        0  pre !
        0  seq !
      THEN
      ( perhaps reset spike to zero for each loop? 14oct2010 )
      0 spike !  \ reset to start each loop again; 14oct2010
    -1  +LOOP
  THEN
;  ( End of VerbAct )


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
           35 I  1 psi{ +!  \ Relative, not absolute; 12aug2011
         THEN   \  End of new test for external POV;  7may2011
            I  0 psi{ @  54 = IF  \ 54=WHAT; 24sep2010
          0 I  1 psi{ !
            THEN
            I  0 psi{ @  55 = IF  \ 55=WHO;  3may2011
          0 I  1 psi{ !  \ As in InStantiate; 3may2011
            THEN  \ end of test for 55=WHO;  3may2011
            I  0 psi{ @  59 = IF  \ 12jan2010 59=DO
          0 I  1 psi{ !   \ 12jan2010 For what-do queries.
            THEN          \ 12jan2020 End of test for 59=DO
        0 oldpos !
        0 cogpsi !
        0 oldact !
        0    pre !
        0 prepsi !  \ replacing presyn; 15sep2010
        0    seq !
        0 seqpsi !  \ replacing seqsyn; 15sep2010
        0   psi1 !
        1  spike !
      THEN
    -1  +LOOP
    0 caller !
    0 urpsi !
  THEN
;  ( End of ReActivate )


:  InStantiate ( create a concept-fiber node )
  precand @ 0 > IF precand @ pre ! THEN
  ordo @ 1 = IF  0 prevtag ! THEN
  lastword @ 1 = IF
    0 seq !
    0 lastword !
  THEN
  t @ 439 > IF   \  Avoid the EnBoot vault  19jul2011
    whoflag @ 1 = IF
      psi @ 57 = IF 57 beflag ! THEN  ( AM )
      psi @ 66 = IF 66 beflag ! THEN  ( IS )
      psi @ 67 = IF 67 beflag ! THEN  ( ARE )
      pos @ 5 = pos @ 7 = OR IF
        beflag @ seq !
        0 beflag !
      THEN
    THEN
    psi @ 54 = IF  \ Special handling of psi #54 "WHAT"
      1 indefartcon ! \ Set indefinite article condition 16apr2011
      0 act !      \ To suppress "WHAT" during answer.
    THEN           \ End of test for input of "WHAT"
    psi @ 55 = IF  \ Special handling of psi #55 WHO; 3may2011
      1 defartcon ! \ Set definite article condition 16apr2011
      1 whoflag !
      1 whomark !  \ for who-is queries; 26jul2010
      0 act !      \ To suppress "WHO" during answer.
    THEN
    singflag @ 1 = IF
      pos @ 5 = IF
        1 num !
        0 singflag !
      THEN
    THEN
    psi @ 1 =  psi @ 83 = OR IF  \ "A" or "AN"; 6aug2011
      1 singflag !
      0 act !
    THEN
  THEN
  pos @ 5 = IF  \ noun either external or internal; 6aug2011
    recnum @ 0 > IF   \ If positive recog-num; 6aug2022
      recnum @ num !  \ Override num(ber); 6aug2011
      0 recnum !  \ reset for safety; 6aug2011
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
  THEN  \ End of test for #internal POV;  7may2011
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
  prevtag @ pre !
  ( concept fiber psi )             psi @  t @  0 psi{ !
  ( Set "act" activation level. )   act @  t @  1 psi{ +!
  ( Set "num" number flag       )   num @  t @  2 psi{ !
  ( Store JUXtaposition tags. )     jux @  t @  3 psi{ !
  ( Store PREvious associand. )     pre @  t @  4 psi{ !
  ( Store functional pos code. )    pos @  t @  5 psi{ !
  ( Store the subSEQuent tag. )     seq @  t @  6 psi{ !
  ( Store the EN-transfer tag. )    enx @  t @  7 psi{ !
  num @ instnum !
  pos @ 5 = IF num @ putnum ! THEN \ noun to verb; 24jun2011
  0 num !
  jux @ 12 = IF 0 jux ! THEN  \ reset after use; 21jul2011
  prejux @ 12 = IF  \ 12=NOT from OldConcept; 21jul2011
    12 jux !  \  set jux for next instantiand; 21jul2011
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
  ordo @ 1 > IF
    psi @ seq !
    vault @  t @ 2 -  DO
      I 0 psi{ @  0 > IF  \ Upon finding a single psi
        skipseq @ 1 = IF  \ if set one loop ago; 11aug2011
          t @ 12 -  t @ 4 -  DO  \ go further back; 21sep2010
            I     0 psi{ @ 0 > IF  \ Upon finding single psi
              I   5 psi{ @ 8 = IF  \ a verb
                I 6 psi{ @ 0 = IF  \ upon a zeroed seq
                  seq @ I 6 psi{ !  \ replace the seq
                THEN   \ end of test for a zeroed seq
                LEAVE  \ change only one seq
              THEN  \ end of test for "8" verb
            THEN  \  end of test for a positive psi
          -1 +LOOP  \ end of loop checking for a zero-seq
          0 skipseq !  \ reset after use; 11aug2011
        THEN   \ end of test of a lacking seq
        seq @ 12 = IF  \ 12=NOT; 28jul2011
          0 seq ! \ replace NOT with zero; 28jul2011
          1 skipseq ! \ flag for lack of "seq"; 11aug2011
        THEN  \ end of test for 12=NOT; 28jul2011
        seq @ 83 = IF  1 seq ! THEN \ treat AN as A
        seq @ 1 =  seq @ 7 = OR IF  \ A or THE
          0 seq ! \ replace A, AN, THE with zero
          1 skipseq ! \ flag for lack of "seq"; 11aug2011
        THEN  \ end of test for articles
        whoflag @ 1 = IF  \ during who-query
           I 0 psi{ @ 66 = IF  \ 66=IS
             0 seq !  \ after 66=IS blank seq
             0 whoflag !  \ reset for safety
           THEN  \ end of test for 66=IS
        THEN  \ end of test for who-query
        whoflag @ 1 = IF  \ during who-query; 25aug2010
           I 0 psi{ @ 58 = IF  \ 58=BE
             0 seq !  \ after 58=BE blank seq
             0 whoflag !  \ reset for safety
           THEN  \ end of test for 58=IF
        THEN  \ end of test for who-query; 25aug2010
        seq @ I 6 psi{ !
        LEAVE  \ Store only a recent "seq"
      THEN  \ end of test for a positive psi; 23aug2010
    -1 +LOOP
  THEN
  0 recnum !  \ lest carry-over to other words; 19jul2011
  0 seq !
;  ( End of InStantiate )


:  EnVocab ( English Vocabulary node creation )
  ( Number "nen" of English )       nen @  t @  0  en{ !
  ( Do not store the activation level; it is a transient.)
  ( Store "num" number tag. )       num @  t @  2  en{ !
  ( Store "mfn" gender tag. )       mfn @  t @  3  en{ !
  ( Store mindcore EXit tag. )      fex @  t @  4  en{ !
  ( Store part of speech "pos".)    pos @  t @  5  en{ !
  ( Store mindcore IN tag. )        fin @  t @  6  en{ !
  ( Store the auditory "aud" tag. ) aud @  t @  7  en{ !
;  ( End of EnVocab )


:  EnParser ( determine the part of speech )
  5 bias !
  35 act !  \ Activate lower than ReActivate; 29may2011
\ 30 act !  \ Activate lower than ReActivate; 11aug2011
  pov @ 42 = IF  \ only during external input; 9oct2010
    act @ ordo @ - act !  \ reduce S-V-O act's; 9oct2010
  THEN  \ end of tesrt for external POV; 9oct2010
  InStantiate  \ create a Psi concept node; 6nov2010
  pos @ 5 = IF  8 bias !  THEN
  pos @ 7 = IF  8 bias !  THEN
  pos @ 8 = IF  5 bias !  THEN
;  ( End of EnParser )


\ Activations no longer need to be transferred as of 12aug2011.
:  EnReify ( express abstract concepts as real words )
  0 act !
  midway @  t   @  DO
          I   1 psi{ @  0 > IF
          I   1 psi{ @  lexact !
          I   2 psi{ @  num !
        \ I   7 psi{ @  enx !
        \ I   0  en{ @  enx @ = IF \ test; 2aug2011
        \ I   0  en{ @  enx @ = IF \ Commenting out; 8aug2011
 lexact @ I   1  en{ !
    num @ I   2  en{ !
            0 lexact !
        \ THEN
         THEN
    0 enx !
    0 act !
    0 lexact !
  -1  +LOOP
  0 act !
;  ( End of EnReify )


:  KbSearch ( knowledge base search )
  ordo @ 2 = IF
    NounAct  ( may need a "nacpsi" value )
    EnReify
  THEN
  ordo @ 3 = IF
    0 act !
    midway @ t  @ DO
      I     5 en{ @  8 = IF   \ Test part-of-speech.
        I   1 en{ @  act @ > IF  ( if en1 is higher )
          I 0 en{ @  memoire !  ( store psi-tag of word )
          I 1 en{ @  act !  ( to test for a higher en1 )
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
    EnReify
  THEN
  ordo @ 4 = IF
    0 act !
    0 memoire !
    midway @ t  @ DO
      I 5 en{ @ 5 = I 5 en{ @ 7 = OR IF
        I    1 en{ @  act @ > IF  ( if en1 is higher )
          I  0 en{ @  memoire !  ( store psi-tag of word )
          I  1 en{ @  act !  ( to test for a higher en1 )
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
  THEN
  0 kbquiz !
  ordo @ 4 = IF 0 ordo ! THEN
;  ( End of KbSearch )


( http://code.google.com/p/mindforth/wiki/KbRetro )
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


:  OldConcept ( recognize a known word )
  28 act !  \ A value subject to optimization; 28sep2010
  midway @ t @ DO
    I 0 en{ @ oldpsi @ = IF
    I 2 en{ @    0 > IF
  \ I 2 en{ @  num ! THEN  \ Commenting out on 19jun2011
    I 2 en{ @  unk ! THEN  \ Preserve global "num" value.
    I 3 en{ @    0 > IF
    I 3 en{ @  mfn ! THEN
    I 4 en{ @    0 > IF
    I 4 en{ @  fex ! THEN
    I 5 en{ @    0 > IF
    I 5 en{ @  pos ! THEN
    I 6 en{ @    0 > IF
    I 6 en{ @  fin ! THEN
    LEAVE
    THEN
  -1 +LOOP
    pos @ 8 = IF  \ verb? for WhatAuxSVerb 13jun2011
      numsubj @ unk !  \ assume agreement; 19jun2011
    THEN  \ end of test for verb \ 13jun2011
  oldpsi @ 57 = IF t @ tbev ! THEN  \ 57=AM;  27jul2011
  oldpsi @ 58 = IF t @ tbev ! THEN  \ 58=BE;  28jul2011
  oldpsi @ 66 = IF t @ tbev ! THEN  \ 66=IS;  27jul2011
  oldpsi @ 67 = IF t @ tbev ! THEN  \ 67=ARE; 27jul2011
  ( oldpsi found by AudRecog )   oldpsi @  t @  0  en{ ! 
\ ( Store zero activation. )          0    t @  1  en{ !
  ( Add zero activation 28jul2011 )   0    t @  1  en{ +!
  ( Store number tag; 19jun2011 )   unk @  t @  2  en{ !
  ( Store "mfn" gender tag. )       mfn @  t @  3  en{ !
  ( Store mindcore EXit tag. )      fex @  t @  4  en{ !
  ( Store part of speech "pos".)    pos @  t @  5  en{ !
  ( Store mindcore IN tag. )        fin @  t @  6  en{ !
  ( Store the auditory "aud" tag. ) aud @  t @  7  en{ !
  pov @  35 = IF fex @ oldpsi ! THEN  ( internal pov )
  pov @  42 = IF fin @ oldpsi ! THEN  ( external pov )
  oldpsi @  enx !
  oldpsi @ 12 = IF  \ 12=NOT; 27jul2011
    tbev @ 0 > IF   \ if positive be-verb time; 27jul2011
    12  tbev @  3 psi{ !  \ set verb "jux" to NOT; 27jul2011
    0 tbev !  \ reset for safety; 27jul2011
    THEN  \ end of test for a positive tbev; 27jul2011
  THEN  \ end of test for input of 12=NOT; 27jul2011
  oldpsi @ 54 = IF 8 act ! THEN  ( 54=WHAT )
  oldpsi @ 55 = IF 8 act ! THEN  ( 55=WHO )
  ordo @ 1 = IF
    oldpsi @ 59 = IF  ( 59=DO )
      1 kbquiz !
    THEN
  THEN
  oldpsi @ 59 = IF 0 act ! THEN  ( 59=DO )
  oldpsi @  7 = IF 1 act ! THEN  (  7=THE )
  kbcon @  0 > IF  \ if awaiting answer; 2jul2011
    KbRetro  \ retroactively adjust knowledge base;  2jul2011
  THEN  \  2jul2011
  oldpsi @ 12 = IF  \ 12=NOT; 21jul2011
    12 prejux !  \ set flag for verb; 21jul2011
    12 aftjux !  \ set flag for a be-verb; 28jul2011
  \ CR ." OldPsi: setting prejux to 12=NOT " \ 21jul2011
  THEN  \ end of test for 12=NOT negation; 21jul2011
  oldpsi @ psi !
  EnParser
  fyi @ 2 > IF CR
  ."   from OldConcept "
  THEN
  pov @ 42 = IF  ( external pov )
    whatdoflag @ 1 = IF  \ If flag set after "what do"
      psi @ 59 = IF  \ After "DO"
        quset @ 0 = IF  \ Prevent call during reply.
        \ CR ." OldC calling PsiClear " \ test; 7may2011
          PsiClear  \ Zero out MindGrid for sake of query.
        THEN  \ End of test of quset
      THEN  \ End of test for 59=DO.
    THEN   \ End of test for "what do" flag.
    ReActivate
  THEN
  0 act !
  pov @ 35 = IF  ( internal pov )
    1 match !
  THEN
  pos @ 8 = IF psi @ quverb ! THEN  \ for yes-or-no; 24jun2011
  kbquiz @ 0 > IF
    1 yesorno !
    KbSearch
  THEN
  yesorno @ 0 > IF
    KbSearch
  THEN
  0 pos !  \ Reset no longer above but down here.
;  ( End of OldConcept; return to AudInput )


:  NewConcept ( machine learning of new concepts )
  0 newpsi !
  1 unkflag !  \ for SelfRef NOT-KNOW response.
  1 nen +!
  1 nwc +!
  nen @ IQ !
  nen @ newpsi !
  nen @ stempsi !
  nen @ psi !
  nen @ fex !
  nen @ fin !
  bias @ pos !
  bias @ 8 = IF putnum @ num !  THEN  \ 24jun2011
  EnVocab ( to create an English vocabulary node )
  0 fex !
  0 fin !
  nen @  enx !
  EnParser
  pos @ 8 = IF nen @ quverb ! THEN  \ for yes-or-no; 24jun2011
  kbcon @  0 > IF  \ if awaiting answer; 2jul2011
    KbRetro  \ retroactively adjust knowledge base;  2jul2011
  THEN  \  2jul2011
  0 pos !
  0 act !
;  ( End of NewConcept )


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
          \ I 1 aud{ @ 0 > IF  \ Or test for eight (8).
            I 1 aud{ @ 7 > IF  \ testing for eight (8).
              I 5 aud{ @ psibase !  \ Assume a match.
            THEN  \  End of test for act=8 or positive.
          THEN   \ End of test for two-letter words.
        THEN   \ End of test for end of word.
        I 1 aud{ @ 8 > IF  \ If activation higher than initial
          8 actbase !  \ Since act is > 8 anyway; 8may2010
          I 4 aud{ @ 0 = IF  \ If matching word-engram now ends,
            I 1 aud{ @ actbase @ > IF  \ Testing for high act.
              I 5 aud{ @ audrec !  \ Fetch the potential tag
              I 5 aud{ @ subpsi !  \ Seize a potential stem.
              len @ sublen !    \ Hold length of word-stem.
              I 5 aud{ @ psibase !  \ Hold onto winner.
              I 2 psi{ @ recnum !   \ recognized number 19jul2011
              I 1 aud{ @ actbase !  \ Winner is new actbase.
            THEN  \ End of test for act higher than actbase.
          ELSE
            0 audrec !
            monopsi @ 0 > IF
              monopsi @ audrec !
              0 monopsi !
            THEN   \ End of inner test.
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
;  ( End of AudRecog; return to AudMem auditory memory )


:  AudMem ( auditory memory channel )
  t @ vault @ > IF
    pho @ 32 > IF
      AudRecog
    THEN  ( ASCII 32 = SPACE-bar )
  THEN
    t @ 1-  0 aud{ @  0 = IF  1 beg !  THEN
    t @ 1-  0 aud{ @ 32 = IF  1 beg !  THEN
    pho @  t @  0 aud{ !
    pov @  t @  2 aud{ !
    beg @  t @  3 aud{ !
    ctu @  t @  4 aud{ !
    ctu @ 0 = IF
      audpsi @ 0 > IF
        audpsi @  t @  5 aud{ !
      THEN
      0 audpsi !
    THEN
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
;  ( End of AudMem; return to AudInput )


:  AudListen ( preparation for AudInput )
  rsvp @  1  DO
    KEY? IF
      KEY pho !
      0 quiet !
      pho @  8 = IF 7 EMIT THEN
      pho @  9 = IF
         400 rsvp !  ( 23dec2009 From Supercomputer mind.frt )
        pho @ 13 = IF  1 lastword !  THEN
        fyi @ 0 = IF CR CR
          TIME&DATE  tsyear ! tsmonth ! tsday !
          tshour ! tsminute ! tssecond !
          ." Transcript of AI Mind interview at "
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
        CR ." You may enter .psi or .en or .aud to view "
        ." memory engrams, or " CR ." MainLoop [ENTER] "
        ." to erase memories and restart the Mind."
        CR ." Type 'bye' to quit Forth, EXIT to quit DOS."
        CR
        0 audpsi ! 0 newpsi ! 0 oldpsi ! 0 stempsi !
        0 areflag !    \ 11dec2009 In case AI is run again.
        1 audrun !     \ 26jul2010 In case AI is run again.
        0 beact !      \ 10aug2010 In case AI is run again.
        0 defartcon !  \ 16apr2011 In case AI is run again.
        0 indefartcon ! \ 16apr2011 In case AI is run again.
        0 isflag !     \  7dec2009 In case AI is run again.
        0 kbtv !       \ 28sep2010 In case AI is run again.
        0 maxbeact !   \ 19aug2010 In case AI is run again.
        0 mfn !        \ 25aug2010 In case AI is run again.
        0 mfnflag !    \ 23aug2010 In case AI is run again.
        0 motjuste !   \ 29aug2010 In case AI is run again.
        0 objold !     \ 12oct2010 In case AI is run again.
        0 ordo !       \ 21dec2009 In case AI is run again.
        0 prsn !       \ 29aug2010 In case AI is run again.
        0 psi1 !       \ 25aug2010 In case AI is run again.
        0 qus !        \ 27dec2009 In case AI is run again.
        0 quset !      \  3jan2010 In case AI is run again.
        0 quo !        \ 27dec2009 In case AI is run again.
        0 qup !        \ 28dec2009 In case AI is run again.
        0 sknlp !      \  8jan2010 In case AI is run again.
        0 subjold !    \  9oct2010 In case AI is run again.
        0 subjpsi !    \  1jan2010 In case AI is run again.
        0 vphract !    \ 21jun2011 In case AI is run again.
        0 whatdoflag ! \ 21jan2010 In case AI is run again.
        0 whoflag !    \ 23jul2010 In case AI is run again.
        0 unkflag !    \  7dec2009 In case AI is run again.
        QUIT
      THEN
      pho @ 0 > IF
        pho @ EMIT
      THEN
      pho @ DUP 96 > IF
        DUP 123 < IF
          32 -
        THEN
      THEN  pho !
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
;  ( End of AudListen )


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
     CR ." Human: "
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
      THEN
      bias @ 5 = IF  \ If EnParser expects a noun; 6aug2011
        pho @ 83 = IF  \ If "83=S";  6aug2011
          2 num !  \ Assign plural number; 6aug2011
        THEN  \ Only terminating "S" governs "num" 6aug2011
        pho @  0 > IF   \ Disregard empty pho; 6aug2011
          pho @  32 = NOT IF  \ Disregard SPACE; 6aug2011
            pho @  13 = NOT IF  \ Disregard CR; 6aug2011
              pho @ 83 = NOT IF \ If other than "S"; 6aug2011
                1 num !  \ Assume singular number; 6aug2011
              THEN  \ If last letter is not "S"; 6aug2011
            THEN  \ End of test for carriage-return 6aug2011
          THEN  \  End of test for SPACE; 6aug2011
        THEN  \ End of test for empty pho; 6aug2011
      THEN  \ End of test for noun-expected; 6aug2011
    THEN  \ end of test for pov "35=#" internal reentry
    pov @ 42 = IF   ( during external input )
      AudListen
      pho @ 0 > IF
        0 kbtv !
        1 upnext +!
        upnext @ 1 = IF
          hipsi @ urpsi !  \ What-do queries require
          urpsi @ 0 > IF  \ only positive concepts; 14sep
            104 caller !  \ wiping out even of residuum.
          \ PsiDamp  \ leaving a "residuum" activation.
          \ PsiDamp  \ Commenting out; test; 11oct2010
          THEN  \ end of test for positive psi; 14sep2010
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
        pho @ 13 = IF 10 EMIT THEN
        prepho @ 83 = IF
          0 t @ 1 - 4 aud{ !
          0 prepho !
        THEN
      THEN
      bias @ 5 = IF  \ If EnParser expects a noun 26may2011
        pho @ 83 = IF  \ If "S"
          2 num !  \ Assign plural number; 26may2011
        THEN  \ Only terminating "S" governs "num" 26may2011
        pho @  0 > IF   \ Disregard empty pho;  26may2011
          pho @  32 = NOT IF  \ Disregard SPACE; 26may2011
            pho @  13 = NOT IF  \ Disregard CR; 26may2011
              pho @ 83 = NOT IF \ If other than "S" 26may2011
                1 num !  \ Assume singular number; 26may2011
              THEN  \ If last letter is not "S"; 26may2011
            THEN  \ End of test for carriage-return 26may2011
          THEN  \  End of test for SPACE; 26may2011
        THEN  \ End of test for empty pho;  26may2011
      THEN  \ End of test for noun-expected; 26may2011
    THEN  \ End of test for external input
    pho @  0 > IF
      1 t +!
    THEN
    pho @ 13 = IF
       1 audrun !  \ Reset to one at CR end of input.
       1 quiet !
       1 beg !
      13 eot !
      32 pho !
      10 EMIT
      CR
       1 lastword !
    THEN
    pho @ 27 =  IF
      CR ." AudInput: halt"  0 pho !  0 fyi !  0 nounval !
      CR ." You may enter .psi .en .aud to view memory "
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
            nen @  tult @  5 aud{ !
     nen @  tult @ 1- 5 aud{ !
            nen @ retropsi !
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
;  ( End of AudInput; return to SensoryInput or SpeechAct. )


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
;  ( End of SensoryInput )


:  EnBoot ( English bootstrap of initial concepts )
  0 act ! 0 jux ! 35 pov ! 0 t ! t @ spt !
  ." clearing memory"
  CR ." There is no warranty for what this software does."
 ( ERROR -- first word so any bug will announce itself )
    1 t !  69 pho !  1 beg !  1 ctu !  0 audpsi ! AudMem \ E
    2 t !  82 pho !  0 beg !  1 ctu !  0 audpsi ! AudMem \ R
    3 t !  82 pho !  0 beg !  1 ctu !  0 audpsi ! AudMem \ R
    4 t !  79 pho !  0 beg !  1 ctu !  0 audpsi ! AudMem \ O
    5 t !  82 pho !  0 beg !  0 ctu ! 82 audpsi ! AudMem \ R
 82 nen !   3 mfn ! 82 fex !  5 pos ! 82 fin !  1 aud ! EnVocab
 82 psi !   1 num !  0 pre !  0 seq ! 82 enx ! InStantiate

 ( A -- for EnArticle module )
    7 t ! 65 pho !   1 beg !  0 ctu !  1 audpsi ! AudMem \ A
  1 nen !  0 mfn !   1 fex !   1 pos !  1 fin ! 7 aud ! EnVocab
  1 psi !  1 num !   0 pre !  0 seq !  1 enx ! InStantiate

 ( ALL -- for machine reasoning logic )
    9 t ! 65 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ A
   10 t ! 76 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ L
   11 t ! 76 pho !   0 beg !  0 ctu !  2 audpsi ! AudMem \ L
  2 nen !  0 mfn !   2 fex !   1 pos !  2 fin ! 9 aud ! EnVocab
  2 psi !  0 num !   0 pre !  0 seq !  2 enx ! InStantiate

 ( AN -- to be selected instead of "A" before a vowel )
   13 t ! 65 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ A
   14 t ! 78 pho !   0 beg !  0 ctu ! 83 audpsi ! AudMem \ N
 83 nen !  0 mfn !  83 fex !  1 pos ! 83 fin ! 13 aud ! EnVocab
 83 psi !  1 num !   0 pre !  0 seq ! 83 enx ! InStantiate

 ( AND -- for machine reasoning logic )
   16 t ! 65 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ A
   17 t ! 78 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ N
   18 t ! 68 pho !   0 beg !  0 ctu ! 17 audpsi ! AudMem \ D
 17 nen !  0 mfn !  17 fex !  3 pos ! 17 fin ! 16 aud ! EnVocab
 17 psi !  0 num !   0 pre !  0 seq ! 17 enx ! InStantiate

 ( ANY -- for machine reasoning logic )
   20 t ! 65 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ A
   21 t ! 78 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ N
   22 t ! 89 pho !   0 beg !  0 ctu !  3 audpsi ! AudMem \ Y
  3 nen !  0 mfn !   3 fex !  1 pos !  3 fin ! 20 aud ! EnVocab
  3 psi !  0 num !   0 pre !  0 seq !  3 enx ! InStantiate

 ( ANYTHING -- a default direct object for AskUser 19jul2011 )
   24 t ! 65 pho !   1 beg !  1 ctu !   0 audpsi ! AudMem \ A
   25 t ! 78 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ N
   26 t ! 89 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ Y
   27 t ! 84 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ T
   28 t ! 72 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ H
   29 t ! 73 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ I
   30 t ! 78 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ N
   31 t ! 71 pho !   0 beg !  0 ctu ! 110 audpsi ! AudMem \ G
110 nen !  0 mfn ! 110 fex !  5 pos ! 110 fin ! 24 aud ! EnVocab
110 psi !  1 num !   0 pre !  0 seq ! 110 enx ! InStantiate

 ( ARE -- essential intransitive verb )
   33 t ! 65 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ A
   34 t ! 82 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ R
   35 t ! 69 pho !   0 beg !  0 ctu ! 67 audpsi ! AudMem \ E
 67 nen !  0 mfn !  67 fex !  8 pos ! 67 fin ! 33 aud ! EnVocab
 67 psi !  0 num !   0 pre !  0 seq ! 67 enx ! InStantiate

 ( BAD -- adjective for EnAdjective module )
   37 t ! 66 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ B
   38 t ! 65 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ A
   39 t ! 68 pho !   0 beg !  0 ctu ! 84 audpsi ! AudMem \ D
 84 nen !  0 mfn !  84 fex !  1 pos ! 84 fin ! 37 aud ! EnVocab
 84 psi !  0 num !   0 pre !  0 seq ! 84 enx ! InStantiate

( BE -- for SelfReferentialThought )
  41 t ! 66 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ B
  42 t ! 69 pho !   0 beg !  0 ctu ! 58 audpsi ! AudMem \ E
 58 nen !  0 mfn !  58 fex !  8 pos ! 58 fin ! 41 aud !  EnVocab
 58 psi !  0 num !   0 pre !  0 seq ! 58 enx ! InStantiate

 ( BECAUSE -- for machine reasoning logic )
   44 t ! 66 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ B
   45 t ! 69 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ E
   46 t ! 67 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ C
   47 t ! 65 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ A
   48 t ! 85 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ U
   49 t ! 83 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ S
   50 t ! 69 pho !   0 beg !  0 ctu ! 18 audpsi ! AudMem \ E
 18 nen !  0 mfn !  18 fex !  3 pos ! 18 fin ! 44 aud ! EnVocab
 18 psi !  0 num !   0 pre !  0 seq ! 18 enx ! InStantiate

 ( BECOME -- essential intransitive verb )
   52 t ! 66 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ B
   53 t ! 69 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ E
   54 t ! 67 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ C
   55 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
   56 t ! 77 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ M
   57 t ! 69 pho !   0 beg !  0 ctu ! 85 audpsi ! AudMem \ E
 85 nen !  0 mfn ! 85 fex !   8 pos ! 85 fin ! 52 aud ! EnVocab
 85 psi !  0 num !   0 pre !  0 seq ! 85 enx ! InStantiate

 ( BOY -- always masculine noun for use with gender flags )
   59 t ! 66 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ B
   60 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
   61 t ! 89 pho !   0 beg !  0 ctu ! 96 audpsi ! AudMem \ Y
 96 nen !  1 mfn !  96 fex !  5 pos ! 96 fin ! 59 aud !  EnVocab
 96 psi !  1 num !   0 pre !  0 seq ! 96 enx ! InStantiate

 ( BUT -- conjunction for ConJoin module )
   63 t ! 66 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ B
   64 t ! 85 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ U
   65 t ! 84 pho !   0 beg !  0 ctu ! 86 audpsi ! AudMem \ T
 86 nen !  0 mfn !  86 fex !  3 pos ! 86 fin ! 63 aud ! EnVocab
 86 psi !  0 num !   0 pre !  0 seq ! 86 enx ! InStantiate

( CHESS -- important singular AI noun ending in "S" 19jul2011 )
   67 t ! 67 pho !   1 beg !  1 ctu !   0 audpsi ! AudMem \ C
   68 t ! 72 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ H
   69 t ! 69 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ E
   70 t ! 83 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ S
   71 t ! 83 pho !   0 beg !  0 ctu ! 111 audpsi ! AudMem \ S
111 nen !  0 mfn ! 111 fex !  5 pos ! 111 fin ! 67 aud !  EnVocab
111 psi !  1 num !   0 pre !  0 seq ! 111 enx ! InStantiate

 ( DATA -- always plural noun in correction of modern usage )
   73 t ! 68 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ D
   74 t ! 65 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ A
   75 t ! 84 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ T
   76 t ! 65 pho !   0 beg !  0 ctu ! 97 audpsi ! AudMem \ A
 97 nen !  0 mfn !  97 fex !  5 pos ! 97 fin ! 73 aud  ! EnVocab
 97 psi !  2 num !   0 pre !  0 seq ! 97 enx ! InStantiate

 ( DO -- essential for AuxVerb module )
   78 t ! 68 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ D
   79 t ! 79 pho !   0 beg !  0 ctu ! 59 audpsi ! AudMem \ O
 59 nen !  0 mfn !  59 fex !  8 pos ! 59 fin ! 78 aud ! EnVocab
 59 psi !  0 num !   0 pre !  0 seq ! 59 enx ! InStantiate

 ( DOES -- essential for AuxVerb module )
   81 t ! 68 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ D
   82 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
   83 t ! 69 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ E
   84 t ! 83 pho !   0 beg !  0 ctu ! 87 audpsi ! AudMem \ S
 87 nen !  0 mfn !  87 fex !  8 pos ! 87 fin ! 81 aud ! EnVocab
 87 psi !  1 num !   0 pre !  0 seq ! 87 enx ! InStantiate

 ( DOING -- high word-frequency verb participle )
   86 t ! 68 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ D
   87 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
   88 t ! 73 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ I
   89 t ! 78 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ N
   90 t ! 71 pho !   0 beg !  0 ctu ! 88 audpsi ! AudMem \ G
 88 nen !  0 mfn !  88 fex !  1 pos ! 88 fin ! 86 aud ! EnVocab
 88 psi !  0 num !   0 pre !  0 seq ! 88 enx ! InStantiate

 ( ELSE -- adverb to be ignored as part of input queries )
   92 t ! 69 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ E
   93 t ! 76 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ L
   94 t ! 83 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ S
   95 t ! 69 pho !   0 beg !  0 ctu ! 10 audpsi ! AudMem \ E
 10 nen !  0 mfn !  10 fex !  2 pos ! 10 fin ! 92 aud ! EnVocab
 10 psi !  0 num !   0 pre !  0 seq ! 10 enx ! InStantiate

 ( FOR -- preposition for EnPrep module )
   97 t ! 70 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ F
   98 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
   99 t ! 82 pho !   0 beg !  0 ctu ! 42 audpsi ! AudMem \ R
 42 nen !  0 mfn !  42 fex !  6 pos ! 42 fin ! 97 aud ! EnVocab
 42 psi !  0 num !   0 pre !  0 seq ! 42 enx ! InStantiate

 ( FRIEND -- for coding assignment of ad-hoc gender tags )
  101 t ! 70 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ F
  102 t ! 82 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ R
  103 t ! 73 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ I
  104 t ! 69 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ E
  105 t ! 78 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ N
  106 t ! 68 pho !   0 beg !  0 ctu ! 98 audpsi ! AudMem \ D
 98 nen !  0 mfn !  98 fex !  5 pos ! 98 fin ! 101 aud ! EnVocab
 98 psi !  1 num !   0 pre !  0 seq ! 98 enx ! InStantiate

 ( GIRL -- always feminine noun for use with gender flags )
  108 t ! 71 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ G
  109 t ! 73 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ I
  110 t ! 82 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ R
  111 t ! 76 pho !   0 beg !  0 ctu ! 99 audpsi ! AudMem \ L
 99 nen !  2 mfn !  99 fex !  5 pos ! 99 fin ! 108 aud ! EnVocab
 99 psi !  1 num !   0 pre !  0 seq ! 99 enx ! InStantiate

 ( GOD -- masculine noun important for philosophy of AI )
  113 t ! 71 pho !   1 beg !  1 ctu !   0 audpsi ! AudMem \ G
  114 t ! 79 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ O
  115 t ! 68 pho !   0 beg !  0 ctu ! 100 audpsi ! AudMem \ D
100 nen !  1 mfn ! 100 fex !  5 pos ! 100 fin ! 113 aud ! EnVocab
100 psi !  1 num !   0 pre !  0 seq ! 100 enx ! InStantiate

( GOOD -- adjective for EnAdjective module )
  117 t ! 71 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ G
  118 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
  119 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
  120 t ! 68 pho !   0 beg !  0 ctu ! 89 audpsi ! AudMem \ D
 89 nen !  0 mfn !  89 fex !  1 pos ! 89 fin ! 117 aud ! EnVocab
 89 psi !  0 num !   0 pre !  0 seq ! 89 enx ! InStantiate

( HAS -- high word-frequency irregular verb form )
  122 t ! 72 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ H
  123 t ! 65 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ A
  124 t ! 83 pho !   0 beg !  0 ctu ! 90 audpsi ! AudMem \ S
 90 nen !  0 mfn !  90 fex !  8 pos ! 90 fin ! 122 aud ! EnVocab
 90 psi !  1 num !   0 pre !  0 seq ! 90 enx ! InStantiate

( HAVE -- high word-frequency verb )
  126 t ! 72 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ H
  127 t ! 65 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ A
  128 t ! 86 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ V
  129 t ! 69 pho !   0 beg !  0 ctu ! 70 audpsi ! AudMem \ E
 70 nen !  0 mfn !  70 fex !  8 pos ! 70 fin !  126 aud ! EnVocab
 70 psi !  2 num !   0 pre !  0 seq ! 70 enx ! InStantiate

( HE -- high word-frequency pronoun )
  131 t !  72 pho !  1 beg !  1 ctu !  0 audpsi ! AudMem \ H
  132 t !  69 pho !  0 beg !  0 ctu ! 49 audpsi ! AudMem \ E
 49 nen !   1 mfn ! 49 fex !  7 pos ! 49 fin ! 131 aud ! EnVocab
 49 psi !   1 num !  0 pre !  0 seq ! 49 enx ! InStantiate

( HELLO -- for human-computer interaction )
  134 t ! 72 pho !   1 beg !  1 ctu !   0 audpsi ! AudMem \ H
  135 t ! 69 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ E
  136 t ! 76 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ L
  137 t ! 76 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ L
  138 t ! 79 pho !   0 beg !  0 ctu !  26 audpsi ! AudMem \ O
 26 nen !  0 mfn !  26 fex !  4 pos !  26 fin ! 134 aud !  EnVocab
 26 psi !  0 num !   0 pre !  0 seq ! 105 enx ! InStantiate

( HER -- high word-frequency pronoun )
  140 t ! 72 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ H
  141 t ! 69 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ E
  142 t ! 82 pho !   0 beg !  0 ctu ! 91 audpsi ! AudMem \ R
 91 nen !  2 mfn !  91 fex !  7 pos ! 91 fin ! 140 aud !  EnVocab
 91 psi !  0 num !   0 pre !  0 seq ! 91 enx ! InStantiate

( HERE -- adverb for discussion of physical location )
  144 t ! 72 pho !   1 beg !  1 ctu !   0 audpsi ! AudMem \ H
  145 t ! 69 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ E
  146 t ! 82 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ R
  147 t ! 69 pho !   0 beg !  0 ctu ! 101 audpsi ! AudMem \ E
101 nen !  0 mfn ! 101 fex !  2 pos ! 101 fin ! 144 aud !  EnVocab
101 psi !  0 num !   0 pre !  0 seq ! 101 enx ! InStantiate

( HIM -- high word-frequency pronoun )
  149 t ! 72 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ H
  150 t ! 73 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ I
  151 t ! 77 pho !   0 beg !  0 ctu ! 92 audpsi ! AudMem \ M
 92 nen !  1 mfn !  92 fex !  7 pos ! 92 fin ! 149 aud ! EnVocab
 92 psi !  1 num !   0 pre !  0 seq ! 92 enx ! InStantiate

( HIS -- high word-frequency pronoun )
  153 t ! 72 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ H
  154 t ! 73 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ I
  155 t ! 83 pho !   0 beg !  0 ctu ! 93 audpsi ! AudMem \ S
 93 nen !  0 mfn !  93 fex !  1 pos ! 93 fin ! 153 aud ! EnVocab
 93 psi !  0 num !   0 pre !  0 seq ! 93 enx ! InStantiate

( HOW -- adverb for EnAdverb module )
  157 t ! 72 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ H
  158 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
  159 t ! 87 pho !   0 beg !  0 ctu ! 11 audpsi ! AudMem \ W
 11 nen !  0 mfn ! 11 fex !   2 pos ! 11 fin ! 157 aud ! EnVocab
 11 psi !  0 num !   0 pre !  0 seq ! 11 enx ! InStantiate

( IF -- for machine reasoning logic )
  161 t !  73 pho !  1 beg !  1 ctu !  0 audpsi ! AudMem \ I
  162 t !  70 pho !  0 beg !  0 ctu ! 20 audpsi ! AudMem \ F
 20 nen !   0 mfn ! 20 fex !  3 pos ! 20 fin ! 161 aud ! EnVocab
 20 psi !   0 num !  0 pre !  0 seq ! 20 enx ! InStantiate

( IN -- preposition for EnPrep module )
  164 t ! 73 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ I
  165 t ! 78 pho !   0 beg !  0 ctu ! 44 audpsi ! AudMem \ N
 44 nen !  0 mfn !  44 fex !  6 pos ! 44 fin ! 164 aud ! EnVocab
 44 psi !  0 num !   0 pre !  0 seq ! 44 enx ! InStantiate

( IS -- for machine reasoning logic -- 58 fin as of 30jul2010 )
  167 t ! 73 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ I
  168 t ! 83 pho !   0 beg !  0 ctu ! 66 audpsi ! AudMem \ S
 66 nen !  0 mfn !  66 fex !  8 pos ! 58 fin ! 167 aud ! EnVocab
 58 psi !  1 num !   0 pre !  0 seq ! 66 enx ! InStantiate

( IT -- high word-frequency pronoun )
  170 t !  73 pho !  1 beg !  1 ctu !  0 audpsi ! AudMem \ I
  171 t !  84 pho !  0 beg !  0 ctu ! 95 audpsi ! AudMem \ T
 95 nen !   3 mfn ! 95 fex !  7 pos ! 95 fin ! 170 aud !  EnVocab
 95 psi !   1 num !  0 pre !  0 seq ! 95 enx ! InStantiate

( KNOW -- germane to artificial intelligence )
  173 t ! 75 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ K
  174 t ! 78 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ N
  175 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
  176 t ! 87 pho !   0 beg !  0 ctu ! 61 audpsi ! AudMem \ W
 61 nen !  0 mfn !  61 fex !  8 pos ! 61 fin ! 173 aud !  EnVocab
 61 psi !  2 num !   0 pre !  0 seq ! 61 enx ! InStantiate

( MAN -- always masculine noun for use with gender flags )
  178 t ! 77 pho !   1 beg !  1 ctu !   0 audpsi ! AudMem \ M
  179 t ! 65 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ A
  180 t ! 78 pho !   0 beg !  0 ctu ! 102 audpsi ! AudMem \ N
102 nen !  1 mfn ! 102 fex !  5 pos ! 102 fin ! 178 aud !  EnVocab
102 psi !  1 num !   0 pre !  0 seq ! 102 enx ! InStantiate

( MAYBE -- adverb response as alternative to YES or NO )
  182 t ! 77 pho !   1 beg !  1 ctu !   0 audpsi ! AudMem \ M
  183 t ! 65 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ A
  184 t ! 89 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ Y
  185 t ! 66 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ B
  186 t ! 69 pho !   0 beg !  0 ctu ! 109 audpsi ! AudMem \ E
109 nen !  0 mfn ! 109 fex !  2 pos ! 109 fin ! 182 aud !  EnVocab
109 psi !  0 num !   0 pre !  0 seq ! 109 enx ! InStantiate

( MEDIA -- always plural noun in correction of modern usage )
  188 t ! 77 pho !   1 beg !  1 ctu !   0 audpsi ! AudMem \ M
  189 t ! 69 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ E
  190 t ! 68 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ D
  191 t ! 73 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ I
  192 t ! 65 pho !   0 beg !  0 ctu ! 103 audpsi ! AudMem \ A
103 nen !  0 mfn ! 103 fex !  5 pos ! 103 fin ! 188 aud !  EnVocab
103 psi !  2 num !   0 pre !  0 seq ! 103 enx ! InStantiate

( MY -- for SelfReferentialThought )
  194 t ! 77 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ M
  195 t ! 89 pho !   0 beg !  0 ctu ! 94 audpsi ! AudMem \ Y
 94 nen !  0 mfn !  94 fex !  1 pos ! 76 fin ! 194 aud !  EnVocab
 94 psi !  0 num !   0 pre !  0 seq ! 94 enx ! InStantiate

( NO -- for human-computer interaction )
  197 t ! 78 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ N
  198 t ! 79 pho !   0 beg !  0 ctu ! 27 audpsi ! AudMem \ O
 27 nen !  0 mfn !  27 fex !  4 pos ! 27 fin ! 197 aud !  EnVocab
 27 psi !  0 num !   0 pre !  0 seq ! 27 enx ! InStantiate

( NOT -- for machine reasoning logic )
  200 t ! 78 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ N
  201 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
  202 t ! 84 pho !   0 beg !  0 ctu ! 12 audpsi ! AudMem \ T
 12 nen !  0 mfn !  12 fex !  2 pos ! 12 fin ! 200 aud !  EnVocab
 12 psi !  0 num !   0 pre !  0 seq ! 12 enx ! InStantiate

( OF -- preposition for EnPrep module )
  204 t ! 79 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ O
  205 t ! 70 pho !   0 beg !  0 ctu ! 45 audpsi ! AudMem \ F
 45 nen !  0 mfn !  45 fex !  6 pos ! 45 fin ! 204 aud !  EnVocab
 45 psi !  0 num !   0 pre !  0 seq ! 45 enx ! InStantiate

( OR -- for machine reasoning logic )
  207 t ! 79 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ O
  208 t ! 82 pho !   0 beg !  0 ctu ! 21 audpsi ! AudMem \ R
 21 nen !  0 mfn !  21 fex !  3 pos ! 21 fin ! 207 aud !  EnVocab
 21 psi !  0 num !   0 pre !  0 seq ! 21 enx ! InStantiate

( OUR -- for SelfReferentialThought )
  210 t ! 79 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ O
  211 t ! 85 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ U
  212 t ! 82 pho !   0 beg !  0 ctu ! 81 audpsi ! AudMem \ R
 81 nen !  0 mfn !  81 fex !  1 pos ! 76 fin ! 210 aud !  EnVocab
 81 psi !  0 num !   0 pre !  0 seq ! 81 enx ! InStantiate

( PEOPLE -- establish as plural for EnParser )
  214 t ! 80 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ P
  215 t ! 69 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ E
  216 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
  217 t ! 80 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ P
  218 t ! 76 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ L
  219 t ! 69 pho !   0 beg !  0 ctu ! 37 audpsi ! AudMem \ E
 37 nen !  0 mfn !  37 fex !  5 pos ! 37 fin ! 214 aud !  EnVocab
 37 psi !  2 num !   0 pre !  0 seq ! 37 enx ! InStantiate

( PERSON -- for ad-hoc gender tags and robot philosophy )
  221 t ! 80 pho !   1 beg !  1 ctu !   0 audpsi ! AudMem \ P
  222 t ! 69 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ E
  223 t ! 82 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ R
  224 t ! 83 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ S
  225 t ! 79 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ O
  226 t ! 78 pho !   0 beg !  0 ctu ! 104 audpsi ! AudMem \ N
104 nen !  0 mfn ! 104 fex !  5 pos ! 104 fin ! 221 aud !  EnVocab
104 psi !  1 num !   0 pre !  0 seq ! 104 enx ! InStantiate

( PLEASE -- for human-computer interaction )
  228 t ! 80 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ P
  229 t ! 76 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ L
  230 t ! 69 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ E
  231 t ! 65 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ A
  232 t ! 83 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ S
  233 t ! 69 pho !   0 beg !  0 ctu ! 30 audpsi ! AudMem \ E
 30 nen !  0 mfn !  30 fex !  4 pos ! 30 fin ! 228 aud !  EnVocab
 30 psi !  0 num !   0 pre !  0 seq ! 30 enx ! InStantiate

( SHE -- high word-frequency pronoun )
  235 t ! 83 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ S
  236 t ! 72 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ H
  237 t ! 69 pho !   0 beg !  0 ctu ! 80 audpsi ! AudMem \ E
 80 nen !  2 mfn !  80 fex !  7 pos ! 80 fin ! 235 aud !  EnVocab
 80 psi !  1 num !   0 pre !  0 seq ! 80 enx ! InStantiate

( SOME -- for machine reasoning logic )
  239 t ! 83 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ S
  240 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
  241 t ! 77 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ M
  242 t ! 69 pho !   0 beg !  0 ctu ! 69 audpsi ! AudMem \ E
 69 nen !  0 mfn !  69 fex !  1 pos ! 69 fin ! 239 aud !  EnVocab
 69 psi !  0 num !   0 pre !  0 seq ! 69 enx ! InStantiate

( THAT -- conjunction for ConJoin module )
  244 t ! 84 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ T
  245 t ! 72 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ H
  246 t ! 65 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ A
  247 t ! 84 pho !   0 beg !  0 ctu ! 22 audpsi ! AudMem \ T
 22 nen !  0 mfn !  22 fex !  3 pos ! 22 fin ! 244 aud !  EnVocab
 22 psi !  0 num !   0 pre !  0 seq ! 22 enx ! InStantiate

( THE -- EnArticle highest-frequency English word )
  249 t ! 84 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ T
  250 t ! 72 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ H
  251 t ! 69 pho !   0 beg !  0 ctu !  7 audpsi ! AudMem \ E
  7 nen !  0 mfn !   7 fex !  1 pos !  7 fin ! 249 aud !  EnVocab
  7 psi !  0 num !   0 pre !  0 seq !  7 enx ! InStantiate

( THEIR -- high word-frequency pronoun )
  253 t ! 84 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ T
  254 t ! 72 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ H
  255 t ! 69 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ E
  256 t ! 73 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ I
  257 t ! 82 pho !   0 beg !  0 ctu ! 79 audpsi ! AudMem \ R
 79 nen !  0 mfn !  79 fex !  1 pos ! 79 fin ! 253 aud !  EnVocab
 79 psi !  0 num !   0 pre !  0 seq ! 79 enx ! InStantiate

( THEM -- high word-frequency pronoun )
  259 t ! 84 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ T
  260 t ! 72 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ H
  261 t ! 69 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ E
  262 t ! 77 pho !   0 beg !  0 ctu ! 78 audpsi ! AudMem \ M
 78 nen !  0 mfn !  78 fex !  7 pos ! 78 fin ! 259 aud !  EnVocab
 78 psi !  2 num !   0 pre !  0 seq ! 78 enx ! InStantiate

( THEN -- for machine reasoning logic )
  264 t ! 84 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ T
  265 t ! 72 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ H
  266 t ! 69 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ E
  267 t ! 78 pho !   0 beg !  0 ctu ! 13 audpsi ! AudMem \ N
 13 nen !  0 mfn !  13 fex !  2 pos ! 13 fin ! 264 aud !  EnVocab
 13 psi !  0 num !   0 pre !  0 seq ! 13 enx ! InStantiate

( THERE -- adverb for discussion of physical location )
  269 t ! 84 pho !   1 beg !  1 ctu !   0 audpsi ! AudMem \ T
  270 t ! 72 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ H
  271 t ! 69 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ E
  272 t ! 82 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ R
  273 t ! 69 pho !   0 beg !  0 ctu ! 105 audpsi ! AudMem \ E
105 nen !  0 mfn ! 105 fex !  2 pos ! 105 fin ! 269 aud !  EnVocab
105 psi !  0 num !   0 pre !  0 seq ! 105 enx ! InStantiate

( THEY -- high word-frequency pronoun )
  275 t ! 84 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ T
  276 t ! 72 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ H
  277 t ! 69 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ E
  278 t ! 89 pho !   0 beg !  0 ctu ! 52 audpsi ! AudMem \ Y
 52 nen !  0 mfn !  52 fex !  7 pos ! 52 fin ! 275 aud !  EnVocab
 52 psi !  2 num !   0 pre !  0 seq ! 52 enx ! InStantiate

( THINK -- germane to artificial intelligence )
  280 t ! 84 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ T
  281 t ! 72 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ H
  282 t ! 73 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ I
  283 t ! 78 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ N
  284 t ! 75 pho !   0 beg !  0 ctu ! 63 audpsi ! AudMem \ K
 63 nen !  0 mfn !  63 fex !  8 pos ! 63 fin ! 280 aud !  EnVocab
 63 psi !  0 num !   0 pre !  0 seq ! 63 enx ! InStantiate

( US -- for SelfReferentialThought )
  286 t ! 85 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ U
  287 t ! 83 pho !   0 beg !  0 ctu ! 77 audpsi ! AudMem \ S
 77 nen !  0 mfn !  77 fex !  7 pos ! 56 fin ! 286 aud !  EnVocab
 77 psi !  2 num !   0 pre !  0 seq ! 77 enx ! InStantiate

( WE -- for SelfReferentialThought )
  289 t ! 87 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ W
  290 t ! 69 pho !   0 beg !  0 ctu ! 53 audpsi ! AudMem \ E
 53 nen !  0 mfn !  53 fex !  7 pos ! 56 fin ! 289 aud !  EnVocab
 53 psi !  2 num !   0 pre !  0 seq ! 53 enx ! InStantiate

( WHAT -- for SelfReferentialThought )
  292 t ! 87 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ W
  293 t ! 72 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ H
  294 t ! 65 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ A
  295 t ! 84 pho !   0 beg !  0 ctu ! 54 audpsi ! AudMem \ T
 54 nen !  3 mfn !  54 fex !  7 pos ! 54 fin ! 292 aud !  EnVocab
 54 psi !  1 num !   0 pre !  0 seq ! 54 enx ! InStantiate

( WHEN -- for SelfReferentialThought )
  297 t ! 87 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ W
  298 t ! 72 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ H
  299 t ! 69 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ E
  300 t ! 78 pho !   0 beg !  0 ctu ! 14 audpsi ! AudMem \ N
 14 nen !  0 mfn !  14 fex !  2 pos ! 14 fin ! 297 aud !  EnVocab
 14 psi !  0 num !   0 pre !  0 seq ! 14 enx ! InStantiate

( WHERE -- for SelfReferentialThought )
  302 t ! 87 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ W
  303 t ! 72 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ H
  304 t ! 69 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ E
  305 t ! 82 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ R
  306 t ! 69 pho !   0 beg !  0 ctu ! 15 audpsi ! AudMem \ E
 15 nen !  0 mfn !  15 fex !  2 pos ! 15 fin ! 302 aud !  EnVocab
 15 psi !  0 num !   0 pre !  0 seq ! 15 enx ! InStantiate

( WHO -- for SelfReferentialThought )
  308 t ! 87 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ W
  309 t ! 72 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ H
  310 t ! 79 pho !   0 beg !  0 ctu ! 55 audpsi ! AudMem \ O
 55 nen !  0 mfn !  55 fex !  7 pos ! 55 fin ! 308 aud !  EnVocab
 55 psi !  0 num !   0 pre !  0 seq ! 55 enx ! InStantiate

( WHOM -- for AI to ask grammatically correct questions )
  312 t ! 87 pho !   1 beg !  1 ctu !   0 audpsi ! AudMem \ W
  313 t ! 72 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ H
  314 t ! 79 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ O
  315 t ! 77 pho !   0 beg !  0 ctu ! 106 audpsi ! AudMem \ M
106 nen !  0 mfn ! 106 fex !  7 pos ! 106 fin ! 312 aud !  EnVocab
106 psi !  0 num !   0 pre !  0 seq ! 106 enx ! InStantiate

( WHY -- for machine reasoning logic )
  317 t ! 87 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ W
  318 t ! 72 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ H
  319 t ! 89 pho !   0 beg !  0 ctu ! 16 audpsi ! AudMem \ Y
 16 nen !  0 mfn !  16 fex !  2 pos ! 16 fin ! 317 aud !  EnVocab
 16 psi !  0 num !   0 pre !  0 seq ! 16 enx ! InStantiate

( WITH -- preposition for EnPrep module )
  321 t ! 87 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ W
  322 t ! 73 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ I
  323 t ! 84 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ T
  324 t ! 72 pho !   0 beg !  0 ctu ! 48 audpsi ! AudMem \ H
 48 nen !  0 mfn !  48 fex !  6 pos ! 48 fin ! 321 aud !  EnVocab
 48 psi !  0 num !   0 pre !  0 seq ! 48 enx ! InStantiate

( WOMAN -- always feminine noun for use with gender flags )
  326 t ! 87 pho !   1 beg !  1 ctu !   0 audpsi ! AudMem \ W
  327 t ! 79 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ O
  328 t ! 77 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ M
  329 t ! 65 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ A
  330 t ! 78 pho !   0 beg !  0 ctu ! 107 audpsi ! AudMem \ N
107 nen !  2 mfn ! 107 fex !  5 pos ! 107 fin ! 326 aud !  EnVocab
107 psi !  1 num !   0 pre !  0 seq ! 107 enx ! InStantiate

( YES -- for human-computer interaction )
  332 t !  89 pho !  1 beg !  1 ctu !  0 audpsi ! AudMem \ Y
  333 t !  69 pho !  0 beg !  1 ctu !  0 audpsi ! AudMem \ E
  334 t !  83 pho !  0 beg !  0 ctu ! 32 audpsi ! AudMem \ S
 32 nen !   0 mfn ! 32 fex !  4 pos ! 32 fin ! 332 aud !  EnVocab
 32 psi !   0 num !  0 pre !  0 seq ! 32 enx ! InStantiate

( YOU -- for SelfReferentialThought )
  336 t ! 89 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ Y
  337 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
  338 t ! 85 pho !   0 beg !  0 ctu ! 56 audpsi ! AudMem \ U
 56 nen !  0 mfn !  56 fex !  7 pos ! 50 fin ! 336 aud !  EnVocab
 56 psi !  0 num !   0 pre !  0 seq ! 56 enx ! InStantiate

( YOUR -- for SelfReferentialThought )
  340 t ! 89 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ Y
  341 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
  342 t ! 85 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ U
  343 t ! 82 pho !   0 beg !  0 ctu ! 76 audpsi ! AudMem \ R
 76 nen !  0 mfn !  76 fex !  1 pos ! 94 fin ! 340 aud !  EnVocab
 76 psi !  0 num !   0 pre !  0 seq ! 76 enx ! InStantiate

( YOU -- innate response to who-am-i query )
  345 t ! 89 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ Y
  346 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
  347 t ! 85 pho !   0 beg !  0 ctu ! 56 audpsi ! AudMem \ U
 56 nen !  0 mfn !  56 fex !  7 pos ! 50 fin ! 345 aud !  EnVocab
 56 psi !  0 num !   0 pre !  58 seq ! 56 enx ! InStantiate

( ARE -- essential intransitive verb -- 58 fin as of 30jul2010 )
  349 t ! 65 pho !   1 beg !   1 ctu !  0 audpsi ! AudMem \ A
  350 t ! 82 pho !   0 beg !   1 ctu !  0 audpsi ! AudMem \ R
  351 t ! 69 pho !   0 beg !   0 ctu ! 67 audpsi ! AudMem \ E
 67 nen !  0 mfn !  67 fex !   8 pos ! 58 fin ! 349 aud ! EnVocab
 58 psi !  0 num !  56 pre ! 108 seq ! 67 enx ! InStantiate

( MAGIC -- for testing purposes )
  353 t ! 77 pho !   1 beg !  1 ctu !   0 audpsi ! AudMem \ M
  354 t ! 65 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ A
  355 t ! 71 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ G
  356 t ! 73 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ I
  357 t ! 67 pho !   0 beg !  0 ctu ! 108 audpsi ! AudMem \ C
108 nen !  0 mfn ! 108 fex !  5 pos ! 108 fin ! 353 aud !  EnVocab
108 psi !  0 num !  58 pre !  0 seq ! 108 enx ! InStantiate

( I -- for SelfReferentialThought )
  359 t ! 73 pho !   1 beg !  0 ctu ! 50 audpsi ! AudMem \ I
  50 nen !  0 mfn ! 50 fex !  7 pos ! 56 fin  ! 359 aud ! EnVocab
  50 psi !  1 num !   0 pre ! 58 seq ! 50 enx ! InStantiate

( AM -- for SelfReferentialThought -- 58 fin as of 30jul2010 )
  361 t ! 65 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ A
  362 t ! 77 pho !   0 beg !  0 ctu ! 57 audpsi ! AudMem \ M
 57 nen !  0 mfn !  57 fex !  8 pos ! 58 fin ! 361 aud !  EnVocab
 58 psi !  0 num !  50 pre ! 33 seq ! 57 enx ! InStantiate

( ANDRU -- for SelfReferentialThought )
  364 t ! 65 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ A
  365 t ! 78 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ N
  366 t ! 68 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ D
  367 t ! 82 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ R
  368 t ! 85 pho !   0 beg !  0 ctu ! 33 audpsi ! AudMem \ U
 33 nen !  1 mfn !  33 fex !  5 pos ! 33 fin ! 364 aud !  EnVocab
 33 psi !  1 num !  58 pre !  0 seq ! 33 enx ! InStantiate

( I -- innate KB-item for testing inhibition of idea-pairs )
  370 t ! 73 pho !   1 beg !  0 ctu ! 50 audpsi ! AudMem \ I
  50 nen !  0 mfn ! 50 fex !  7 pos ! 56 fin  ! 370 aud ! EnVocab
  50 psi !  1 num !   0 pre ! 58 seq ! 50 enx ! InStantiate

( AM -- for SelfReferentialThought -- 58 fin as of 30jul2010 )
  372 t ! 65 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ A
  373 t ! 77 pho !   0 beg !  0 ctu ! 57 audpsi ! AudMem \ M
 57 nen !  0 mfn !  57 fex !  8 pos ! 58 fin ! 372 aud !  EnVocab
 58 psi !  1 num !  50 pre ! 39 seq ! 57 enx ! InStantiate

( A -- for EnArticle module )
  375 t ! 65 pho !   1 beg !  0 ctu !  1 audpsi ! AudMem \ A
  1 nen !  0 mfn !   1 fex !   1 pos !  1 fin ! 375 aud ! EnVocab
  1 psi !  1 num !   0 pre !  39 seq !  1 enx ! InStantiate

( ROBOT -- important for target user base )
  377 t ! 82 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ R
  378 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
  379 t ! 66 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ B
  380 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
  381 t ! 84 pho !   0 beg !  0 ctu ! 39 audpsi ! AudMem \ T
 39 nen !  3 mfn !  39 fex !  5 pos ! 39 fin ! 377 aud !  EnVocab
 39 psi !  1 num !  58 pre !  0 seq ! 39 enx ! InStantiate

( I -- innate KB-item for testing inhibition of idea-pairs )
  383 t ! 73 pho !   1 beg !  0 ctu ! 50 audpsi ! AudMem \ I
  50 nen !  0 mfn ! 50 fex !  7 pos ! 56 fin  ! 383 aud ! EnVocab
  50 psi !  1 num !   0 pre ! 58 seq ! 50 enx ! InStantiate

( AM -- for SelfReferentialThought -- 58 fin as of 30jul2010 )
  385 t ! 65 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ A
  386 t ! 77 pho !   0 beg !  0 ctu ! 57 audpsi ! AudMem \ M
 57 nen !  0 mfn !  57 fex !  8 pos ! 58 fin ! 385 aud !  EnVocab
 58 psi !  0 num !  50 pre ! 104 seq ! 57 enx ! InStantiate

( A -- for EnArticle module )
  388 t ! 65 pho !   1 beg !  0 ctu !  1 audpsi ! AudMem \ A
  1 nen !  0 mfn !   1 fex !   1 pos !  1 fin ! 388 aud ! EnVocab
  1 psi !  1 num !   0 pre !  104 seq !  1 enx ! InStantiate

( PERSON -- for ad-hoc gender tags and robot philosophy )
  390 t ! 80 pho !   1 beg !  1 ctu !   0 audpsi ! AudMem \ P
  391 t ! 69 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ E
  392 t ! 82 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ R
  393 t ! 83 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ S
  394 t ! 79 pho !   0 beg !  1 ctu !   0 audpsi ! AudMem \ O
  395 t ! 78 pho !   0 beg !  0 ctu ! 104 audpsi ! AudMem \ N
104 nen !  0 mfn ! 104 fex !  5 pos ! 104 fin ! 390 aud !  EnVocab
104 psi !  1 num !  58 pre !  0 seq ! 104 enx ! InStantiate

( I -- for SelfReferentialThought )
  397 t ! 73 pho !   1 beg !  0 ctu ! 50 audpsi ! AudMem \ I
  50 nen !  0 mfn ! 50 fex !  7 pos ! 56 fin ! 397 aud ! EnVocab
  50 psi !  1 num !   0 pre ! 75 seq ! 50 enx ! InStantiate

( HELP -- socially significant common verb )
  399 t ! 72 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ H
  400 t ! 69 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ E
  401 t ! 76 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ L
  402 t ! 80 pho !   0 beg !  0 ctu ! 75 audpsi ! AudMem \ P
  75 nen !  0 mfn ! 75 fex !  8 pos ! 75 fin ! 399 aud !  EnVocab
  75 psi !  0 num !  50 pre ! 72 seq ! 75 enx ! InStantiate

( KIDS -- noun lends itself to educational purposes )
  404 t ! 75 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ K
  405 t ! 73 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ I
  406 t ! 68 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ D
  407 t ! 83 pho !   0 beg !  0 ctu ! 72 audpsi ! AudMem \ S
  72 nen !  0 mfn ! 72 fex !  5 pos ! 72 fin ! 404 aud !  EnVocab
  72 psi !  2 num ! 75 pre !  0 seq ! 72 enx ! InStantiate

( KIDS -- noun lends itself to educational purposes )
  409 t ! 75 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ K
  410 t ! 73 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ I
  411 t ! 68 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ D
  412 t ! 83 pho !   0 beg !  0 ctu ! 72 audpsi ! AudMem \ S
 72 nen !  0 mfn !  72 fex !  5 pos ! 72 fin ! 409 aud ! EnVocab
 72 psi !  2 num !   0 pre ! 73 seq ! 72 enx ! InStantiate

( MAKE -- common verb of high word-frequency )
  414 t ! 77 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ M
  415 t ! 65 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ A
  416 t ! 75 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ K
  417 t ! 69 pho !   0 beg !  0 ctu ! 73 audpsi ! AudMem \ E
 73 nen !  0 mfn !  73 fex !  8 pos ! 73 fin ! 414 aud !  EnVocab
 73 psi !  2 num !  72 pre ! 39 seq ! 73 enx ! InStantiate

( ROBOTS -- important for target user base )
  419 t ! 82 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ R
  420 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
  421 t ! 66 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ B
  422 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
  423 t ! 84 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ T
  424 t ! 83 pho !   0 beg !  0 ctu ! 39 audpsi ! AudMem \ S
 39 nen !  3 mfn !  39 fex !  5 pos ! 39 fin ! 419 aud !  EnVocab
 39 psi !  2 num !  73 pre !  0 seq ! 39 enx ! InStantiate

( ROBOTS -- important for target user base )
  426 t ! 82 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ R
  427 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
  428 t ! 66 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ B
  429 t ! 79 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ O
  430 t ! 84 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ T
  431 t ! 83 pho !   0 beg !  0 ctu ! 39 audpsi ! AudMem \ S
 39 nen !  3 mfn !  39 fex !  5 pos ! 39 fin ! 426 aud !  EnVocab
 39 psi !  2 num !   0 pre ! 74 seq ! 39 enx ! InStantiate

( NEED -- common verb used for describing goals )
  433 t ! 78 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ N
  434 t ! 69 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ E
  435 t ! 69 pho !   0 beg !  1 ctu !  0 audpsi ! AudMem \ E
  436 t ! 68 pho !   0 beg !  0 ctu ! 74 audpsi ! AudMem \ D
 74 nen !  0 mfn !  74 fex !  8 pos ! 74 fin ! 433 aud !  EnVocab
 74 psi !  2 num !  39 pre ! 65 seq ! 74 enx ! InStantiate

( ME -- for SelfReferentialThought )
  438 t ! 77 pho !   1 beg !  1 ctu !  0 audpsi ! AudMem \ M
  439 t ! 69 pho !   0 beg !  0 ctu ! 65 audpsi ! AudMem \ E
 65 nen !  0 mfn !  65 fex !  7 pos ! 56 fin ! 438 aud !  EnVocab
 65 psi !  1 num !  74 pre !  0 seq ! 65 enx ! InStantiate
( Declaration of "vault" must reflect final EnBoot "t".)
  1 t +!
    t @  vault !
    t @  tov !
  1 t +!
    t @ nlt !  ( nlt may be basis for DAMP functions )
  72 urpsi ! \ As if "KIDS" were the cresting concept.
  111 nen !  \ Adding CHESS as concept #111; 19jul2011
  5 bias !
  0 lurk !   \ prepare to auto-start thinking; 19sep2010
  0 num !
  0 mfn !  \ Prevent carry-over.
  0 mfnflag !  \ Prevent carry-over; 23aug2010
  0 nwc !
  0 pho !
  0 pre !  0 seq !
;  ( End of EnBoot English Bootstrap; return to MainLoop )


:  KbTraversal ( reactivate KB concepts )
  35 pov !
  kbtv @ 4 > IF  1 kbtv !  THEN
  CR ." Knowledge base traversal with kbtv at " kbtv @ .
  kbtv @ 1 = IF
     1 kbyn !   \ for AskUser Y/N query subject; 24jun2011
     1 recon !  \ ask "YOU" a question; 19sep2010
    56 nacpsi ! \ 56=YOU noun-activation psi; 3oct2010
    56 qusub !  \ in case a query will be made; 3oct2010
    56 subjpsi !  \ a test to help WhoBe; 7aug2010
    ." activating concept of YOU" CR \ for who-query; 7aug2010
    62 nounval !
    NounAct
    0 nacpsi !
  THEN
  kbtv @ 2 = IF
     2 kbyn !   \ for AskUser Y/N query subject; 24jun2011
    39 nacpsi !  \ 39=ROBOTS noun-activation psi; 3oct2010
    ." activating concept of ROBOTS" CR  ( 7aug2010 )
    39 qusub !  \ in case a query will be made; 3oct2010
    39 subjpsi ! \ external tagging as subject; 3oct2010
     2 nphrnum ! \ prescriptive for plural ROBOTS; 21jun2011
    62 nounval !
    NounAct
    0 nacpsi !
  THEN
  kbtv @ 3 = IF
     3 kbyn !   \ for AskUser Y/N query subject; 24jun2011
    50 nacpsi !  \ 50=I noun-activation psi; 3oct2010
    ." activating concept of I" CR     ( 7aug2010 )
    50 qusub !  \ in case a query will be made; 3oct2010
    50 subjpsi ! \ external tagging as subject; 3oct2010
  \ 62 nounval !
  \ 62 nounval ! \ Temporarily commenting out; 29jul2011
    NounAct
    0 nacpsi !
  THEN
  kbtv @ 4 = IF
     4 kbyn !   \ for AskUser Y/N query subject; 24jun2011  
   100 nacpsi ! \ 100=GOD noun-activation psi; 3oct2010
    ." activating concept of GOD" CR   ( 7aug2010 )
    100 qusub !  \ in case a query will be made; 3oct2010
    100 subjpsi ! \ external tagging as subject; 3oct2010
    62 nounval !
    NounAct
    0 nacpsi !
  THEN
  42 pov !
;  ( End of KbTraversal; return to ReJuvenate )


( http://code.google.com/p/mindforth/wiki/ReJuvenate )
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
      I 6 psi{ @  jrt @  6 psi{ !  0 I 6 psi{ !
      I 7 psi{ @  jrt @  7 psi{ !  0 I 7 psi{ !
    THEN
    edge @  1 =  IF
      en7 @  1 <  IF  0 en7 !  THEN
      I 0 en{ @  jrt @  0 en{ !  0 I 0 en{ !
      I 1 en{ @  jrt @  1 en{ !  0 I 1 en{ !
      I 2 en{ @  jrt @  2 en{ !  0 I 2 en{ !
      I 3 en{ @  jrt @  3 en{ !  0 I 3 en{ !
      I 4 en{ @  jrt @  4 en{ !  0 I 4 en{ !
      I 5 en{ @  jrt @  5 en{ !  0 I 5 en{ !
      I 6 en{ @  jrt @  6 en{ !  0 I 6 en{ !
      I 7 en{ @  en7 !
          en7 @  vault @ < IF
          en7 @  jrt @  7 en{ !  0 I 7 en{ !  THEN
          en7 @  coda @  vault @ +  > IF
          en7 @  coda @ -  jrt @ 7 en{ !
          THEN               0 I 7 en{ !
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
      0 jrt @ 0 en{ !
      0 jrt @ 1 en{ !
      0 jrt @ 2 en{ !
      0 jrt @ 3 en{ !
      0 jrt @ 4 en{ !
      0 jrt @ 5 en{ !
      0 jrt @ 6 en{ !
      0 jrt @ 7 en{ !
      0 jrt @ 0 psi{ !
      0 jrt @ 1 psi{ !
      0 jrt @ 2 psi{ !
      0 jrt @ 3 psi{ !
      0 jrt @ 4 psi{ !
      0 jrt @ 5 psi{ !
      0 jrt @ 6 psi{ !
      0 jrt @ 7 psi{ !
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
    0  I 0   en{ !
    0  I 1   en{ !
    0  I 2   en{ !
    0  I 3   en{ !
    0  I 4   en{ !
    0  I 5   en{ !
    0  I 6   en{ !
    0  I 7   en{ !
    0  I 0  psi{ !
    0  I 1  psi{ !
    0  I 2  psi{ !
    0  I 3  psi{ !
    0  I 4  psi{ !
    0  I 5  psi{ !
    0  I 6  psi{ !
    0  I 7  psi{ !
  LOOP
  t @ 32 - tov !  \ 12jan2010 Avoid truncating thoughts.
  CR CR ." End of ReJuvenate #" rjc @ .
  ." in the AI Mind display for science museum exhibits."
  CR ." Tab key cycles through Normal, Transcript, "
   ." Tutorial, Diagnostic display-modes. "  CR
  1 kbtv +!
  kbtv @ 0 > IF
    CR ." For lack of human input, "
    ." ReJuvenate calls KbTraversal" CR
    KbTraversal
  THEN
  rsvp @ rjc @ - rsvp !
  rsvp @ 2 < IF 2 rsvp ! THEN  \ 23dec2009 Maintain speed.
;  ( End of ReJuvenate )


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
        inflex1 @ 0 > IF  \ 30aug2010
          inflex1 @ pho !  \ 30aug2010
          0 inflex1 !  \ reset for safety; 30aug2010
        THEN  \  30aug2010
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
      THEN
      LEAVE
    THEN
    t2s @  1+  t2s !
    t2s @  4 aud{ @ 0 = IF 32 pho ! THEN ( If end of word )
    match @ 1 = IF
      0 match !
      LEAVE
    THEN
  LOOP
  0 match !
  0 obstat !
;  ( End of SpeechAct )


:  SayYes ( to utter "YES" in response )
  midway @  t @  DO
    I       0 en{ @  32 = IF
      I     7 en{ @  aud !
      LEAVE
    THEN
  -1 +LOOP
  SpeechAct
  0 kbquiz !
  0 yesorno !
;  ( End of SayYes )


:  EnArticle ( select "a" or "the" before a noun )
  nphrpos @ 7 = NOT IF
    nphrnum @  1 = IF
      motjuste @ ghost @ = NOT IF
       indefartcon @  1 = IF  \ from WHAT-query; 16apr2011
        anset @ 0 = IF ( If no vowel is next )
          midway @  t @  DO
            I       0 en{ @  1 = IF  \ If #1 "A" is found,
              I     7 en{ @  aud !
              LEAVE
            THEN
          -1 +LOOP
        THEN  ( End of test for absence of a vowel )
        anset @ 0 > IF  ( If anset-flag is positive )
          midway @  t @  DO
            I       0 en{ @ 83 = IF  \ If #83 "AN" is found,
              I     7 en{ @  aud !
              LEAVE
            THEN
          -1 +LOOP
        THEN  ( End of test for a vowel coming next )
        1 numflag ! \ With "A" assume singular number.
        SpeechAct
        0 indefartcon !  \ Reset; 16apr2011
       THEN  \ End of test for positive indefartcon; 16apr2011
      THEN
      motjuste @ ghost @ = IF
       defartcon @  1 = IF  \ from WH0-query; 16apr2011
        midway @  t @  DO
          I       0 en{ @  7 = IF  \ If "THE" is found; 16apr2011
            I     7 en{ @  aud !
            LEAVE
          THEN
        -1 +LOOP
        SpeechAct
        0 defartcon !  \ Reset; 16apr2011 
       THEN  \ End of test for positive defartcon; 16apr2011
      THEN
    THEN
  THEN
  nphrpos @ 7 = NOT IF
    nphrnum @  2 = IF
      midway @  t @  DO
        I       0 en{ @  7 = IF  \ If "THE" is found; 16apr2011
          I     7 en{ @  aud !
          LEAVE
        THEN
      -1 +LOOP
      SpeechAct
    THEN
  THEN
  dirobj @ 1 = IF
    motjuste @ ghost !
  THEN
;  ( End of EnArticle; return to NounPhrase )


:  AuxVerb ( auviliary Verb )
  subjnum @ 1 =  prsn @ 3 = AND IF  \ 19jul211
    midway @  t @  DO
      I       0 en{ @  87 = IF  \ 87=DOES 13jun2011
        I     7 en{ @  aud !
        LEAVE
      THEN
    -1 +LOOP
    SpeechAct  \ Say word starting at "aud" value; 20jul2011
    87 urpsi !    \ 13jun2011
    51 caller !
    PsiDamp
    0 caller !
  ELSE  \ all other cases except 3rd prsn sing; 25jun2011
    midway @  t @  DO
      I       0 en{ @  59 = IF  \ 59=DO; 25jun2011
        I     7 en{ @  aud !
        LEAVE
      THEN
    -1 +LOOP
    SpeechAct
    fyi @ 2 > IF CR
      ."   from AuxVerb after speaking of DO, "
      ." psiDamping concept #59 DO"
    THEN
    59 urpsi !
    51 caller !
    PsiDamp
    0 caller !
  THEN  \ end of test for both sing & 3rd prsn; 25jun2011
;  ( End of AuxVerb; return to SelfRef or WhatAuxSDo or AskUser )


:  WhatAuxSVerb ( What DO Subjects Verb; 13jun2011 )
  PsiDecay
  midway @  t @  DO
    I       0 en{ @  54 = IF  \ 54=WHAT  13jun2011
      I     7 en{ @  aud !
      LEAVE
    THEN
  -1 +LOOP
  SpeechAct  \ Say word starting at "aud" value; 20jul2011
  54 urpsi !
  PsiDamp
  AuxVerb  \ Say DOES or DO depending on num(ber) 20jul2011
  0 motjuste !
  midway @  t @  DO
    I       0 en{ @  topic @ = IF  \ 13jun2011
      I     7 en{ @ aud !
      LEAVE
    THEN
  -1 +LOOP
  topic @ urpsi !  \ 14aug2011
  PsiDamp
  SpeechAct
  verbpsi @ 0 = IF 59 verbpsi ! THEN  \ 59=DO DeFault; 5aug2011
  midway @  t @  DO
    I       0 en{ @  verbpsi @ = IF  \ 13jun2011
      I     2 en{ @  2 = IF  \ as if infinitive; 13jun2011
        I     7 en{ @  aud !
        LEAVE
      THEN  \ End of test for plural as if infinitive
    THEN
  -1 +LOOP
  aud @ 0 = IF  \ if no plural accept singular 14aug2011
    midway @  t @  DO  \ search English vocab; 14aug2011
      I       0 en{ @  verbpsi @ = IF  \ 14aug2011
        I   7 en{ @  aud !  \ for SpeechAct; 14aug2011
        LEAVE  \ one engram is enough; 14aug2011
      THEN  \ end of test for verbpsi; 14aug2011
    -1 +LOOP   \ end of backwards search loop; 14aug2011
  THEN  \ end of test for no engram found; 14aug2011
  SpeechAct
  verbpsi @ urpsi !  \ 13jun2011
  PsiDamp
  PsiDecay
;  ( End of WhatAuxSVerb; first created 13jun2011 )


:  WhatAuxSDo ( What DO Subjects DO )
  PsiDecay
  midway @  t @  DO
    I       0 en{ @  54 = IF  \ 54=WHAT; 14aug2011
      I     7 en{ @  aud !
      LEAVE
    THEN
  -1 +LOOP
  SpeechAct
  54 urpsi !
  42 caller !
  PsiDamp
  0 caller !
  AuxVerb   \ to include DO or DOES; 14aug2011
  midway @  t @  DO
    I       0 en{ @  topic @ = IF
      I     7 en{ @ aud !
      LEAVE
    THEN
  -1 +LOOP
  topic @ urpsi !   \ 14aug2011
  42 caller !
  PsiDamp
  SpeechAct
  midway @  t @  DO
    I       0 en{ @  59 = IF  \ 59=DO; 14aug2011
      I     7 en{ @  aud !
      LEAVE
    THEN
  -1 +LOOP
  SpeechAct
  fyi @ 2 > IF CR
    ."   from whatAuxSDo after speaking of DO, "
    ." psiDamping concept #59 DO"
  THEN
  59 urpsi !
  42 caller !
  PsiDamp
  0 caller !
  PsiDecay
;  ( End of WhatAuxSDo; orphaned from AskUser; 9aug2010 )


:  WhoBe  ( for asking WHO IS-AM-ARE; 9aug2010 )
  topic @ 0 > IF topic @ qusub ! THEN  \ review; 30jul2011
  subjpsi @ 0 > IF subjpsi @ qusub ! THEN  \ 30jul2011
  midway @  t @  DO  \ Say the word "WHO"; 19aug2010
    I       0 en{ @  55 = IF  ( 55=WHO; 9aug2010 )
      I     7 en{ @  aud !
      LEAVE
    THEN
  -1 +LOOP
  SpeechAct
  8766 caller !  \ ASCII 87=W 66=B; test; 26sep2010
  55 urpsi !  \ Designate concept to be psi-damped; 19aug2010
  PsiDamp
  0 caller !  \ reset after use; 26sep2010
  qusub @ 50 = IF 1 prsn ! THEN \ 1st person "I"  4oct2010
  qusub @ 53 = IF 1 prsn ! THEN \ 1st person WE   4oct2010
  qusub @ 56 = IF 2 prsn ! THEN \ 2nd person YOU  4oct2010
  qusub @ 49 = IF 3 prsn ! THEN \ 3rd person HE   4oct2010
  qusub @ 80 = IF 3 prsn ! THEN \ 3rd person SHE  4oct2010
  qusub @ 95 = IF 3 prsn ! THEN \ 3rd person IT   4oct2010
  qusub @ 52 = IF 3 prsn ! THEN \ 3rd person THEY 1sep2010
  prsn @ 3 = IF  \ only for 3rd person; 1sep2010
    midway @  t @  DO  \ Say "IS" after "WHO"; 19aug2010
      I       0 en{ @  66 = IF  ( 66=IS )
        I     7 en{ @  aud !
        LEAVE
      THEN
    -1 +LOOP
    SpeechAct   \ to say "IS"; 17aug2010
    0 mfn !  \ test; remove; 25aug2010
    0 mfnflag ! \ Reset after use; 19aug2010
  THEN  \ end of test for prsn=1; 1sep2010
  qusub @ 50 = IF  ( I; 4oct2010 )
    1 prsn !  \ first person; 1sep2010
    1 nphrnum !  \ singular; 1sep2010
    midway @  t @  DO
      I       0 en{ @  57 = IF   ( 57=AM )
        I     7 en{ @  aud !
        LEAVE
      THEN
    -1 +LOOP
  THEN    \ 9aug2010
  qusub @ 65 = IF  \ treat 65=ME like 50=I; 4oct2010
    midway @  t @  DO
      I       0 en{ @  57 = IF   ( 57=AM )
        I     7 en{ @  aud !
        LEAVE
      THEN
    -1 +LOOP
    SpeechAct  \ moved inside the IF-clause; 10aug2010
  THEN    \ 9aug2010
  qusub @ 56 = IF  ( YOU; 4oct2010 )
    2 prsn !  \ second person; 1sep2010
    midway @  t @  DO
      I       0 en{ @  67 = IF  ( 67=ARE )
        I     7 en{ @  aud !
        LEAVE
      THEN
    -1 +LOOP
    SpeechAct   \ to say "ARE"; 10aug2010
  THEN    \ 9aug2010
  qusub @ 49 = IF  ( HE; 4oct2010 )
    3 prsn !  \ third person; 1sep2010
    1 nphrnum !  \ singular; 1sep2010
    midway @  t @  DO
      I       0 en{ @  66 = IF  ( 66=IS )
        I     7 en{ @  aud !
        LEAVE
      THEN
    -1 +LOOP
  THEN    \ 10aug2010
  midway @  t @  DO  \ search for who-query subject; 23aug2010
  \ I       0 en{ @  subjpsi @ = IF  \ 23aug2010
    I       0 en{ @  qusub @ = IF  \ if qusub found; 3oct2010
      I     7 en{ @  aud !  \ recall-tag; 23aug2010
      LEAVE   \ one exemplar is enough; 23aug2010
    THEN   \ end of test for subject; 23aug2010
  -1 +LOOP  \ end of search-loop; 23aug2010
  SpeechAct  \ speak (WHO IS) qusub query-subject; 3oct2010
  0 recon !  \ Reset for safety; 25aug2010
;  \ End of WhoBe; return to VerbPhrase; 30jul2011


:  WhatBe ( what IS/ARE Subjects ) \ 25feb2011
  subjpsi @ 56 = IF 2 prsn ! THEN  \ 2nd person YOU; 19sep2010
  PsiDecay
  midway @  t @  DO
    I       0 en{ @  54 = IF
      54 motjuste !
      I     7 en{ @  aud !
      LEAVE
    THEN
  -1 +LOOP
  SpeechAct
  fyi @ 2 > IF CR
    ."   from WhatBe after speaking of WHAT, "  \ 25feb2011
    ." psiDamping concept #54"
  THEN
  8773 caller !  \ ASCII 87=W 73=I; test; 26sep2010
  54 urpsi !
  PsiDamp
  0 caller !
  topicnum @ 2 = NOT IF
   prsn @ 3 = IF  \ 3rd person singular; 19sep2010
    midway @  t @  DO
      I       0 en{ @  66 = IF
        66 motjuste !  \ "IS"; 19sep2010
        I     7 en{ @  aud !
        LEAVE
      THEN
    -1 +LOOP
    SpeechAct
    fyi @ 2 > IF CR
      ."   from WhatBe after speaking of IS, " \ 25feb2011
      ." psiDamping concept #66"
    THEN
    8773 caller !  \ ASCII 87=W 73=I; test; 26sep2010    
    66 urpsi !
    PsiDamp
    0 caller !
    0 motjuste !
   THEN  \ end of test for 3rd person singular; 19sep2010
  THEN
  topicnum @ 2 =  prsn @ 2 =  OR IF  \ test; 19sep2010
    midway @  t @  DO
      I       0 en{ @  67 = IF
        67 motjuste !    \ "ARE"; 19sep2010
        I     7 en{ @  aud !
        LEAVE
      THEN
    -1 +LOOP
    SpeechAct
    fyi @ 2 > IF CR
      ."   from WhatBe after speaking of ARE, " \ 25feb2011
      ." psiDamping concept #67"
    THEN
    8773 caller !  \ ASCII 87=W 73=I; test; 26sep2010
    67 urpsi !
    PsiDamp
    0 caller !  \ test; 26sep2010
    0 motjuste !
    0 topicnum !
  THEN
  topicnum @ 2 = NOT IF  \ if singular; 21jun2011
    prsn @ 3 = IF  \ 3rd person singular; 21jun2011
      EnArticle  \ chance for "A" or "THE"; 21jun2011
    THEN   \ end of test for 3rd person; 21jun2011
  THEN   \ end of test for singular; 21jun2011
 topic @ subjpsi @ = IF  \ 19sep2010
  midway @  t @  DO
    I       0 en{ @  topic @ = IF
      I     7 en{ @ aud !
      LEAVE
    THEN
  -1 +LOOP
  motjuste @ urpsi !
  8773 caller !  \ ASCII 87=W 73=I; test; 26sep2010
  PsiDamp
  0 caller !  \ test; 26sep2010
 THEN  \ 19sep2010 
  aud @ 0 > IF  \ avoid #zero ERROR; \ 19sep2010
    SpeechAct
  THEN  \ end of test to avoid ERROR; 19sep2010
  PsiDecay
  0 isflag !    \ 11dec2009 For sake of SelfRef
  0 areflag !   \ 11dec2009 For sake of SelfRef
  0 unkflag !   \ 11dec2009 For sake of SelfRef
;  ( End of WhatBe; return to AskUser; 25feb2011 )


( http://code.google.com/p/mindforth/wiki/AskUser )
:  AskUser  ( outputs questions of a speculative nature )
  kbyn  @ 0 = IF  \ insurance; 24jun2011
    39 qusub !    \ start with ROBOTS; 24jun2011
     3 prsn !     \ third person; 24jun2011
     2 numsubj !  \ plural; 24jun2011
     2 putnum !   \ plural for InStantiate; test; 5aug2011
     2 subjnum !  \ plural; 21jul2011
  THEN  \ end of test for no query-subject 24jun2011 
  ynverb @ 0 = IF  \ only ask y/n question once; 24jun2011
   quverb @ ynverb !  \ isolate at start; 24jun2022
   nphrnum @ 2 = IF  \ if plural trigger; test; 24jun2011
    kbyn @ 1 = IF  \ from KbTraversal; 24jun2011
      56 qusub !  \ 56=YOU for yes-or-no query 24jun2011
       2 prsn !     \ YOU is second person; 24jun2011
       1 numsubj !  \ assume YOU is singular; 24jun2011
       1 subjnum !  \ assume YOU is singular; 21jul2011
    THEN  \ end of test for KbTraversal; 24jun2011
    kbyn @ 2 = IF  \ from KbTraversal; 24jun2011
     39 qusub !  \ use ROBOTS as a test item; 24jun2011
      3 prsn !     \ third person; 24jun2011
      2 numsubj !  \ plural; 24jun2011
      2 subjnum !  \ plural; 21jul2011
    THEN  \ end of test for KbTraversal; 24jun2011
    kbyn @ 3 = IF  \ from KbTraversal; 24jun2011
      50 qusub !  \ 50=I for yes-or-no query 24jun2011
       1 prsn !     \ I is first person; 24jun2011
       1 numsubj !  \ since I is singular; 24jun2011
       1 subjnum !  \ since "I" is singular; 21jul2011
    THEN  \ end of test for KbTraversal; 24jun2011
    kbyn @ 4 = IF  \ from KbTraversal; 24jun2011
     100 qusub !  \ 100=GOD for yes-or-no query 24jun2011
       3 prsn !     \ GOD is third person; 24jun2011
       1 numsubj !  \ GOD is singular; 24jun2011
       1 subjnum !  \ GOD is singular; 21jul2011 
    THEN  \ end of test for KbTraversal; 24jun2011
     AuxVerb       \ to say DO or DOES; 24jun2011
     midway @  t @  DO  \ search English vocab; 24jun2011
       I       0 en{ @  qusub @ = IF  ( kbtv )
         I     7 en{ @  aud !
         LEAVE
       THEN
     -1 +LOOP
     SpeechAct   \ to say the subject; 24jun2011
     t @ tkbn !  \ if engram is to be changed; 2jul2011
     qusub @ nacpsi !  \ transfer activand; 25jun2011
     62 nounval !  \ prime NounAct; 24jun2011
     NounAct  \ activate the query subject; 24jun2011 
     midway @  t @  DO  \ search English vocab; 24jun2011
       I       0 en{ @  ynverb @ = IF  ( yes-or-no verb )
         I     2 en{ @  2 = IF  \ as if infinitive; 24jun2011
           I   7 en{ @  aud !  \ fetch recall-vector
           LEAVE  \ one engram is enough; 24jun2011
         THEN  \ end of test for plural as if infinitive
       THEN
     -1 +LOOP
     aud @ 0 = IF  \ if no plural accept singular 24jun2011
       midway @  t @  DO  \ search English vocab; 24jun2011
         I       0 en{ @  ynverb @ = IF  ( yes-or-no verb )
           I     2 en{ @  1 = IF  \ second choice; 24jun2011
             I   7 en{ @  aud !  \ fetch recall-vector
             LEAVE  \ one engram is enough; 24jun2011
           THEN  \ end of test for plural as if infinitive
         THEN
       -1 +LOOP
     THEN  \ end of test for no engram found; 24jun2011
   ( insert call to VerbAct for sake of quasi-NegSvo )
     ynverb @ nacpsi !  \ transfer activand; 25jun2011
     62 verbval !  \ prime VerbAct;  2jul2011
     VerbAct  \ activate the query verb; 25jun2011
     SpeechAct   \ to say yes-or-no verb; 24jun2011
     t @ 1 - tkbv !  \ if engram is to be changed; 2jul2011
     quobj @ 0 = IF  \ if no query-object; 20jul2011
       110 quobj !  \ 110=ANYTHING by default; 20jul2011
     THEN  \ end of test for a query-object; 20jul2011
     midway @  t @  DO  \ search English vocab; 24jun2011
       I       0 en{ @  quobj @ = IF  ( query-object? )
         I     7 en{ @  aud !
         LEAVE
       THEN
     -1 +LOOP
     SpeechAct   \ to say query-object; 24jun2011
   THEN  \  end of test for a plural nphrnum; 24jun2011
   0 yncon !  \ because question has been asked;  2jul2011
   1 kbcon !  \ because waiting for answer;  2jul2011
   0 ynverb !  \ zero out; prevent repeat of query 24jun2011
  THEN  \ end of test for a positive ynverb; 24jun2011
   0 recon ! 
   0 isflag !    \ 10dec2009 Prevent pseudo-isflag.
   0 areflag !   \ 11dec2009 Prevent pseudo-areflag.
   5 bias !  \ Restore expectation of noun; 24jun2011
;  ( End of AskUser; return to EnCog or BeVerb )


\ The SelfRef module aims for the following entelechy goals:
\ [ ] It shall enable the AI to think of "you and I" as "we".
\ [ ] It shall decide correctly the use of "I" or "ME".
\ 4aug2011 Special Note: The "I dunno" function of SelfRef
\ is becoming obsolete, to be replaced by a DeFault mechanism
\ when KbSearch does not yield a yes-answer or a "No" answer.
:  SelfRef  ( 3dec2009 self-reference with pronouns )
  subjectflag @ 0 = IF  \ 29dec2009 Prevent spurious NOT-KNOW
    isflag @   areflag @  OR  1 =   IF \ 11dec2009
      \ We insert a "{" for the sake of ReJuvenate.
      123  t @  2 aud{ !  \  123 is ASCII bracket "{"
      t @ tov !  \ 12jan2010 "{" marks start of thought.
      midway @  t @  DO  \ Look backwards for 50=I.
        I       0 en{ @  50 = IF  \ If #50 "I" is found,
          50 motjuste !  \ "nen" concept #50 for "I".
          I     7 en{ @  aud !  \ Recall-vector for "I".
          LEAVE  \ Use the most recent engram of "I".
        THEN  \ End of search for #50 "I".
      -1 +LOOP  \ End of loop finding the word "I".
      SpeechAct   \ 7dec2009 Speak or display the word "I".
      AuxVerb   \ Fetch a form of auxiliary verb "do".
      midway @  t @  DO  \ Look backwards for 12=not.
        I       0 en{ @  12 = IF  \ If #12 "not" is found,
          12 motjuste !  \ "nen" concept #12 for "not".
          I     7 en{ @  aud !  \ Recall-vector for "not".
          LEAVE  \ Use the most recent engram of "not".
        THEN  \ End of search for #12 "not".
      -1 +LOOP  \ End of loop finding the word "not".
      SpeechAct   \ 7dec2009 Speak or display the word "not".
      midway @  t @  DO  \ Look backwards for 61=KNOW.
        I       0 en{ @  61 = IF  \ If #61 "KNOW" is found,
          61 motjuste !  \ "nen" concept #61 for "KNOW".
          I     7 en{ @  aud !  \ Recall-vector for "KNOW".
          LEAVE  \ Use the most recent engram of "not".
        THEN  \ End of search for #61 "KNOW".
      -1 +LOOP  \ End of loop finding the word "KNOW".
      SpeechAct   \ 7dec2009 Speak or display the word "KNOW".
    THEN    \ 7dec2009 End of test for isflag from EnCog
  THEN \ 29dec2009 End of test of subjectflag
  subjectflag @ 3 < IF  \ Accept ANY value of flag.
    ( We insert a "{" for the sake of Rejuvenate. )
    123  t @  2 aud{ !  \  123 is ASCII bracket "{"
    t @ tov !  \ 12jan2010 "{" marks start of thought.
    midway @  t @  DO  \ Look backwards for 50=I.
      I       0 en{ @  50 = IF  \ If #50 "I" is found,
              50 motjuste !  \ "nen" concept #50 for "I".
        I     7 en{ @  aud ! \ Recall-vector for "I".
        LEAVE  \ Use the most recent engram of "I".
      THEN  \ End of search for #50 "I".
    -1 +LOOP  \ End of loop finding the word "I".
    SpeechAct \ 13dec2009 Speak or display the word "I".
    AuxVerb   \ Fetch a form of auxiliary verb "do".
    midway @  t @  DO  \ Look backwards for 12=not.
      I       0 en{ @  12 = IF  \ If #12 "not" is found,
        12 motjuste !  \ "nen" concept #12 for "not".
        I     7 en{ @  aud !  \ Recall-vector for "not".
        LEAVE  \ Use the most recent engram of "not".
      THEN  \ End of search for #12 "not".
    -1 +LOOP  \ End of loop finding the word "not".
    SpeechAct \ 13dec2009 Speak or display the word "not".
    midway @  t @  DO  \ Look backwards for 61=KNOW.
      I       0 en{ @  61 = IF  \ If #61 "KNOW" is found,
        61 motjuste !  \ "nen" concept #61 for "KNOW".
        I     7 en{ @  aud ! \ Recall-vector for "KNOW".
        LEAVE  \ Use the most recent engram of "not".
      THEN  \ End of search for #61 "KNOW".
    -1 +LOOP  \ End of loop finding the word "KNOW".
    SpeechAct \ 13dec2009 Speak or display the word "KNOW".
  THEN \ 29dec2009 End of test of subjectflag
  subjectflag @ 1 = IF  ( 3dec2009 NounPhrase seeks a subject )
    motjuste @ 65 = IF  ( 3dec2009 If candidate is 65=ME )
      50 motjuste !  ( 32dec2009 Change 65=ME to 50=I )
      \ Activate auditory engram of pronoun "I":
      midway @  t @  DO  \ Look backwards for 50=I.
        I       0 en{ @  50 = IF  \ If #50 "I" is found,
          50 motjuste !  \ "nen" concept #50 for "I".
          I     7 en{ @  aud ! \ Recall-vector for "I".
          LEAVE  \ Use the most recent engram of "I".
        THEN  \ End of search for #50 "I".
      -1 +LOOP  \ End of loop finding pronoun "I".
      motjuste @ psi ! \ For use in NounAct module.
      motjuste @ nacpsi !  \  1jan2010 Needed in NounAct
      62 nounval !  \  8jan2010 test; remove
      NounAct          \ For slosh-over to related concept.
      SpeechAct        \ To say or display the pronoun
    THEN  ( 3dec2009 End of test for candidate 65=ME )
    0 subjectflag !  \ 29dec2009 test; remove
  THEN  ( 3dec2009 End of test for NounPhrase seeking a subject )
  1 sknlp !  \ 8jn2010 Skip NLP generation in EnCog.
;  \ End of SelfRef; return to NounPhrase or EnCog


:  EnPronoun  \ For use with what-do-X-do queries.
  num @ 1 = IF  \ If antecedent num(ber) is singular.
    mfn @ 1 = IF  \ if masculine singular; 13apr2010
      midway @  t @  DO  \ Look backwards for 49=HE.
        I       0 en{ @  49 = IF  \ If #49 "he" is found,
          49 motjuste !  \ "nen" concept #49 for "he".
          I     7 en{ @  aud !  \ Recall-vector for "he".
          LEAVE  \ Use the most recent engram of "he".
        THEN  \ End of search for #49 "he".
      -1 +LOOP  \ End of loop finding pronoun "he".
      SpeechAct \ Speak or display the pronoun "he".
    THEN  \ end of test for masculine gender-flag.
    mfn @ 2 = IF  \ if feminine singular.
      midway @  t @  DO  \ Look backwards for 80=SHE
        I       0 en{ @  80 = IF  \ If #80 "she" is found,
          80 motjuste !  \ "nen" concept #80 for "she".
          I     7 en{ @  aud !  \ Recall-vector for "she".
          LEAVE  \ Use the most recent engram of "she".
        THEN  \ End of search for #80 "she".
      -1 +LOOP  \ End of loop finding pronoun "she"
      SpeechAct \ Speak or display the pronoun "she"
    THEN  \ end of test for feminine gender-flag.
    mfn @ 3 = IF  \ if neuter singular; 13apr2010
      midway @  t @  DO  \ Look backwards for 95=IT.
        I       0 en{ @  95 = IF  \ If #95 "it" is found,
          95 motjuste !  \ "nen" concept #95 for "it".
          I     7 en{ @  aud !  \ Recall-vector for "it".
          LEAVE  \ Use the most recent engram of "it".
        THEN  \ End of search for #95 "it"; 13apr2010
      -1 +LOOP  \ End of loop finding pronoun "it".
      SpeechAct \ Speak or display the pronoun "it".
    THEN  \ end of test for neuter gender-flag.
    0 numsubj !  \ safety measure; 13apr2010
  THEN  \ End of test for singular num(ber)
  num @ 2 = IF  \ 30dec2009 If num(ber) of antecedent is plural
    ( code further conditions for "WE" or "YOU" )
    midway @  t @  DO  \ Look backwards for 52=THEY.
      I       0 en{ @  52 = IF  \ If #52 "they" is found,
        52 motjuste !  \ "nen" concept #52 for "they".
        I     7 en{ @  aud !  \ Recall-vector for "they".
        LEAVE  \ Use the most recent engram of "they".
      THEN  \ End of search for #52 "they".
    -1 +LOOP  \ End of loop finding pronoun "they".
    SpeechAct \ Speak or display the pronoun "they".
  THEN  \ 30dec2009 End of test for plural num(ber)
;  ( End of EnPronoun; return to EnCog or to NounPhrase )


\ Noun-selection shifts from En{ to Psi{ on 12aug2011.
:  NounPhrase ( select part of a thought )
  PsiDecay  \ reduce stray activations; 17aug2011
  66 caller !  \ here and further down; 12oct2010
  objold @ urpsi !  \ here and further down; 12oct2010
  0 caller !  \ reset after use; 12oct2010
  0 urpsi !  \ reset for safety; 12oct2010
  0 reject !
  EnReify ( move abstract Psi concepts to EnVocab reality )
  0 act !
  0 aud !
  0 kibosh !  \ for de-activating non-selectees; 17aug2011  
  0 motjuste !
  0 num !   \ without prejudice; 29aug2010
  0 prsn !  \ without prejudice; 29aug2010
  5 opt !
  35 pov !
  1 subjectflag !  ( 3dec2009 A default until countermanded )
  dirobj @ 1 = IF 0 subjectflag ! THEN  ( 3dec2009 anti-default )
  predflag @ 1 = IF 0 subjectflag ! THEN ( anti-default 8oct2010 )  
  0 psi !
  midway @  t @  DO
    I 5 psi{ @ 5 =  I 5 psi{ @ 7 = OR IF  \ POS; 12aug2011
      \ SHOW ALL POSITIVE ACTIVATIONS; test; 15aug2011
    \ I    1 psi{ @ 0 > IF  \ test; remove; 18aug2011
    \ CR ." NPhrA: I psi0 psi1 = "  \ test 18aug2011
    \ I . I 0 psi{ @ .  I 1 psi{ @ .  \ test 18aug2011
    \ THEN  \ test; remove; 18aug2011
      I   0 en{ @ 65 = IF I 7 en{ @ audme ! THEN  \ 25jul2010
      I  1 psi{ @  act @ > IF  \ if higher; 12aug2011
        subjectflag @ 1 = IF  \ 28jul2011
          I        tsels ! \ retain time of subject;  28jul2011
        THEN  \ end of test for selection of subject  28jul2011
        I          tseln ! \ retain time of motjuste;  8may2011
        tseln @  kibosh @  < IF  \ if different; 17aug2011
        \ ."  KIBOSH = " kibosh @ .  \ 18aug2011
          0 kibosh @ 1 psi{ !  \ deactivate also-ran; 17aug2011
        THEN  \ 17aug2011
        I         kibosh ! \ time of predecessor cand 17aug2011
        I  0 psi{ @  motjuste !  \ 12aug2011
        ( insert NPhr diagnostic code here; 11aug2011 )
      \ CR ."  NPhr: I kibosh motjuste psi1 = "  \ test 18aug2011
      \ I . kibosh @ . motjuste @ . I 1 psi{ @ . \ test 18aug2011
        alsoran @ 0 > IF  \ if there is an alsoran; 5nov2010
          motjuste @ alsoran @ = NOT IF  \ superseded? 5nov2010
            alsoran @ urpsi !  \ prepare to psi-damp; 5nov2010
            0 urpsi !  \ reset for safety; 5nov2010
            0 alsoran !  \ reset for safety; 5nov2010
          THEN  \ end of test for higher-act motjuste; 5nov2010
        THEN  \ end of test for postive alsoran; 5nov2010
        \ Code below may obviate need for alsoran code; 9nov2010
     \  I     1 en{ @ 5 > IF  \ above arbitrary 5?  9nov2010
     \    I   1 en{ @  act @ < IF  \ non-winner?  9nov2020
     \      I 0 en{ @  urpsi !  \ prepare to psi-damp; 9nov2010
     \      0 urpsi !  \ reset for safety;  9nov2010
     \    THEN   \ end of test for non-winner;  9nov2010
     \  THEN  \ end of test for positive activation; 9nov2010
        motjuste @ alsoran !  \ in case higher is found; 5nov2010
        subjectflag @ 1 = IF  \ avoid direct objects; 3oct2010
         I 2 psi{ @ subjnum !  \ verbs in general; 12aug2011
          motjuste @ subjold !  \ keep oldsubject ready; 8oct
        THEN  \ end of test for a thought-subject; 3oct2010
       I 0 psi{ @  subjpsi !  \ 12aug2011
       I 2 psi{ @  nphrnum !  \ NounPhrase num(ber); 12aug2011
       I 2 psi{ @  putnum !   \ putative num for verb; 12aug2011
       I 5 psi{ @  nphrpos !  \ NounPhrase part-of-speech 12aug2011
       I 5 psi{ @  posflag ! ( AskUser discriminand; 12aug2011 )
        I 7 en{ @  aud !      \ 31jan2010
        I 7 en{ @  audjuste ! \ 31jan2010
        dirobj @ 1 = IF
          motjuste @ objold ! \ a test ICW slosh-over; 12oct2010
          motjuste @  50 = IF
            fyi @ 3 = IF
              CR ." nPhr: Switching dirobj I to ME"  CR
            THEN
            65 motjuste !
            audme @ aud !
            audme @ audjuste !
          THEN
        THEN
       I 1 psi{ @  act !  \ 12aug2011
      THEN
    THEN
  -1 +LOOP
  midway @  t @  DO  \ search backwards; 12aug2011
    I       0 en{ @  motjuste @ = IF  \ 12aug2011
      I     7 en{ @  aud !  \ auditory recall-vector; 12aug2011
      I     7 en{ @  audjuste !  \ recall-vector; 12aug2011
      LEAVE  \ one auditory engram is enough; 12aug2011
    THEN   \ end of test for match with motjuste; 12aug2011
  -1 +LOOP  \ end of backwards search loop; 12aug2011
  dirobj @ 1 = IF  \ When seeking direct object; 13jun2011
    act @  20 < IF  \ If activation too low; 13jun2011
      WhatAuxSVerb  \ ask question for lack of dirobj 30jul2011
      EXIT  \ Abandon rest of NounPhrase; 13jun2011
    THEN  \ End of test for sufficient activation; 13jun2011
  THEN  \ End of test for direct object; 13jun2011
  act @  8 < IF  \ if no subject of thought is found; 16aug2011
    50 motjuste !  \ 50=I default concept of AI Mind; 16aug2011
    50 subjpsi !   \ for use elsewhere; 16aug2011
    50 topic !     \ for question-asking modules; 16aug2011
     1 subjnum !   \ for use elsewhere; 16aug2011
     1 prsn !      \ for use elsewhere; 16aug2011
    midway @  t @  DO  \ Look backwards for 50=I; 16aug2011
      I       0 en{ @  50 = IF  \ If #50 "I" is found; 16aug2011
        I     7 en{ @  aud !  \ Recall-vector for "I"; 16aug2011
        LEAVE  \ Use the most recent engram of "I"; 16aug2011
      THEN  \ End of search for #50 "I"; 16aug2011
    -1 +LOOP  \ End of loop finding the word "I"; 16aug2011
    SpeechAct   \ Speak or display the word "I". 16aug2011
    EXIT  \ Abandon rest of NounPhrase; 16aug2011
  THEN  \ end of test for low activation warranting a default
  act @  20 < IF  \ if winning activation too low; 28sep2010
    midway @  t @  DO   \ search for WHAT; test; 4aug2011
      I       0 en{ @  54 = IF   \ test;  4aug2011
        54 motjuste !            \ test;  4aug2011
        1 subjnum !              \ test; 14aug2011
        I     7 en{ @  aud !     \ test;  4aug2011
        LEAVE                    \ test;  4aug2011
      THEN                       \ test;  4aug2011
    -1 +LOOP                     \ test;  4aug2011
    SpeechAct  \ say "WHAT"; test; 4aug2011
    EXIT  \ Abandon rest of NounPhrase; 4aug2011
  THEN  \ end of threshold-test to reject subject; 28sep2010
  motjuste @ 50 = IF  \ if 50=I selected; 29aug2010
    1 prsn !  \ first person; 29aug2010
    1 num !   \ singular; 29aug2010
    1 nphrnum !  \ singular; 30aug2010
  THEN  \ end of test for 50=I; 29aug2010
  subjpsi @ 0 > IF  \ if positive subjpsi; 26jul2010
    whomark @ 0 > IF  \ if positive from InSt; 26jul2010
      subjpsi @ qutop !  \ xfer value; 26jul2010
      0 whomark !  \ reset after single use; 26jul2010
    THEN  \ end of test for positive whomark; 26jul2010
  THEN  \ end of test for positive subjpsi; 26jul2010
  EnDamp
  subjectflag @ 1 = IF  \ 3dec2009 If seeking a subject...
    motjuste @ 65 = IF SelfRef EXIT  THEN  \ Pronoun "ME"
  THEN   \ 3dec2009 End of test for positive subjectflag
  act @ nounval !
  dirobj @ 1 = IF  \ 13dec2009 Only if seeking direct object
    motjuste @ 0 > IF  \ 13dec2009 If a candidate is found
    THEN    \ 13dec2009 End of test for a positive candidate.
  THEN  \ 13dec2009 End of test for seeking a direct object.
  act @ 2 < IF
    motjuste @ 0 > IF
      1 reject !
    THEN
  THEN
  motjuste @  hipsi !
  0 anset !   ( Insert "AN" article before vowels. )
  aud @  0  aud{ @ 65 = IF 65 anset ! THEN  ( if vowel A )
  aud @  0  aud{ @ 69 = IF 69 anset ! THEN  ( if vowel E )
  aud @  0  aud{ @ 73 = IF 73 anset ! THEN  ( if vowel I )
  aud @  0  aud{ @ 79 = IF 79 anset ! THEN  ( if vowel O )
  aud @  0  aud{ @ 85 = IF 85 anset ! THEN  ( if vowel U )
  whoflag @ 0 = IF  \ If not answering a who-is query; 23jul2010
  \ EnArticle    \ Give a chance, not an order; 23jul2010
  \ EnArticle    \ Commenting out; inhibition test; 9sep2010
    0 whoflag !  \ Here instead of at InStantiate; 23jul2010
  THEN  \ End of test for zero whoflag; 23jul2010
  num @ 1 = IF  \ If num(ber is singular; 10ap2010
    EnPronoun   \ Prepare to substitute he she it; 10apr2010
  THEN   \ End of test of num(ber); 10apr2010
  motjuste @ 50 = NOT IF  \ if not 50=I; 29aug2010
    motjuste @ 56 = NOT IF  \ not 56=you; 29aug2010
      motjuste @ 53 = NOT IF  \ 56=WE; 29aug2010
        3 prsn !  \ not I YOU WE; 29aug2010
      THEN  \ end of test for 53=WE; 29aug2010
    THEN  \ end of test for 56=YOU; 29aug2010
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
\ -64 tsels @  1 psi{ ! \ ICW be-verb ActRules; 29jul2011
  -32 tsels @  1 psi{ ! \ AI is now robust enough; 5aug2011
\ predflag @ 1 = IF  \ omit dir-obj for now; 22sep2010
  predflag @ 1 = dirobj @ 1 = OR IF  \ test; 29may2011
    NounClear  \ deactivate before inhibiting; 18aug2011
  \ -32 tseln @  1 psi{ ! \ a hefty inhibition; 8may2011
  \ -64 tseln @  1 psi{ ! \ for response-variety; 29may2011
    -32 tseln @  1 psi{ ! \ AI is now robust enough; 5aug2011
    PsiDecay  \ try to knock out also-rans; 8nov2010
    PsiDecay  \ try to knock out also-rans; 8nov2010
  THEN  \ only inhibit predicate nominatives; 11sep2010
  predflag @ 1 = IF  \ helps for Is-a; 15sep2010
    EnArticle  \ say "A" or "THE"; 15sep2010
  THEN  \ end of test; 15sep2010
  audjuste @ aud !
  aud @ 0 > IF  \ avoid ERROR; 19sep2010
    SpeechAct
  THEN   \ end of test for 0=aud ERROR; 19sep2010 
  predflag @ 1 = dirobj @ 1 = OR IF  \ both; 23jun2011
    -32 t @ 1 -  1 psi{ ! \ inhibit new noun-node; 27sep2010
  \ -64 t @      1 psi{ ! \ test; revert; 25jun2011
    -32 t @      1 psi{ ! \ AI is now robust enough; 5aug2011
  THEN  \ only inhibit predicate nominatives; 12sep2010
\ -64 t @        1 psi{ !  \ also inhibit subjects; 28jul2011
  -32 t @        1 psi{ !  \ AI is now robust enough; 5aug2011
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
  0 alsoran !  \ reset for safety; 5nov2010
  0 psi  !
  0 aftjux !  \ reset for safety; 27jul2011
  0 prejux !  \ reset for safety; 27jul2011
  0 jux !     \ reset for safety; 27jul2011
  0 psi3 !    \ reset for safety  27jul2011
;  ( NounPhrase returns to BeVerb, VerbPhrase, or EnCog )


:  ConJoin
  questype @  16 =  IF
    18     conj !
  ELSE  17 conj !
  THEN
  midway @  t @  DO
    I       0 en{ @  conj @ = IF
      conj @  motjuste !
      I     7 en{ @  aud !
      LEAVE
    THEN
  -1 +LOOP
  SpeechAct
  0 questype !
;  ( End of ConJoin; return to an English generation module )


:  BeVerb ( intransitive verbs of being )
  \ BeVerb is being repatriated into VerbPhrase; 8aug2011
     maxbeact @ 21 < IF  \ tighten up; test; 28sep2010
     6 maxbeact +!  \ test, REMOVE; 25aug2010
       AskUser   \ locus for reactive code? 9aug2010
       0 posflag !  \ reset for safety; 9aug2010     \
       0 detour !   \ test, remove; 10aig2010
       400 rsvp !   \ Give user time to respond. 10aug2010
       EXIT  \ avoid callling NounPhrase again; 10aug2010
     THEN  \ end of test of activation; 8aug2010
     0 beact !  \ reset after any usage; 8aug2010
     0 maxbeact !  \ reset; 19aug2010
   nphrnum @ 1 = IF  ( If number is singular; 20sep2010 )
     prsn @ 1 = IF  \ 1st person singular; 20sep2010
       midway @  t @  DO
         I       0 en{ @  57 = IF  \ 20sep2010
           57 motjuste !  ( Set verbform to "AM" 20sep2010 )
           I     7 en{ @  aud ! ( Start of AM-engram )
           LEAVE
         THEN
       -1 +LOOP
     THEN  \ end of test for first person; 20sep2010
     prsn @ 3 = IF  \ 3rd person singular; 20sep2010
       midway @  t @  DO
         I       0 en{ @  66 = IF
           66 motjuste !  ( 4dec2009 Set verbform to "IS" )
           I     7 en{ @  aud ! ( Start of IS-engram )
           LEAVE
         THEN
       -1 +LOOP
     THEN  \ end of test for third person; 20sep2010
   THEN ( 4dec2009 Pronoun-tests below may override these values )
 \ num @ 2 = IF  ( 4dec2009 if number is plural )
   nphrnum @ 2 = IF  ( if number is plural; 20sep2010 )
       midway @  t @  DO
         I       0 en{ @  67 = IF
           67 motjuste !  ( 4dec2009 Set verbform to "ARE" )
           I     7 en{ @  aud !  ( Start of ARE-engram )
           LEAVE
         THEN
       -1 +LOOP
   THEN  ( Pronoun-tests below may override these values. )
   numflag @ 1 = IF  ( If EnArticle "A" has set singular )
 \ CR ."    BeVerb IS w. numflag " numflag @ . \ 20sep2010
       midway @  t @  DO
         I       0 en{ @  66 = IF
           66 motjuste !   ( 66 = IS )
           I     7 en{ @  aud !
           LEAVE
         THEN
       -1 +LOOP
   THEN
   subjpsi @ 50 = IF  ( I )
     motjuste @ 57 = NOT IF  ( AM )
       midway @  t @  DO
         I       0 en{ @  57 = IF
           57 motjuste !
           I     7 en{ @  aud !
           LEAVE
         THEN
       -1 +LOOP
     THEN
   THEN
   subjpsi @ 56 = IF  ( YOU )
     motjuste @ 67 = NOT IF   ( ARE )
       midway @  t @  DO
         I       0 en{ @  67 = IF
           67 motjuste !
           I     7 en{ @  aud !
           LEAVE
         THEN
       -1 +LOOP
     THEN
   THEN
   subjpsi @ 49 = IF  ( HE )
     motjuste @ 66 = NOT IF  ( IS )
       midway @  t @  DO
         I       0 en{ @  66 = IF
           66 motjuste !
           I     7 en{ @  aud !
           LEAVE
         THEN
       -1 +LOOP
     THEN
   THEN
   subjpsi @ 80 = IF  ( SHE )
     motjuste @ 66 = NOT IF   ( IS )
       midway @  t @  DO
         I       0 en{ @  66 = IF
           66 motjuste !
           I     7 en{ @  aud !
           LEAVE
         THEN
       -1 +LOOP
     THEN
   THEN
   subjpsi @ 95 = IF  ( IT )
     motjuste @ 66 = NOT IF  ( IS )
       midway @  t @  DO
         I       0 en{ @  66 = IF
           66 motjuste !
           I     7 en{ @  aud !
           LEAVE
         THEN
       -1 +LOOP
     THEN
   THEN
   subjpsi @ 53 = IF  ( WE )
     motjuste @ 67 = NOT IF  ( ARE )
       midway @  t @  DO
         I       0 en{ @  67 = IF
           67 motjuste !
           I     7 en{ @  aud !
           LEAVE
         THEN
       -1 +LOOP
     THEN
   THEN
   subjpsi @ 52 = IF  ( THEY )
     motjuste @ 67 = NOT IF    ( ARE)
       midway @  t @  DO
         I       0 en{ @  67 = IF
           67 motjuste !
           I     7 en{ @  aud !
           LEAVE
         THEN
       -1 +LOOP
     THEN
   THEN
   posflag @ 5 = IF  ( for a noun; 20aug2010 )
     nphrnum @ 1 = IF  \ for singular noun; 20sep2010
       midway @  t @  DO
         I       0 en{ @  66 = IF
           66 motjuste !   ( 66 = IS )
           I     7 en{ @  aud !
           LEAVE
         THEN
       -1 +LOOP  \ end of search for "IS"; 20sep2010
     THEN  \ end of test for singular; 20sep2010
     nphrnum @ 2 = IF  \ for plural noun; 20sep2010
       midway @  t @  DO
         I       0 en{ @  67 = IF  \ 20sep2010
           67 motjuste !   ( 67 = ARE; 20sep2010 )
           I     7 en{ @  aud !
           LEAVE
         THEN
       -1 +LOOP  \ end of search for "ARE"; 20sep2010
     THEN  \ end of test for plural; 20sep2010
     subjpsi @ qus !  \ transfer to query-subject; 20aug2010
     0 qus !  \ reset, if safe; 20aug2010
   THEN  \ taking number into consideration; 20sep2010
   0 subjpsi !  \  1jan2010 Assuming use of it has been made.
   motjuste @ vacpsi !  \ prepare to deglobalize; 27sep2010
   VerbAct
   0 vacpsi !  \ reset for safety; 27sep2010
   motjuste @ 57 = IF  \ 57=AM; test; 8oct2010
   ( It may be necessary to activate 58=BE unconditionally. )
     58 vacpsi !  \ 58=BE; in case stored as such; 8oct2010
     VerbAct  \ activate not only AM but also BE; 8oct2010
     0 vacpsi  \ reset for safety; 8oct2010
   THEN  \ end of test to equate AM & BE; 8oct2010
   motjuste @ 67 = IF  \ 67=ARE; test; 9oct2010
   ( It may be necessary to activate 58=BE unconditionally. )
     58 vacpsi !  \ 58=BE; in case stored as such; 9oct2010
     VerbAct  \ activate not only ARE but also BE; 9oct2010
     0 vacpsi  \ reset for safety; 9oct2010
   THEN  \ end of test to equate ARE & BE; 9oct2010
   \ more than one be-verb may need psi-damping;  9nov2010
 \ -64 tsels @ 1 psi{ ! \ Inhibit subj after thinking; 28jul2011
   -32 tsels @ 1 psi{ ! \ AI is now robust enough; 5aug2011
 \ -64 tselv @ 1 psi{ ! \ Inhibit verb after thinking; 28jul2011
   -32 tselv @ 1 psi{ ! \ AI is now robust enough; 5aug2011
   0 tsels !  \ reset for safety; 28jul2011
   0 tselv !  \ reset for safety; 28jul2011
   motjuste @ urpsi !  \ prepare to psi-damp;  9nov2010
   PsiDamp  \ deactivate the be-verb form;  9nov2010
   0 urpsi !  \ reset for safety;  9nov2010
   SpeechAct
 \ -64 t @ 1 -   1 psi{ ! \ inhibit current be-verb; 28jul2011
   -32 t @ 1 -   1 psi{ ! \ AI is now robust enough; 5aug2011
   1 predflag !  \ briefly set the flag; test; 11sep2010
   notjux @ 12 = IF  \ 12=NOT; 11aug2011
     midway @  t @  DO   \ Search En(glish) array; 27jul2011
       I       0 en{ @  12 = IF  \ Look for "NOT"; 27jul2011
         I     7 en{ @  aud ! \ Auditory start-tag 27jul2011
         LEAVE   \ One instance of NOT suffices; 27jul2011
       THEN   \ End of lexical test for 12=NOT; 27jul2011
     -1 +LOOP  \ End of loop searching for 12=NOT; 27jul2011
     SpeechAct  \ Say the word "NOT"; 27jul2011
     0 aftjux !  \ reset for safety; 27jul2011
     0 notjux !  \ reset for safety; 11aug2011
     0 prejux !  \ reset for safety; 27jul2011
     0 jux !     \ reset for safety; 27jul2011
     0 psi3 !    \ reset for safety  27jul2011
   THEN \ end of test for negated be-verb; 27jul2011
 ( EnAdjective -- a possibility here )
   NounPhrase
   0 predflag !  \ reset for safety; test; 11sep2010
  0 numflag !  \  3dec2009 VerbPhrase also resets numflag.
;  \ 7dec2009  BeVerb returns to VerbPhrase or...


\ The VerbPhrase module aims for the following entelechy goals.
\ [ ] If no predicate nominative is known, detour into a question.
\ [ ] If no transitive verb is most active, default to verb of being.
\ [ ] If no direct object is found, detour into asking a question.
\ 7dec2009 If no verb is found for a noun, defer to SelfRef NOT-KNOW.
\ [ ] If a transitive verb is most active, try to find direct object.
\ [X] Find whatever verb is most active after a noun-phrase.
\ Verb-selection shifts from en{ array to psi{ array on 12aug2011.
:  VerbPhrase ( supervise verb syntax )
  PsiDecay  \ reduce stray activations; 17aug2011
  0 subjectflag !  \ for only absolute SpreadAct; test; 4aug2011 
  EnReify
  0 act !
  0 aud !
  0 detour !
  0 kibosh !  \ for de-activating non-selectees; 17aug2011
  0 motjuste !
  8 opt !
  0 psi !
  0 vphract !  \ for validity of threshold-tests; 15aug2011
  adverbact 32 > IF
    ( EnAdverb )
  THEN
  fyi @ 1 > IF CR
 ."   VerbPhrase preview with slosh-over indicated by + --"
    CR 
    ."   Disparate verb-node activations slosh "  \ 7nov2010
    ." over onto candidate objects."  CR  ."    " \ 7nov2010
  THEN
  midway @ t  @ DO
    I     5 psi{ @  8 = IF  \  if 8=pos verb; 12aug2011
    \ SHOW ALL POSITIVE ACTIVATIONS; test; remove; 15aug2011
    \ I    1 psi{ @ 0 > IF  \ test; remove; 18aug2011
    \ CR ." VPhrA: I psi0 psi1 = "  \ test 18aug2011
    \ I . I 0 psi{ @ .  I 1 psi{ @ .  \ test 18aug2011
    \ THEN  \ test; remove;  17aug2011
      I   1 psi{ @  act @ > IF  ( if psi1 is higher 12aug2011 )
        I          tselv ! \ retain time of winning verb; 8may2011
        tselv @  kibosh @  < IF  \ if different 17aug2011
        \ ."  KIBOSH = " kibosh @ .  \ 17aug2011
          0 kibosh @ 1 psi{ !  \ deactivate also-ran; 17aug2011
        THEN  \ end of comparison; 17aug2011
        I         kibosh ! \ time of predecessor cand 17aug2011
        I 0 psi{ @ motjuste !  ( store psi-tag of verb 12aug2011 )
        ( insert diagnostic code here; 7aug2011 )
      \ CR ."  VPhrB: I motjuste psi1 tselv = "  \ 18aug2011
      \ I . motjuste @ .  I 1 psi{ @ . tselv @ . \ 18aug2011
        I 1 psi{ @ beact ! ( store activation of be-verb; 12aug2011 )
        maxbeact @ beact @ < IF  \ if maximum is smaller; 20aug2010
          beact @ maxbeact !  \ for comparisons; 20aug2010
        THEN  \ only store when beact is large; 20aug2010
   I 1 psi{ @ 0 > IF  \ positive activation; 12aug2011
        I 3 psi{ @ psi3 !  ( Check for negation; 25jun2011 )
        I 3 psi{ @ notjux !  ( check be-verb negation; 11aug2011 )
   THEN  \ end of test for positive activation; 27jul2011
        I 5 psi{ @ predpos ! ( Grab winning part of speech 12aug2011 )
        I  7 en{ @ vphraud ! ( auditory recall-vector 25jun2011 )
        I 1 psi{ @  act !  ( to test for a higher psi1 12aug2011 )
      THEN
    THEN
  -1 +LOOP
  act @ vphract !  \ for threshold comparisons; 21jun2011
  motjuste @ unk !  \ test; 8aug2011
  unk @ 57 = unk @ 58 = OR unk @ 66 = OR unk @ 67 = OR IF
  \ CR ." VPhr: be-verb notjux = "  \ test; 11aug2011
  \ unk @ .  notjux @ . \ test; 11aug2011
  THEN  \ end of test for BE AM IS ARE; 8aug2011
  act @  verbval !
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
        WhoBe  \ ask WHO not WHAT; 30jul2011
        0 mfnflag !  \ reset after use; 30jul2011
        EXIT  \ abandon rest of VerbPhrase
      THEN  \ end of test for positive mfnflag; 30jul2011
      WhatBe  \ for a what-is question; test; 21jun2011
      EXIT  \ abandon rest of VerbPhrase;  2jul2011
    THEN  \ 21jun2011
    nphrnum @ 2 = IF  \  2jul2011
      WhatAuxSDo  \ what do Subjects do? 2jul2011
      1 yncon !  \ after input ask yes-or-no question
      EXIT  \ abandon rest of VerbPhrase;  2jul2011
    THEN  \ end of test for plural noun; 2jul2011
    1 detour !
    fyi @ 1 > IF
      CR ."   VerbPhrase: detouring when "
      ." no candidate-verb is found. "
      CR ."   VerbPhrase: detour value is at " detour @ .
    THEN
  THEN
\ CR ."  VPhrBranch:: motjuste nphrnum vphract = " \ 15aug2011
\ motjuste @ .  nphrnum @ . vphract @ .  \ test; 15aug2011
  motjuste @ 0 > IF
    vphract @ 20 < IF  \ a test ICW WhoBe; 21jun2011
      nphrnum @ 1 = IF  \ 21jun2011
        mfnflag @ 0 > IF  \ if masc. or fem.; 30jul2011
          WhoBe  \ ask WHO not WHAT; 30jul2011
          0 mfnflag !  \ reset after use; 30jul2011
          EXIT  \ abandon rest of VerbPhrase
        THEN  \ end of test for positive mfnflag; 30jul2011
        WhatBe  \ for a what-is question; test; 21jun2011
        EXIT  \ abandon rest of VerbPhrase; 30jul2011
      THEN  \ 21jun2011
      nphrnum @ 2 = IF  \  2jul2011
        WhatAuxSDo  \ what do Subjects do? 2jul2011
        1 yncon !  \ after input ask yes-or-no question
        EXIT  \ abandon rest of VerbPhrase;  2jul2011
      ELSE  \ if "nphrnum" neither 1 nor 2; 15aug2011
        EXIT  \ to avoid a spurious thought; 15aug2011
      THEN  \ end of test for plural noun; 2jul2011
    THEN   \ End of test of vphract; 21jun2011
    psi3 @ 12 = IF  \ test; 25jun2011
     motjuste @ unk !  \ test; 6aug2011
     unk @ 57 = unk @ 58 = OR unk @ 66 = OR unk @ 67 = OR NOT IF
      AuxVerb   \ to say "DO" or "DOES" 25jun2011
      midway @  t @  DO   \ Search En(glish) array; 25jun2011
        I       0 en{ @  12 = IF  \ Look for "NOT"; 25jun2011
          I     7 en{ @  aud ! \ Auditory start-tag 25jun2011
          LEAVE   \ One instance of NOT suffices; 25jun2011
        THEN   \ End of lexical test for 12=NOT; 25jun2011
      -1 +LOOP  \ End of loop searching for 12=NOT; 25jun2011
      SpeechAct  \ Say the word "NOT"; 25jun2011
      0 psi3 !  \ reset for safety; 27jul2011
     THEN  \ end of test to not say do w. be-verbs; 28jul2011
    THEN  \ end of test for psi3 jux negation; 25jun2011
    motjuste @ unk !  \ convenience; 14aug2011
    unk @ 57 = unk @ 58 = OR unk @ 66 = OR unk @ 67 = OR NOT IF
      nphrnum @ 1 = IF  \ 14aug2011
        prsn @ 3 = IF  \ Only for third person;  8may2011
          83 inflex1 !  \ for inflex1,2,3 (ing); 3nov2010
          1 vpos !  \ 14aug2011
        THEN \ End of test for 3rd person (sing) 8may2011
      THEN  \ end of test fof singular; 14aug2011
    THEN  \ end of test for not a be-verb; 14aug2011
    motjuste @  hipsi !
    \ The following code for the irregular English verb
    \ "to have" serves as example code for the many German
    \ irregular verbs that a polyglot AI must deal with.
    motjuste @ 70 = IF  \ irregular 70=HAVE; 13aug2011
      subjnum @ 1 =  prsn @ 3 = AND IF  \ 13aug2011
        midway @  t @  DO  \ search backwards; 13aug2011
          I       0 en{ @  90 = IF  \ 90=HAS;  13aug2011
            I     7 en{ @  vphraud !  \ 13aug2011
            LEAVE  \ one engram is enough; 13aug2011
          THEN  \ end of test for HAS-engram; 13aug2011
        -1 +LOOP  \ end of search of En(glish) lexicon
      THEN  \  end of test for 3rd person singular; 13aug2011
    THEN  \ end of special handling of 70=HAVE; 13aug2011
    motjuste @ unk !  \ use short "unk" to save room; 8ug2011
    unk @ 57 = unk @ 58 = OR unk @ 66 = OR unk @ 67 = OR IF
      subjnum @ 1 = IF  \ singular subject number; 16aug2011
        prsn @ 1 = IF   \ first person; 16aug2011
          midway @  t @  DO  \ search En-lexicon; 16aug2011
            I       0 en{ @  57 = IF  \ 57=AM; 16aug2011
              I     7 en{ @  vphraud !  \ engram; 16aug2011
              LEAVE  \ one engram is enough; 16aug2011
            THEN  \ end of test for 57=AM; 16aug2011
          -1 +LOOP  \ end of loop; 16aug2011
        THEN  \ end of test for first person; 16aug2011
        prsn @ 2 = IF   \ singular or plural; 16aug2011
          midway @  t @  DO  \ search En-lexicon; 16aug2011
            I       0 en{ @  67 = IF  \ 67=ARE; 16aug2011
              I     7 en{ @  vphraud !  \ engram; 16aug2011
              LEAVE  \ one engram is enough; 16aug2011
            THEN  \ end of test for 67=ARE; 16aug2011
          -1 +LOOP  \ end of loop; 16aug2011
        THEN  \ end of test for second person; 16aug2011
        prsn @ 3 = IF  \ third person; 16aug2011
          midway @  t @  DO  \ search En-lexicon; 16aug2011
            I       0 en{ @  66 = IF  \ 66=IS; 16aug2011
              I     7 en{ @  vphraud !  \ engram; 16aug2011
              LEAVE  \ one engram is enough; 16aug2011
            THEN  \ end of test for 66=IS; 16aug2011
          -1 +LOOP  \ end of loop; 16aug2011
        THEN  \ end of test for third person; 16aug2011
      THEN  \ end of test for singular; 16aug2011
      subjnum @ 2 = IF  \ if plural subject; 16aug2011
        midway @  t @  DO  \ search En-lexicon; 16aug2011
          I       0 en{ @  67 = IF  \ 67=ARE; 16aug2011
            I     7 en{ @  vphraud !  \ engram; 16aug2011
            LEAVE  \ one engram is enough; 16aug2011
          THEN  \ end of test for 67=ARE; 16aug2011
        -1 +LOOP  \ end of loop; 16aug2011
      THEN  \ end of test for plural number; 16aug2011
    THEN  \ end of two-step be-verb substitution; 16aug2011
    motjuste @ 58 = IF  \  12aug2011
      subjpsi @ 50 = IF  \ 50=I; 12aug2011
        midway @  t @  DO  \ search En(glish) array; 21aug2011
          I       0 en{ @  57 = IF  \ 57=AM; 12aug2011
            57 motjuste !  ( Set verbform to "AM" 20sep2010 )
            57 urpsi !  ( parameter for PsiDamp 14aug2011 )
            I     7 en{ @  vphraud ! \ for SpeechAct 12aug2011
            LEAVE  \ finding recent "AM" is enough; 12aug2011
          THEN  \ end of two-step test to say "AM"; 12aug2011
        -1 +LOOP  \ end of backwards loop; 12aug2011
      THEN  \ end of test for "50=I" subject-psi; 12aug2011
      subjpsi @ 56 = IF  ( YOU )          \ 8aug2011
        midway @  t @  DO               \ 8aug2011
          I    0 en{ @  67 = IF    \ 67=ARE 8aug2011
            I  7 en{ @  vphraud !  \ 8aug2011
            LEAVE                     \ 8aug2011
          THEN                        \ 8aug2011
        -1 +LOOP                      \ 8aug2011
      THEN  \ 8aug2011
    THEN  \  end of test for 58=BE; 13aug2011
    motjuste @ 67 = IF  \ 67=ARE; 11aug2011
      subjpsi @ 50 = IF  \ 50=I; 11aug2011
        midway @  t @  DO  \ search En(glish) array; 11aug2011
          I       0 en{ @  57 = IF  \ 57=AM; 11aug2011
            57 motjuste !  ( Set verbform to "AM" 20sep2010 )
            I     7 en{ @  vphraud ! \ for SpeechAct 11aug2011
            LEAVE  \ finding recent "AM" is enough; 11aug2011
          THEN  \ end of two-step test to say "AM"; 11aug2011
        -1 +LOOP  \ end of backwards loop; 11aug2011
      THEN  \ end of test for "50=I" subject-psi; 11aug2011
    THEN  \ end of test for be-verb 67=ARE; 11aug2011
    motjuste @ 58 = IF  \ shift from BE; 27aug2010
      num @ 1 = IF  \ singular; 27aug2010
        prsn @ 1 = IF  \ if first person; 29aug2010
          midway @  t @  DO  \ search backwards in time
            I       0 en{ @  57 = IF \ recent 57=AM; 12sep2010
              I     7 en{ @  aud !  \ get recall-vector
              LEAVE  \ after finding recent "AM"; 29aug2010
            THEN     \ end of test for 67=AM; 29aug2010
          -1 +LOOP \ end of retrieval loop for "AM"; 29aug2010
          0 prsn !  \ reset after use; 29aug2010
        THEN  \ end of test for 1st person sing; 29aug2010
        prsn @ 3 = IF  \ if third person; 12sep2010
          midway @  t @  DO  \ search backwards in time
            I       0 en{ @  66 = IF \ most recent instance
              66 motjuste ! ( 66=IS; 27aug2010 )
              I     7 en{ @  aud !  \ get recall-vector
              LEAVE  \ after finding recent "IS"; 28aug2010
            THEN     \ end of test for 66=IS; 27aug2010
          -1 +LOOP \ end of retrieval loop for "IS"; 27aug2010
        THEN  \ end of test for 3rd person sing; 12sep2010
      THEN  \ end of test for singular; 27aug2010
      ( following code covers undeclared plurals; 27aug2010 )
      num @ 1 = NOT IF  \ other than singular; 27aug2010
        midway @  t @  DO  \ search backwards in time
          I       0 en{ @  67 = IF  \ most recent instance
            67 motjuste ! ( 67=ARE; 27aug2010 )
            I     7 en{ @  aud !  \ get recall-vector
            LEAVE  \ after finding recent "ARE"; 27aug2010
          THEN     \ end of test for 67=ARE; 27aug2010
        -1 +LOOP \ end of retrieval loop for "ARE"; 27aug2010
      THEN  \ end of test for not singular; 27aug2010
    THEN  \ end of test for 58=BE; 27aug2010
    0 subjectflag !  \ for SpreadAct slosh-over; 18oct2010
  \ motjuste @ psi !
    motjuste @ vacpsi !  \ prepare to deglobalize; 27sep2010
    motjuste @ verbpsi !  \ for WhatAuxSVerb; 13jun2011
    VerbAct
    0 vacpsi !  \ reset for safety; 27sep2010
    nphrnum @ 2 = NOT IF  \ if not plural; test; 30aug2010
      1 nphrnum !  \ default to singular; test; 30aug2010
    THEN  \ end of test for plural nphrnum; 30aug2010
    prsn @ 3 = IF  \ 3rd person? 29aug2010
      nphrnum @ 1 = IF  \ test; 30aug2010
      83 inflex1 !  \ xfer to SpeechAct; 30aug2010
      THEN  \ end of test for singular nphrnum; 30aug2010
    THEN  \ end of test for 3rd person; 29aug2010
    vphraud @ aud !  \ transfer just before call; 25jun2011
    SpeechAct  ( main call from VerbPhrase to SpeechAct )
      VerbClear  \ deactivate before inhibiting; 17aug2011
      -48 t @ 1 -  1 psi{ ! \ inhibit new verb-node; 8may2011
      -48 t @      1 psi{ ! \ inhibit new verb-node; 7may2011
      0 inflex1 !  \ test; 30aug2010
      0 vphraud !  \ reset for safety; 25jun2011
      0 vpos !
    motjuste @ unk !  \ use short "unk" to save room; 8ug2011
    unk @ 57 = unk @ 58 = OR unk @ 66 = OR unk @ 67 = OR IF
      notjux @ 12 = IF  \ 12=NOT; OR aftjux? 11aug2011
        midway @  t @  DO   \ Search En(glish) array; 27jul2011
          I       0 en{ @  12 = IF  \ Look for "NOT"; 27jul2011
            I     7 en{ @  aud ! \ Auditory start-tag 27jul2011
            LEAVE   \ One instance of NOT suffices; 27jul2011
          THEN   \ End of lexical test for 12=NOT; 27jul2011
        -1 +LOOP  \ End of loop searching for 12=NOT; 27jul2011
        SpeechAct  \ Say the word "NOT"; 27jul2011
        0 aftjux !  \ reset for safety; 27jul2011
        0 notjux !  \ reset for safety; 12aug2011
        0 prejux !  \ reset for safety; 27jul2011
        0 jux !     \ reset for safety; 27jul2011
        0 psi3 !    \ reset for safety; 27jul2011
      THEN \ end of test for negated be-verb; 27jul2011
    THEN  \ end of test for be-verb; 27jul2011
  THEN  \ end of test for positive motjuste; 29aug2010
  10 act !
  motjuste @  urpsi !
  62 caller !
  PsiDamp  \ Necessary for chain of thought; 24oct2010
  0 caller !
  EnDamp
  \ Following lines inhibit old KB verb-node; 13jun2011
\ -32 tselv @ 1 psi{ ! \ To avoid spurious NOT; 12aug2011
  -64 tselv @ 1 psi{ ! \ Prevent spurious thoughts; 16aug2011
  0 tselv ! \ Reset tselv after use; 13jun2011
  32 EMIT
  1 dirobj !
  motjuste @ 57 = IF 1 predflag ! THEN \ 57=AM; 12sep2010
  NounPhrase
  0 predflag !  \ reset for safety; 12sep2010
  motjuste @ 0 > IF motjuste @ dopsi ! THEN
  0 dirobj !
  0 notjux !  \ Used for negating verbs; 11aug2011
  0 numflag !  \  3dec2009 Whether used here or in BeVerb.
  0 psi3 !  \ reset for safety; 27jul2011
;  ( End of VerbPhrase; return to EnCog )


:  DeCog ( Deutsch Cognition -- thinking in German )
  CR ." Achtung! German input flips thinking into German."
( HauptWort  \ Call a German NounPhrase module; 20jul2011 )
( ZeitWort   \ Call a German VerbPhrase module; 20jul2011 )
;  ( End of DeCog; return to ThInk )


:  EnCog ( English Cognition -- thinking in English )
  0 morphpsi !
  0 psi !
  0 sublen !
  t @ tov !
  yncon @ 1 = IF  \ if flag set in VerbPhrase; 2jul2011
    AskUser  \ for a yes-or-no question; 2jul2011
    EXIT  \ abandon rest of EnCog;  2jul2011
  THEN  \ 2jul2011
  yesorno @ 0 > IF
    SayYes
    CR
    EXIT
  THEN
  0 isflag !   \ 10dec2009 So AI forgets its own "what-is"
  0 areflag !  \ 11dec2009 So AI forgets its own "what-are"
  0 unkflag !  \ 10dec2009 safety measure.
  400 rsvp !   \ Give user time to respond. 23aug2010
  ( exceptional think was above; normal thinking below here )
  CR ." Robot: "
  123  t @  2 aud{ !
  t @ tov !  \ 12jan2010 "{" marks start of thought.
  NounPhrase  \ First of two Chomskyan bifurcations.
  VerbPhrase  \ Second of two Chomskyan bifurcations.
  0 quo !  \ 27dec2009 Reset
  dunnoobject @ 1 = IF  \ 5jan2010 If not yet reset
    qus @ 0 > IF  \ 5jan2010 If query-subject is positive
      qus @ nacpsi !  \ 5jan2010 Prepare for call to NounAct
      48 nounval !  \ 5jan2010 Beef up the activation.
      NounAct  \ 5jan2010 Provide subject for next thought
    THEN  \ 5jan2010 End of test for positive query-subject
  THEN  \ 5jan2010 End of test of dunnoobject
  0 dunnoobject !  \ 5jan2010 No longer an issue.
  0 qus !          \ 5jan2010 Reset after use.
  0 quo !          \ 5jan2010 Reset after use.
  0 quset !        \ 5jan2010
  5 bias !
  0 sknlp !  \ 8jan2010 Reset for use in SelfRef.
  0 qup !   \ 10jan2010 Must be at zero to be used again.
  PsiDecay  \ Reduce activation after each thought; 4aug2011
;  ( End of EnCog )


:  ThInk ( calls EnCog to think in English; 20sep2010 )
  PsiDecay  \ discourage also-rans; 8aug2011
  PsiDecay  \ discourage also-rans; 8aug2011
  0 ordo !
  35 pov !
  glot @ 1 = IF  \ flag for polyglot AI; 20jul2011
    EnCog  ( think in English; 20jul2011 )
  THEN  \ input of German might switch glot to two; 20jul2011
  glot @ 2 = IF  \ upon input of multiple German words;
    DeCog  ( think in Deutsch -- German;  20jul2011 )
  THEN  \ end of test for language-choice in polyglot AI
  fyi @ 1 = IF CR THEN
  0 recon !
  0 ordo !
  rjc @ 1 < IF  \ if AI on but not yet ReJuvenated; 19sep2010
    lurk @ greet @ > IF  \ if limit exceeded; 19sep2010
      100 rsvp !  \ slow down the display; 19sep2010
      -1 lurk ! \ reset for safety; 19sep2010
      kbtv @ 4 > IF  1 kbtv !  THEN  \ test; 19sep2010
    \ 1 kbtv !  \ start the looping cycle; 19sep2010
      1 kbtv +!  \ cycle through values; 19sep2010
      KbTraversal  \ if no input, begin thinking; 19sep2010
    THEN  \ end of test for limit reached; 19sep2010
  THEN  \ end of test of ReJuvenation-count (rjc); 19sep2010
;  ( End of ThInk )


:  MotorOutput ( stub for autonomous control of robots )
   7 EMIT
 ( MOVE_FORWARD   )
 ( MOVE_BACKWARDS )
 ( STOP_MOTION    )
 ( TURN_LEFT      )
 ( TURN_RIGHT     )
;  ( End of MotorOutput stub )


:  TuringTest ( Human-Computer Interaction )
  fyi @ 0 = IF CLS CR CR CR CR CR CR CR
    t @ 439 < IF CR  \ "vault" after "MAYBE"; 21jul2011.
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
;  ( End of TuringTest Human-Computer Interaction )


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
  t   @  1024 > IF
    t @  1024 -  midway !  ( for range limit on searches )
    ELSE
    1   midway !
  THEN
  0 quiet !
;  ( End of SeCurity module )


:  MainLoop  ( changed from ALIFE for wiki doc page )
  TIME&DATE byear ! bmonth ! bday ! bhour ! bminute ! bsec !
  TabulaRasa
  EnBoot
  BEGIN
    SeCurity
    fyi @ 2 = IF CR
    ." MainLoop calls the SensoryInput module." CR
    THEN
    SensoryInput
  ( EmotiOn )
    fyi @ 2 = IF CR
    ." MainLoop calls the ThInk mind-module." CR
    THEN
    ThInk
  ( FreeWill )
  ( MotorOutput )
  AGAIN
;  ( End of MainLoop )


:  ALIFE  ( Call MainLoop if not called by user. )
  MainLoop
; 
```