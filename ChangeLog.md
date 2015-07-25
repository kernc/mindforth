AiEvolution MileStones MindForth TimeLine


### NotaBene ###

This MindForth changelog archive shows the development of the AI
Mind over time. Each entry begins with a version identifier
consisting of the calendar date and a letter of the alphabet
to indicate any multiple versions created on the same date.
Each version ends in ".f" or ".F" for loading into Win32Forth or for changing into ".frt" and loading into 64-bit [iForth](http://store.kagi.com/cgi-bin/store.cgi?storeID=AMP_Live) to run on a 64-bit [Linux](http://cyborg.blogspot.com/2009/11/linux.html) SuperComputer.

Only changes deemed significant at the time were
recorded in the changelog. Individual releases of MindForth may
include a changelog with only recent entries. Any fork or bifurcation
in the development of MindForth may cause the splitting of the
changelog into two divergent channels through time. The German artificial intelligence [Wotan](http://www.scn.org/~mentifex/DeKi.txt) has its own, separate changelog near the start of the Deki.txt AI source code.

### Entries ###

```
\ 25jun01A.f transposes "fin" and "fex" in en{ array for clarity;
\ eliminates HCI pause; adopts JavaScript AI Troubleshoot labels;
\ begins to phase out Tutorial and Troubleshoot in favor of jsaimind.
\ 27jun01A.f eliminates most use of the "spy" variable; makes more
\ Mind.Forth functions similar to the JavaScript Artificial Mind.
\ 25jan02A.f changes ATTACH to enVocab; changes BOOTSTRAP to enBoot;
\ replaces "meme" with "urpsi"; articulates THINK/ ENGLISH/ SVO;
\ reintroduces psiDecay; 
\ 29jan02A.f implements Rejuvenate;
\ 31jan02A.f adopts JavaScript AI Mind way of "spreading activation."
\  4feb02A.f uses "attn" values similar to those in JavaScript AI.
\  5feb02A.f made the AI display more interesting but was buggy.
\  7feb02A.f implements EGO; displays data-transfer of Rejuvenate.
\  8feb02A.f debugs AUDITION timing problems; uses "isolation".
\ 10feb02A.f uses "inert" not "isolation"; fixes .echo display.
\ 11feb02A.f eliminates STRING-EFFECT by inclusion in COMPARATOR.
\ 12feb02A.f fits revised COMPARATOR together with other modules.
\ 14feb02A.f corrects minor errors.
\ 16feb02A.f introduces LTM (Long Term Memory) for bootstrap use.
\ 17feb02A.f begins to rationalize the Comparator module.
\ 18feb02B.f shows improvement in recognizing old concepts.
\ 20feb02A.f prevents THINK mode from calling LISTEN module.
\ 22feb02C.f stabilizes word-recognitions in the COMPARATOR.
\ 24feb02A.f encourages programmers to Web-host AI evolutions.
\ 25feb02A.f removes ACTIVATE bug that impeded pre & seq tags.
\ 25feb02B.f puts higher residual activation on direct objects.
\ 26feb02A.f stubs in MOTORIUM as a challenge for roboticists.
\ 27feb02A.f eliminates RETRO by moving its code into AUDITION.
\  4mar02A.f changes STM to audSTM and COMPARATOR to audRecog.
\ 13mar02A.f removes excess variables from audRecog module.
\ 15apr02A.f uses "pho" instead of "unk" for quasi-phonemes;
\ uses audRecog "LEAVE" to accept first recognition of a word;
\ uses "psi" to replace "f"; "mt"; and "utg" variables;
\ replaces grammar variable "g" with part-of-speech "pos".
\ 21apr02A.f changes "blankt" to space-time "spt";
\ replaces recall-vector "rv" with "aud" for "auditory".
\ 11may02A.f removes "attn" flag in favor of "quiet";
\ streamlines aLife with AI namespace function calls.
\ 23may02A.f renames PREDICATE module as "verbPhrase" module;
\ eliminates SUBJECT module in favor of code in SVO module;
\ changes FLUSHVECTOR to REIFY for ontological reification.
\ 21jul02A.f increases the mindcore Psi array from 6 to 7 columns;
\ uses "jux" variable instead of "mod" reserved word in Win32Forth.
\ 22jul02A.f dismantles the primitive SVO parsing mechanism in favor
\ of an initially primitive but most evolvable Parser module.
\ 23jul02A.f eliminates audLTM by protecting "vault" in audSTM.
\ 24jul02A.f experiments with problems in the Audition module.
\ 25jul02A.f has a new test for terminating the Audition module.
\ 26jul02A.f makes AUDITION serve SENSORIUM and SPEECH equally.
\ 26jul02B.f integrates AUDITION and SPEECH during reentry.
\ 27jul02A.f makes minor corrections in audRecog and elsewhere.
\ 28jul02A.f greatly expands the English bootstrap enBoot.
\ 29jul02A.f introduces auxVerb and negSVO for negative reasoning.
\  3aug02A.f makes minor corrections to previous source code;
\ introduces the asking of questions by the AI about new concepts.
\ 16aug02A.f introduces Conjoin module for selecting conjunctions.
\  9mar05A.f sets tov in ENGLISH so as to clear up .echo bug that
\ was causing the AI Mind to crash after a period of no human input.
\ 11mar05A.f announces, for bragging rights, when the AI came to life.
\ 12mar05A.f lets the user enter TEST or ALIFE to start the AI.
\ 13mar05A.f prevents screen-clearing, for better TEST observations.
\ 14mar05A.f seems to generate an endless stream of thoughts.
\ 14mar05B.f rearranges HCI presentation; uses "anxiety" not "inert".
\ 16mar05A.f offers choice of ALIFE, DIAGNOSTIC or TUTORIAL mode.
\ 28apr05C.f shall be a commented version of the AI source code.
\ 29apr05C.F sets an activation-limit of 63 in spreadAct.
\ 30apr05C.F uses Tab key to cycle among display modalities.
\  1may05C.F removes add-on modules obsoleted by Tab functionality.
\  4may05C.F replaces display-mode flags with fyi variable.
\ 31may05C.F uses terse display to prevent blur of scrolling diagnostics.
\  2jun05C.F combines tutorial messages with diagnostics; asks IQ of AI.
\  3jun05C.F initiates the diagnostic display of AI thought processes.
\  4jun05C.F maximizes diagnostic display by minimizing HCI messages.
\  5jun05C.F shows hidden diagnostic details of spreading activation..
\ 30jun05C.F reapportions constituent activations within limitation range.
\  4jul05C.F lets THINK invoke EGO if ENGLISH does not generate thoughts.
\ 12jul05C.F prevents .echo from spuriously repeating robot output.
\ 15jul05C.F enhances interactive messages in Tab-selectable Tutorial mode.
\ 22jul05C.F prevents the Tab-key from haphazardly instantiating concepts.
\ 23jul05C.F removes unwarranted linkages among concepts from enBoot.
\ 28jul05C.F separates the activation tracks of parsing and NLP generation.
\ 31jul05C.F adds deep diagnostics for debugging spurious SVO associations.
\  2aug05C.F uses variable "spike" to carry bulge of spreading activation.
\  3aug05C.F clears the screen to remove scrolling at start of Rejuvenate.
\  4aug05C.F eliminates "actfan" variable; updates psiDecay module.
\  5aug05C.F clarifies diagnostics; removes unnecessary calls to Activate.
\  6aug05C.F uses psiDamp to prevent the inappropriate asking of questions.
\  7aug05C.F encounters unresolved activations after asking of questions.
\ 21aug05C.F explores calls to psiDecay as a fix of unresolved activations.
\ 23aug05C.F streamlines psiDecay module by removing commented-out code.
\ 26aug05C.F moves toward looping chains of thought for AI normalcy tests.
\ 28aug05C.f introduces psiDamp variable "lump" to enable chains of thought.
\ 29aug05C.F has Think module check for active nouns instead of verbs;
\ switches listing-order of psiDamp and psiDecay so psiDamp calls psiDecay;
\ achieves a looping chain of thought that breaks down after rejuvenations.
\ 30aug05C.F speeds up the thinking of the AI Mind if no input is detected.
\ 31aug05C.F substitutes the question word "what" for low-activation nouns.
\  3sep05C.F enhances Tutorial mode by showing generation of thoughts.
\  5sep05C.F deactivates WHAT; displays spreading activation in Tutorial mode.
\  6sep05C.F uses oldpsi and oldact to show source of spreading activations.
\  9sep05C.F begins fix of spreadAct "zone" that was sending too many spikes.
\ 12sep05C.F moves diagnostics from Tutorial display into Diagnostic display.
\ 13sep05C.F shows pathway of spreading activation in Tutorial display mode.
\ 14sep05C.F restores initiation of chains of thought but has "YES" bug.
\ 17sep05C.F solves the YES bug as a problem of spurious "motjuste" signals.
\ 18sep05C.F has single activations move like a wave through the mindgrid.
\ 21sep05C.F uses psiDamp and psiDecay to make "crest" concepts preponderate.
\ 23sep05C.F uses quiescent intervals in the Moving Wave Algorithm psychonomy.
\ 24sep05C.F makes Tutorial mode more informative, as requested by user base.
\  6oct05C.F again lets whatAuxSDo use psiDecay on unresolved activations;
\ parentheticalizes Comments for only ZIP files having backslash Comments.
\  8oct05C.F lets user inputs cause higher activations than internal thought.
\ 13oct05C.F introduces a Transcript display mode to record AI Mind behavior.
\ 14oct05C.F gives expanded names of mind-modules in parenthesis comments.
\ 15oct05C.F revives a flatline AI by recalling oldest memories and by
\ asking users to enter information for meandering chains of thought.
\ 31oct05C.F reduces risk of word-wrap problems and improves Tutorial mode.
\  9nov05C.F consolidates Tutorial messages horizontally to avoid scrolling.
\ 22jan06C.F starts in Tutorial mode until user presses Tab for other modes.
\ 23jan06C.F engenders an upper tier of conceptual activation for a moving
\ wave of consciousness and thought, and a lower tier of residual activation.
\ 27feb06C.F makes new concepts have an activation at top of lower tier.
\ 20apr06C.F uses decpsi1 and decpsi2 to avoid endless repetition of output.
\ 23may06C.F in transcript mode shows activation-levels of selected words.
\ 25may06C.F enhances transcript mode with date, time and explanation.
\ 29may06C.F maintains thought-chains by removing ACTIVATE call to psiDecay.
\ 31may06C.F uses nPhr activation threshold to prevent spurious associations.
\  1jun06C.F splits calling of Activate between internal POV and external POV.
\  2jun06C.F aims for subconscious lower tier and upper consciousness tier.
\  5jun06C.F splits ACTIVATE mind-module into subAct and superAct modules.
\  7jun06C.F uses nounAct and verbAct for SVO activation slosh-over effect.
\  9jun06C.F indicates potential +slosh-over direct objects in Tutorial mode.
\ 10jun06C.F leaves nounAct, verbAct and ACTIVATE after clean-up of modules.
\ 13jun06C.F enhances slosh-over in a try to eliminate spurious associations.
\ 18jun06C.F overhauls Tutorial for a better display of deep thought process.
\ 29mar07A.F introduces add-on ontology from JavaScript AI for sake of EGO.
\ 30mar07A.F makes verbAct module conform with JavaScript AI Mind algorithm.
\ 31mar07A.F updates nounAct, psiDamp and psiDecay in accordance with JSAI.
\  2apr07A.F corrects problem of associative tags not being assigned.
\  3apr07A.F fixes "pre" and "seq" assignments by replicating JSAI code.
\  4apr07A.F uses a nested BEGIN (flag) UNTIL loop in the Reify module.
\  7apr07A.F cleans up commented-out code and fixes Transcript display bug.
\  9apr07A.F fixes nounAct ACCESS_VIOLATION with help of Jos van de Ven.
\ 27apr07A.F in verbAct augments verb-nodes only up to consciousness tier.
\ 30nov07A.F displays AI thought processes more clearly in Tutorial mode.
\  2dec07A.F makes only cosmetic changes in messages of the Tutorial mode.
\  5dec07B.F solves an aboriginal major audRecog bug of false recognitions.
\ 14dec07A.F increases spreadAct zone of search for "seq" direct objects.
\ 17dec07A.F introduces "detour" as abort-flag for insufficient knowledge.
\ 19dec07A.F flushes out verb-activation-too-high and BIRDS-as-IS bugs.
\ 23dec07B.F solves aboriginal audRecog false-positive recognition bug.
\ 27dec07A.F causes verbPhrase to LEAVE when a detour-condition is met.
\ 28dec07A.F reveals a deeply hidden YES-bug in the SPEECH mind-module.
\  1jan08A.F fixes SPEECH YES-bug by isolating fetch of auditory engrams.
\  3jan08A.F asks a question if the "detour" flag is set to true.
\  4jan08A.F explores the role of activational "actset" settings.
\  6jan08A.F prevents spurious detours by raising psiDamp "residuum".
\  7jan08A.F is a general clean-up of commented-out "junk DNA" code.
\  9jan08A.F fixes audRecog bug of failure to recognize two-char words.
\ 10jan08A.F uses "psicrest" and "trough" for Moving Wave Algorithm (MWA).
\ 11jan08A.F prevents rejected verbs from spreading spurious activation.
\ 12jan08B.F troubleshoots why post-thought activations are too high.
\ 13jan08A.F introduces code to deactivate known words at MWA crest.
\ 13jan08B.F uses AI4U page numbers to identify modules calling psiDamp.
\ 14jan08A.F uses "lopsi" and "hipsi" for only one wave crest at a time.
\ 14jan08B.F comments out diagnostic messages of Moving Wave Algorithm.
\ 15jan08A.F lets Audition psi-damp only at the start of a reentrant word.
\ 16jan08A.F eliminates a one-word delay in the psi-damping of input words.
\ 18jan08B.F solves too-many-questions bug by simplifying the REIFY module.
\ 20jan08A.F fixes topic-jumping bug and attains cognitive chain reaction.
\ 20jan08B.F leaves in but comments out diagnostics for further debugging.
\ 22jan08A.F tightens up activation-settings to prevent spurious thoughts.
\ 22jan08B.F calls EGO resuscitation upon detection of repetitious thought.
\ 24jan08A.F changes verbClear into verbClip to merely reduce activations.
\ 27jan08A.F uses "EEG" and "redux" to revive oldest concept during lull.
\ 29jan08A.F comments out "actset" because Moving Wave sets one activation.
\ 30jan08A.F removes "trough"; comments out "uract"; fixes verbClip module.
\  1feb08A.F removes "actset" and "uract"; improves activation settings.
\ 24aug08A.F adds a "num" (number) flag to the flag-panel of the psi array.
\ 25aug08A.F tests new Article module by inserting "the" before all nouns.
\ 27aug08A.F adds "num" to English array with value-transfer in Reify.
\ 29aug08A.F avoids SVO in preparation for thinking with verbs of being.
\ 30aug08A.F inaugurates practice of stating entelechy goals for modules.
\ 31aug08A.F uses psiDecay to keep verbs of being at a default activation.
\  1sep08A.F converts whatAuxSDo into whatIs to initiate verbs of being.
\  2sep08A.F reintroduces Conjoin module from 16aug02A.F source code.
\  3sep08A.F introduces knowledge-base traversal module kbTraversal.
\ 12sep08A.F solves "pov" bug of "YOU" input not activating "I" concept.
\ 17sep08A.F uses kbSearch and Affirmative to answer YES to DO-queries.
\ 25sep08A.F introduces beVerb module to think with intransitive verbs.
\ 27sep08A.F has nounPhrase switch from "I" to "ME" for direct objects.
\ 30sep08A.F has audRecog detect noun-stems close to end of plurals.
\  1oct08A.F asks "what is" or "what are" after input of unknown words.
\  4oct08A.F intervenes in beVerb to choose correct form of "to be".
\ 14oct08A.F begins the renaming of modules as links to wiki-page docs.
\ 15oct08A.F eliminates SVO module; changes Predicate to VerbPhrase.
\ 16oct08A.F renames Activate ReActivate; Listen AudListen; audSTM AudMem.
\ 18oct08A.F minor changes, including durable comments in parentheses.
\ 20apr09A.F updates Normal display; installs JSAI who-are-you code.
\ 23apr09A.F answers "who are you" with "I AM..." statements.
\  6may09A.F begins de-globalizing variables with audpsi and audrec.
\  7may09A.F uses non-global "presyn" and "seqsyn" in SpreadAct.
\  8may09A.F lets InStantiate declare only a noun or pronoun as "pre".
\  9may09A.F de-globalizes the OldConcept module with "oldpsi".
\ 10may09A.F restores KbTraversal, who-are-you and stem-recognition.
\ 16may09A.F changes EnBoot to regard all words as ending with a space.
\ 17may09A.F fails to get auditory memory working right with ASCII 32.
\ 17may09B.F reverts to 15may09B.F cleaned-up code with old EnBoot.
\ 19may09A.F upon entry of article "a" sets next noun to singular.
\ 20may09A.F adds "S" to an English verb in third-person singular.
\ 23may09A.F reformats the EnBoot sequence to fit within 60 characters.
\ 24may09A.F prevents "S" from accumulating on verbs; uses 60 char width.

\  7dec09A.F SelfRef answers "I DO NOT KNOW" if warranted.
\ 10dec09A.F answers "dunno" if verb-activation is too low.
\ 11dec09A.F can answer what-is or what-are with NOT-KNOW.
\ 12dec09A.F increases SpreadAct "zone" search space.
\ 13dec09A.F answers what-do with NOT-KNOW if warranted.
\ 16dec09A.F fixes bug revealed in 32/64-bit iForth coding.
\ 18dec09A.F comments out obsolete variables pre-deletion.
\ 20dec09A.F abandons generation in favor of comprehension.
\ 22dec09A.F zeroes noun-activations for what-do questions.
\ 22dec09B.F answers "what-do" tersely or "I DO NOT KNOW".
\ 23dec09A.F restores EnCog English cognition mind-module.
\ 24dec09A.F answers questions of the "what-do-X-do" form.
\ 25dec09A.F fails to advance and is therefore abandoned.
\ 27dec09A.F introduces qus quv quo to track query-words.
\ 27dec09B.F responds with subject + verb + query-object.
\ 28dec09A.F answers what-do-X-do with diagnostic messages.
\ 29dec09A.F improves upon "What-do-X-do?" responses.
\ 30dec09A.F introduces EnPronoun English pronoun module.
\  1jan10A.F solves post-query-thought SelfRef nacpsi bug.
\  1jan10B.F removes diagnostic messages needed in bugfix.
\  2jan10A.F uses "quset" flag to isolate EnCog module.
\  4jan10A.F uses new query flags for sake of EnCog.
\  4jan10B.F isolates EnCog from OldConcept comprehension.
\  5jan10A.F guts heart of EnCog and builds back up again.
\  5jan10B.F removes diagnostic messages from bugfix code.
\  6jan10A.F builds back up "what-do-X-do?" code in EnCog.
\  7jan10A.F merges what-do-X-do and what-do-X-verb code.
\  8jan10A.F avoids generation of non-reply query thought.
\  8jan10B.F removes diagnostic messages prior to upload.
\ 11jan10A.F troubleshoots query-variables used for EnCog.
\ 12jan10A.F fixes bug in .echo to prevent infinite loops.
\ 12jan10B.F deactivates "do" during what-do-X-do queries.
\ 13jan10A.F answers what-do-X-do? with OldConcept search.
\ 13jan10B.F removes diagnostic messages after debugging.
\ 15jan10A.F solves InStantiate "seq" mis-assignment bug.
\ 16jan10A.F removes diagnostic messages used for bugfix.
\ 18jan10A.F introduces SubjectClear for query responses.
\ 20jan10A.F removes diagnostics prior to upload of code.
\ 21jan10A.F blanks MindGrid for "what-do-X-do?" queries.
\ 22jan10A.F alternates faster and slow speed of thought.
\ 31jan10A.F expands English array with "mfn" gender tag.
\ 10apr10A.F calls EnPronoun from EnCog to use HE SHE IT.
\ 20apr10A.F adds twelve new concepts to EnBoot sequence.
\  8may10A.F fixes a major bug always hidden in AudRecog.
\ 10may10A.F general clean-up; KbTraversal activates GOD.
\ 23jul10A.F omits EnArticle before name after who-query.
\ 24jul10A.F adds "YOU ARE YOURSELF" to EnBoot sequence.
\ 25jul10A.F introduces WhoPlex as a quasi-mind-module.
\ 26jul10A.F removes test-comments prior to Web upload.
\ 27jul10A.F makes "IS" a default verb of being in BeVerb.
\ 30jul10A.F merges incoming AM IS ARE with "fin" #58=BE.
\  7aug10A.F introduces WhoBe for asking who-queries.
\ 10aug10A.F coordinates WhoBe with BeVerb and AskUser.
\ 11aug10A.F in NounAct de-activates 55=WHO after queries.
\ 17aug10A.F calls WhoBe if noun has male or fem. gender.
\ 19aug10A.F makes knowledge-base responses to who-queries.
\ 20aug10A.F skips A, THE between associative psi concepts.
\ 23aug10A.F calls AskUser, WhatIs, WhoBe more correctly.
\ 24aug10A.F enhances query-responses made by EnCog.
\ 25aug10A.F retrieves knowledge gained from human users.
\ 27aug10A.F modifies VerbPhrase to correct be-verb forms.
\ 28aug10A.F introduces "prsn" for 1st, 2nd and 3rd person.
\ 29aug10A.F uses "prsn" to govern inflectional "S" ending.
\ 30aug10A.F lets VerbPhrase govern SpeechAct inflections.
\ 31aug10A.F has subject-verb agreement in person & number.
\  1sep10A.F uses "prsn" variable to improve WhoBe module.
\  5sep10A.F codes quasi-neuronal inhibition into the AI.
\  9sep10A.F causes verb-node inhibition to dwindle down.
\ 11sep10A.F fixes VerbPhrase bugs impeding self-knowledge.
\ 12sep10A.F inhibits old KB and new predicate nominatives.
\ 13sep10A.F tightens up on BeVerb control of verb forms.
\ 14sep10A.F blocks inhibition to focus on what-queries.
\ 17sep10A.F re-organizes EnBoot sequence for inhibitions.
\ 19sep10A.F uses KbTraversal to greet users with no input.
\ 20sep10A.F achieves KB-exhaustive responses to questions.
\ 21sep10A.F uses inhibition instead of whatflag settings.
\ 24sep10A.F clamps down on stray activation in NounPhrase.
\ 26sep10A.F answers "what are you" or "what am i" from KB.
\ 27sep10A.F provides comprehensive overview of activation.
\ 28sep10A.F removes distortions from spreading activation.
\ 28sep10C.F uses threshold-test to reject inactive nouns.
\  3oct10B.F uses "qusub" for provisional query-subjects.
\  6oct10A.F adjusts settings to reduce stray activations.
\  8oct10A.F fixes deglobalization bug in VerbAct module.
\  9oct10A.F improves upon be-verb KB responses to queries.
\ 10oct10A.F revisits Subject-Verb slosh-over onto objects.
\ 12oct10A.F interim release of 10oct10A minus diagnostics.
\ 13oct10A.F disallows calls from ReActivate to SpreadAct.
\ 13oct10B.F is 13oct10A.F cleaned up for release to Web.
\ 14oct10A.F uses subject-verb slosh-over to direct object.
\ 14oct10B.F is 14oct10A.F cleaned up for release to Web.
\ 17oct10A.F uses JSAI techniques to enhance slosh-over.
\ 18oct10A.F shows verb-object slosh-over in Tutorial mode.
\ 22oct10A.F begins to reconcile inhibition and slosh-over.
\ 24oct10A.F is 22oct10A.F with diagnostics commented out.
\  2nov10A.F in VerbAct narrows gap between "spike" values.
\  3nov10A.F is 2nov10A.F with diagnostics commented out.
\  5nov10A.F psi-damps also-ran candidates in NounPhrase.
\  6nov10A.F is 5nov10A.F with diagnostics commented out.
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
\ 10aug11A.F is before removal of diagnostics messages.
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
\ 19aug11A.F adds irregular noun plurals to EnBoot sequence.
\ 20aug11A.F prevents disruptive activation of query concepts.
\ 21aug11A.F improves NounPhrase defaulting to "I" concept.
\ 24aug11A.F eliminates BeVerb and SubjectClear mind-modules.
\ 25aug11A.F improves operation of AskUser module defaults.
\ 27aug11A.F uses query-moot and seq-check for AI thinking.
\ 28aug11A.F is a test of locking verbs with their objects.
\ 29aug11A.F stops ReActivate interfering with inhibition.
\  1sep11A.F includes Web links for crowd-sourcing the AI.
\  3sep11A.F makes NounAct pass over inhibited concepts.
\  7sep11A.F prepares for disparate "proxcon" reactivation.
\  8sep11A.F removes subj-verb and verb-obj locks to debug.
\  9sep11A.F implements disparate reactivation of prox-psi.
\ 11sep11A.F solves double-subject bug in NounPhrase module.
\ 12sep11A.F introduces idea of "AN" as "A" plus "flex1".
\ 13sep11A.F enhances EnArticle for multiple "indefartcon".
\ 14sep11A.F after IF THEN comments-in major Forth URL links.
\ 16sep11A.F treats 0 and 1 as singular grammatical num(ber).
\ 18sep11A.F reinstates NounPhrase code to seek "audjuste".
\ 19sep11A.F makes predicate nominative agree with "subjnum".
\ 22sep11A.F after "I SEE" calls VisRecog coding challenge.
\ 28sep11A.F introduces "tqv" for locking in "seq" concepts.
\ 29sep11A.F uses "tqv" to ensure verb-direct-object lock.
\ 30sep11A.F introduces "seqpos" to track seq part-of-speech.
\  1oct11A.F uses "seqpos" to skip articles to set tqv-point.
\  1oct11B.F from verb skips intervening words to assign seq.
\  2oct11A.F finds even remote "seq" for nouns and for verbs.
\  3oct11A.F uses InNativate against corruption during EnBoot.
\  5oct11A.F replaces "skipseq" mechanism with "seqneed" code.
\  6oct11A.F lets NounPhrase select subjects after seq-check.
\  6oct11B.F streamlines subject-selection inside NounPhrase.
\  6oct11C.F comprehends and remembers input of negated verbs.
\  7oct11A.F after subject reliably picks knowledge-base verb.
\  8oct11A.F uses verblock and nounlock to retrieve KB info.
\  9oct11A.F debugs verblock to pass activation threshold-test.
\  9oct11B.F activates specific engrams of default ego-concept.
\ 10oct11A.F improves WhatBe for asking a question by default.
\ 11oct11A.F assures correct num(ber) influence on EnArticle.
\ 12oct11A.F inserts "tqv" into Psi flag-panel before "seq".
\ 14oct11A.F corrects faulty num(ber) storage in En{ array.
\ 15oct11A.F improves upon thinking by the default ego "I".
\ 16oct11A.F in ThInk rotates through KbTraversal questions.
\ 17oct11A.F uses "cogpsi" to ask questions about new nouns.
\ 19oct11A.F preemptively follows "nounlock" in NounPhrase.
\ 20oct11A.F preemptively follows "verblock" in VerbPhrase.
\ 21oct11A.F fixes minor parameter problems in the AI-Complete.
\ 22oct11A.F uses "cognum" to select "IS" or "ARE" in WhatBe.
\ 23oct11A.F fixes spurious subject-selection in NounPhrase.
\ 24oct11A.F turns "moot" on and off in WhatBe and WhoBe.
\ 25oct11A.F latches onto "12=NOT" during verblock override.
\  4nov11A.F uses 0 and 1 as singular to control use of "A".
\ 10nov11A.F implements special handling of irregular nouns.
\ 28jun12A.F adds extra activation to verbs in InStantiate.
\ 29jun12A.F implements Mind as a natural-language IdeaPlex.
\  1jul12A.F uses "tsn" variable to solve "seqneed" problem.
\  4jul12A.F corrects fundamental flaw in the EnBoot module.
\ 17jul12A.F introduces "scn" and "pcn" num(ber) variables.
\ 20jul12A.F debugs the function of the WhatBe mind-module.
\ 22jul12A.F debugs the function of the WhoBe mind-module
\ 26jul12A.F prevents ascribing of robot output to humans.
\ 27jul12A.F after verb attaches "seq" of a direct object.
\ 29jul12A.F prevents unwarranted "S" as ending of verbs.
\  1aug12A.F handles "tqv" in InStantiate, WhatBe, WhoBe.
\  3aug12A.F doubles "cns" to 2048 for response to queries.
\ 10aug12A.F uses retroactive SpreadAct for query-response.
\ 11aug12A.F corrects SeCurity problem affecting "midway".
\ 12aug12A.F removes obsolete comments in many AI modules.
\ 13aug12A.F isolates value of "cns" so users may change it.
\ 14aug12A.F performs mutatis mutandis of "tqv" in ReJuvenate.
\ 15aug12A.F in NounPhrase forces proper "nounlock" pronouns.
\ 16aug12A.F cleans up code for NounPhrase pronoun overrides.
\  8nov12A.F renumbers EnBoot sequence as with JavaScript AI.
\ 10nov12A.F replaces two-digit concept numbers with 3-digit.
\ 10nov12B.F comments out old 2-digits in favor of 3-digits.
\ 11nov12A.F uses parameters to find nominative form of "I".
\ 12nov12A.F moves input words through AudBuffer and OutBuffer.
\ 15nov12A.F stubs in the VerbGen module for generating verbs.
\ 20dec12A.F introduces InFerence module for machine reasoning.
\ 21dec12A.F troubleshoots InFerence with diagnostic messages.
\ 22dec12A.F finds alternate auditory engrams for inferences.
\ 25dec12A.F achieves inferences about new input not held in KB.
\ 27dec12A.F feeds inference into AskUser for a yes-or-no query.
\ 28dec12A.F displays internal mental time and ReJuvenate count.
\ 29dec12A.F asks user to confirm or deny inference; adjusts KB.
```


### CyberSpace ###

http://aimind-i.com

http://en.wikipedia.org/wiki/Changelog

http://en.wikipedia.org/wiki/Internet_Archive

http://www.amazon.com/The-Art-Meme-ebook/dp/B007ZI66FS

http://www.scn.org/~mentifex/DeKi.txt

http://www.scn.org/~mentifex/Dushka.html

http://www.scn.org/~mentifex/mindforth.txt


### MemeSpace ###

AdminisTrivia AiEvolution AiTree AskUser CodeBase CodeComplete DeBug DeFault EnTelEchy FreeWare InFerence KbRetro MainLoop MfPj MileStones MindForth MindGrid MindModule MindRexx OldestLivingAiMind OpenSource  ParaMeter PortingOfCode RoadMap TextBook TimeLine ToDo TwItter UseNet UserManual


### AI For You ###

Click to run

[![](http://farm1.static.flickr.com/51/179758367_f283f0d6e0_s.jpg)](http://www.scn.org/~mentifex/AiMind.html)

AI For You