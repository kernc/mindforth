
```
<html lang="ru">
<head>
<title>Dushka - Russian JavaScript artificial intelligence for MSIE</title>
<meta http-equiv="content-type" content="text/html; charset=windows-1251" />
<meta name="description"
 content="Russian-language artificial intelligence in JavaScript" />
<meta name="keywords" 
 content="AI, Cyrillic, Dushka, artificial intelligence, Mentifex" />
<script language="JavaScript"> 
var abc = "";  // AudBuffer() transfer character; 4jan2012
var abort = false;
var act = 0;
var actbase = 0;
var actran = 0;  // psi-decay holder of also-ran act-levels; 14may2011
var anset = 0;  // Set "an" before a vowel at start of noun.
var apb = "";
var artnum = 0;  // article num(ber) as parameter for EnArticle; 6nov2011
var associand = "";
var aud = 0; // 5apr2010
var aud0 = "";
var audbase = 0;  // recall-vectory for VerbGen(); 18jan2012
var auddata = ("<b>" + "Auditory memory nodes" + "<\/b>" + "<BR>");
auddata += ("krt pho act pov beg ctu audpsi");  // 8dec2009
var audjuste = 0;
var audme = 0;
var audpsi = 0; // 6dec2009 de-globalizing the "psi" variable 
var audrec = 0; // 8dec2009 Replaces "psi" in AudRecog module.
var audrun = 0; // Counter of loops through AudRecog(); 7jul2010 
var audstop = 0; // Flag to stop SpeechAct after one word; 7jul2010
var b01 = "";  // for OutBuffer();  4jan2012
var b02 = "";  // for OutBuffer();  4jan2012
var b03 = "";  // for OutBuffer();  4jan2012
var b04 = "";  // for OutBuffer();  4jan2012
var b05 = "";  // for OutBuffer();  4jan2012
var b06 = "";  // for OutBuffer();  4jan2012
var b07 = "";  // for OutBuffer();  4jan2012
var b08 = "";  // for OutBuffer();  4jan2012
var b09 = "";  // for OutBuffer();  4jan2012
var b10 = "";  // for OutBuffer();  4jan2012
var b11 = "";  // for OutBuffer();  4jan2012
var b12 = "";  // for OutBuffer();  4jan2012
var b13 = "";  // for OutBuffer();  4jan2012
var b14 = "";  // for OutBuffer();  4jan2012
var b15 = "";  // for OutBuffer();  4jan2012
var b16 = "";  // for OutBuffer(); 12jan2012
var beact = 0;  // for discrimination during BeVerb; 13aug2010
var beg = 0;
var bias = 5;
var binc = 0;  // "b" increment for AudBuffer; 19jan2012
var brain = true;
var brevity = 0;
var btw = "Rejuvenating...";
var c = "";
var c01 = "";  // for AudBuffer();  4jan2012
var c02 = "";  // for AudBuffer();  4jan2012
var c03 = "";  // for AudBuffer();  4jan2012
var c04 = "";  // for AudBuffer();  4jan2012
var c05 = "";  // for AudBuffer();  4jan2012
var c06 = "";  // for AudBuffer();  4jan2012
var c07 = "";  // for AudBuffer();  4jan2012
var c08 = "";  // for AudBuffer();  4jan2012
var c09 = "";  // for AudBuffer();  4jan2012
var c10 = "";  // for AudBuffer();  4jan2012
var c11 = "";  // for AudBuffer();  4jan2012
var c12 = "";  // for AudBuffer();  4jan2012
var c13 = "";  // for AudBuffer();  4jan2012
var c14 = "";  // for AudBuffer();  4jan2012
var c15 = "";  // for AudBuffer();  4jan2012
var c16 = "";  // for AudBuffer();  4jan2012
var caller = "none";
var casus = "0";
var city = 0;
var cns = 768;  // prevent bog-down; 15oct2010
var coda = 128;
var cognum = 0;  // grammatical number of cogpsi; 27oct2011
var cogpsi = 0;  // new noun being learned; 18oct2011
var cogpsinum = 0;  // non-volatile for WhatBe; 18oct2011
var conj = 0;
var ctu = 1;
var cyct = 0;
var danger = true;
var dba = 0;  // case for nouns; person for verbs;  4jan2012
var defact = 0;  // default activation for NounPhrase; 25oct2011
var defartcon = 0;  // definite article condition; 19apr2011
var defcon = 0;  // for KbTraversal to override NounAct; 17nov2010
var detour = 0;
var dialog = "";
var dirobj = 0;
var dob = new Date();
var edge = 0;
var endata = ("<b>" + "English lexical fibers" + "<\/b>" + "<BR>");
endata += ("krt nen act num mfn dba fex pos fin aud"); // 4jan2012
var engram = "";
var enx = 0;
var en0 = 0; // "nen" for "n(umber)" in "En(glish)"; 4apr2010
var en1 = 0; // "act(ivation)" level; 4apr2010
var en2 = 0; // "num(ber)" since 12apr09B.html; 4apr2010
var en3 = 0; // "mfn" being introduced as gender flag; 4apr2010
var en4 = 0; // "dba" being intorduced as case or person; 4jan2012
var en5 = 0; // "fex" fiber-out from Psi array; 4apr2010; 4jan2012
var en6 = 0; // "pos" part-of-speech flag; 4apr2010; 4jan2012
var en7 = 0; // "fin" fiber-in to Psi array; 4apr2010; 4jan2012
var en8 = 0; // "aud" recall-vector onset-tag; 4apr2010; 4jan2012
var eot = 0;
var equity = 0;
var fex = 0;
var fin = 0;
var firstword = 0;  // for identifying input of a query; 22aug2011
var flex1 = "";  // first inflection phoneme; 14sep2011
var flex2 = "";  // second inflection phoneme; 14sep2011
var flex3 = "";  // third inflection phoneme; 14sep2011
var freedom = true;
var fyi = 0;
var gencon = 0;  // status-con flag when calling VerbGen; 19jan2012
var ghost = 0;
var glot = 1;  // flag for which language to think in; 9jul2011
// var greet = 10;  // greeting-trigger; 17nov2010
var greet = 5;  // for speedier testing; 29oct2011
var hardcopy = false;
var holdaud = 0;
var html = "";
var i = 0;
var img = "xoxoxoxox";
var inbuffer = "";
var indefartcon = 0;  // indefinite article condition; 19apr2011
var indefmust = 0;  // force saying of "A" or "AN"; 23oct2011
// var inert = 0;
// var inert = 1;  // Until user presses a key; 20jul2011
var inert = 0;  // for quick asking of a cogpsi question; 23oct2011
var inhibcon = 0;  // flag for inhibition in InStantiate; 27oct2011
var instnum = 0;  // instantiation number for immediate or delayed use )
var j = 0;
var jrt = 0;
var jux = 0;
var kbcon = 0;  // flag for awaiting a yes-or-no answer; 29jun2011
var kbtv = 0;  // for use in KbTraversal; 13aug2010
var kbyn = 0;  // holds kbtv values for asking Y/N 30jun2011
var krt = 0;
var lastpho = 0; // to avoid extra "S" on verbs; 2sep2010
var lastword = false;
var len = 0;
var lexact = 0;
var life = true;
var lurk = 0;  // counter to activate initial thinking; 29sep2010
var maxbeact = 0; // to prevent BeVerb from calling AskUser; 16sep2010
var mfn = 0;  // 2apr2010 for En(glish) gender flag.
var mfnflag = 0;  // gender flag to cause a who-query; 3aug2011
var midway = 0;  // 22aug2011
var monopsi = 0;
var moot = 0;  // flag to prevent associations in DO-queries; 22aug2011
var morphpsi = 0;
var motjuste = "";
var muse = 1;
var nacpsi = 0;  // de-globalized psi for NounAct; 13aug2010
var negjux = 0;  // flag for 12=NOT juxtaposed to a verb; 13oct2011
var nen = 0;
var nlt = 5;
var node = 0;
// var nonce = 1;
var nonce = 476;  // = vault; to speed up Diagnostics; 11jan2012
var nounaud = 0;
var nouncall = 0;  // Try not to show articles as subjects; 21may2011
var nounduck = 0;
var nounlock = 0;  // for a verb to lock onto a seq-noun; 13oct2011
var nounval = 0;
var nphrnum = 0;
var nphrpos = 0;  // for testing in EnCog; 13aug2010
var nru = 0;  // Number of Russian concept; 18dec2011; 5jan2012
var num = 0;
var numflag = 0;  // for EnArticle() 1oct2010
var numsubj = 0;  // for number of subject; 14jun2011
var objold = 0; // a test for optimizing slosh-over; 18oct2010
var obstat = 0;
var oldact = 0;
var oldpos = 0;
var oldpsi = 0;
var onset = 0;
var ordo = 0;
var origin = "";
var output = "&#1055;&#1056;&#1048;&#1042;&#1045;&#1058;  "  // "Greeting"
// var output = ""; // commenting out on 5jan2012
var pho = "";
var phodex = 0;  // pho-index for AudBuffer(); 4jan2012
var pos = 0;
var posflag = 0;  // AskUser discriminand; 13aug2010
var pov = "#";
var pre = 0;
var precand = 0;
var predflag = 0;  // indicates predicate nominative; 16sep2010
var prejux = 0;  // previous jux to carry NOT to verb; 24jul2011
var prepsi = 0;  // for deglobalizing "pre" in SpreadAct(); 16sep2010
var preset = 0;
var presubj = 0;
var preverb = 0;
var preview = "";
var prevtag = 0;
var provrec = 0;  // provisional recognition in AudRecog; 15jan2012
var prox1 = 0;  // first proximate concept of input cluster; 14sep2011
var prox2 = 0;  // for determining association among engrams; 14sep2011
var prox3 = 0;  // for disparate reactivation in ReActivate; 14sep2011
var proxcon = 0;  // flag to indicate usage of prox variables; 14sep2011
var prsn = 0;  // 1st, 2nd, 3rd person; 2sep2010
var psi = 0;
var psi0 = 0;
var psi1 = 0;
var psi8 = 0;
var psibase = 0;
var psidata = ("<b>" + "Psi mindcore concepts" + "<\/b>" + "<BR>");
psidata += ("krt psi act num jux pre pos tqv seq rux"); // 21jan2012
var putnum = 0;  // putative num(ber) for subj-verb agreement; 24oct2011
var questype = 0;
var quiet = true;
var quobj = 0;  // query-object for yes-or-no questions; 22jun2011
var qus = 0;  // provisional query-subject in advance of queries
var qusub = 0; // query subject in more readable code; 2oct2010
var qusubnum = 0;  // num(ber) of query-subject; 27oct2011
var quverb = 0;  // query-verb for yes-or-no questions; 22jun2011
var recnum = 0;  // recognized number of a recognized word 20jul2011
var recogcon = false;  // for AudInput to passim-ize audpsi; 15jan2012
var recon = 0;
var residuum = 0;
var rjc = 0;
var rsvp = 1000;
var rudata = ("<b>" + "Russian lexical fibers" + "<\/b>" + "<BR>");
// rudata += ("krt nru act num mfn fex pos fin aud"); // 2jan2012
rudata += ("krt nru act num mfn dba fex pos fin aud"); // 17jan2012
var rux = 0;  // transfer from deep concept to Russian lexicon; 22dec2011
var ru0 = 0; // "nru" for "n(umber)" in Russian; 5jan20121
var ru1 = 0; // "act(ivation)" level; 5apr2012
var ru2 = 0; // "num(ber)" 5jan2012
var ru3 = 0; // "mfn" male-female-neuter gender flag; 5jan2012
var ru4 = 0; // "dba" being introduced as case or person; 4jan2012
var ru5 = 0; // "fex" fiber-out from Psi array; 5jan2012
var ru6 = 0; // "pos" part-of-speech flag; 5jan2012
var ru7 = 0; // "fin" fiber-in to Psi array; 5jan2012
var ru8 = 0; // "aud" recall-vector onset-tag; 5jan2012
var seq = 0;
var seq5aud = 0;  // being replaced by "seq7aud"; 13oct2011
var seq7aud = 0;  // auditory engram for psi7 "seq"; 13oct2011
var seq7enx = 0;  // SpreadAct(): for enLexicon search; 13oct2011
var seqneed = 0;  // noun/pronoun or verb needed as a "seq"; 4oct2011
var seqpos = 0;  // "seq" concept part-of-sppeech; 4oct2011
var seqpsi = 0;  // for deglobalizing "seq" in SpreadAct(); 16sep2010
var seqverb = "";
var singflag = 0;  // singularity flag for singular nouns; 4nov2011
var skip = 0;
var sloshmark = "+"; // more like MindForth; 30may2011
var spike = 0;
var spt = 0;
var star = 0;  // For tutorial slosh-over showSubject() display.
var stemgap = 0;
var subjcall = 0;  // To avoid showSubject() of articles; 21may2011
var subjectflag = 0;  // 9dec2009 For NounPhrase to call SelfRef.
var subjnum = 0;  // for agreement with predicate nominative; 18may2011
var subjold = 0;  // old subject as default candidate 29sep2010
var subjpsi = 0;
var sublen = 0;
var subpsi = 0;
var svo3 = 0;  // for VisRecog; 25sep2011
var svo5aud = 0;
var svoyes = false;
var t = 0;
var tag0 = 0;
var tag1 = 0;
var tag2 = 0;
var tag3 = 0;
var tag4 = 0;
var tag5 = 0;
var tag6 = 0;
var tag7 = 0;
var tag8 = 0;  // For safekeeping values in SpreadAct(); 13oct2011
var tbev = 0;  // time of be-verb for use with notjux; 15aug2011
var the1 = 0;
var the2 = 0;
var the3 = 0;
var the4 = 0;
var the5 = 0;
var the6 = 0;
var the7 = 0;
var tkbn = 0;  // time of retroactive KB noun adjustment; 28jun2011
var tkbv = 0;  // time of retroactive KB verb adjustment; 28jun2011
var tobject = "";
var topic = "";
var topicnum = 0;  // grammatical number of question "topic"; 18oct2011
var tov = 1;
var tqv = 0;  // tempus quod vide for specific psi instance; 4oct2011
var trouble = false;
var tseln = 0;  // NounPhrase: time of selection of noun; 10may2011
var tsels = 0;  // 25oct2011
var tselv = 0;  // VerbPhrase: time of selection of Verb; 10may2011
var tsubject = "";  // showSubject(): For "tutorial subjects".
var tult = 0;
var tutor = false;
var tverb = "";
var ufo = 0;
var unk = "";
var upnext = 0;
var urpre = 0;  // original pre for swapping during function-calls.
var urpsi = 0;
var userline = "";
var vacpsi = 0;  // de-globalized psi for VerbAct(); 1oct2010
var vault = 476; // size (time at end) of RuBoot; 10jan2012
var verblock = 0;  // for subject-noun to lock onto seq-verb; 13oct2011
var verbnum = 0;
var verbpsi = 0;  // for transit into WhatAuxSVerb() 14jun2011
var verbval = 0;
var verbcall = 0;
var vphract = 0;  // verb phrase activation level 22jun2011
var vphraud = 0;  // holds aud-fetch for SpeechAct; 28jun2011
var vrsn = "21jan12"; // for Transcript mode; 21jan2012
var vpos = 0;
var wxdflag = 0;  // for inhibition of what-do-X-DO queries; 16sep2010
var wxvflag = 0;  // for inhibition of what-do-X-VERB queries; 16sep2010
var whoskip = 0;
var xthe = 0;
var yncon = 0;  // a statuscon to trigger yes-or-no query; 27jun2011
var ynverb = 0;  // yes-or-no verb for AskUser; 29jun2011
var zone = 0;
 
// defaultStatus="Click on View...Source to save Dushka.html"
 
Psi = new Array(cns);
for (i = 0; i < cns; i++) {
  Psi[i] = new psiNode(" "," "," "," "," "," "," "," "," "); // 13oct2011
}

ruLexicon = new Array(cns);  // 2jan2012
for (i = 0; i < cns; i++) {  // adding extra " " for "dba"; 2jan2012
  ruLexicon[i] = new ruNode(" "," "," "," "," "," "," "," "," ");
}  // 2jan2012


audMemory = new Array(cns);
for (i = 0; i < cns; i++) {
  audMemory[i] = new audNode(" ",0," "," "," "," ");
}
 
function Tutorial() {
  if (document.all["cb2"].checked == true) {
    document.all["cb1"].checked = false;
    document.all.souvenir.innerHTML = "";
    hardcopy = false;
    document.all["cb3"].checked = false;
    document.all.tabula.innerHTML = "";
    document.all.psicolumn.innerHTML = "";
    document.all.rucolumn.innerHTML = ""; // 5jan2012
    document.all.audcolumn.innerHTML = "";
    trouble = false;
    tutor = true;
    fyi = 2;
  }
  if (document.all["cb2"].checked == false) {
    fyi = 0;
    tutor = false;
  }
  document.forms[1].ear.focus();
}
 
 
function NounClear() {
  for (i = t; i>0; --i) {
    Psi[i].psiExam();
    if (psi5==5 || psi5==7) {  // pro(noun) 18aug2011
     if (psi1 > -1) { // if not inhibited below zero; 27oct2011
      psi1 = 0;
      Psi[i] = new psiNode(psi0,psi1,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
     }  // end of test for positive (not inhibited) psi1; 18aug2011
    }  // end of test for 5=noun or 7=pronoun; 18aug2011
  }  // end of search for 5=noun or 7=pronoun; 18aug2011
}  // end of NounClear(0; return to NounPhrase(); 18aug2011
 
 
function VerbClear() {
  for (i = t; i>0; --i) {
    Psi[i].psiExam();
    if (psi5 == 8) { // 8sep2010
     if (psi1 > 0) { // if not inhibited below zero; 8sep2010
      psi1 = 0;
      Psi[i] = new psiNode(psi0,psi1,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
     }  // end of test for positive (not inhibited) psi1; 8sep2010
    }  // 8sep2010
  }
}

 
function verbClip() {
  for (i = t; i>0; --i) {
    Psi[i].psiExam();
    if (psi5 == 8) { 
     if (psi1 > 0) { // if not inhibited below zero; 8sep2010
      psi1 = 20;
      Psi[i] = new psiNode(psi0,psi1,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
     } // end of test for positive (not inhibited) psi1; 8sep2010
    } // end of test for 8=pos verb; 8sep2010
  }
}
 
function PsiClear() {
  for (i = t; i>0; --i) {
    Psi[i].psiExam();
    if (psi1 > 0) { // if not inhibited below zero; 8sep2010
      Psi[i] = new psiNode(psi0,0,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
    } // end of test for positive (not inhibited) psi1; 8sep2010
  }
}
 
 
function PsiDecay() {  // replacement for old PsiDecay(); 14may2011
  actran = 0;  // preserve-inhibition test; 14jun2011
  for (i = t; i>midway; --i) {
    Psi[i].psiExam();
    if (psi1 > 0) { // Avoid inhibited nodes;  8jun2011
      actran = 0;  // preserve-inhibition test; 14jun2011
      if (psi1 > 40) actran = 34;  // 8jun2011
      if (psi1 > 50) actran = 35;  // 8jun2011
      if (psi1 > 60) actran = 36;  // 8jun2011
      if (psi1 > 70) actran = 37;  // 8jun2011
      if (psi1 > 80) actran = 38;  // 8jun2011
      if (psi1 > 90) actran = 39;  // highest going last; 8jun2011 
      if (actran > 0) psi1 = actran; // Differential act; 8jun2011
      actran = 0;  // Reset to zero for safety;  8jun2011
      --psi1;  // Decrement the psi1 activation-level; 8sep2010
      if (psi0 == 781) psi1 = 0;  // 781=CHTO (what); 11jan2012
      Psi[i] = new psiNode(psi0,psi1,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
    } //  End of if-clause finding and reducing positive activations
    Psi[i].psiExam();  // test; REMOVE; 14jun2011
    if (psi1 < 0) {  // If act. negative (inhibited); 8sep2010
      ++psi1;  // Increment psi1 up towards zero; 8sep2010
      Psi[i] = new psiNode(psi0,psi1,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
    } // End of test for inhibited nodes;  8jun2011 
  } // End of loop in search of conceptual activation-levels.
} // End of PsiDecay(); 14may2011
 
 
function PsiDamp() {
  residuum = 16;
  if (urpsi==57) urpsi = 58;  // 57=AM;  15aug2011
  if (urpsi==66) urpsi = 58;  // 66=IS;  15aug2011
  if (urpsi==67) urpsi = 58;  // 67=ARE; 15aug2011
  for (i = t; i>midway; --i) {
   Psi[i].psiExam();
   if (urpsi > 0) {  // 20sep2006 To prevent needless dampings.
    if (psi0==urpsi) { 
     if (psi1 > -1) {  // positive activation?; 27oct2011
      Psi[i] = new psiNode(psi0,residuum,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
     }  // end of test to avoid inhibited concepts; 8sep2010
    }
   }
  }
  residuum = 0;
  PsiDecay();  // Testing to see if new version works well; 25may2011
}  // End of PsiDamp(); 15nov2010

 
function RuDamp() {  // Wiki-page form of name; 5jan2012
  for (i = (t + 1); i>midway; --i) {
    ruLexicon[i].ruExam();  // 5jan2012
    ruLexicon[i] = new ruNode(ru0,0,ru2,ru3,ru4,ru5,ru6,ru7,ru8);
  }  // end of passage through Ru(ssian) array; 5jan2012
}  // end of RuDamp() fashioned from EnDamp(); 5jan2012

 
function audDamp() {
  for (i = t; i > midway; --i) {
    audMemory[i].audExam();
 // if (aud4 == 1) aud5 = 0;
 // if (aud4 == 1) aud5 = 0;  // commenting out on 15jan2012
    audMemory[i] = new audNode(aud0,0,aud2,aud3,aud4,aud5);
  }
}
 
function Shutdown() {
  if (document.all["cb4"].checked == true) {
    life = false;
apb = "You have halted the Dushka AI at Rejuvenation cycle #"+rjc+".";
    Voice();
  }
  if (document.all["cb4"].checked == false) {
    life = true;
    document.forms[1].ear.focus();
    TID=window.setTimeout("MainLoop();",1000);
  }
}


function Destroy() {
  document.forms[1].ear.focus();
  life = false;
  apb = "Closing the window will destroy the AI.";
  Voice();
  alert("The AI Mind is alive. You may unclick your decision.");
  TID=window.setTimeout("window.close();",500);
}

 
function Transcribe() {
  if (hardcopy == true) {  
    dialog += ("<P>Robot: " + output);  // moved up on 27oct2011
    dialog += ("<BR>Human: <b>" + userline + '<\/b>');
    output = "";  // avoid spurious repeats; 6nov2011
    userline = "";
  }
}


function Transcript() {
  if (document.all["cb1"].checked == true) {
    document.all["cb2"].checked = false;
    document.all["cb3"].checked = false;
    document.all.tabula.innerHTML = "";
    document.all.psicolumn.innerHTML = "";
    document.all.rucolumn.innerHTML = "";  // 5jan2012
    document.all.audcolumn.innerHTML = "";
    trouble = false;
    hardcopy = true;
    fyi = 1;
    now = new Date(); 
    adcopy=
("<font size='+2'>Dushka AI version "+vrsn+" on " +now+"<\/b><\/font>");
    document.all.souvenir.innerHTML = adcopy;
  }
  Transcribe();
  if (hardcopy == true) {
    document.all.psicolumn.innerHTML = "";
    document.all.rucolumn.innerHTML = "";  // 5jan2012
    document.all.audcolumn.innerHTML = "";
  }
  document.all.tabula.innerHTML = dialog;
  if (document.all["cb1"].checked == false) {
    document.all.souvenir.innerHTML = "";
    hardcopy = false;
    document.all.tabula.innerHTML = "";
  }
  if (hardcopy == false) html = "";
}
 
function psiList() {
  for (i = nonce; i < (t +1); i++) {
    Psi[i].psiExam();
    psidata += ("<BR>" +i+ ". <b>" +psi0+ "<\/b> " +psi1+ " " +psi2);
    psidata += (" "+psi3+" "+psi4+" "+psi5+" "+psi6+" "+psi7+" "+psi8);
  }
}
 

function ruList() {  // 22dec2011
  for (i = nonce; i < (t +1); i++) {
    ruLexicon[i].ruExam();
 // rudata += ("<BR>"+i+". <b>" +ru0+"<\/b> "+ru1+" "+ru2+" ");
 // rudata += (ru3+" "+ru4+" "+ru5+" "+ru6+" "+ru7+" "+ru8);

    rudata += ("<BR>"+i+". <b>" +ru0+"<\/b> "+ru1+" "+ru2);
    rudata += (" "+ru3+" "+ru4+" "+ru5+" "+ru6+" "+ru7+" "+ru8);

  }  // 2jan2012
}  // end of ruList(); 22dec2011

 
function audList() {
  for (i = nonce; i < (t +1); i++) {
    audMemory[i].audExam();  // again removing bold; 10jan2012
    auddata += ("<BR>" + i + ". ");
    if (aud2 == "*") auddata += ("<font color='red'>");
    auddata += (aud0 + " ");  // removing bold; 10jan2012
    if (aud2 == "*") auddata += ("<\/font>");
    if (aud0 == " ") aud1 = " ";
    auddata += (aud1+" "+aud2+" "+aud3+" "+aud4+" "+aud5); 
  }
}
 
 
function SpreadAct() {
  if (prepsi > 0) {  // deglobalized; 1oct2010
   for (j = zone; j > midway; --j) {
    Psi[j].psiExam();
    if (psi0 == prepsi) {  // deglobalized; 1oct2010
     psi1 = (psi1 + 1);
     Psi[j] = new psiNode(psi0,psi1,psi2,psi3,psi4,psi5,psi6,psi7,psi8); 
    }
    if (j < (zone - 6)) break; // eventually 64; 12nov2010
   }
  }
  if (seqpsi > 0) {  // deglobalized variable; 1oct2010
    for (j = zone; j < t; ++j) {
      Psi[j].psiExam();
      tag0 = psi0;
      tag1 = psi1;
      tag2 = psi2;
      tag3 = psi3;
      tag4 = psi4;
      tag5 = psi5;
      tag6 = psi6;
      tag7 = psi7;
      tag8 = psi8;  // Prevent corruption of values; 13oct2011
      if (psi0 == seqpsi) {  // deglobalized; 1oct2010
        if (fyi == 2) {
          if (pov == "#") {
            if (oldpsi > 0) {
              for (k=(t + 1); k>midway; --k) {
                Psi[k].psiExam();
                if (psi0 == seqpsi) {  // deglobalized; 1oct2010
                  if (psi8 > 0) {  // after adding in "tqv"; 13oct2011
                    seq7enx = psi8;  // Get seq enx as seq7enx; 13oct2011
                    for (k=t; k>midway; --k) {
                      ruLexicon[k].ruExam();
                      if (seq7enx == ru0) {  // 6jan2012
                        seq7aud = ru8; // aud for psi7 "seq";  5jan2012
                      }
                    }
                    engram = "";
                    do {
                      audMemory[seq7aud].audExam();  // 13oct2011
                      engram += aud0;
                      ctu = aud4;
                      seq7aud = (seq7aud + 1);  // 13oct2011
                    }
                    while (ctu == 1);
                      if (ctu == 0) {
                      pho = 32;
                    }
                    engram += " ";
                    for (k=t; k>midway; --k) {
                      ruLexicon[k].ruExam();  // 10jan2012
                      if (oldpsi == ru0) {    // 10jan2012
                        svo5aud = ru8; // 5jan2012
                        if (nouncall == 1) {
                          if (engram != "") {
                            brevity = (brevity + 1);
                            aud = svo5aud;
                            showSubject();
                          }
                        }
                         if (verbcall == 1) {
                          if (engram != "") {
                            equity = (equity + 1);
                            aud = svo5aud;
                            if (tutor == true) {
                              showVerb();
                            }
                            aud = 0;
                            sloshmark = "";
                          }
                        }
                        if (nouncall == 4) {
                          if (engram != "") {
                            city = (city + 1);
                            aud = svo5aud;
                            if (tutor == true) {
                              showObject();
                            }
                          }
                        }
                        star = 0; // Reset for showSubject(); 21may2011
                        node = 0; // Reset for showVerb(); 21may2011
                        ufo = 0;  // Reset for showObject(); 21may2011
                      }
                    }
                    break;
                  }
                }
              }
            }
          }
        }
        if (tag1 > -1) {  // avoid inhibition; 16sep2010
          if (subjectflag == 1) {  // onto verb-nodes; 18oct2010
            tag1 = (tag1 + spike); // add spike to seqpsi 18oct2010
          }  // end of test for subject-nodes; 18oct2010
          else  // in all other cases, e.g. dirobj; 18oct2010
          {  // for "dirobj" or "predflag" cases; 18oct2010
            tag1 = spike;  // Transfer absolute act; 18oct2010
          } // End of else-clause; 18oct2010
        }  // end of test to skip inhibited nodes; 16sep2010
        Psi[j] = new psiNode(tag0,tag1,tag2,tag3,tag4,tag5,tag6,tag7,tag8);
      tag0=0; tag1=0; tag2=0; tag3=0; tag4=0; tag5=0; tag6=0; tag7=0; tag8=0;
        break;  // After finding one seqpsi; 15oct2010
      }  // End of inner if-clause.
    if (j > (zone + 64)) break; // Assume single word found; 12nov2010
    }  // End of forwards loop.
  }  // End of outer if-clause.
  spike = 0;  // safety measure; 16sep2010
}  // end of SpreadAct(); 16sep2010
 

function NounAct() {
  if (nacpsi > 0) {  // using deglobalized variable; 13aug2010
    oldpsi = nacpsi;  // nacpsi replaces psi; 13aug2010
    for (i=(t + 1); i>midway; --i) {
      Psi[i].psiExam();
      if (psi0 == nacpsi) {  // nacpsi replaces psi; 13aug2010
        if (psi1 > -1) {   // avoid inhibition; 29oct2011
          psi1 = 26;  // start near a threshold level; 7jun2011
        }  //
        Psi[i] = new psiNode(psi0,psi1,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
        if (psi0 == 781) {  // 781=CHTO (what); 11jan2012    
          PsiDecay();  // MindForth: await active subject; 13may2011
          PsiDecay();  // MindForth: await active subject;  7jun2011
        }  // from MindForth; 13may2011
        spike = 12;  // Aim for ample spikes;  7jun2011
        prepsi = psi4;  // deglobalized; 1oct2010
        seqpsi = psi7;  // psi6 is changing to "qtv"; 13oct2011
        zone = i;  // for use in SpreadAct;  7jun2011
        if (psi1 == 0) spike = 0;
        if (psi1 >  5) spike = 12;  // from MindForth; 25may2011
        if (psi1 > 10) spike = 24;  // from MindForth;  7jun2011
        if (psi1 > 15) spike = 26;  // from MindForth;  7jun2011
        if (psi1 > 20) spike = 27;  // 10jun2011
        if (psi1 > 25) spike = 28;  // 10jun2011
        if (psi1 > 30) spike = 29;  // 10jun2011
        if (psi1 > 35) spike = 30;  // 10jun2011
        if (psi1 > 40) spike = 31;  // 10jun2011
        if (psi1 > 45) spike = 32;  // 10jun2011
        if (psi1 > 50) spike = 33;  // 10jun2011
        if (psi1 > 55) spike = 34;  // 10jun2011
        if (psi1 > 60) spike = 35;  // 10jun2011
        if (seqpsi > 0) {  // if positive association;  7jun2011
          if (seqpsi == 55) {  // deglobalized; 1oct2010
            spike = 1;  // de-activate 55=WHO; 13aug2010
          }  // end of test for 55=WHO; 13aug2010
          if (dirobj == 1) {  // 13jul2011
            spike = 8;  // 13jul2011
          }  // 13jul2011
          SpreadAct();  // deglobalized; 1oct2010
        }  // 
        pre = precand;
        seqpsi = 0;  // deglobalized; 1oct2010
      }  // end of test for psi0 to equal nacpsi;  7jun2011
      spike = 0;  // reset for each new loop; 15oct2010
    }
  }
  oldpsi = 0;
  spike = 0;  // reset; 15oct2010
}  // End of NounAct(); 13aug2010
 
 
function VerbAct() {
  verbval = 15; // oppose stray activations;  7jun2011
  if (vacpsi > 0) {  // if a vacpsi exists;  7jun2011
    oldpsi = vacpsi;  // deglobalized; 1oct2010
    if (vacpsi==57) vacpsi = 58;  //  AM becomes BE; 11aug2011
    if (vacpsi==66) vacpsi = 58;  //  IS becomes BE; 11aug2011
    if (vacpsi==67) vacpsi = 58;  // ARE becomes BE; 11aug2011
    for (i=(t + 1); i>midway; --i) {
      Psi[i].psiExam();
      if (psi0 == vacpsi) {  // deglobalized; 1oct2010
         if (psi1 > -1) { // avoid inhibited nodes;  7jun2011
          if (moot==0) {  // deprive queries of tags; 22aug2011
           psi1 = (psi1 + verbval); // CUMULATIVE for slosh-over; 7jun2011
          }  // end of test for a moot query input; 22aug2011
         }  // end of test to skip inhibited nodes;  7jun2011
         if (psi0 == 781) {  // 781=CHTO (what); 11jan2012
           psi1 = 0;  // Set WHAT at zero activation; 7jun2011
         }  // End of test for 781=CHTO (what); 11jan2012
         Psi[i] = new psiNode(psi0,psi1,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
         prepsi = psi4;  // deglobalized for SpreadAct; 1oct2010
         seqpsi = psi7;  // psi6 is changing to "tqv"; 13oct2011
         zone = i;  // for use in SpreadAct;  7jun2011
         if (psi1 == 0)  spike = 0;
         if (psi1 > 0)  spike = 1;
         if (psi1 > 5)  spike = 3;  // 10nov2010
         if (psi1 > 10) spike = 6;  // 10nov2010
         if (psi1 > 15) spike = 9;  // 10nov2010
         if (psi1 > 20) spike = 12;  // 10nov2010
         if (psi1 > 25) spike = 15;  // 10nov2010
         if (psi1 > 30) spike = 18;  // 10nov2010
         if (psi1 > 35) spike = 21;  // 10nov2010
         if (psi1 > 40) spike = 24;  // 10nov2010
         if (psi1 > 45) spike = 27;  // 10nov2010
         if (psi1 > 50) spike = 30;  // 10nov2010
         if (psi1 > 55) spike = 33;  // 10nov2010
         if (psi1 > 60) spike = 36;  // 10nov2010
         if (psi1 > 65) spike = 39;  // 10nov2010
         if (psi1 > 70) spike = 42;  // 10nov2010
         if (psi1 > 75) spike = 45;  // 10nov2010
         if (psi1 > 80) spike = 48;  // 10nov2010
         if (psi1 > 85) spike = 50;  //  7jun2011
         if (psi1 > 90) spike = 52;  //  7jun2011
         if (psi1 > 95) spike = 54;  //  7jun2011
         if (seqpsi > 0) SpreadAct();  // deglobalized; 1oct2010
         pre = precand;
         prepsi = precand;  // 1oct2010
         psi1 = 0;
         seqpsi = 0;  // 1oct2010
      }
      psi1 = 0;  // reset to start each loop again;  8jun2011
      spike = 0; // reset to start each loop again; 15oct2010
    }  // end of backwards search loop;  7jun2011
  }  // end of test for positive vacpsi;  7jun2011
  oldpsi = 0;
  verbcall = 0;
  verbval = 0;
}  // end of VerbAct; 1oct2010
 
 
function ReActivate() { // re-activate recent nodes of a concept
  spike = 0;
  if (psi > 0) {
    for (i=tov; i>midway; --i) { // Omitting current input; 27oct2011
      Psi[i].psiExam();
      if (psi0 == psi) {
       if (pov == "*") {  // Only during "*" external POV; 10may2011
        if (moot==0) {  // deprive queries of tags; 22aug2011
          if (psi1 < 0) {  // if inhibited; 27oct2011
            psi1 = (psi1 + 1);  // reactivate only slightly; 27oct2011
          }  // end of test for inhibited concept; 27oct2011
          else psi1 = psi1 + 35;  // full reactivation; 27oct2011
        }  // end of test for a moot query input; 22aug2011
        if (firstword==54) psi1 = 48;  // affirm queries; 1nov2011
        if (psi0 == 781) psi1 =  0; // 781=CHTO (what); 11jan2011
        if (psi0 == 791) psi1 =  0; // 791=KTO (who); 11jan2012
        Psi[i] = new psiNode(psi0,psi1,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
        spike = 1;
        if (psi1 == 0)  spike = 0;
        if (psi1 > 5)   spike =  7;
        if (psi1 > 10)  spike =  8;
        if (psi1 > 15)  spike =  9;
        if (psi1 > 20)  spike = 10;
        if (psi1 > 25)  spike = 11;
        if (psi1 > 30)  spike = 12;
        if (psi1 > 35)  spike = 13;
        if (psi1 > 40)  spike = 14;
        if (psi1 > 45)  spike = 15;
        if (psi1 > 50)  spike = 16;
        if (psi1 > 55)  spike = 17;
        if (psi1 > 60)  spike = 18;
        prepsi = psi4;
        seqpsi = psi7;
        zone = i;
        pre = precand;
        psi1 = 0;
        seqpsi = 0;
        spike = 1;
       }  // End of test for external "*" POV; 10may2011 
      }
    }
  }
}  // end of ReActivate() 1oct2010
 
 
function InNativate() { // quasi-instantiate EnBoot sequence; 23oct2011
  Psi[t] = new psiNode(psi,0,num,0,pre,pos,tqv,seq,rux);
}  // end of InNativate(); 23oct2011


function OutBuffer() {  // for manipulation of SpeechAct words; 4jan2012
// alert("OutBuffer called by c = "+c+" and binc = "+binc); // 19jan2012
  if (c16>"") {  // if the AudBuffer full; 4jan2012
    b16=c16; b15=c15; b14=c14; b13=c13; b12=c12; b11=c11; 
    b10=c10; b09=c09; b08=c08; b07=c07; b06=c06; b05=c05; 
    b04=c04; b03=c03; b02=v02; b01=c01;  // 4jan2012
// alert("OutBuffer16 = "+b10+b11+b12+b13+b14+b15+b16);
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 16-character word; 4jan2012
  if (c15>"") {  
    b16=c15; b15=c14; b14=c13; b13=c12; b12=c11; b11=c10;
    b10=c09; b09=c08; b08=c07; b07=c06; b06=c05; b05=c04; 
    b04=c03; b03=c02; b02=c01; b01="";  // 4jan2012
// alert("OutBuffer15 = "+b10+b11+b12+b13+b14+b15+b16);
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 15-character word; 4jan2012
  if (c14>"") {
    b16=c14; b15=c13; b14=c12; b13=c11; b12=c10; b11=c09;
    b10=c08; b09=c07; b08=c06; b07=c05; b06=c04; b05=c03;
    b04=c02; b03=c01; b02="";  b01="";  // 4jan2012
//  alert("OutBuffer14 = "+b10+b11+b12+b13+b14+b15+b16);
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 14-character word; 4jan2012
  if (c13>"") {
    b16=c13; b15=c12; b14=c11; b13=c10; b12=c09; b11=c08;
    b10=c07; b09=c06; b08=c05; b07=c04; b06=c03; b05=c02;
    b04=c01; b03="";  b02="";  b01="";  // 4jan2012
//  alert("OutBuffer13 = "+b10+b11+b12+b13+b14+b15+b16);
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 13-character word; 4jan2012
  if (c12>"") {
    b16=c12; b15=c11; b14=c10; b13=c09; b12=c08; b11=c07;
    b10=c06; b09=c05; b08=c04; b07=c03; b06=c02; b05=c01;
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
//  alert("OutBuffer12 = "+b10+b11+b12+b13+b14+b15+b16);
    return;  // abandon remainder of function; 
  }  // end of transfer of a 12-character word; 4jan2012
  if (c11>"") {
    b16=c11; b15=c10; b14=c09; b13=c08; b12=c07; b11=c06;
    b10=c05; b09=c04; b08=c03; b07=c02; b06=c01; b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
//  alert("OutBuffer11 = "+b10+b11+b12+b13+b14+b15+b16);
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of an 11-character word; 4jan2012
  if (c10>"") {
    b16=c10; b15=c09; b14=c08; b13=c07; b12=c06; b11=c05;
    b10=c04; b09=c03; b08=c02; b07=c01; b06="";  b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
 // alert("OutBuffer10 = "+b10+b11+b12+b13+b14+b15+b16);
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 10-character word; 4jan2012
  if (c09>"") {
    b16=c09; b15=c08; b14=c07; b13=c06; b12=c05; b11=c04;
    b10=c03; b09=c02; b08=c01; b07="";  b06="";  b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
//  alert("OutBuffer9 = "+b10+b11+b12+b13+b14+b15+b16);
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 9-character word; 4jan2012
  if (c08>"") {
    b16=c08; b15=c07; b14=c06; b13=c05; b12=c04; b11=c03;
    b10=c02; b09=c01; b08="";  b07="";  b06="";  b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
//  alert("OutBuffer8 = "+b10+b11+b12+b13+b14+b15+b16);
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of an 8-character word; 4jan2012
  if (c07>"") {
    b16=c07; b15=c06; b14=c05; b13=c04; b12=c03; b11=c02;
    b10=c01; b09="";  b08="";  b07="";  b06="";  b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
// alert("OutBuffer7 = "+b10+b11+b12+b13+b14+b15+b16);
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 7-character word; 4jan2012
  if (c06>"") {
    b16=c06; b15=c05; b14=c04; b13=c03; b12=c02; b11=c01;
    b10="";  b09="";  b08="";  b07="";  b06="";  b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
// alert("OutBuffer6 = "+b10+b11+b12+b13+b14+b15+b16);
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 6-character word; 4jan2012
  if (c05>"") {
    b16=c05; b15=c04; b14=c03; b13=c02; b12=c01; b11="";
    b10="";  b09="";  b08="";  b07="";  b06="";  b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
 //  alert("OutBuffer5 = "+b10+b11+b12+b13+b14+b15+b16);
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 5-character word; 4jan2012
  if (c04>"") {
    b16=c04; b15=c03; b14=c02; b13=c01; b12="";  b11="";
    b10="";  b09="";  b08="";  b07="";  b06="";  b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
//  alert("OutBuffer4 = "+b10+b11+b12+b13+b14+b15+b16);
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 4-character word; 4jan2012
  if (c03>"") {
    b16=c03; b15=c02; b14=c01; b13=""; b12="";  b11="";
    b10="";  b09="";  b08="";  b07="";  b06="";  b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
//  alert("OutBuffer3 = "+b10+b11+b12+b13+b14+b15+b16);
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 3-character word; 4jan2012
  if (c02>"") {
    b16=c02; b15=c01; b14="";  b13=""; b12="";  b11="";
    b10="";  b09="";  b08="";  b07="";  b06="";  b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
    return;  // abandon remainder of function; 4jan2012
//  alert("OutBuffer2 = "+b10+b11+b12+b13+b14+b15+b16);
  }  // end of transfer of a 2-character word; 4jan2012
  if (c01>"") {
    b16=c01; b15=""; b14="";  b13=""; b12="";  b11="";
    b10="";  b09="";  b08="";  b07="";  b06="";  b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 1-character word; 4jan2012
//  alert("OutBuffer1 = "+b09+b10+b11+b12+b13+b14+b15+b16);
}  // end of OutBuffer called from AudListen(); 12jan2012
 

function AudBuffer() {  // for transfer of words to OutBuffer.
  phodex = (phodex + 1);  // unitary increment; 4jan2012
  if (phodex==1) {  // 4jan2012
    c01=abc; c02=""; c03=""; c04=""; c05=""; c06=""; c07=""; c08=""; 
    c09="";  c10=""; c11=""; c12=""; c13=""; c14=""; c15=""; c16="";
  }   // emd of using phodex=1 to blank out the AudBuffer; 4jan2012
  if (phodex==2)  c02=abc;  //  4jan2012
  if (phodex==3)  c03=abc;  //  4jan2012
  if (phodex==4)  c04=abc;  //  4jan2012
  if (phodex==5)  c05=abc;  //  4jan2012
  if (phodex==6)  c06=abc;  //  4jan2012
  if (phodex==7)  c07=abc;  //  4jan2012
  if (phodex==8)  c08=abc;  //  4jan2012
  if (phodex==9)  c09=abc;  //  4jan2012
  if (phodex==10)  c10=abc;  // 4jan2012
  if (phodex==11)  c11=abc;  // 4jan2012
  if (phodex==12)  c12=abc;  // 4jan2012
  if (phodex==13)  c13=abc;  // 4jan2012
  if (phodex==14)  c14=abc;  // 4jan2012
  if (phodex==15)  c15=abc;  // 4jan2012
  if (phodex==16)  c16=abc;  // 4jan2012
// alert("AudBuffer = "+c01+c02+c03+c04+c05+c06+c07+c08+c09); // 18jan2012
}  // end of AudBuffer() called from AudListen() or elsewhere.
 

function psiExam() {
  psi0 = this.psi;
  psi1 = this.act;
  psi2 = this.num;
  psi3 = this.jux;
  psi4 = this.pre;
  psi5 = this.pos;
  psi6 = this.tqv;  // time-point for "verblock" or "nounlock"; 2jan2012
  psi7 = this.seq;  // subSEQuent concept; 2jan2012
  psi8 = this.rux;  // Russian-transfer tag; 2jan2012
}
 
function psiNode(psi,act,num,jux,pre,pos,tqv,seq,rux) { // 2jan2012
  this.psi = psi;
  this.act = act;
  this.num = num;
  this.jux = jux;
  this.pre = pre;
  this.pos = pos;
  this.tqv = tqv;
  this.seq = seq;
  this.rux = rux;  // 2jan2012
  this.psiExam = psiExam;
}

  
function InStantiate() {
  if (precand > 0) pre = precand;
  if (ordo == 1) prevtag = 0;
  if (firstword==781) moot = 1;  // 781=CHTO (what); 11jan2012
  if (firstword==59 || firstword==87) {  // 59=DO; 87=DOES; 22aug2011
    moot = 1;  // deprive queries of "pre" and "seq" tags; 22aug2011
  }  // end of test for a DO-query; 24oct2011
  if (lastword == true) {
    seq = 0;
    lastword = false;
  }
  if (t > 201) {  
    if (pos == 6) {
      nounduck = 1;
    }
  }
 if (t > 201) {  
    if (nounduck == 0) {
      if (pos == 5) {
        presubj = psi;
      }
    }
  }
  if (presubj > 0) {
    if (pos == 8) {
      prevtag = presubj;
      presubj = 0;
      if (nounduck == 1) nounduck = 0;
    }
  }
 if (t > 201) {
    if (psi == 55) {
      whoskip = 1;
      act = 0;
    }
  }
  if (t > 201) {
    if (whoskip == 1) {
      if (psi == 57) presubj = 50;
      if (psi == 67) presubj = 0;
      if (psi == 57) preverb = 57;
      if (psi == 56) {
        lastword = false;
        seq = preverb;
        preverb = 0;
        whoskip = 0;
      }
    }
  }
  if (singflag==1) {  // if set recently; 6nov2011
    if (pos==5) {  // after "a(n)" wait for a noun; 6nov2011
      num = 1;  // even if previously "0" by default; 6nov2011
      singflag = 0;  // reset after use; 6nov2011
    }  // end of test for a noun; 6nov2011
  }  // end of test of singularity-flag; 6nov2011
  if (psi==1 || psi==83) singflag = 1;  // after a(n); 6nov2011
// if (psi==54) {  // Special handling of psi #54 WHAT; 19apr2011
  if (psi==781) {  // Special handling of psi #781 CHTO (what)
    indefartcon = 1;  // Set indefinite article condition; 19apr2011
    act = 0; // suppress "what" in queries; 16sep2010 
  }  // Changing from one line to multiple lines; 19apr2011
// if (psi==55) {  // Special handling of psi #55 WHO; 19apr2011
  if (psi==791) {  // Special handling of psi #791 KTO (who)
    defartcon = 1;  // Set definite article condition; 19apr2011
    act = 0;  // To suppress "WHO" during answer; 19apr2011
  }  // End of test for psi #55 WHO; 19apr2011
  if (pov == "*") {  // If POV is external; 20jul2011
    if (pos == 5) {  // If external noun comes in; 20jul2011
       if (recnum > 0) {  // If positive recog-num; 20jul2011
         num = recnum;  // Override num(ber); 20jul2011
         recnum = 0;  // reset for safety; 20jul2011
       }  // End of test for positive recog-num; 20jul2011
       quobj = psi;  // query-object for AskUser; 18aug2011
    }  // End of test for a noun; 20jul2011
  }  // End of test for external "*" point-of-view; 20jul2011
  if (pov == "#") {  // If POV is ASCII 35 "#" internal; 1may2011
    act = 0; // 0 activation for ReEntry concepts; 1may2011
  }  // End of test for "#" internal POV;  1may2011
  Psi[t] = new psiNode(psi,act,num,jux,prevtag,pos,tqv,seq,rux);
  act = 0;  // reset for safety; 27oct2011
  inhibcon = 0;  // reset for safety; 27oct2011
  instnum = num;  // instantiation num(ber); 27oct2011
  if (jux == 250) jux = 0;  // reset after use; 6jan2012
  if (prejux == 250) { // 250=Nye in Russian; 6jan2012
    jux = 250;  // set jux for next instantiand; 6jan2012
    prejux = 0;  // reset for safety; 24jul2011
  }  // end of post-instantiation test; 24jul2011
  if (mfn == 1 || mfn == 2) {  // for calling WhoBe; 3aug2011
    mfnflag = mfn;  // both positive and specific; 3aug2011
  }  // end of test to set mfnflag; 3aug2011
  if (mfn == 0) mfnflag = 0;  // reset for safety; 3aug2011 
  preset = 0;
  prevtag = psi;
  // removing English test for auxiliary; check for Ru "li"? 6jan2012
  if (seqneed==5) {  // if looking for a noun; 4oct2011
    if (pos==5 || pos==7) {  // if noun or pronoun; 4oct2011
      seq = psi;  // because a (pro)noun has arrived; 4oct2011
      seqpos = pos;  // possibly for tqv; 4oct2011
      seqneed = 0;  // zero out after use; 4oct2011
    }  // end of test for 5=pos noun or 7=pos pronoun; 4oct2011
    for (i=(t-2); i>vault; --i) {  // look for verb needing seq; 4oct2011
      Psi[i].psiExam();  // examine the Psi concept array; 4oct2011
        if (psi5==8) {  // verb? 4oct2011
         if (moot==0) {  // deprive queries of tags; 4oct2011
          Psi[i] = new psiNode(psi0,psi1,psi2,psi3,psi4,psi5,psi6,seq,psi8);
          if (seqpos==5 || seqpos==7) {  // (pro)noun? 25oct2011
            tqv = t;  // assign "tqv" value; 25oct2011
            Psi[i].psiExam();  // 25oct2011
            Psi[i] = new psiNode(psi0,psi1,psi2,psi3,psi4,psi5,t,psi7,psi8);
          }  // end of seqpos=(pro)noun test; 25oct2011          
         }  // end of test for a moot query input; 4oct2011
         break;  // Change only one seq; 4oct2011
        }  // end of test for verb; 4oct2011      
    }  // end of backwards loop; 4oct2011
  }  // end of test for needing a noun; 4oct2011
  if (ordo > 1) {  // 4oct2011
    seq = psi;  // 4oct2011
    if (lastword == true) {  // 4oct2011
      seq = 0;  // 4oct2011
      lastword = false;  // 4oct2011
    }  // 4oct2011
  }  // 4oct2011
  if (pos==5 || pos==7) seqneed = 8; // if noun need verb; 4oct2011
  if (pos==6) seqneed = 5;  // if preposition need noun; 4oct2011
  if (psi != 59) {  // skip auxiliary verb "59=DO"; 7oct2011
    if (psi != 87) {  // skip auxiliary "87=DOES"; 8oct2011
      if (pos==8) seqneed = 5;  // if verb need noun; 4oct2011
    }  // end of test to skip auxiliary DOES; 7oct2011
  }  // end of test to skip auxiliary DO; 7oct2011
  recnum = 0;  // lest carry-over to other words; 20jul2011
  seq = 0;
} // End of InStantiate(); 4sep2010
 
function ruExam() {  // transferred from ru120104 on 5jan2012
  ru0 = this.nru;  // was "nen" in English; 2jan2012
  ru1 = this.act;
  ru2 = this.num;
  ru3 = this.mfn; 
  ru4 = this.dba;  // 2jan2012
  ru5 = this.fex;
  ru6 = this.pos;
  ru7 = this.fin;
  ru8 = this.aud;  // nine flags, including zero; 2jan2012
}


function ruNode(nru,act,num,mfn,dba,fex,pos,fin,aud) {
  this.nru = nru;  // was "nen" in English; 2jan2012
  this.act = act;
  this.num = num;
  this.mfn = mfn;
  this.dba = dba;  // 2jan2012
  this.fex = fex;
  this.pos = pos;
  this.fin = fin;
  this.aud = aud;
  this.ruExam = ruExam;  // 2jan2012
}  // transferred from ru120104.html on 5jan2012


function RuVocab() {  // adding "dba"; 2jan2012
  ruLexicon[t] = new ruNode(nru,act,num,mfn,dba,fex,pos,fin,aud);
}  // 2jan2012
 
 
function RuParser() {  // renamed; 5jan2012
  bias = 5;
  act = 30;  // MindForth: Activate lower than ReActivate; 8jun2011
  if (pov == "*") {  // only during external input; 15oct2010
    act = (act - ordo); // reduce S-V-O act's; 15oct2010
  }  // end of test for external POV; 15oct2010
  InStantiate();
  if (pos == 5) bias = 8;
  if (pos == 7) bias = 8;  // from MindForth; 15oct2010
  if (pos == 8) bias = 5;
}  // End of RuParser(); 5jan2012


function RuReify() {  // adapted from EnReify; 5jan2012
  for (i = t; i>midway; --i) {  // from MindForth; test; 8jun2011
    Psi[i].psiExam();
    num = psi2;  // test; 17jan2012
    if (psi1 > 0) {
      lexact = psi1;  // from MindForth;  8jun2011
  //  num = psi2;  // from MindForth;  8jun2011; 17jan2012
  //  j = i;  // Instead of nesting;  8jun2011
      ruLexicon[i].ruExam();  // examine Russian array; 5jan2012
      ruLexicon[i] = new ruNode(ru0,lexact,num,ru3,ru4,ru5,ru6,ru7,ru8);
    }  // end of test for a psi with positive activation; 9aug2011
    lexact = 0;  // reset for safety; 8jun2011
  }  // end of looping through the Psi concept array;  9aug2011
}  // End of RuReify(); return to NounPhrase or VerbPhrase; 5jan2012
 
 
function KbRetro() {  // for yes-or-no answers; 29jun2011
  if (oldpsi == 432 || oldpsi == 427) {  // if yes or no; 11jan2012
    if (oldpsi == 427) {  // 427=NYET (no); 11jan2012
      Psi[tkbv].psiExam(); // expose all values to change two; 3jul2011
      Psi[tkbv] = new psiNode(psi0,64,psi2,12,psi4,psi5,psi6,psi7,psi8);
    }  // End of test for "no" answer; 29jun2011
    if (oldpsi == 432) {  // 432=DA (yes); 11jan2012
      Psi[tkbv].psiExam(); // expose all values to change one; 3jul2011
      Psi[tkbv] = new psiNode(psi0,64,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
    }  // End of test for a "yes" answer; 3jul2011
  }  // end of test for either yes or no; 3jul2011
  else {  // if neither; 29jun2011
  Psi[tkbn].psiExam(); // remove associative tags from noun; 29jun2011
  Psi[tkbn] = new psiNode(psi0,psi1,psi2,psi3,0,psi5,psi6,0,psi8);
  Psi[tkbv].psiExam(); // remove associative tags from verb; 29jun2011
  Psi[tkbv] = new psiNode(psi0,psi1,psi2,psi3,0,psi5,psi6,0,psi8);
  }  // end of else-clause; 29jun2011
  kbcon = 0;  // temporarily here turn off kbcon; 29jun2011
  tkbn = 0;  // reset for safety; 3jul2011
  tkbv = 0;  // reset for safety; 3jul2011
  PsiDecay()  // for distribution of PsiDecay influence; 3jul2011
}  // End of KbRetro(); return to OldConcept(); 30jun2011
 
 
function OldConcept() {
  act = 28;  // from MindForth; test;  8jun2011
//  act = 44;  // test; 21jan2012
  for (i=t; i>midway; --i) {
    ruLexicon[i].ruExam();  // 5jan2012
    if (ru0 == oldpsi) {  // conformance with MindForth; 5jan2012
      if (ru2 > 0) unk = ru2; //  5jan2012
      if (ru3 > 0) mfn = ru3; //  5jan2012
      if (ru5 > 0) fex = ru5; //  5jan2012
      if (ru6 > 0) pos = ru6; //  5jan2012
      if (ru7 > 0) fin = ru7; //  5jan2012
    break;
    }
  }
 // if (pos == 8) unk = numsubj; // assume agreement; 18jun2011; 17jan2017
  if (oldpsi==57) tbev = t;  // 57=AM; 15aug2011
  if (oldpsi==58) tbev = t;  // 58=BE; 15aug2011
  if (oldpsi==66) tbev = t;  // 66=IS; 15aug2011
  if (oldpsi==67) tbev = t;  // 67=ARE; 15aug2011
  ruLexicon[t] = new ruNode(oldpsi,0,unk,mfn,dba,fex,pos,fin,aud);
  if (pov == "{") oldpsi = fex;  // deglobalizing psi; 3jul2011
  if (pov == "#") oldpsi = fex;  // deglobalizing psi; 3jul2011
  if (pov == "}") oldpsi = fex;  // deglobalizing psi; 3jul2011
  if (pov == "*") oldpsi = fin;  // deglobalizing psi; 3jul2011
  rux = oldpsi;  // 5jan2012
  if (oldpsi==12) {  // 12=NOT; 15aug2011
     if (tbev > 0) {  // 15aug2011
       Psi[tbev].psiExam();  // examine Psi array at "tbev"; 15aug2011
       psi3 = 12;  // set verb "jux" to 12=NOT; 15aug2011
       Psi[tbev] = new psiNode(psi0,psi1,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
       tbev = 0;  // reset for safety; 15aug2011
     }  // end of test for positive time-of-beverb; 15aug2011
  }  // end of test for 12=NOT; 15aug2011
  if (oldpsi == 370) {  // 370=POCHEMU (why); 11jan2012
    act = 8;  // subactivate question "why".
    questype = 370;  // Keep track of what was asked; 11jan2012
    // so that ConJoin() may provide the conjunction "because".
  }  // End of test to deal with "why" questions.
  if (oldpsi == 7) act = 0;  // 7=THE; deglobalizing psi; 3jul2011
  if (kbcon > 0) {  // if user answers yes-or-no question; 3jul2011
    KbRetro();  // retroactively adjust knowledge base; 3jul2011
    kbcon = 0;  // reset for safety; 3jul2011
  }  // User has had one chance to answer yes-or-no question.
  if (oldpsi == 707) act = 31;  // Enhance Ty (you); test; 21jan2012
  if (oldpsi == 781) act = 0;  // Suppress 781=CHTO (what); 11jan2012
  if (oldpsi == 791) act = 0;  // Subactivate 791=KTO (who); 11jan2012
  if (oldpsi == 250) {  // upon recognition of 250=NYE (not); 11jan2012
    prejux = 250;  // flag for concept to be negated; 11jan2012
  }  // end of test for input or ReEntry of 250=NYE (not); 11jan2012
  psi = oldpsi;  // from MindForth; 3jul2011
  RuParser();  // 5jan2012
  pos = 0;
  if (pov == "*") {
    urpre = pre;
    caller = "OldConcept";
    ReActivate();
    caller = " ";  // reset after calling;  7jul2011
    pre = urpre;
  }
  unk = 0;
  act = 0;
  if (pos == 8) {  // if a verb; 30jun2011
    quverb = psi;  // for yes-or-no question; 30jun2011
  }  // end of test for incoming verb; 30jun2011
  num = 0;  // test; remove; 18jun2011
  psi = 0;  // test; remove; 30jun2011
}  // End of OldConcept; return to AudInput(); 22aug2011


function NewConcept() {
  nru = (nru + 1);  // 5jan2012
  psi = nru;  // 5jan2012
  fex = nru;  // 5jan2012
  fin = nru;  // 5jan2012
  mfn = 0;  // test; 17jan2012
  act = 24;
  pos = bias;
  RuVocab();  // 5jan2012
  dba = 0;  // reset after storing value; 12jan2012
  fin = 0;
  fex = 0;
  rux = nru;  // 5jan2012
  RuParser();  // 5jan2012
  if (pos == 5) {
    cogpsi = nru;  // for WhatBe; 5jan2012
    cognum = instnum;  // from InStantiate; 27oct2011
    recon = 1;
    topic = nru;  // potentially a query "topic";  5jan2012
    quobj = nru;  // for AskUser; test;  5jan2012
  }
// if (pos == 8) quverb = nen;  // for AskUser; test; 22jun2011
  if (pos == 8) quverb = nru;  // for AskUser; test; 6jan2012
  if (kbcon > 0) {  // if user answers yes-or-no question; 3jul2011
    KbRetro();  // retroactively adjust knowledge base; 3jul2011
    kbcon = 0;  // reset for safety; 3jul2011
  }  // User has had one chance to answer yes-or-no question.
  pos = 0;
  act = 0;
}  // End of NewConcept(); return to AudInput(); 12may2011
 
 
function VisRecog() {  // identification of objects seen by a robot
  if (svo3==0) {  // if no direct object is available; 25sep2011
    for (i = t; i>midway; i--) {  // search for an automatic default
      ruLexicon[i].ruExam();  // examine the Russian lexicon; 10jan2012
      if (ru0 == 860) {  // 860=NICHEGO (nothing); 10jan2012
        aud = ru8; // hold address for SpeechAct; 10jan2012
        break;  // search no further after finding engram; 25sep2011
      }  // end of test for default "51=NOTHING"; 25sep2011
    }  // end of Russian lexicon search loop; 10jan2012
  }  // end of test for zero direct object; 25sep2011
}  // End of VisRecog(); return to VerbPhrase(); 25sep2011


function AudRecog() {
  psi = 0;
  act = 8;
  actbase = 0;
  audpsi = 0;  // for safety; 15jan2012
  for (i=spt; i>midway; i--) {
    audMemory[i].audExam();
    if (aud0 == pho) {
      if (aud1 == 0) {
        if (aud3 == 1) {  // if beg=1 on matching no-act aud engram;
         if (audrun < 2) {  // If comparing start of word; 13jul2010
          if (aud4 == 1) {  // If beg-aud0 has ctu=1 continuing,
            if (aud5 > 0) { 
              provrec = aud5;  // stem? 15jan2012
           // alert("AudRecog1: provrec = "+provrec);  // 15jan2012
            }  // 15jan2012
            j = (i + 1); // 8apr2009 Target next-in-line time-point.
            audMemory[j].audExam();  // Fetch audNode at i+1
            aud1 = 8;  // 16aug2008 Activate next-in-line char,
            audMemory[j] = new audNode(aud0,aud1,aud2,aud3,aud4,aud5);
            psi = 0;  // Revoke any assignment of a matching psi-tag.
            j = 0;  // reset for safety
          }  // end of test for continuation of beg-aud0
          else
          {                  // 16aug2008 ProfJS p. 582
            if (len == 1) {  // 16aug2008 From MindForth
              monopsi = aud5;
            }  // End of test for one char length.
          }  // End of else-clause; 13jul2010
         }  // End of test for audrun=1 start of word; 13jul2010
        }  // end of test for a beg(inning) non-active aud0
      }  // end of test for matching aud0 with no activation
      audMemory[i].audExam();
      if (aud1 > 0) {
        psi = 0;
        if (aud4 == 1) {
          if (aud5 > 0) { 
            provrec = aud5;  // stem? 15jan2012
         // alert("AudRecog2: provrec = "+provrec);  // 15jan2012
          }  // 15jan2012
          act = (act + 2);
          psi = 0;
          j = (i + 1);
          audMemory[j].audExam();
          aud1 = act;
          audMemory[j] = new audNode(aud0,aud1,aud2,aud3,aud4,aud5);
          j = 0;
        }
        audMemory[i].audExam();
        if (aud4 == 0) {
          if (len == 2) {
            if (aud1 > 0) {
              psibase = aud5;
            }  // 15apr2009
          }  // 15apr2009
          if (aud1 > 8) {
            if (aud4 == 0) {
              if (aud1 > actbase) {
                psi = aud5;
                subpsi = aud5;
                sublen = len;
                psibase = aud5;
                Psi[i].psiExam();  // 20jul2011
                if (psi2 > 0) recnum = psi2;  // 20jul2011
                Psi[i+1].psiExam();  // 20jul2011
                if (psi2 > 0) recnum = psi2;  // 20jul2011                
                actbase = aud1;
              }
            }
          }
        }
        else
        {
       // psi = 0;  // Commented out on 15jan2012
          if (provrec == 0) psi = 0;  // 15jan2012
          if (monopsi > 0) {
            psi = monopsi;
            monopsi = 0;
          }  // End of test for a lurking one-letter word.
        }  // 16aug2008 End of "else" statement.
      }  // End of test for matching aud0 with activation.
    }  // End of test for a character matching "pho".
   if (i == (midway+1)) {  // If a loop reaches midway; 13jul2010
      audrun = (audrun + 1);  // Increment audrun; 13jul2010
   }  // End of test for loop reaching midway; 13jul2010
  }  // End of looping backwards from "spt".
  act = 0;      // 16aug2008 Reset act to zero.
  actbase = 0;  // 16aug2008 Reset to zero.
  if (psibase > 0) {
    psi = psibase;
  }
  if (psi == 0) {
    if (monopsi > 0) {
      if (len < 2) {
        psi = monopsi;
      }
      monopsi = 0;
    }
  }
  psibase = 0;
  if (psi==0 && provrec > 0) psi = provrec;  // stem? 15jan2012
  if (psi == 0) {
    psi = morphpsi;
    if (sublen > 0)  {
      stemgap = (len - sublen);
    }
    if (stemgap < 0) stemgap = 0;
    if (stemgap > 1) subpsi = 0;
    if (stemgap > 1) morphpsi = 0;
    if (stemgap > 1) psi = 0;
  }
  morphpsi = subpsi;
  psibase = 0;
  subpsi = 0;
  if (psi > 0) {
    if (stemgap > 2) {
      psi = 0;
    }
    if (pho == "S") {
      num = 2;
    }
    else num = 0;  // a default quasi-singular; 6nov2011
    if (recnum > 0) num = recnum;  // override; 20jul2011
  }
 // if (psi == 0 && provrec > 0) psi = provrec);  // 15jan2012
  if (psi == 0) psi = provrec;  // 15jan2012 
// alert("AudRecog: provrec morphpsi psi = "+provrec+" "+morphpsi+" "+psi);
  audpsi = psi;  // 9dec2009 For transfer from AudRecog() to AudMem()
  morphpsi = 0;  // reset until further notice; 15jan2015
 // provrec = 0;  // reset to prevent carry-over; 15jan2012
  stemgap = 0;  // safety measure; 25sep2011
}  // End of AudRecog(); return to AudMem(); 15jan2012

 
function audExam() {
  aud0 = this.pho;
  aud1 = this.act;
  aud2 = this.pov;
  aud3 = this.beg;
  aud4 = this.ctu;
  aud5 = this.audpsi;  // 8dec2009 deglobalizing from "psi"
}
 
function audNode(pho,act,pov,beg,ctu,audpsi) {
  this.pho = pho;
  this.act = act;
  this.pov = pov;
  this.beg = beg;
  this.ctu = ctu;
  this.audpsi = audpsi;  // 8dec2009 deglobalizing from "psi"
  this.audExam = audExam;
}


function AudMem() {
  if (t > vault) {
    AudRecog();
    if (audpsi == 0) {  // 15jan2012
      if (provrec > 0) audpsi = provrec;  // 15jan2012
      provrec = 0;  // reset in any case; 15jan2012
    }  // 15jan2012
  }
  tult = (t - 1);
  audMemory[tult].audExam();
  if (aud0 == 0) beg = 1;
  if (aud0 == 0) { 
    spt = tult;
  }
  if (beg == 1) onset = t;
  if (aud0 == " ") beg = 1;
  audMemory[t] = new audNode(pho,0,pov,beg,ctu,audpsi); // 8dec2009
// if (ctu==0) quobj = audpsi; // for AskUser; test; 22jun2011
}  // end of AudMem; 15jan2012


function Attention() {
  brain = false;
  danger = false;
  freedom = false;
  if (skip < 1) {  
    danger = true;
    TID=window.setTimeout("SeCurity();",20000);
    skip = skip+1;
  }
}


function AudListen() {
  quiet = false;
  apb = "Calling AudListen module; when done press [ENTER]";
  Voice();
  if (skip < 1) {
  Attention();
  }
  inert = 0;
  pov = "*";
  document.onkeypress = function (evt) {
    c = event.keyCode;
    inert = 0;  // User input cancels "inert" status; 18oct2011
    kbtv = 0;
    lurk = 0;  // de-lurk if user enters datum; 29sep2010
    if (c == 63) alert("Please use no punctuation.");
    if (c == 27) {
      brain = false;
      danger = false;
      freedom = false;
    }
    if (c == 27) {
      document.all["cb4"].checked = true;
      Shutdown();
    }
    if (c != 27) {
      if (life == false) {
        life = true;
        apb = ("AI alive again.");
        Voice();
      }
    }
    if (c == 32 || c == 13) {  // space-bar or CR; 12jan2012
      OutBuffer();  // to right-justify word from AudBuffer
      c01=""; c02=""; c03=""; c04="";  // empty AudBuffer
      c05=""; c06=""; c07=""; c08=""; 
      c09=""; c10=""; c11=""; c12=""; 
      c13=""; c14=""; c15=""; c16="";
      if (b16==String.fromCharCode(1070)) {  // "YU" 18jan2012
         num = 1;  // singular verb form; 18jan2012
         dba = 1;  // first person verb form; 18jan2012
         bias = 8; // overrule pre-existing setting; 18jan2012
         pos = 8;  // part of speech is 8=verb; 18jan2012
         b01=""; b02=""; b03=""; b04="";  // 18jan2012
         b05=""; b06=""; b07=""; b08="";  // 18jan2012
         b09=""; b10=""; b11=""; b12="";  // 18jan2012 
         b13=""; b14=""; b15=""; b16="";  // 18jan2012
  //  alert("AudL: 1st person verb YU");  // test; 18jan2012
      }  // end of nested if-clause; 18jan2012
      if (b14==String.fromCharCode(1045)) {  // "E" 18jan2012
        if (b15==String.fromCharCode(1064)) {  // "SH" 18jan2012
          if (b16==String.fromCharCode(1068)) {  // "b" 18jan2012
            num = 1;  // singular verb form; 12jan2012
            dba = 2;  // 2nd person verb form; 12jan2012
            bias = 8; // overrule pre-existing setting; 12jan2012
            pos = 8;  // part of speech is 8=verb; 12jan2012
            b01=""; b02=""; b03=""; b04="";  // 12jan2012
            b05=""; b06=""; b07=""; b08="";  // 12jan2012
            b09=""; b10=""; b11=""; b12="";  // 12jan2012 
            b13=""; b14=""; b15=""; b16="";  // 12jan2012
   //  alert("AudL: 2nd person verb YESH");  // test; 12jan2012
      } } }  // end of nested if-clauses; 12jan2012
      if (b15==String.fromCharCode(1045)) {  // "E" 18jan2012
        if (b16==String.fromCharCode(1058)) {  // "T" 18jan2012
          num = 1;  // singular verb form; 18jan2012
          dba = 3;  // 3rd person verb form; 18jan2012
          bias = 8; // overrule pre-existing setting; 18jan2012
          pos = 8;  // part of speech is 8=verb; 18jan2012
          b01=""; b02=""; b03=""; b04="";  // 18jan2012
          b05=""; b06=""; b07=""; b08="";  // 18jan2012
          b09=""; b10=""; b11=""; b12="";  // 18jan2012 
          b13=""; b14=""; b15=""; b16="";  // 18jan2012
   // alert("AudL: 3rd person verb YET");  // test; 18jan2012
      } }  // end of nested if-clauses; 18jan2012
      if (b15==String.fromCharCode(1045)) {  // "E" 18jan2012
        if (b16==String.fromCharCode(1052)) {  // "M" 18jan2012
          num = 2;  // plural verb form; 18jan2012
          dba = 1;  // 1st person verb form; 18jan2012
          bias = 8; // overrule pre-existing setting; 18jan2012
          pos = 8;  // part of speech is 8=verb; 18jan2012
          b01=""; b02=""; b03=""; b04="";  // 18jan2012
          b05=""; b06=""; b07=""; b08="";  // 18jan2012
          b09=""; b10=""; b11=""; b12="";  // 18jan2012 
          b13=""; b14=""; b15=""; b16="";  // 18jan2012
  //  alert("AudL: 1st person verb YEM");  // test; 18jan2012
      } }  // end of nested if-clauses; 18jan2012
      if (b14==String.fromCharCode(1045)) {  // "E" 18jan2012
        if (b15==String.fromCharCode(1058)) {  // "T" 18jan2012
          if (b16==String.fromCharCode(1045)) {  // "E" 18jan2012
            num = 2;  // plural verb form; 18jan2012
            dba = 2;  // 2nd person verb form; 18jan2012
            bias = 8; // overrule pre-existing setting; 18jan2012
            pos = 8;  // part of speech is 8=verb; 18jan2012
            b01=""; b02=""; b03=""; b04="";  // 18jan2012
            b05=""; b06=""; b07=""; b08="";  // 18jan2012
            b09=""; b10=""; b11=""; b12="";  // 18jan2012 
            b13=""; b14=""; b15=""; b16="";  // 18jan2012
   // alert("AudL: 2nd person verb YETYE");  // test; 18jan2012
      } } }  // end of nested if-clauses; 18jan2012
      if (b15==String.fromCharCode(1070)) {  // "YU" 18jan2012
        if (b16==String.fromCharCode(1058)) {  // "T" 18jan2012
          num = 2;  // plural verb form; 18jan2012
          dba = 3;  // 3rd person verb form; 18jan2012
          bias = 8; // overrule pre-existing setting; 18jan2012
          pos = 8;  // part of speech is 8=verb; 18jan2012
          b01=""; b02=""; b03=""; b04="";  // 18jan2012
          b05=""; b06=""; b07=""; b08="";  // 18jan2012
          b09=""; b10=""; b11=""; b12="";  // 18jan2012 
          b13=""; b14=""; b15=""; b16="";  // 18jan2012
   // alert("AudL: 3rd person verb YUT");  // test; 18jan2012
      } }  // end of nested if-clauses; 18jan2012
    }  // end of test for a space-bar or carriage-return.
    pho = String.fromCharCode(c);
    if (hardcopy == true) {
      inbuffer += pho; 
    }
    ++t;
    if (eot == 13) {
      beg = 1;
      c = 32;
   // output = "";  // end on-screen persistence of output; 6nov2011
   // outputplus = "";  // end on-screen persistence of output.
      phodex = 0;  // reset for AudBuffer(); 12jan2012
    }
    if (c == 32) { // From CR or space-bar; 12jul2010.
      audrun = 1;  // Reset to 1 at end of word; 12jul2010.
      ordo = (ordo + 1);  // 22aug2011
      phodex = 0;  // reset for AudBuffer(); 12jan2012
      if (ordo==1) firstword = audpsi;  // 22aug2011
      AudInput();  // To register a space-bar; 12jul2010.
    }  // End of expanded if-clause; 12jul2010.
    beg = 1;
    ctu = 1;
    pho = pho.toUpperCase();
    abc = pho;  // for transfer to AudBuffer; 12jan2012
    AudBuffer();  // to transfer engrams; 12jan2012
    onset = (spt + 1);
    if (onset == t) beg = 1;
    else beg = 0;
    if (c > 32) {
      len = (len + 1);
      AudMem();
    }
    c = " ";
    pho = " ";
    return true;
  }
}  // End of AudListen(); 29sep2010
 

function Tab() {
  document.forms[1].ear.focus();
  fyi = (fyi + 1);
   if (fyi == 0)  {
    document.all.souvenir.innerHTML = "Cycling through display modes.";
    document.all["cb1"].checked = false;
    document.all["cb2"].checked = false;
    document.all["cb3"].checked = false;
    trouble = false;
   }
   if (fyi == 1)  {
    document.all["cb2"].checked = false;
    document.all["cb3"].checked = false;
    trouble = false;
    document.all.psicolumn.innerHTML = "";
    document.all.rucolumn.innerHTML = "";  // 5jan2012
    document.all.audcolumn.innerHTML = "";
    document.all["cb1"].checked = true;
   }
  if (fyi == 2) {
    document.all["cb1"].checked = false;
    document.all.psicolumn.innerHTML = "";
    document.all.rucolumn.innerHTML = "";  // 5jan2012
    document.all.audcolumn.innerHTML = "";
    document.all["cb3"].checked = false;
    trouble = false;
    document.all.souvenir.innerHTML = "Tutorial has been called.";
    document.all.tabula.innerHTML = "Watch the artificial mind think.";
    document.all["cb2"].checked = true;
    tutor = true;
  }
   if (fyi == 3)  {
    document.all["cb1"].checked = false;
    document.all["cb2"].checked = false;
    document.all.souvenir.innerHTML = "Diagnostic mode has been called.";
    document.all.tabula.innerHTML = "Diagnostic troubleshoot mode.";
    document.all["cb3"].checked = true;
    trouble = true;
   }
  if (fyi > 3) {
    document.all["cb1"].checked = false;
    document.all["cb2"].checked = false;
    document.all["cb3"].checked = false;
    trouble = false;
    document.all.psicolumn.innerHTML = ""; 
    document.all.rucolumn.innerHTML = "";  // 5jan2012
    document.all.audcolumn.innerHTML = "";
    document.all.souvenir.innerHTML = "Tab key changes display modes.";
    fyi = 0;
  }
  TID=window.setTimeout("CR();",1000);
}
 
function CR() {
  document.forms[1].elements[0].value = "";
  if (trouble == true) Diagnostic();
  userline = inbuffer;
  inbuffer = "";
  spt = t;
  audMemory[t] = new audNode(" ",0," "," "," "," ");
  lastword = true;
  audrun = 1; // Reset to 1 at CR end of input; 12jul2010.
  beg = 1;  // no "if CR 13" is required within CR().
  eot = 13; // for use in AudListen() to indicate CR.
  c = 32;   // as if SPACE-BAR "32" were pressed
  phodex = 0;  // a reset at end of word; 12jan2012
  c01=""; c02=""; c03=""; c04=""; c05=""; c06=""; c07=""; c08=""; 
  c09=""; c10=""; c11=""; c12=""; c13=""; c14=""; c15=""; c16="";
  b01=""; b02=""; b03=""; b04=""; b05=""; b06=""; b07=""; b08="";
  b09=""; b10=""; b11=""; b12=""; b13=""; b14=""; b15=""; b16="";
  AudInput();  // Imitating AudListen(); 12jan2012
  eot = 0;
  firstword = 0;  // not valid beyond current input; 1nov2011
  moot = 0;  // assuming end of moot user queries; 1nov2011
  ordo = 0;
  quiet = true;
// output = "";  // end on-screen persistence of output; 6nov2011
// outputplus = "";  // end on-screen persistence of output;
}
 

function AudInput() {
  ordo = (ordo + 1 );
  spt = t;
  upnext = 0;
  if (urpsi > 0) {
    audDamp();
  }
  tult = (t - 1);
  audMemory[tult].audExam();
  audMemory[tult] = new audNode(aud0,aud1,aud2,aud3,0,aud5);
  if (audpsi > 0) {   // 8dec2009 "audpsi" replacing "psi"
    aud = onset;
    audMemory[tult].audExam();
    if (aud4 == 0) {  // If "continuation" is false; 12may2011
      if (pov == "*") {  // only during input; 15jan2012
        recogcon = true;  // word or stem has been recognized; 15jan2012
      }  // end of test for input-only; 15jan2012
      audMemory[tult] = new audNode(aud0,aud1,aud2,aud3,aud4,audpsi);
    }  // end of "aud4" continuation-test; 15jan2012
    if (recogcon == true) {  // is word recognized? 15jan2012
      if (len > 3) {  // if long enough for inflection; 15jan2012
        audMemory[tult-3].audExam();  // far enough back for stem? 15jan2012
        audMemory[tult-3] = new audNode(aud0,aud1,aud2,aud3,aud4,audpsi);
        audMemory[tult-2].audExam();  // two phonemes back; 15jan2012
        audMemory[tult-2] = new audNode(aud0,aud1,aud2,aud3,aud4,audpsi);
        audMemory[tult-1].audExam();  // penujltimate phoneme; 15jan2012
        audMemory[tult-1] = new audNode(aud0,aud1,aud2,aud3,aud4,audpsi);
       }  // end of test of length of recognized word; 15jan2012
       recogcon = false;  // reset after use; 15jan2012
    }  // 15jan2012
    recogcon = false;   // reset; 15jan2012
    oldpsi = audpsi;  // for conformance with MindForth; 3jul2011
    OldConcept();
    psi = 0;
    audpsi = 0;
    aud5 = 0;  // test; remove; 15jan2012
    aud = 0;
  } else {  // i.e., if AudRecog has not recognized word; 12may2011
    if (len > 0) {
      aud = onset;
      NewConcept();  // AudInput() calls NewConcept(); 12may2011
      audMemory[tult].audExam();
      if (aud4 == 0) {
        audMemory[tult] = new audNode(aud0,aud1,aud2,aud3,aud4,nru);
      }
    }
  }
  audDamp();
  len = 0;
  onset = 0;
  aud = 0;
} // End of AudInput; return to AudListen(), CR() or ReEntry().

 
function SensoryInput() {
  // navigator.geolocation.getCurrentPosition(lost,found) // 16oct2010
  if (life == true) {
    document.forms[1].ear.focus();
  }
}


function RuBoot() {  // diverging from English AI; 7jan2012
TuringTest();
act = 0;    // 8dec2009
jux = 0;    // 8dec2009
pov = "#";  // 8dec2009
t = 0;      // 8dec2009
spt = t;    // 8dec2009
// 582 OSHIBKA (error) first word so any bug will announce itself 
t=1;c=1054; beg=1; ctu=1; audpsi=0; 
    pho = String.fromCharCode(c); AudMem();  // 7jan2012
t=2;c=1064; beg=0; ctu=1; audpsi=0; 
    pho = String.fromCharCode(c); AudMem();  // 7jan2012
t=3;c=1048; beg=0; ctu=1; audpsi=0;     
    pho = String.fromCharCode(c); AudMem();  // 7jan2012
t=4;c=1041; beg=0; ctu=1; audpsi=0; 
    pho = String.fromCharCode(c); AudMem();  // 7jan2012
t=5;c=1050; beg=0; ctu=1; audpsi=0; 
    pho = String.fromCharCode(c); AudMem();  // 7jan2012
t=6;c=1040; beg=0; ctu=0; audpsi=582; 
    pho = String.fromCharCode(c); AudMem();  // 7jan2012
nru=582; mfn=2; dba=1; fex=582; pos=5; fin=582; aud=1;
psi=582; num=1; pre=0; seq=0; rux=582; RuVocab(); InNativate();

// 270 AVOS' (maybe) for KbRetro to treat as answer; 9jan2012
t=8;c=1040; beg=1; ctu=1; audpsi=0; 
    pho = String.fromCharCode(c); AudMem();  // 9jan2012
t=9;c=1042; beg=0; ctu=1; audpsi=0; 
    pho = String.fromCharCode(c); AudMem();  // 9jan2012
t=10;c=1054; beg=0; ctu=1; audpsi=0; 
    pho = String.fromCharCode(c); AudMem();  // 9jan2012
t=11;c=1057; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem();  // 9jan2012
t=12;c=1068; beg=0; ctu=0; audpsi=270; 
     pho = String.fromCharCode(c); AudMem();  // 9jan2012
nru=270; mfn=0; dba=0; fex=270; pos=2; fin=270; aud=8;
psi=270; num=0; pre=0; seq=0; rux=800; RuVocab(); InNativate();

// 813 BWIVAT' (to occur) verb; infinitive 9jan2012
t=14;c=1041; beg=1; ctu=1; audpsi=0; 
    pho = String.fromCharCode(c); AudMem();  // 9jan2012
t=15;c=1067; beg=0; ctu=1; audpsi=0; 
    pho = String.fromCharCode(c); AudMem();  // 9jan2012
t=16;c=1042; beg=0; ctu=1; audpsi=0; 
    pho = String.fromCharCode(c); AudMem();  // 9jan2012
t=17;c=1040; beg=0; ctu=1; audpsi=813;  // provisional; 15jan2012
    pho = String.fromCharCode(c); AudMem();  // 9jan2012
t=18;c=1058; beg=0; ctu=1; audpsi=813;  // provisional; 15jan2012 
     pho = String.fromCharCode(c); AudMem();  // 7jan2012
t=19;c=1068; beg=0; ctu=0; audpsi=813; 
     pho = String.fromCharCode(c); AudMem();  // 7jan2012
nru=813; mfn=0; dba=0; fex=813; pos=8; fin=813; aud=14;
psi=813; num=0; pre=0; seq=0; rux=813; RuVocab(); InNativate();

// 800 BWIT' (to be) verb; irreg; infinitive 4jan2012
t=21;c=1041; beg=1; ctu=1; audpsi=0; 
    pho = String.fromCharCode(c); AudMem();  // 7jan2012
t=22;c=1067; beg=0; ctu=1; audpsi=0; 
    pho = String.fromCharCode(c); AudMem();  // 7jan2012
t=23;c=1058; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem();  // 7jan2012
t=24;c=1068; beg=0; ctu=0; audpsi=800; 
     pho = String.fromCharCode(c); AudMem();  // 7jan2012
nru=800; mfn=0; dba=0; fex=800; pos=8; fin=800; aud=21;
psi=800; num=0; pre=0; seq=0; rux=800; RuVocab(); InNativate();
 
// 807 BUDU (will be) verb; irreg; 1st person future 4jan2012
t=26;c=1041; beg=1; ctu=1; audpsi=0;
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=27;c=1059; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=28;c=1044; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=29;c=1059; beg=0; ctu=0; audpsi=807; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=807; mfn=0; dba=1; fex=807; pos=8; fin=800; aud=26;
psi=800; num=1; pre=0; seq=0; rux=807; RuVocab(); InNativate();
 
// 737 VWI (you) pronoun; familiar nom. plural; 11jan2012
t=31;c=1042; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=32;c=1067; beg=0; ctu=0; audpsi=737; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=737; mfn=0; dba=1; fex=737; pos=7; fin=731; aud=31;
psi=737; num=2; pre=0; seq=0; rux=737; RuVocab(); InNativate();
 
// 738 VAS (of you) pronoun; familiar gen. plural; 11jan2012
t=34;c=1042; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=35;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=36;c=1057; beg=0; ctu=0; audpsi=738; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=738; mfn=0; dba=2; fex=738; pos=7; fin=732; aud=34;
psi=737; num=2; pre=0; seq=0; rux=738; RuVocab(); InNativate();

// 739 VAM (to you) pronoun; familiar dat. plural; 11jan2012
t=38;c=1042; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=39;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=40;c=1052; beg=0; ctu=0; audpsi=739; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=739; mfn=0; dba=3; fex=739; pos=7; fin=722; aud=38;
psi=737; num=2; pre=0; seq=0; rux=739; RuVocab(); InNativate();
 
// 740 VAS (you) pronoun; familiar acc. plural; 11jan2012
t=42;c=1042; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=43;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=44;c=1057; beg=0; ctu=0; audpsi=740; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=740; mfn=0; dba=4; fex=740; pos=7; fin=734; aud=42;
psi=737; num=2; pre=0; seq=0; rux=740; RuVocab(); InNativate();
 
// 741 VAMI (you) pron; familiar instrumental plural; 11jan2012
t=46;c=1042; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=47;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=48;c=1052; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=49;c=1048; beg=0; ctu=0; audpsi=741; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=741; mfn=0; dba=5; fex=741; pos=7; fin=735; aud=46;
psi=737; num=2; pre=0; seq=0; rux=741; RuVocab(); InNativate();
 
// 742 VAS (you) pron; familiar prep. plural; 11jan2012
t=51;c=1042; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=52;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=53;c=1057; beg=0; ctu=0; audpsi=786; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=742; mfn=0; dba=6; fex=742; pos=7; fin=736; aud=51;
psi=737; num=2; pre=0; seq=0; rux=742; RuVocab(); InNativate();

// 749 VWI (you) pronoun; formal nom. sing. 2jan2012
t=55;c=1042; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=56;c=1067; beg=0; ctu=0; audpsi=781; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=749; mfn=0; dba=1; fex=749; pos=7; fin=701; aud=55;
psi=749; num=1; pre=0; seq=0; rux=749; RuVocab(); InNativate();
 
// 750 VAS (of you) pronoun; formal gen. sing. 2jan2012
t=58;c=1042; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=59;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=60;c=1057; beg=0; ctu=0; audpsi=750; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=750; mfn=0; dba=2; fex=750; pos=7; fin=702; aud=58;
psi=749; num=1; pre=0; seq=0; rux=750; RuVocab(); InNativate();

// 751 VAM (to you) pronoun; formal dat. sing. 2jan2012
t=62;c=1042; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=63;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=64;c=1052; beg=0; ctu=0; audpsi=751; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=751; mfn=0; dba=3; fex=751; pos=7; fin=703; aud=62;
psi=749; num=1; pre=0; seq=0; rux=751; RuVocab(); InNativate();
 
// 752 VAS (you) pronoun; formal acc. sing. 2jan2012
t=66;c=1042; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=67;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=68;c=1057; beg=0; ctu=0; audpsi=752; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=752; mfn=0; dba=4; fex=752; pos=7; fin=704; aud=66;
psi=749; num=1; pre=0; seq=0; rux=752; RuVocab(); InNativate();
 
// 753 VAMI (you) pron; formal instrumental sing. 2jan2012
t=70;c=1042; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=71;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=72;c=1052; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=73;c=1048; beg=0; ctu=0; audpsi=753; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=753; mfn=0; dba=5; fex=753; pos=7; fin=705; aud=70;
psi=749; num=1; pre=0; seq=0; rux=753; RuVocab(); InNativate();
 
// 754 VAS (you) pron; formal prep. sing. 2jan2012
t=75;c=1042; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=76;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=77;c=1057; beg=0; ctu=0; audpsi=754; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=754; mfn=0; dba=6; fex=754; pos=7; fin=706; aud=75;
psi=749; num=1; pre=0; seq=0; rux=754; RuVocab(); InNativate();

// 755 VWI (you) pronoun; formal nom. plural; 11jan2012
t=79;c=1042; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=80;c=1067; beg=0; ctu=0; audpsi=755; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=755; mfn=0; dba=1; fex=755; pos=7; fin=731; aud=79;
psi=755; num=2; pre=0; seq=0; rux=755; RuVocab(); InNativate();
 
// 756 VAS (of you) pronoun; formal gen. plural 2jan2012
t=82;c=1042; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=83;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=84;c=1057; beg=0; ctu=0; audpsi=756; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=756; mfn=0; dba=2; fex=756; pos=7; fin=732; aud=82;
psi=755; num=2; pre=0; seq=0; rux=756; RuVocab(); InNativate();

// 757 VAM (to you) pronoun; formal dat. plural; 11jan2012
t=86;c=1042; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=87;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=88;c=1052; beg=0; ctu=0; audpsi=757; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=757; mfn=0; dba=3; fex=757; pos=7; fin=733; aud=86;
psi=755; num=2; pre=0; seq=0; rux=757; RuVocab(); InNativate();
 
// 758 VAS (you) pronoun; formal acc. plural; 11jan2012
t=90;c=1042; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=91;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=92;c=1057; beg=0; ctu=0; audpsi=758; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=758; mfn=0; dba=4; fex=758; pos=7; fin=734; aud=90;
psi=755; num=2; pre=0; seq=0; rux=758; RuVocab(); InNativate();
 
// 759 VAMI (you) pron; formal instrumental plural 11jan2012
t=94;c=1042; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=95;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=96;c=1052; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=97;c=1048; beg=0; ctu=0; audpsi=759; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=759; mfn=0; dba=5; fex=759; pos=7; fin=735; aud=94; 
psi=755; num=2; pre=0; seq=0; rux=759; RuVocab(); InNativate();
 
// 760 VAS (you) pron; formal prep. plural; 11jan2012
t=99;c=1042; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=100;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=101;c=1057; beg=0; ctu=0; audpsi=760; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=760; mfn=0; dba=6; fex=760; pos=7; fin=736; aud=99;
psi=755; num=2; pre=0; seq=0; rux=760; RuVocab(); InNativate();

// 432 DA (yes) interjection 4jan2012
t=103;c=1044; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=104;c=1040; beg=0; ctu=0; audpsi=432; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=432; mfn=0; dba=0; fex=432; pos=4; fin=432; aud=103;
psi=432; num=0; pre=0; seq=0; rux=432; RuVocab(); InNativate();

// 820 DELAT' ("to do"); sample verb; 9jan2012
t=106;c=1044; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=107;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=108;c=1051; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=109;c=1040; beg=0; ctu=1; audpsi=820;  // provisional; 15jan2012 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=110;c=1058; beg=0; ctu=1; audpsi=820;  // provisional; 15jan2012
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=111;c=1068; beg=0; ctu=0; audpsi=820; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=820; mfn=0; dba=0; fex=820; pos=8; fin=820; aud=106; 
psi=820; num=0; pre=0; seq=0; rux=820; RuVocab(); InNativate();

// 820 DELAYU ("I do"); sample verb; 9jan2012
t=113;c=1044; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=114;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=115;c=1051; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=116;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=117;c=1070; beg=0; ctu=0; audpsi=820; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=820; mfn=0; dba=1; fex=821; pos=8; fin=823; aud=113; 
psi=820;  num=1; pre=0; seq=0; rux=821; RuVocab(); InNativate();

// 820 DELAYESH ("you do"); sample verb; 17jan2012
t=119;c=1044; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=120;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=121;c=1051; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=122;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=123;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=124;c=1064; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=125;c=1068; beg=0; ctu=0; audpsi=820;  // 17jan2012
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=820; mfn=0; dba=2; fex=820; pos=8; fin=820; aud=119; 
psi=820;  num=1; pre=0; seq=0; rux=820; RuVocab(); InNativate();

// 820 DELAYET ("he does"); sample verb; 9jan2012
t=127;c=1044; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=128;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=129;c=1051; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=130;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=131;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=132;c=1058; beg=0; ctu=0; audpsi=820; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=820; mfn=0; dba=3; fex=820; pos=8; fin=820; aud=127; 
psi=820;  num=1; pre=0; seq=0; rux=820; RuVocab(); InNativate();

// 820 DELAYEM ("we do"); sample verb; 9jan2012
t=134;c=1044; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=135;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=136;c=1051; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=137;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=138;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=139;c=1052; beg=0; ctu=0; audpsi=820; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=820; mfn=0; dba=1; fex=820; pos=8; fin=820; aud=134; 
psi=820;  num=2; pre=0; seq=0; rux=820; RuVocab(); InNativate();

// 820 DELAYETE ("you do"); verb; plural; 9jan2012
t=141;c=1044; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=142;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=143;c=1051; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=144;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=145;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=146;c=1058; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=147;c=1045; beg=0; ctu=0; audpsi=820; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=820; mfn=0; dba=2; fex=820; pos=8; fin=820; aud=141; 
psi=820;  num=2; pre=0; seq=0; rux=820; RuVocab(); InNativate();

// 820 DELAYUT ("they do"); verb; 3rd pers. plural; 9jan2012
t=149;c=1044; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=150;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=151;c=1051; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=152;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=153;c=1070; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=154;c=1058; beg=0; ctu=0; audpsi=820; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=820; mfn=0; dba=3; fex=820; pos=8; fin=820; aud=149; 
psi=820;  num=2; pre=0; seq=0; rux=820; RuVocab(); InNativate();

// 514 DETYI (children) noun; plural; 9jan2012
t=156;c=1044; beg=1; ctu=1; audpsi=0;
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=157;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=158;c=1058; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=159;c=1048; beg=0; ctu=0; audpsi=807; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=514; mfn=0; dba=1; fex=514; pos=5; fin=514; aud=156;
psi=514; num=2; pre=0; seq=0; rux=514; RuVocab(); InNativate();

// 830 DUMAT' ("to think"); verb; infinitive; 9jan2012
t=161;c=1044; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=162;c=1059; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=163;c=1052; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=164;c=1040; beg=0; ctu=1; audpsi=830;  // provisional; 15jan2012 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=165;c=1058; beg=0; ctu=1; audpsi=830;  // provisional; 15jan2012 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=166;c=1068; beg=0; ctu=0; audpsi=830; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=830; mfn=0; dba=0; fex=830; pos=8; fin=830; aud=161; 
psi=830;  num=1; pre=0; seq=0; rux=830; RuVocab(); InNativate();

// 521 DUSHKA ("little soul"); name of the Russian AI; 4jan2012
t=168;c=1044; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=169;c=1059; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=170;c=1064; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=171;c=1050; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=172;c=1040; beg=0; ctu=0; audpsi=521; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=521; mfn=2; dba=1; fex=521; pos=5; fin=521; aud=168; 
psi=521;  num=1; pre=0; seq=0; rux=521; RuVocab(); InNativate();
 
// 803 YEST' ("there is"); verb; 4jan2012
t=174;c=1045; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=175;c=1057; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=176;c=1058; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=177;c=1068; beg=0; ctu=0; audpsi=803; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=803; mfn=0; dba=3; fex=803; pos=8; fin=803; aud=174;
psi=803; num=1; pre=0; seq=0; rux=803; RuVocab(); InNativate();
 
// 840 ZNAT' ("to know"); sample verb; 2jan2012
t=179;c=1047; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=180;c=1053; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=181;c=1040; beg=0; ctu=1; audpsi=840;  // provisional; 15jan2012
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=182;c=1058; beg=0; ctu=1; audpsi=840;  // provisional; 15jan2012 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=183;c=1068; beg=0; ctu=0; audpsi=840; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=840; mfn=0; dba=0; fex=840; pos=8; fin=840; aud=179;
psi=840; num=0; pre=0; seq=0; rux=840; RuVocab(); InNativate();
 
// 360 EE ("and") conjunction; 4jan2012
t=185;c=1048; beg=1; ctu=0; audpsi=360; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=360; mfn=0; dba=1; fex=360; pos=3; fin=360; aud=185;
psi=360; num=0; pre=0; seq=0; rux=360; RuVocab(); InNativate();

// 340 ILI (or) conjunction; 9jan2012
t=187;c=1048; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=188;c=1051; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=189;c=1048; beg=0; ctu=0; audpsi=340; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=340; mfn=0; dba=0; fex=340; pos=3; fin=340; aud=187;
psi=340; num=0; pre=0; seq=0; rux=427; RuVocab(); InNativate();

// 266 INACHE ("else"); conjunction; 9jan2012
t=191;c=1048; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=192;c=1053; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=193;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=194;c=1063; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=195;c=1045; beg=0; ctu=0; audpsi=571; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=571; mfn=1; dba=1; fex=571; pos=5; fin=571; aud=191; 
psi=571;  num=1; pre=0; seq=0; rux=571; RuVocab(); InNativate();

// 791 KTO (who) pronoun; 9jan2012
t=197;c=1050; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=198;c=1058; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=199;c=1054; beg=0; ctu=0; audpsi=791; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=791; mfn=0; dba=1; fex=791; pos=7; fin=791; aud=197;
psi=791; num=1; pre=0; seq=0; rux=791; RuVocab(); InNativate();

// 320 LI (whether) adverb; 9jan2012
t=201;c=1051; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=202;c=1048; beg=0; ctu=0; audpsi=250; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=320; mfn=0; dba=0; fex=320; pos=3; fin=320; aud=201;
psi=320; num=0; pre=0; seq=0; rux=320; RuVocab(); InNativate();

// 587 LYUDI (people) noun; plural; 4jan2012
t=204;c=1051; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=205;c=1070; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=206;c=1044; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=207;c=1048; beg=0; ctu=0; audpsi=587; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=587; mfn=0; dba=1; fex=587; pos=5; fin=587; aud=204;
psi=587; num=2; pre=0; seq=0; rux=587; RuVocab(); InNativate();

// 731 MWI (we) pronoun; 10jan2012
t=209;c=1052; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=210;c=1067; beg=0; ctu=0; audpsi=731; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=731; mfn=0; dba=1; fex=731; pos=7; fin=737; aud=209;
psi=731; num=2; pre=0; seq=0; rux=731; RuVocab(); InNativate();

// 732 NAS (us) pron. genitive plural; 10jan2012
t=212;c=1053; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=213;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=214;c=1057; beg=0; ctu=0; audpsi=732; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=732; mfn=0; dba=2; fex=732; pos=7; fin=738; aud=212;
psi=731; num=2; pre=0; seq=0; rux=732; RuVocab(); InNativate();

// 733 NAM (to us) pron. dative plural; 10jan2012
t=216;c=1053; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=217;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=218;c=1052; beg=0; ctu=0; audpsi=733; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=733; mfn=0; dba=3; fex=733; pos=7; fin=739; aud=216;
psi=731; num=2; pre=0; seq=0; rux=733; RuVocab(); InNativate();

// 734 NAS (us) pron. accusative plural; 10jan2012
t=220;c=1053; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=221;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=222;c=1057; beg=0; ctu=0; audpsi=732; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=734; mfn=0; dba=2; fex=734; pos=7; fin=740; aud=220;
psi=731; num=2; pre=0; seq=0; rux=734; RuVocab(); InNativate();

// 735 NAMI (us) pron; instrumental plural; 10jan2012
t=224;c=1053; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=225;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=226;c=1052; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=227;c=1048; beg=0; ctu=0; audpsi=735; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=735; mfn=0; dba=5; fex=735; pos=7; fin=741; aud=224;
psi=731; num=1; pre=0; seq=0; rux=735; RuVocab(); InNativate();

// 736 NAS (us) pron. prepositional plural; 10jan2012
t=229;c=1053; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=230;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=231;c=1057; beg=0; ctu=0; audpsi=736; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=736; mfn=0; dba=6; fex=736; pos=7; fin=742; aud=229;
psi=731; num=2; pre=0; seq=0; rux=736; RuVocab(); InNativate();
 
// 850 MWISLIT' ("to think"); verb; infinitive; 4jan2012
t=233;c=1052; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=234;c=1067; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=235;c=1057; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=236;c=1051; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=237;c=1048; beg=0; ctu=1; audpsi=850;  // provisional; 15jan2012 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=238;c=1058; beg=0; ctu=1; audpsi=850;  // provisional; 15jan2012 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=239;c=1068; beg=0; ctu=0; audpsi=850; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=850; mfn=0; dba=0; fex=850; pos=8; fin=850; aud=233;
psi=850; num=0; pre=0; seq=0; rux=850; RuVocab(); InNativate();
 
// 250 NYE (not) adverb for negation; 2jan2012
t=241;c=1053; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=242;c=1045; beg=0; ctu=0; audpsi=250; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=250; mfn=0; dba=0; fex=250; pos=2; fin=250; aud=241;
psi=250; num=0; pre=0; seq=0; rux=250; RuVocab(); InNativate();
 
// 427 NYET (no) interjection; 4jan2012
t=244;c=1053; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=245;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=246;c=1058; beg=0; ctu=0; audpsi=427; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=427; mfn=0; dba=0; fex=427; pos=4; fin=427; aud=244;
psi=427; num=0; pre=0; seq=0; rux=427; RuVocab(); InNativate();

// 228 NYETU (is not) adverb; 9jan2012
t=248;c=1053; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=249;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=250;c=1058; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=251;c=1059; beg=0; ctu=0; audpsi=228; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=228; mfn=0; dba=0; fex=228; pos=2; fin=228; aud=248;
psi=228; num=0; pre=0; seq=0; rux=228; RuVocab(); InNativate();

// 860 NICHEGO ("nothing"); pronoun; 9jan2012
t=253;c=1053; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=254;c=1048; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=255;c=1063; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=256;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=257;c=1043; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=258;c=1054; beg=0; ctu=0; audpsi=860; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=860; mfn=0; dba=0; fex=860; pos=8; fin=860; aud=253;
psi=860; num=0; pre=0; seq=0; rux=860; RuVocab(); InNativate();

// 713 ON (he) pronoun; nom. sing. masc. 10jan2012
t=260;c=1054; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=261;c=1053; beg=0; ctu=0; audpsi=713; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=713; mfn=1; dba=1; fex=713; pos=7; fin=713; aud=260;
psi=713; num=1; pre=0; seq=0; rux=713; RuVocab(); InNativate();

// 714 EGO (of him) pronoun; gen. sing. masc. 10jan2012
t=263;c=1045; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=264;c=1043; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=265;c=1054; beg=0; ctu=0; audpsi=714; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=714; mfn=1; dba=2; fex=714; pos=7; fin=714; aud=263;
psi=713; num=1; pre=0; seq=0; rux=714; RuVocab(); InNativate();

// 715 EMU (to him) pronoun; dat. sing. masc. 10jan2012
t=267;c=1045; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=268;c=1052; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=269;c=1059; beg=0; ctu=0; audpsi=715; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=715; mfn=1; dba=3; fex=715; pos=7; fin=715; aud=267;
psi=713; num=1; pre=0; seq=0; rux=715; RuVocab(); InNativate();

// 716 EGO (him) pronoun; acc. sing. masc. 10jan2012
t=271;c=1045; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=272;c=1043; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=273;c=1054; beg=0; ctu=0; audpsi=716; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=716; mfn=1; dba=4; fex=716; pos=7; fin=716; aud=271;
psi=713; num=1; pre=0; seq=0; rux=716; RuVocab(); InNativate();

// 717 IM (him) pronoun; instrumental sing. masc. 10jan2012
t=275;c=1048; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=276;c=1052; beg=0; ctu=0; audpsi=717; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=717; mfn=1; dba=5; fex=717; pos=7; fin=717; aud=275;
psi=713; num=1; pre=0; seq=0; rux=717; RuVocab(); InNativate();

// 717 NYOM (him) pronoun; prepositional sing. masc. 10jan2012
t=278;c=1053; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=279;c=1025; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=280;c=1052; beg=0; ctu=0; audpsi=717; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=717; mfn=1; dba=6; fex=717; pos=7; fin=717; aud=278;
psi=713; num=1; pre=0; seq=0; rux=717; RuVocab(); InNativate();

// 719 ONA (she) pronoun; nom. sing. fem. 10jan2012
t=282;c=1054; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=283;c=1053; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=284;c=1040; beg=0; ctu=0; audpsi=719; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=719; mfn=2; dba=1; fex=719; pos=7; fin=719; aud=282;
psi=719; num=1; pre=0; seq=0; rux=719; RuVocab(); InNativate();

// 720 YEYO (of her) pronoun; gen. sing. fem. 10jan2012
t=286;c=1045; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=287;c=1025; beg=0; ctu=0; audpsi=720; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=720; mfn=2; dba=2; fex=720; pos=7; fin=720; aud=286;
psi=719; num=1; pre=0; seq=0; rux=720; RuVocab(); InNativate();

// 721 YEY (to her) pronoun; dat. sing. fem. 10jan2012
t=289;c=1045; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=290;c=1049; beg=0; ctu=0; audpsi=721; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=721; mfn=2; dba=3; fex=721; pos=7; fin=721; aud=289;
psi=719; num=1; pre=0; seq=0; rux=721; RuVocab(); InNativate();

// 722 YEYO (her) pronoun; acc. sing. fem. 10jan2012
t=292;c=1045; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=293;c=1025; beg=0; ctu=0; audpsi=722; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=722; mfn=2; dba=4; fex=722; pos=7; fin=722; aud=292;
psi=719; num=1; pre=0; seq=0; rux=722; RuVocab(); InNativate();

// 723 YEY (her) pronoun; instrumental. sing. fem. 10jan2012
t=295;c=1045; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=296;c=1049; beg=0; ctu=0; audpsi=723; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=723; mfn=2; dba=5; fex=723; pos=7; fin=723; aud=295;
psi=719; num=1; pre=0; seq=0; rux=723; RuVocab(); InNativate();

// 724 NYEY (her) pronoun; prepositional sing. fem. 10jan2012
t=298;c=1053; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=299;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=300;c=1049; beg=0; ctu=0; audpsi=724; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=724; mfn=2; dba=6; fex=724; pos=7; fin=724; aud=298;
psi=719; num=1; pre=0; seq=0; rux=724; RuVocab(); InNativate();

// 725 ONO (it) pronoun; nom. sing. neuter; 10jan2012
t=302;c=1054; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=303;c=1053; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=304;c=1054; beg=0; ctu=0; audpsi=725; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=725; mfn=3; dba=1; fex=725; pos=7; fin=725; aud=302;
psi=725; num=1; pre=0; seq=0; rux=725; RuVocab(); InNativate();

// 726 EGO (of it) pronoun; gen. sing. neuter; 10jan2012
t=306;c=1045; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=307;c=1043; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=308;c=1054; beg=0; ctu=0; audpsi=726; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=726; mfn=3; dba=2; fex=726; pos=7; fin=726; aud=306;
psi=725; num=1; pre=0; seq=0; rux=726; RuVocab(); InNativate();

// 727 EMU (to it) pronoun; dat. sing. neuter; 10jan2012
t=310;c=1045; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=311;c=1052; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=312;c=1059; beg=0; ctu=0; audpsi=727; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=727; mfn=3; dba=3; fex=727; pos=7; fin=727; aud=310;
psi=725; num=1; pre=0; seq=0; rux=727; RuVocab(); InNativate();

// 728 EGO (it) pronoun; acc. sing. neuter; 10jan2012
t=314;c=1045; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=315;c=1043; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=316;c=1054; beg=0; ctu=0; audpsi=728; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=728; mfn=3; dba=4; fex=728; pos=7; fin=728; aud=314;
psi=725; num=1; pre=0; seq=0; rux=728; RuVocab(); InNativate();

// 729 IM (it) pronoun; instrumental sing. neuter; 10jan2012
t=318;c=1048; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=319;c=1052; beg=0; ctu=0; audpsi=729; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=729; mfn=3; dba=5; fex=729; pos=7; fin=729; aud=318;
psi=725; num=1; pre=0; seq=0; rux=729; RuVocab(); InNativate();

// 730 NYOM (it) pronoun; prepositional sing. neuter; 10jan2012
t=321;c=1053; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=322;c=1025; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=323;c=1052; beg=0; ctu=0; audpsi=730; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=730; mfn=3; dba=6; fex=730; pos=7; fin=730; aud=321;
psi=725; num=1; pre=0; seq=0; rux=730; RuVocab(); InNativate();

// 743 ONI (they) pronoun; nom. plural; 10jan2012
t=325;c=1054; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=326;c=1053; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=327;c=1048; beg=0; ctu=0; audpsi=743; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=743; mfn=0; dba=1; fex=743; pos=7; fin=743; aud=325;
psi=743; num=2; pre=0; seq=0; rux=743; RuVocab(); InNativate();

// 744 IKH (of them) pronoun; gen. plural 10jan2012
t=329;c=1048; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=330;c=1061; beg=0; ctu=0; audpsi=744; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=744; mfn=0; dba=2; fex=744; pos=7; fin=744; aud=329;
psi=743; num=2; pre=0; seq=0; rux=744; RuVocab(); InNativate();

// 745 IM (to them) pronoun; dative plural; 10jan2012
t=332;c=1048; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=333;c=1052; beg=0; ctu=0; audpsi=745; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=745; mfn=0; dba=3; fex=745; pos=7; fin=745; aud=331;
psi=743; num=2; pre=0; seq=0; rux=745; RuVocab(); InNativate();

// 746 IKH (them) pronoun; acc. plural 10jan2012
t=335;c=1048; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=336;c=1061; beg=0; ctu=0; audpsi=746; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=746; mfn=0; dba=4; fex=746; pos=7; fin=746; aud=335;
psi=743; num=2; pre=0; seq=0; rux=746; RuVocab(); InNativate();

// 747 IMI (them) pronoun; instrumental plural; 10jan2012
t=338;c=1048; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=339;c=1052; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=340;c=1048; beg=0; ctu=0; audpsi=747; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=747; mfn=0; dba=5; fex=747; pos=7; fin=747; aud=338;
psi=743; num=2; pre=0; seq=0; rux=747; RuVocab(); InNativate();

// 748 NIKH (they) pronoun; prepositional plural; 10jan2012
t=342;c=1053; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=343;c=1048; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=344;c=1061; beg=0; ctu=0; audpsi=748; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=748; mfn=0; dba=6; fex=748; pos=7; fin=748; aud=342;
psi=743; num=2; pre=0; seq=0; rux=748; RuVocab(); InNativate();

// 860 PONIMAT' ("to understand"); sample verb; 2jan2012
t=346;c=1055; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=347;c=1054; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=348;c=1053; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=349;c=1048; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=350;c=1052; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=351;c=1040; beg=0; ctu=1; audpsi=860;  // provisional; 15jan2012 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=352;c=1058; beg=0; ctu=1; audpsi=860;  // provisional; 15jan2012 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=353;c=1068; beg=0; ctu=0; audpsi=860; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=860; mfn=0; dba=0; fex=860; pos=8; fin=860; aud=346;
psi=860; num=0; pre=0; seq=0; rux=860; RuVocab(); InNativate();

// 370 POCHEMU ("why"); conjunction; 9jan2012
t=355;c=1055; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=356;c=1054; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=357;c=1063; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=358;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=359;c=1052; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=360;c=1059; beg=0; ctu=0; audpsi=370; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=370; mfn=0; dba=0; fex=370; pos=3; fin=370; aud=355;
psi=370; num=0; pre=0; seq=0; rux=370; RuVocab(); InNativate();

// 571 ROBOT ("robot"); noun; nominative 4jan2012
t=362;c=1056; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=363;c=1054; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=364;c=1041; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=365;c=1054; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=366;c=1058; beg=0; ctu=0; audpsi=571; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=571; mfn=1; dba=1; fex=571; pos=5; fin=571; aud=362; 
psi=571;  num=1; pre=0; seq=0; rux=571; RuVocab(); InNativate();

// 680 S ("with") preposition; 4jan2012
t=368;c=1057; beg=1; ctu=0; audpsi=680; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=680; mfn=0; dba=0; fex=680; pos=6; fin=680; aud=368;
psi=680; num=0; pre=0; seq=0; rux=680; RuVocab(); InNativate();
 
// 681 SO ("with") preposition; 4jan2012
t=370;c=1057; beg=1; ctu=1; audpsi=0; AudMem();
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=371;c=1054; beg=0; ctu=0; audpsi=681; AudMem();
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=681; mfn=0; dba=0; fex=681; pos=6; fin=680; aud=370;
psi=680; num=0; pre=0; seq=0; rux=681; RuVocab(); InNativate();

// 170 TAKOYE ("such"); adjective; 9jan2012
t=373;c=1058; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=374;c=1040; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=375;c=1050; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=376;c=1054; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=377;c=1045; beg=0; ctu=0; audpsi=170; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=170; mfn=3; dba=1; fex=170; pos=1; fin=170; aud=373;
psi=170; num=0; pre=0; seq=0; rux=170; RuVocab(); InNativate();

// 880 TREBOVAT' ("to demand"); verb; infinitive; 4jan2012
t=379;c=1058; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=380;c=1056; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=381;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=382;c=1041; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=383;c=1054; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=384;c=1042; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=385;c=1040; beg=0; ctu=1; audpsi=880;  // provisional; 15jan2012 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=386;c=1058; beg=0; ctu=1; audpsi=880;  // provisional; 15jan2012
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=387;c=1068; beg=0; ctu=0; audpsi=880; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=880; mfn=0; dba=0; fex=880; pos=8; fin=880; aud=379;
psi=880; num=0; pre=0; seq=0; rux=880; RuVocab(); InNativate();
 
// 707 TY ("you") pronoun; familiar; nom. sing. 11jan2012
t=389;c=1058; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=390;c=1067; beg=0; ctu=0; audpsi=707; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=707; mfn=0; dba=1; fex=707; pos=7; fin=701; aud=389;
psi=707; num=1; pre=0; seq=0; rux=707; RuVocab(); InNativate();
 
// 707 TEBYA ("of you") pronoun; familiar; gen. sing. 21jan2012
t=392;c=1058; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=393;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=394;c=1041; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=395;c=1071; beg=0; ctu=0; audpsi=707;  // 21jan2012
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=707; mfn=0; dba=2; fex=707; pos=7; fin=701; aud=392;
psi=707; num=1; pre=0; seq=0; rux=707; RuVocab(); InNativate();

// 707 TEBYE ("to you") pronoun; familiar; dat. sing. 4jan2012
t=397;c=1058; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=398;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=399;c=1041; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=400;c=1045; beg=0; ctu=0; audpsi=707;  // 21jan2012
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=707; mfn=0; dba=3; fex=707; pos=7; fin=701; aud=397;
psi=707; num=1; pre=0; seq=0; rux=707; RuVocab(); InNativate();
 
// 707 TEBYA ("you") pronoun; familiar; acc. sing. 21jan2012
t=402;c=1058; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=403;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=404;c=1041; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=405;c=1071; beg=0; ctu=0; audpsi=707;  // 21jan2012
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=707; mfn=0; dba=4; fex=707; pos=7; fin=701; aud=402;
psi=707; num=1; pre=0; seq=0; rux=707; RuVocab(); InNativate();
 
// 707 TOBOY ("you") pronoun; familiar; instrumental sing. 21jan2012
t=407;c=1058; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=408;c=1054; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=409;c=1041; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=410;c=1054; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=411;c=1049; beg=0; ctu=0; audpsi=701;  // 21jan2012
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=707; mfn=0; dba=5; fex=707; pos=7; fin=701; aud=407;
psi=707; num=1; pre=0; seq=0; rux=707; RuVocab(); InNativate();

// 707 TEBYE ("you") pronoun; familiar; prep. sing. 4jan2012
t=413;c=1058; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=414;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=415;c=1041; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=416;c=1045; beg=0; ctu=0; audpsi=707;  // 21jan2012
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=707; mfn=0; dba=6; fex=707; pos=7; fin=701; aud=413;
psi=707; num=1; pre=0; seq=0; rux=707; RuVocab(); InNativate();

// 816 KHOCHU ("want") verb; 1st pers. sing. 11jan2012
t=418;c=1061; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=419;c=1054; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=420;c=1063; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
t=421;c=1059; beg=0; ctu=0; audpsi=816; 
     pho = String.fromCharCode(c); AudMem(); // 9jan2012
nru=816; mfn=0; dba=6; fex=816; pos=8; fin=816; aud=418;
psi=811; num=1; pre=0; seq=0; rux=616; RuVocab(); InNativate();

// 581 CHELOVEK ("human being") noun; nom. sing. 4jan2012
t=423;c=1063; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=424;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=425;c=1051; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=426;c=1054; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=427;c=1042; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=428;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=429;c=1050; beg=0; ctu=0; audpsi=581; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=581; mfn=1; dba=1; fex=581; pos=5; fin=581; aud=423; 
psi=581;  num=1; pre=0; seq=0; rux=581; RuVocab(); InNativate();

// 781 CHTO (what) pronoun; nominative singular 10jan2012
t=431;c=1063; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=432;c=1058; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=433;c=1054; beg=0; ctu=0; audpsi=781; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=781; mfn=3; dba=1; fex=781; pos=7; fin=781; aud=431; 
psi=781; num=1; pre=0; seq=0; rux=781; RuVocab(); InNativate();

// 310 CHTO (that) conjunction; 10jan2012
t=435;c=1063; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=436;c=1058; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=437;c=1054; beg=0; ctu=0; audpsi=310; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=310; mfn=0; dba=0; fex=310; pos=3; fin=310; aud=435;
psi=310; num=0; pre=0; seq=0; rux=310; RuVocab(); InNativate();

// 701 YA (I) pronoun; nom. sing. 2jan2012
t=439;c=1071; beg=1; ctu=0; audpsi=701; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=701; mfn=0; dba=1; fex=701; pos=7; fin=707; aud=439;
psi=701; num=1; pre=0; seq=831; rux=701; RuVocab(); InNativate();
 
// 701 MENYA ("of me") pronoun; familiar; gen. sing. 21jan2012
t=441;c=1052; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=442;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=443;c=1053; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=444;c=1071; beg=0; ctu=0; audpsi=701;  // 21jan2012
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=701; mfn=0; dba=2; fex=701; pos=7; fin=707; aud=441;
psi=701; num=1; pre=0; seq=0; rux=701; RuVocab(); InNativate();

// 701 MNYE ("to me") pronoun; familiar; dat. sing. 21jan2012
t=446;c=1052; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=447;c=1053; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=448;c=1045; beg=0; ctu=0; audpsi=701;  // 21jan2012
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=701; mfn=0; dba=3; fex=701; pos=7; fin=707; aud=446;
psi=701; num=1; pre=0; seq=0; rux=701; RuVocab(); InNativate();

// 701 MENYA ("me") pronoun; familiar; acc. sing. 21jan2012
t=450;c=1052; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=451;c=1045; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=452;c=1053; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=453;c=1071; beg=0; ctu=0; audpsi=701;  // 21jan2012
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=701; mfn=0; dba=4; fex=701; pos=7; fin=707; aud=450;
psi=701; num=1; pre=0; seq=0; rux=701; RuVocab(); InNativate();

// 701 MNOY ("me") pronoun; familiar; instr. sing. 4jan2012
t=455;c=1052; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=456;c=1053; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=457;c=1054; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=458;c=1049; beg=0; ctu=0; audpsi=701;  // 21jan2012
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=701; mfn=0; dba=5; fex=701; pos=7; fin=707; aud=455;
psi=701; num=1; pre=0; seq=0; rux=701; RuVocab(); InNativate();

// 701 MNYE ("me") pronoun; familiar; prep. sing. 21jan2012
t=460;c=1052; beg=1; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=461;c=1053; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
t=462;c=1045; beg=0; ctu=0; audpsi=701;  // 21jan2012
     pho = String.fromCharCode(c); AudMem(); // 7jan2012
nru=701; mfn=0; dba=6; fex=701; pos=7; fin=707; aud=460;
psi=701; num=1; pre=0; seq=0; rux=701; RuVocab(); InNativate();

// 501 BOG (God) noun, singular; 9jan2012
t=464;c=1041; beg=1; ctu=1; audpsi=0; 
    pho = String.fromCharCode(c); AudMem();  // 9jan2012
t=465;c=1054; beg=0; ctu=1; audpsi=0; 
     pho = String.fromCharCode(c); AudMem();  // 9jan2012
t=466;c=1043; beg=0; ctu=0; audpsi=501; 
     pho = String.fromCharCode(c); AudMem();  // 9jan2012
nru=501; mfn=1; dba=1; fex=501; pos=5; fin=501; aud=464;
psi=501; num=1; pre=0; seq=0; rux=501; RuVocab(); InNativate();
t = 476;  // approximate source of "vault" value; 9jan2012
  audpsi = 0;  // lest pass through AudInput to EnParser; 22aug2011
  indefartcon = 0;  // lest WHO trigger EnArticle; 17jun2011
  psi = 0;
  pre = 0;
  t = (t+1);
  vault = t;
  t = (t+1);
  spt = t;
  nlt = t;
  tov = t;  // For the sake of EnReify(); 24may2011
  pho=" ";
  nru = 900; // to avoid confusion with verbs; 12jan2012 
  bias = 5;  // from MindForth; 15oct2010
  lurk = 0;  // 15oct2010
  mfn = 0;  // prevent carry-over; 15oct2010
  num = 0;
  apb = "RuBoot: Russian bootstrap has loaded; calling MainLoop()";
  Voice();
  document.forms[1].ear.focus();
  MainLoop();
}  // end of RuBoot Russian bootstrap; 5jan2012


function KbTraversal() {
  if (kbtv==0) kbtv = 1;  // Input sets to zero; 23may2011
  apb=("Rejuvenation count is at " + rjc); // 24may2011
  if (kbtv==1) {  // State the concept by name; 20may2011
    apb=("KbTraversal activates concept of YOU in the knowledge base.");
  }  // End of test to identify concept by name; 20may2011
  if (kbtv==2) {  // State the concept by name; 20may2011
    apb=("KbTraversal activates concept of ROBOT in the knowledge base.");
  }  // End of test to identify concept by name; 20may2011
  if (kbtv==3) {  // State the concept by name; 20may2011
    apb=("KbTraversal activates concept of I in the knowledge base.");
  }  // End of test to identify concept by name; 20may2011
  if (kbtv==4) {  // State the concept by name; 20may2011
    apb=("KbTraversal activates concept of GOD in the knowledge base.");
  }  // End of test to identify concept by name; 20may2011
  Voice(); // speak the all-points-bulletin "apb"; 29sep2010  
  pov = "#";  // Internal point-of-view; 24may2011
  if (kbtv > 4) kbtv = 1;
  if (kbtv==1) {
    kbyn = 1;  // for AskUser Y/N query subject; 30jun2011
    psi = 707;    // Russian "Ty" for "you"; 11jan2012
    nacpsi = 707; // Russian "Ty" for "you"; 11jan2012
    qusub = 707;  // Russian "Ty" for "you"; 11jan2012
    subjpsi = 56;  // a test to help WhoBe; 13aug2010
    nounval = 62;
    defcon = nounval;  // force majeure into NounAct; 17nov2010
    NounAct();
    nacpsi = 0;  // reset for safety; 13aug2010
  }
  if (kbtv==2) {
    kbyn = 2;  // for AskUser Y/N query subject; 30jun2011
    psi = 571;   // 571=ROBOT (robot); 11jan2012
    nacpsi = 571;  // 11jan2012
    qusub = 571;  // in case a query will be made; 11jan2012
    subjpsi = 571;  // provisional subject of a query; 11jan2012
    nphrnum = 1;  // prescriptive for sing. ROBOT; 11jan2012
    nounval = 62;
    defcon = nounval;  // force majeure into NounAct; 17nov2010
    NounAct();
    nacpsi = 0;  // reset for safety; 13aug2010
  }
  if (kbtv==3) {
    kbyn = 3;  // for AskUser Y/N query subject; 30jun2011
    psi = 701;  // 701=YA (I); 11jan2012
    nacpsi = 701;  // 11jan2012
    qusub = 701;  // in case a query will be made; 11jan2012
    subjpsi = 701;  // provisional subject of a query; 11jan2012
    nounval = 8;  // test; 27oct2011
    defcon = nounval;  // force majeure into NounAct; 17nov2010
    NounAct();
    nacpsi = 0;  // reset for safety; 13aug2010
  }
  if (kbtv==4) {
    kbyn = 4;  // for AskUser Y/N query subject; 30jun2011
    psi = 501;  // 501=BOG (God); 11jan2012
    nacpsi = 501;  // noun-activation-psi; 11jan2012
    qusub = 501;  // in case a query will be made; 11jan2012
    subjpsi = 501;  // provisional subject of a query; 11jan2012
    nounval = 62;
    defcon = nounval;  // force majeure into NounAct; 17nov2010
    NounAct();
    nacpsi = 0;  // reset for safety; 13aug2010
  }
  defcon = 0;   // reset for safety; 17nov2010
  lurk = 0;  // reset invoker of KbTraversal; 17nov2010
  nounval = 0;  // reset for safety; 17nov2010
}  // End of KbTraversal; return to ReJuvenate or ThInk;  7jul2011
 
 
function ReJuvenate() {
  edge = 0;
  rjc = (rjc+1);
  if (rjc > 99999) rjc = 1; 
    apb=("<font color='red'>"+"Rejuvenating; please wait!"+"<\/font>");
    Voice();
  for (i = (vault+coda); i<(t+2); ++i) {
    jrt = (i - coda);
    if (edge == 1) {
      Psi[i].psiExam();  // fixing 22aug08A.html JSAI bug; 12jul2011:
      Psi[jrt] = new psiNode(psi0,psi1,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
      Psi[i] = new psiNode(" "," "," "," "," "," "," "," "," "); // 13oct
    }
    if (edge == 1) {
      ruLexicon[i].ruExam();  // 5jan2012
     // if (en8 > (vault+coda)) { // 4jan2012
        if (ru8 > (vault+coda)) { // 6jan2012
          ru8 = (ru8 - coda); // 5jan2012
        } // 5jan2012
      ruLexicon[jrt] = new ruNode(ru0,ru1,ru2,ru3,ru4,ru5,ru6,ru7,ru8);
      ruLexicon[i] = new ruNode(" "," "," "," "," "," "," "," "," ");
    }
    if (edge == 1) {
      audMemory[i].audExam();
      audMemory[jrt] = new audNode(aud0,aud1,aud2,aud3,aud4,aud5);
      audMemory[i] = new audNode(" ",0," "," "," "," ");
    }
    if (edge == 0) {
      audMemory[i].audExam();
   // if (aud2 == "{") edge = true;
      if (aud2 == "{") edge = 1;  // a one-time switch; 14jul2011
      audMemory[jrt] = new audNode(" ",0," "," "," "," ");
      ruLexicon[jrt] = new  ruNode(" "," "," "," "," "," "," "," "," ");
      Psi[jrt] = new psiNode(" "," "," "," "," "," "," "," "," "); 
    }
  }
  t = jrt;
  for (j = t; j < cns; ++j) {  // adding " " for enNode; 5apr2010
    audMemory[j] = new audNode(" ",0," "," "," "," "); // 6jan2012:
    ruLexicon[j] = new  ruNode(" "," "," "," "," "," "," "," "," ");
          Psi[j] = new psiNode(" "," "," "," "," "," "," "," "," ");
  }
  kbtv = (kbtv + 1);
  if (kbtv > 0) {
    KbTraversal();
  }
}  // End of ReJuvenate(); return to SeCurity(); 12jul2011
 
function EmotiOn() {
  apb = "EmotiOn module has been called.";
  Voice();
}
 
 
function ReEntry() {
  pov = "#";
  t = (t + 1);
  onset = (spt + 1);
  upnext = (upnext + 1);
  if (upnext == 1) {
    if (urpsi > 1) {
    }
  }
  if (onset == t) beg = 1;
  else beg = 0;
  if (pho != 32) {
    len = (len +1);
    AudMem();
  }  // End of test that input "pho" is not a "space".
  if (pho == 32) { // If pho is a "space".
    audrun = 1;  // Reset to 1 at end of word; 13jul2010
    AudInput();  // Re-entry into audition; 13jul2010
  }  // End of test for space-bar re-entry; 13jul2010
}  // End of ReEntry(); return to SpeechAct().
 
function Voice() {
outputplus = ("<font size='+3' color='navy'>"+output+"<\/b><\/font>");
  document.all.mouth.innerHTML = outputplus;
  document.all.brain.innerHTML = apb;
}
 
function SpeechAct() {  // output of a word as text or sound
  if (aud == 0) aud = 1;  // say diagnostic "ERROR"; 16jul2011
  ctu = 1;
  spt = (t - 1 );
  do {
    audMemory[aud].audExam();
    pho = aud0;
    lastpho = aud0;  // Keep track of previous pho. 2sep2010
    output += aud0;
    ctu = aud4;
    pov = "#";
    ReEntry();
    aud = (aud + 1);
  }
  while (ctu == 1);
  if (ctu == 0) {
    pho = 32;
    ReEntry();
  }
  output += " ";
  Voice();
}  // End of SpeechAct(); 13aug2010

 
function AuxVerb() {  // 12jan2012
  // Removing code for English "DO" or "DOES"; 12jan2012
  // Saving AuxVerb() for Russian MOGU or KHOCHU; 12jan2012
}  // End of AuxVerb()


function WhatSVerb() {  // What Do Subjects Verb; 10jan2012
  for (i = t; i>midway; i--) {  // search backwards in time.
    ruLexicon[i].ruExam();  // examine Russian lexixon; 10jan2012
    if (ru0 == 781) {  // 781=CHTO (what); 10jan2012
      aud = ru8; // beginning of auditory engram; 10jan2012
      break;  // one instance is enough; 10jan2012
    }
  }
  SpeechAct();
  for (i = t; i>midway; i--) {
    ruLexicon[i].ruExam();
    if (ru0 == topic) {  // if same subject found; 10jan2012
      aud = ru8;  // recall-vector for subject topic; 10jan2012
      break;  // one instance is enough; 10jan2012
    }  // end of test to find "topic"; 10jan2012
  }  // end of backwards loop; 10jan2012
  SpeechAct();
  if (verbpsi == 0) verbpsi = 820;  // 820=Delat' default;
  for (i = t; i>midway; i--) {
    ruLexicon[i].ruExam();
    if (ru0 == verbpsi) {  // if concept number of verb; 10jan2012
      if (ru2 == 2) {  // assume plural is like infinitive; 10jan2012
        aud = ru8; // recall-vector for verb-form; 10jan2012
        break;  // one instance is enough; 10jan2012
      }  // end of test for plural verb as if infinitive; 10jan2012
    }  // end of test to find same verb; 10jan2012
  }  // end of backwards loop; 10jan2012
  if (aud==0) {  // if no plural accept singular; 10jan2012
    for (i = t; i>midway; i--) {  // search backwards; 10jan2012
      ruLexicon[i].ruExam();  // examine Russian lexicon; 10jan2012
      if (ru0 == verbpsi) {  // if concept number of verb; 10jan2012
        aud = ru8; // recall-vector for verb-form; 10jan2012
        break;  // one instance is enough; 10jan2012
      }  // end of test to find same verb; 10jan2012
    }  // end of backwards loop; 10jan2012
  }  // end of test for no engram found; 10jan2012
  SpeechAct();
}  // end of Russian WhatSVerb module; 10jan2012


function WhatSDo() {  // modified from WhatAuxSDo(); 10jan2012
  tov = t;
  for (i = t; i>midway; i--) {
    ruLexicon[i].ruExam();
    if (ru0 == 781) {  // 781=CHTO (what); 10jan2012
      aud = ru8; // 10jan2012
      break;  // exit loop after first find; 10jan2012
    }
  }
  SpeechAct();
  flex1 = "";  // reset for safety; 10jan2012
  for (i = t; i>midway; i--) { 
    ruLexicon[i].ruExam();  
    if (ru0 == 820) {  // 820=DELAT' ("do"); 10jan2012
      aud = ru8; // 10jan2012
      break;  // exit loop after first find; 10jan2012
    } 
  }
  SpeechAct();
  topic = ""; 
}  // 10jan2012

 
function WhoBe() {  // for asking WHO IS-AM-ARE; 10jan2012
  moot = 1;  // prevent storage of spurious ideas; 10jan2012
  if (topic > 0) qusub = topic;  // not yet definite source; 3aug2011
  if (subjpsi > 0) qusub = subjpsi;  // not yet sure source; 3aug2011
  for (i = t; i>midway; i--) {  // first look for 55=WHO; 13aug2010
    ruLexicon[i].ruExam();  // examine Russian lexicon; 10jan2012
    if (ru0 == 791) {  // if 791=KTO (who) is found; 10jan2012
      aud = ru8;  // assign most recent recall-tag; 10jan2012
      break;  // exit the loop after first find; 10jan2012
    }  // end of test for 791=KTO (who); 10jan2012 
  }  // end of loop in search of 791=KTO (who); 10jan2012
  SpeechAct();  // say word starting at "aud" value; 10jan2012
  if (subjpsi==701) prsn=1; // 1st person "I"; 10jan2012
  if (subjpsi==731) prsn=1; // 1st person "WE" 10jan2012
  if (subjpsi==707) prsn=2; // 2nd person YOU; 11jan2012
  if (subjpsi==713) prsn=3; // 3rd person HE;  10jan2012
  if (subjpsi==719) prsn=3; // 3rd person SHE; 10jan2012
  if (subjpsi==725) prsn=3; // 3rd person IT;  10jan2012
  if (subjpsi==743) prsn=3; // 3rd person THEY; 10jan2012
  for (i = t; i>midway; i--) { // search for who-query subject
    ruLexicon[i].ruExam();  // examine Russian lexicon; 6jan2012
    if (ru0 == qusub) {  // if qusub found; 6jan2012
      motjuste = qusub;  // also = ru0; 6jan2012
      aud = ru8;  // assign most recent recall-tag; 6jan2012
      break;  // one exemplar is enough; 10jan2012
    }  // end of test for subject; 10jan2012
  }  // end of search-loop; 10jan2012
  SpeechAct();  // say word starting at "aud" value; 10jan2012
  if (recon != 250) recon = 0;  // test for yes-or-no; 6jan2012
  moot = 0;  // end of not tagging query-concepts; 10jan2012 
}  // End of WhoBe(); return to AskUser(); 10jan2012


function WhatBe() {  // what AM/IS/ARE Subjects
  moot = 1;  // prevent storage of spurious ideas; 24oct2011
  for (i = t; i>midway; i--) {  // 19jun2011
    ruLexicon[i].ruExam();  // 10jan2012
    if (ru0 == 781) {  // 781=CHTO (what); 10jan2012
      aud = ru8; // 10jan2012
      break;  // 19jun2011
    }  // 19jun2011
  }  // end of search loop; 19jun2011
  SpeechAct();  // 19jun2011
  for (i = t; i>midway; i--) { // 19jun2011
    ruLexicon[i].ruExam(); // 10jan2012
    if (ru0 == qusub) {  // 10jan2012
      aud = ru8; // 10jan2012
      break;     // 19jun2011
    } // end of test for subjpsi;  5jul2011
  }  // end of search of En array; 19jun2011
  SpeechAct();  // 19jun2011
  PsiDecay();  // from MindForth;  3jul2011
  for (i = t; i>midway; i--) {  // 11jan2012
    ruLexicon[i].ruExam();  // 11jan2012
    if (ru0 == 170) {  // 170=TAKOYE for idiomatic questions.
      aud = ru8; // recall-vector; 11jan2012
      break;  // one engram is enough; 11jan2012
    }  // end of test for 170=TAKOYE; 11jan2012
  }  // end of search loop; 11jan2012
  SpeechAct();  // speak word starting at "aud" location; 11jan2012
  cognum = 0;  // reset for safety; 27oct2011
  cogpsi = 0;  // let another new word call WhatBe; 18oct2011
  indefmust = 0;  // reset for safety; 23oct2011
  moot = 0;  // resume associative tagging of valid ideas; 24oct2011
  qusub = 0;  // reset for safety; 27oct2011
  qusubnum = 0;  // reset for safety; 27oct2011
}  // End of WhatBe(); 27oct2011
 
 
function AskUser() {  // selector of question formats; 13aug2010
  if (posflag==7 || posflag==5) {  // noun or pronoun; 13aug2010
//  WhoBe();  // to generate a who-question; 13aug2010; 15oct2010
  }  // end of test of posflag; 13aug2010
  if (kbyn == 0) {  // 30jun2011
    qusub = 571;  // start with 571=ROBOT (robot); 11jan2012
    prsn = 3;  // third person; 30jun2011
    numsubj = 1;  // singular; 11jan2012
    subjnum = 1;  // singular; 11jan2012
  }  // 30jun2011
  if (ynverb == 0) {  // ask y/n question only once; 30jun2011
    ynverb = quverb;  // isolate at start; 30jun2011
    if (kbyn == 1) {  // from KbTraversal; 30jun2011
      qusub = 707;  // 707=TY (you) to ask questions about; 11jan2012
      prsn = 2;  // YOU is second person; 30jun2011
      numsubj = 1;  // assume YOU is singular; 30jun2011
      subjnum = 1;  // assume YOU is singular; 20jul2011
    }  // end of test for KbTraversal; 30jun2011
    if (kbyn == 2) {  // from KbTraversal; 30jun2011
      qusub = 571;  // 571=ROBOT (robot) to ask questions about.
      prsn = 3;  // ROBOT is third person; 11jan2012
      numsubj = 1;  // singular; 11jan2012
      subjnum = 2;  // singular; 11jan2012
    }  // end of test for KbTraversal; 30jun2011
    if (kbyn == 3) {  // from KbTraversal; 30jun2011
      qusub = 701;  // 701=YA (I) to ask questions about; 11jan2012
      prsn = 1;  // "I" is first person; 30jun2011
      numsubj = 1;  // since "I" is singular; 30jun2011
      subjnum = 1;  // since "I" is singular; 20jul2011
    }  // end of test for KbTraversal; 30jun2011
    if (kbyn == 4) {  // from KbTraversal; 30jun2011
      qusub = 501;  // 501=BOG (God) to ask questions about.
      prsn = 3;  // GOD is third person; 30jun2011
      numsubj = 1;  // GOD is singular; 30jun2011
      subjnum = 1;  // GOD is singular; 20jul2011
    }  // end of test for KbTraversal; 30jun2011
    for (i = t; i>midway; i--) {  // seek query-subject; 30jun2011
      ruLexicon[i].ruExam();  // examine Russian lexicon; 11jan2012
      if (ru0 == qusub) {  // if query-subject found; 11jan2012
        aud = ru8;  // assign auditory recall-tag; 11jan2012
        break;  // exit the loop after first find; 30jun2011
      }  // end of test for query-subject; 30jun2011
    }  // end of loop in search of qusub; 30jun2011
    SpeechAct();  // say word starting at "aud" value; 30jun2011
    tkbn = t; // if engram is to be changed; 29jun2011
    nacpsi = qusub;  // 30jun2011
    nounval = 62;  // 22jun2011 
    NounAct();  // 22jun2011
    for (i = t; i>midway; i--) {  // 11jan2012
      ruLexicon[i].ruExam();  // 11jan2012
      if (ru0 == 320) {  // 320=LI (whether) for asking a question.
        aud = ru8; // recall-vector; 11jan2012
        break;  // one engram is enough; 11jan2012
      }  // end of test for 320=LI; 11jan2012
    }  // end of search loop; 11jan2012
    SpeechAct();  // speak word starting at "aud" location; 11jan2012
    if (quverb == 0) quverb = 820;  // 820=DELAT' (do) by default.
    for (i = t; i>midway; i--) {  // seek yn query-verb; 30jun2011
      ruLexicon[i].ruExam();  // examine Russian lexicon; 11jan2012
      if (ru0 == quverb) {  // if yn query-verb found; 11jan2012
        aud = ru8;  // assign most recent recall-tag; 11jan2012
        break;  // exit the loop after first find; 30jun2011
      }  // end of test for quverb; 30jun2011
    }  // end of loop in search of yn quverb; 30jun2011
    nacpsi = ynverb;  // transfer activand; 30jun2011
    verbval = 62;  // prime VerbAct(); 30jun2011
    VerbAct();  // activate the yn query verb; 25jun2011
    SpeechAct();  // say word starting at "aud" value; 30jun2011
    tkbv = t; // if engram is to be changed; 30jun2011
 // if (quobj == 0) quobj = 110;  // 110=ANYTHING default; 19jul2011
    for (i = t; i>midway; i--) {  // look for quobj; 30jun2011
      ruLexicon[i].ruExam();  // examine Russian lexicon; 11jan2012
      if (ru0 == quobj) {  // if query-object found; 11jan2012
        aud = ru8;  // assign most recent recall-tag; 11jan2012
        break;  // exit the loop after first find; 30jun2011
      }  // end of test for quobj; 30jun2011
    }  // end of loop in search of quobj; 30jun2011
    SpeechAct();  // say word starting at "aud" value; 30jun2011
    yncon = 0;  // because question has been asked; 30jun2011
    kbcon = 1;  // because waiting for answer; 30jun2011
    ynverb = 0;  // zero out; prevent repeat of query; 30jun2011
  }  // end of test of ynverb; 30jun2011
  if (subjpsi==701) prsn=1; // 1st person "I"; 11jan2012
  if (subjpsi==731) prsn=1; // 1st person "WE" 11jan2012
  if (subjpsi==707) prsn=2; // 2nd person YOU; 11jan2012
  if (subjpsi==713) prsn=3; // 3rd person HE;  11jan2012
  if (subjpsi==719) prsn=3; // 3rd person SHE; 11jan2012
  if (subjpsi==725) prsn=3; // 3rd person IT;  11jan2012
  if (subjpsi==743) prsn=3; // 3rd person THEY; 11jan2012
  numsubj = 0;  // reset for safety; 22jun2011
  qusubj = 0;  // reset for safety; 22jun2011
  quobj = 0;  // reset for safety; 22jun2011
  recon = 0;  // 
  bias = 5;  // restore expectation of a noun; 30jun2011
}  // End of AskUser(); return to RuCog(); 11jan2012

 
function NounPhrase() {
  audjuste = 0;  // prevent carry-over; 24oct2011
  if (verblock > 0) {  // 24oct2011
    Psi[verblock].psiExam(); // expose all values to change one; 24oct2011
    nounlock = psi6;  // time-point of "seq" engram; 24oct2011
    motjuste = psi4;  // let "pre" = motjuste?; test; 30oct2011
 // tsels = t;  // foregone subject? test; 29oct2011
  }  // end of test for a positive verblock; 24oct2011
  RuReify();  // 5jan2012
  for (i = t; i>midway; i--) {
    ruLexicon[i].ruExam();  // 5jan2012
    if (ru0 == 704) {  // accusative; 5jan2011
      audme = ru8; // 5jan2012
      break;
    }
  }
  abort = false;
  act = 0;  // Start with zero to look for en1 higher than act.
  defact = -8;  // for default comparisons with "50=I"; 29oct2011
  motjuste = 0;
  nphrnum = 0;  // prevent carry-overs; 24oct2011
  num = 0;   // without prejudice; 2sep2010
  prsn = 0;  // without prejudice; 2sep2010
  if (nounlock > 0) {  // already a nounlock? 24oct2011
    Psi[nounlock].psiExam(); // find nounlock inside Psi array; 1nov2011
    motjuste = psi0;  // test;  inov2011
    ruLexicon[nounlock].ruExam();  // examine Russian lexicon; 11jan2012
    audjuste = ru8;  // hold the auditory recall-vector;  5jan2012
  }  // end of test for a positive nounlock; 24oct2011
  opt = 5; // 
  subjectflag = 1;  // 9dec2009 A default until countermanded 
  if (dirobj == 1) subjectflag = 0;  // toggle; 24oct2011
  if (dirobj == 1) dba = 4;  // seek accusative case; 21jan2012
  if (predflag == 1) subjectflag = 0;  // toggle; 24oct2011
  if (predflag == 1) dba = 1;  // seek nominative case; 21jan2012
  psi = 0;  // The "psi-tag" carried by the "en0" flag.
  for (i = t; i>midway; --i) {
    Psi[i].psiExam(); // examine Psi array for most active concept.
    if (psi5 == 5 || psi5 == 7) {  // Logical OR; 13aug2011
      if (subjectflag == 1) {  // selecting a subject? 24oct2011
     // if (psi1 > act) {  // If psi1 is higher than "act"; 13aug2011
        if (psi1 > act && psi6 > 0) {  // tqv-check; 24oct2011
          if (psi7 > 0) {  // Testing for seq-concept; 24oct2011
            tsels = i;  // retain time of subject; 24oct2011
            tseln = i;  // time of selected noun; 10may2011
            motjuste = psi0; // store psi-tag of noun/pronoun; 13aug2011
            nphrnum = psi2;  // 13aug2011
            subjnum = psi2;  // for AuxVerb DOES or DO; 13aug2011
          }  // for subjects; 24oct2011
          subjpsi = psi0;  // 13aug2011
          subjnum = psi2;  // for AuxVerb DOES or DO; 13aug2011
          putnum = psi2;  // putative num for verb; 24oct2011
          nphrpos = psi5;  // NounPhrase part-of-speech; 13aug2011
          posflag = psi5; // AskUser discriminand; 13aug2011
          if (psi1 > act && psi7 > 0) {  // seq-check; 25oct2011
            verblock = psi6;  // tqv of seq-concept; 24oct2011
            ruLexicon[i].ruExam();  // examine Russian lexicon; 5jan2012
            audjuste = ru8;  // avoid the spurious; 24oct2011; 5jan2012
            if (motjuste == 701) {  // guarantee "I"; 5jan2012
              for (i = t; i>midway; i--) {  //search backwards; 25oct2011
                ruLexicon[i].ruExam(); // examine Russian lexicon; 5jan2012
                if (ru0 == 701) {  // "701=Ya"; 5jan2012
                  audjuste = ru8;  // auditory recall-vector;  5jan2012
                  break; // one I-engram is enough; 25oct2011
                }  // end of test for "701=Ya";  5jan2012 
              }  // end of backwards loop; 25oct2011
            }  // end of test for "701=Ya"; 5jan2012
         // if (motjuste == 711) {  // guarantee "Ty";  5jan2012
            if (motjuste == 707) {  // guarantee "Ty"; 21jan2012
              for (i = t; i>midway; i--) {  //search backwards; 25oct2011
                ruLexicon[i].ruExam(); // examine Russian lexicon; 5jan2012
            // if (ru0 == 711) {  // "711=Ty";  5jan2012
               if (ru0 == 707) {  // "707=Ty"; 21jan2012
                  audjuste = ru8;  // auditory recall-vector;  5jan2012
                  break; // one you-engram is enough;  5jan2012
                }  // end of test for "707=Ty"; 21jan2012
              }  // end of backwards loop; 25oct2011
            }  // end of test for "707=Ty"; 21jan2012
            if (ru6 == 5) prsn = 3; // assume 3rd prsn noun;  5jan2012
            act = psi1; // after passing seq-check; 24oct2011
          }  // prevent false motjuste; 24oct2011
        }  // End of test for a higher activation; 24oct2011
      }  // end of test for 1=subjectflag; 24oct2011
      if (subjectflag == 0) {  // i.e., dir.obj or pred.nom; 24oct2011
        if (psi1 > act) {  // If psi1 is higher than "act"; 24oct2011
          tseln = i;  // retain time of motjuste; 24oct2011
          motjuste = psi0;  // 24oct2011
          if (nounlock > 0) {  // if positive nounlock exists; 24oct2011
            if (i == nounlock) {  // upon reaching engram; 24oct2011
              motjuste = psi0;  // grab nounlock psi; 24oct2011
              nphrnum = psi2;  // NounPhrase num(ber) 24oct2011
              ruLexicon[i].ruExam();  // Examine Ru-lexicon;  5jan20p12
              audjuste = ru8;  // auditory fetch-tag;  5jan2012
              break;  // prevent usurpation of pre-ordained seq 24oct2011
            } // end of test for index = nounlock; 24oct2011
          }  // end of test for positive nounlock; 24oct2011
          subjpsi = psi0;  // 24oct2011
          nphrnum = psi2;  // 24oct2011
          putnum = psi2;   // putative num for verb; 24oct2011
          nphrpos = psi5;  // NounPhrase part-of-speech; 24oct2011
          if (dirobj == 1)  {  // seeking direct object? 24oct2011
            Psi[i].psiExam(); // avoid error-on-page; 18oct2011
            nphrnum = psi2; // 13aug2011
            objold = motjuste; // a test ICW slosh-over; 18oct2010
            if (motjuste == 701) {  // 701=Ya; 5jan2012
             if (nounlock == 0) {  // test; 25oct2011
              motjuste = 704;  // 704=MENYA; 5jan2012
              aud = audme; 
              audjuste = audme;
             }  // end of anti-substitution test; 25oct2011
            }  // end of test for "701=Ya"; 5jan2012
          }  // end of test for needing a direct object; 24oct2011
          if (psi1 > act) act = psi1;  // change the metric; 24oct2011
        }  // end of test for a higher activation; 24oct2011
      }  // end of test for 0=subjectflag; test; 24oct2011
    }  // End of test of for a noun or pronoun; 24oct2011
  }  // End of backwards search for most active "motjuste"; 25may2011
     for (i = t; i>midway; i--) {  // 13aug2011
      ruLexicon[i].ruExam();      //  5jan2012
      if (ru0 == motjuste) {      //  5jan2012
        if (predflag==1) {  // only for predicate nominatives; 20sep2011
         if (nounlock == 0) {  // in absence of nounlock; 25oct2011
          if (ru2==subjnum) {  // num(ber) agreement? 5jan20p12
            audjuste = ru8;  // set auditory recall-vector;  5jan2012
            break;  // one auditory engram is enough; 20sep2011 
          }  // end of test for agreement in num(ber); 20sep2011
         }  // end of test for absence of nounlock; 25oct2011
        }  // end of test for positive "predflag"; 20sep2011
        else  // for normal direct objects; 20sep2011
          if (verblock == 0) {  // if no verblock; 25oct2011
           if (ru4 == dba) {  // if dba-4 accusative; 21jan2012
            audjuste = ru8;  // for NounPhrase SpeechAct;  5jan2012
            break;  // one auditory engram is enough; 20sep2011
           }  // end of test for ru4 accusative dba; 21jan2012
          }  // end of test for absence of verblock; 25oct2011
      }  // end of test for motjuste; 13aug2011
    }  // end of backwards loop; 13aug2011
  star = 0;
  node = 0;
  ufo = 0;
 if (nounlock == 0) {  // if no nounlock override; 24oct2011
  if (act < 20) {  // if no subject of thought is found; 21aug2011
    if (subjectflag==1) {  // default to "I" only as subject 18oct2011
      motjuste = 701;  // default concept of an AI Mind; 5jan2012
      nphrpos = 7;  // pronoun "I"; to prevent EnArticle; 14sep2011
      subjpsi = 701;  // use elsewhere; 5jan2012
      topic = 701;  // use elsewhere; 5jan2012
      for (i = t; i>midway; i--) {  // Look for "50=I"; 9jul2011
        Psi[i].psiExam(); // examine Psi array; 25oct2011
        if (psi0 == 701 && psi7 > 0) {  // 5jan2012
          if (psi1 > defact) {  // 25oct2011 
            tsels = i;  // retain time of subject; 25oct2011
            tseln = i;  // retain time of motjuste; 25oct2011
            verblock = psi6;  // lock onto valid verb; 25oct2011
            break;  // test; 29oct2011
          }  // end of test for higher-act ego-concept; 25oct2011
        }  // end of test for "50=I" with seq-check; 29oct2011
      }  // End of search for #50 "I"; 9jul2011
      dba = 1;  // subject requires nominative case; 21jan2012
      subjpsi = 701;  // for use elsewhere;  5jan2012
      topic = 701;   // for question-asking modules;  5jan2012
      nphrnum = 1;  // for EnArticle and VerbPhrase; 29oct2011
      nphrpos = 7;  // prevent article "A" with "I"; 29oct2011
      subjnum = 1;  // for use elsewhere; 29oct2011
      prsn = 1;  // for use elsewhere; 29oct2011
      for (i = t; i>midway; i--) {  // Look backwards for 50=I; 29oct2011
        ruLexicon[i].ruExam();  // examine the Russian lexicon;  5jan2012
        if (ru0 == 701) {  // If "701=Ya" is found; 5jan2012
         if (ru4 == 1) {  // ru4 = 1 = dba; 21jan2012
          audjuste = ru8;  // "I" recall-vector;  5jan2012
          break;  // Use the most recent engram of "I"; 29oct2011
         }  // end of test for nominative dba ru4; 21jan2012
        }  // End of search for "701=Ya"; 5jan2012
      }  // end of Russian lexicon search loop; 5jan2012
    }  // end of test for "I" to become subj. not obj. 18oct2011
  }  // end of threshold-test; 18oct2011
 }  // end of test for absence of pre-ordained nounlock; 24oct2011
  if (motjuste==701) {  // if 701=Ya selected; 5jan2012
    prsn = 1;  // first person; 2sep2010
    num = 1;   // singular; 2sep2010
    nphrnum = 1;  // xfer into VerbPhrase; 2sep2010
  }  // end of test for 701=Ya; 5jan2012
  if (dirobj == 1) {  // When seeking direct object; 14jun2011
   if (nounlock == 0) {  // if no nounlock override; 24oct2011
    if (act < 20) {  // Revert to general threshold; 8jul2011
      Psi[i].psiExam(); // expose psi2 to avoid error-on-page; 18oct2011
      nphrnum = psi2; // 13aug2011
      WhatSVerb();  // Russian module without auxiliary; 10jan2012 
      return;  // Abandon the rest of NounPhrase()  14jun2011
    }  // End of test for sufficient activation; 14jun2011
   }  // end of test for a nounlock in play; 24oct2011
  }  // End of test for direct object; 14jun2011
  RuDamp();  // Wiki-page form of name; 5jan2012
  nounval = act;
  if (nphrnum != subjnum) {  // make sure of agreement; 18may2011
    for (i = t; i>midway; i--) {  // Search backwards in time; 18may2011
      ruLexicon[i].ruExam();  // Examine Russian lexicon; 5jan2012
      if (ru0 == motjuste) {  // If chosen concept is found; 5jan2012
        if (ru2 == subjnum) {  // If matching num(ber); 5jan2012
         if (ru4 == dba) {  // if correct case; 21jan2012
          audjuste = ru8; // Switch away from wrong number;  5jan2012
          num = subjnum;  // For InStantiate of new engram; 18may2011
          nphrnum = subjnum;  // for EnArticle; test; 19jun2011
          subjnum = 0;  // Reset after use for safety; 18may2011
          break;
         }  // end of dba-test for correct case; 21jan2012
        }  // End of test for matching num(ber); 18may2011
      }  // End of search for engram of proper number; 18may2011
    }  // End of finding not only engram but proper number. 18may2011
  }  // end of test to match subjnum and found noun; 18may2011
  anset = 0;  // Safety measure reset to zero; 4may2011
//  audMemory[aud].audExam();  // Inspect auditory memory at "aud";
//  if (aud0 == "A") anset = 65;  // If vowel "A"; 4may2011
//  if (aud0 == "E") anset = 69;  // If vowel "E"; 4may2011
//  if (aud0 == "I") anset = 73;  // If vowel "I"; 4may2011
//  if (aud0 == "O") anset = 79;  // If vowel "O"; 4may2011
//  if (aud0 == "U") anset = 85;  // If vowel "U"; 4may2011
  ghost = 0;
  xthe = 0;  
    urpsi = motjuste; // prepare to psi-damp; 18oct2010
  urpsi = 0;  // reset for safety; 18oct2010
  urpsi = objold; // prepare to psi-damp; 18oct2010
// PsiDamp();  // Commenting out as a test; 29oct2011 
  urpsi = 0;  // reset for safety; 18oct2010
  psi = 0;
  aud = audjuste; 
  SpeechAct();  // main call from NounPhrase to SpeechAct; 18may2011
  if (dirobj==1 || predflag==1) {  // d.o. OR pred.nom. 30may2011
    Psi[t].psiExam(); // expose all values to change one; 14jun2011
    Psi[t] = new psiNode(psi0,-32,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
    // Try accentuating object nouns to start the next thought; 29oct2011
 // Psi[t] = new psiNode(psi0,48,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
  }  // only inhibit predicate nominatives; 16sep2010
  if (motjuste != 701) {  // if not 701=Ya; 5jan2012
    if (motjuste != 707) {  // not 707=Ty; 11jan2012
      if (motjuste != 731) {  // not 731=MWI (we); 11jan2012
        prsn = 3;  // third person; not I YOU WE; 2sep2010
      }  // end of test for 53=WE; 2sep2010
    }  // end of test for 56=YOU; 2sep2010
  }  // end of test for "not I"; 2sep2010
  if (subjcall == 1) {  // _After_ any call to EnArticle(); 21may2011
    nouncall = 1;  // 1=nom.; (2=gen.); (3=dat.); 4=acc.; 21may2011
  }  // End of test to prevent showSubject() of articles; 21may2011
  if (dirobj == 1) {  // _After_ any call to EnArticle(); 21may2011
    nouncall = 4;  // 1=nom.; (2=gen.); (3=dat.); 4=acc.; 21may2011
  }  // End of test to prevent showObject() of articles; 21may2011
  caller = "NounPhrase";
  urpre = pre;
  psi = motjuste; 
  nacpsi = motjuste;  // de-globalized psi for NounAct; 13aug2010
  nounval = 32;  // arbitrary test value;  9jul2011
  NounAct();
  nouncall = 0;  // Reset, whether subj. or dir. obj.; 21may2011
  nounval = 0;
  Psi[tsels].psiExam(); // impose neural inhibition on subject; 27oct2011
  Psi[tsels] = new psiNode(psi0,-64,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
  tsels = 0;  // reset for safety after inhibiting; 27oct2011
  if (dirobj==1 || predflag==1) { // noun after verb; 30may2011
 // NounClear();  // deactivate before inhibiting; 18aug2011
    Psi[tseln].psiExam(); // expose all values to change one; 30may2011
    // following line inhibits old KB noun-node; 24may2011; 30may2011
    Psi[tseln] = new psiNode(psi0,-64,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
    tseln = 0;  // Reset after use; 24may2011
    Psi[t].psiExam(); // expose all values to change one; 14jun2011
    Psi[t] = new psiNode(psi0,-64,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
    motjuste = psi0;   // test; 29oct2011
    // Try accentuating, not inhibiting; 29oct2011
 // Psi[t] = new psiNode(psi0,48,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
    PsiDecay();  // Try _differential_ psi-decay; 14may2011
    PsiDecay();  // MindForth: try to knock out also-rans; 8jun2011
    PsiDecay();  // test; remove; 3jul2011
  }  // end of test for positive predflag; 16sep2010
  inhibcon = 1;  // flag for OldConcept and InStantiate; 27oct2011
  if (dirobj != 1 && predflag !=1 ) { // only subjects; 29oct2011
    Psi[t].psiExam(); // inhibit subjects to a shallow depth; 27oct2011
    Psi[t] = new psiNode(psi0,-64,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
    motjuste = psi0;  // test; 29oct2011
  }  // end of test to avoid inhibiting prednoms and dirobjs; 29oct2011
  topic = motjuste;  // needed by WhatAuxSVerb()  14jun2011
  pre = urpre;  // from before call to NounAct; 27oct2011
  if (dirobj == 1 || predflag == 1) {  // other than subject; 27oct2011
    caller = "NounPhrase";
    urpsi = motjuste;
    PsiDamp();  // commenting out as test; 14jun2011
    urpsi = 0;  // reset for safety; 18oct2010
  }  // end of test for a non-subject (pro)noun; 27oct2011
  act = 0;
  motjuste = 0;
  nounlock = 0;  // after causing selection of VPhr seq-noun; 24oct2011
  psi = 0;
}  // End of NounPhrase; return to VerbPhrase or RuCog; 9jan2012


function ConJoin() { 
  if (questype == 370) {  // 370=POCHEMU (why?); 11jan2012
    conj = 350;  // 350=___ (because) to answer "why?"; 11jan2012
  } else conj = 360;  // 360=EE (and) default conjunction.
  for (i = t; i>midway; i--) {
    ruLexicon[i].ruExam();  // 11jan2012
      if (ru0 == conj) {  // 5jan2012
        aud = ru8; // 5jan2012
        break;
      }
    }
  SpeechAct();
  questype = 0;
}  // End of ConJoin(); currently not called; 13aug2010


function VerbGen() {  // to creat missing verb-forms; 18jan2012
  do {  // first loop fills in AudBuffer
    audMemory[audbase].audExam();
    pho = aud0;
    abc = aud0;  // for AudBuffer(); 18jan2012
    AudBuffer();  // to transfer engrams; 18jan2012
    if (aud4==0) {  // no continuation; 19jan2012
      OutBuffer();   // 18jan2012
    }  // 19jan2012
    if (b14==String.fromCharCode(1045)) { // "E"; 19jan2012
      aud0=" ";  // "E"; 19jan2012
    }  // 19jan2012

    if (b14==String.fromCharCode(1045)) { // "E"; 19jan2012
      aud0=" ";  // "E"; 19jan2012
      if (b15==String.fromCharCode(1064)) {  
        aud0=" ";  // "SH"; 19jan2012
        if (b16==String.fromCharCode(1068)) {  // 19jan2012
          aud0=" ";  // "b"; 19jan2012
      //  alert("end three = ESHb");  // 21jan2012
        }  // 19jan2012
      }  // 19jan2012
    }  // 19jan2012
    ctu = aud4;  // continuation criterion; 18jan2012
    audbase = (audbase + 1);  // increment; 18jan2012
  }
  while (ctu == 1);  // during continuation; 18jan2012
  if (ctu == 0) {  // 19jan2012
    OutBuffer();  // upon end of word display OutBuffer; 18jan2012
  }  // 19jan2012
  do {  // second loop uses OutBuffer; 19jan2012  
    OutBuffer();  // 19jan2012
    pov = "#";  // from SpeechAct; 19jan2012
      if (binc==1) {  // 21jan2012
        if (b01 > "") {  // 21jan2012
          output += b01;  // 21jan2012
          pho = b01;  // for ReEntry; 21jan2012
          ReEntry();  // from SpeechAct; 21jan2012
        }  // end of test for content; 21jan2012
      }  // 21jan2012
      if (binc==2) {  // 21jan2012
        if (b02 > "") {  // 21jan2012
          output += b02;  // 21jan2012
          pho = b02;  // for ReEntry; 21jan2012
          ReEntry();  // from SpeechAct; 21jan2012
        }  // end of test for content; 21jan2012
      }  // 21jan2012
      if (binc==3) {  // 21jan2012
        if (b03 > "") {  // 21jan2012
          output += b03;  // 21jan2012
          pho = b03;  // for ReEntry; 21jan2012
          ReEntry();  // from SpeechAct; 21jan2012
        }  // end of test for content; 21jan2012
      }  // 21jan2012
      if (binc==4) {  // 21jan2012
        if (b04 > "") {  // 21jan2012
          output += b04;  // 21jan2012
          pho = b04;  // for ReEntry; 21jan2012
          ReEntry();  // from SpeechAct; 21jan2012
        }  // end of test for content; 21jan2012
      }  // 21jan2012
      if (binc==5) {  // 21jan2012
        if (b05 > "") {  // 21jan2012
          output += b05;  // 21jan2012
          pho = b05;  // for ReEntry; 21jan2012
          ReEntry();  // from SpeechAct; 21jan2012
        }  // end of test for content; 21jan2012
      }  // 21jan2012
      if (binc==6) {  // 21jan2012
        if (b06 > "") {  // 21jan2012
          output += b06;  // 21jan2012
          pho = b06;  // for ReEntry; 21jan2012
          ReEntry();  // from SpeechAct; 21jan2012
        }  // end of test for content; 21jan2012
      }  // 21jan2012
      if (binc==7) {  // 21jan2012
        if (b07 > "") {  // 21jan2012
          output += b07;  // 21jan2012
          pho = b07;  // for ReEntry; 21jan2012
          ReEntry();  // from SpeechAct; 21jan2012
        }  // end of test for content; 21jan2012
      }  // 21jan2012
      if (binc==8) {  // 21jan2012
        if (b08 > "") {  // 21jan2012
          output += b08;  // 21jan2012
          pho = b08;  // for ReEntry; 21jan2012
          ReEntry();  // from SpeechAct; 21jan2012
        }  // end of test for content; 21jan2012
      }  // 21jan2012
      if (binc==9) {  // 21jan2012
        if (b09 > "") {  // 21jan2012
          output += b09;  // 21jan2012
          pho = b09;  // for ReEntry; 21jan2012
          ReEntry();  // from SpeechAct; 21jan2012
        }  // end of test for content; 21jan2012
      }  // 21jan2012
      if (binc==10) {  // 19jan2012
        if (b10 > "") {  // 21jan2012
          output += b10;  // 19jan2012
          pho = b10;  // for ReEntry; 19jan2012
          ReEntry();  // from SpeechAct; 19jan2012
        }  // end of test for content in b10; 21jan2012
      }  // 19jan2012
      if (binc==11) {  // 19jan2012
        if (b11 > "") {  // 21jan2012
          output += b11;  // 19jan2012
          pho = b11;  // for ReEntry; 19jan2012
          ReEntry();  // from SpeechAct; 19jan2012
        }  // end of test for content in b11; 21jan2012
      }  // 19jan2012
      if (binc==12) {  // 19jan2012
        if (b12 > "") {  // 21jan2012
          output += b12;  // 19jan2012
          pho = b12;  // for ReEntry; 19jan2012
          ReEntry();  // from SpeechAct; 19jan2012
        }  // end of test for content in b12; 21jan2012
      }  // 19jan2012
      if (binc==13) {  // 19jan2012
        if (b13 != "") {  // 21jan2012
          output += b13;  // 19jan2012
          pho = b13;  // for ReEntry; 19jan2012
          ReEntry();  // from SpeechAct; 19jan2012
        }  // end of test for content in b13; 21jan2012
      }  // 19jan2012
      if (binc==14) {  
        if (b14==String.fromCharCode(1045)) {  
           b14 = "";  // "E"; 19jan2012
        }  // 19jan2012
        else {  
          output += b14;  // 19jan2012
          pho = b14;  // for ReEntry; 19jan2012
          ReEntry();  // from SpeechAct; 19jan2012
        }  // 19jan2012
      }  // 19jan2012
      if (binc==15) {  // 19jan2012
        if (b15==String.fromCharCode(1064)) {  
          b15 = "";  // "SH"; 19jan2012
      //  output += b15;  // 19jan2012
        }  // 19jan2012
        else {  // 19jan2012
          output += b15;  // 19jan2012
          pho = b15;  // for ReEntry; 19jan2012
          ReEntry();  // from SpeechAct; 19jan2012
        }  // end of else-clause; 19jan2012
      }  // 19jan2012
      if (binc==16) {  // 19jan2012
        if (b16==String.fromCharCode(1068)) { 
          b16 = "";  // "b"; 19jan2012
      //  output += b16;  // 19jan2012
        }  // 19jan2012
        else {  // 19jan2012
          output += b16;  // 19jan2012
          pho = b16;  // for ReEntry; 19jan2012
          ReEntry();  // from SpeechAct; 19jan2012
        }  // end of else-clause; 19jan2012
        if (binc==16) {  // 21jan2012
          if (b16==String.fromCharCode(1070)) { 
            b16 = "";  // "YU"; 21jan2012
          }  // 21jan2012
        }  //
        else {  // 21jan2012
          output += b16;  // 21jan2012
          pho = b16;  // for ReEntry; 21jan2012
          ReEntry();  // from SpeechAct; 21jan2012
        }  // end of else-clause; 21jan2012
      }  // 19jan2012    // 
      binc = (binc + 1);  // increment; 19jan2012
    }  // end of looping through OutBuffer; 19jan2012
    while (binc < 17);  // while inspecting OutBuffer; 19jan2012
    binc = 0;  // reset after use; 19jan2012
    if (dba == 1) {  // 19jan2012
      if (subjnum ==1) {  // a parameter; 21jan2012
        output += "&#1070;"  // "YU"; 21jan2012
        pho = "&#1070;"  // "YU"; 21jan2012
        ReEntry();  // from SpeechAct; 19jan2012
      }  // 21jan2012
    }  // 19jan2012
    if (dba == 2) {  // 21jan2012
      if (subjnum ==1) {  // a parameter; 21jan2012
       output += "&#1045;"  // substitute; 28dec2011
       pho = "&#1045;"  // "YE"; 21jan2012
       ReEntry();  // from SpeechAct; 21jan2012
       output += "&#1064;"  // substitute; 28dec2011   
       pho = "&#1064;"  // "SH"; 21jan2012
       ReEntry();  // from SpeechAct; 21jan2012
       output += "&#1068;"  // substitute; 28dec2011   
       pho = "&#1068;"  // "b"; 21jan2012
       ReEntry();  // from SpeechAct; 21jan2012
      }  // 21jan2012
    }  // 19jan2012
    if (ctu == 0) {  // 19jan2012
      pho = 32;  // intervening space; 19jan2012
      ReEntry();  // 19jan2012
    }  // 19jan2012
    output += " ";  // add a space; 21jan2012
    Voice();  // 21jan2012
// vphract = 32;  // prevent interference; 19jan2012 
  act = 31;  // value intended for "vphract"; 21jan2012
}  // end of VerbGen(); 18jan2012


function VerbPhrase() {
  if (verblock > 0) {  // positive verblock? 24oct2011
    Psi[verblock].psiExam(); // expose all values to change one; 24oct2011
    nounlock = psi6;  // time-point of "seq" engram; 24oct2011
  }  // 24oct2011  
  RuReify();  // 5jan2012
  act = 0;  // Start with zero to look for psi1 higher than act.
  aud = 0;
  detour = 0;
  psi5 = 0; // 13aug2011
  motjuste = 0;
  if (verblock > 0) {  // already a verblock? 24oct2011
    ruLexicon[verblock].ruExam();  // examine row in array;  5jan2012
    vphraud = ru8;  //  5jan2012
  }  // end of test for a positive verblock; 24oct2011
  opt = 8;
  psi = 0;
  verbcall = 1;
  vphract = 0;  // for validity of threshold-tests; 15aug2011
  vphraud = 0;  // prevent spurious carry-overs; 24oct2011
 if (verblock == 0) {  // prevent false negations; 24oct2011
   if (subjpsi==701) dba = 1;  // must be 1st person; 17jan2012
  for (i = t; i>midway; i--) {
    Psi[i].psiExam(); // examine Psi concept array; 13aug2011
      if (psi5 == 8) {  // if 8=pos verb; 13aug2011
        if (psi1 > act) {  // If psi1 is higher than "act"; 13aug2011
          tselv = i;  // time of selected verb; 24may2011
          motjuste = psi0; // store psi-tag of verb; 13aug2011
          verbpsi = motjuste;  // for WhatAuxSVerb;  9jul2011
          beact = psi1; // store activation of be-verb; 13aug2011
          if (maxbeact < beact) {  // if maximum is smaller; 10nov2010
            maxbeact = beact;  // for comparisons; 10nov2010
          }  // only store when beact is large; 10nov2010
          if (psi1 > 0) {  // 15aug2011
            if (psi3==250) {  // 250=NYE ("not"); 17jan2012
              negjux = psi3;  // 13oct2011
            }  // end of test for 250=NYE; 17jan2012
          }  // end of test for positive activation; 15aug2011
          if (verblock > 0) {  // if positive verblock exists; 24oct2011
            if (i == verblock) {  // upon reaching engram; 24oct2011
              motjuste = psi0;  // grab verblock psi; 24oct2011
              act = 64;  // to pass threshold-test; 24oct2011
              negjux = psi3;  // for negation of verb; 24oct2011
              nounlock = psi6;  // after verb grab "seq"; 24oct2011
              if (subjpsi==701) {  // 17jan2012
                dba = 1;  // verb must be 1st person; 17jan2012
              }  // end of test for 1st person singular; 17jan2012
              ruLexicon[i].ruExam();  // Russian lexicon;  5jan2012
              vphraud = ru8;  // for SpeechAct;  5jan2012
              break;  // prevent usurpation of pre-ordained seq; 7oct2011
            }  // end of test for index = verblock; 24oct2011
          }  // end of test for positive verblock; 24oct2011
          if (psi1 > 0) {  // positive activation? 24oct2011
            if (verblock==0) negjux = psi3; // negative be-verbs; 24oct2011
            tqv = psi6;  // underailable tqv; 24oct2011
          }  // end of test for positive activation; 24oct2011
          predpos = psi5;  // 
          Psi[i].psiExam(); // Check for negation on psi3; 29jun2011
          act = psi1; // To test for a higher psi1; 15aug2011
          if (act > 8) {
            sloshmark = "+";  // for Tutorial display; 9aug2011
          }  // end of test for positive activation; 24oct2011
        }  // end of if-clause looking for higher activation
      } else continue;
  }  // end of search for "motjuste" in Psi array; 13aug2011
   for (i = t; i>midway; i--) {  // separate search for verb-form;
    ruLexicon[i].ruExam();  // examine Russian lexicon; 17jan2017
    if (motjuste != 0 && ru0 == motjuste) {  // look for motjuste; 17jan2017
    audbase = ru8;  // location of quasi-stem for VerbGen(); 18jan2012
      if (ru4 == dba)  {  // for proper person; 17jan2012
        if (ru2 == subjnum) {  // num(ber) parameter; 17jan2012
          vphraud = ru8;  // auditory recall-vector; 17jan2012
          break;  // exit the loop after first find; 17jan2017
        }  // end of number-parameter test; 17jan2012
      }  // end of dba-parameter test; 17jan2012
      gencon = 1;  // status flag for detour into VerbGen; 19jan2012
      VerbGen();  // Generate a missing verb-form; 19jan2012
    audbase = 0;  // reset for safety; 18jan2012
 //  alert("VPhr: back from VerbGen");  // 21jan2012
    break;  // test; 19jan2019
    }  // end of test for motjuste; 17jan2017
  }  // end of loop in search of motjuste; 17jan2017
} // end of verblock-test to prevent false negations; 20oct2011
  if (verblock > 0) {  // 24oct2011
    Psi[verblock].psiExam(); // expose all values to change one; 24oct2011
    motjuste = psi0;  // verblock override of activational competition;
    negjux = psi3;  // capture any "12=NOT" during override; 25oct2011
    if (subjpsi==701) {  // 17jan2012
       dba = 1;  // verb must be 1st person; 17jan2012
    }  // end of test for 1st person singular; 17jan2012
    ruLexicon[verblock].ruExam();  // examine Russian lexicon; 5jan2012
    vphraud = ru8;  // hold the auditory recall-vector;  5jan2012
    act = 64;  // prevent rejection of selection; 24oct2011
  }  // 24oct2011
  Psi[tqv].psiExam(); // examine array row at "tqv"; 24oct2011
  Psi[tqv] = new psiNode(psi0,128,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
  node = 0;  // Reset tutorial verb display for showVerb().
  vphract = act;  // from highest-activation verb; 22jun2011
  if (motjuste == 0) {
    tov = t;
    if (nphrnum == 1) {  // 19jun2011
      if (mfnflag > 0) {  // if masc. or fem.; 3aug2011
        WhoBe();  // ask WHO not WHAT; 3aug2011
        mfnflag = 0;  // reset after use; 3aug2011
        return;  // abandon rest of VerbPhrase; 3aug2011
      }  // end of test to ask WHO instead of WHAT; 3aug2011
      qusub = subjpsi;  // as set in NounPhrase; 29oct2011
      qusubnum = subjnum;  // parameter for WhatBe; 28oct2011
  //  alert("VerbPhrA: calling WhatBe");  // 19jan2012
      WhatBe();  // 19jun2011
      return;  // abandon rest of VerbPhrase; 27jun2011
    }  // 19jun2011
    if (nphrnum == 2) {  // if plural subject; 27jun2011
      caller = "VerbPhrase";  // alert-diagnostic;  5jul2011
      topic = subjpsi;  // supersede any default;  7jul2011
      WhatSDo();  // Russian What do Subjects Do? 10jan2012
      yncon = 1;  // delay yes-or-no ? until after input; 27jun2011 
      return;  // abandon rest of VerbPhrase; 27jun2011
    }  // what-do-X-do as prelude to yes-or-no questions; 27jun2011
    else return;  // abort thought if number not known; 15aug2011
  }  // End of test for zero motjuste; 2sep2010
  if (motjuste > 0) {  // if positive motjuste; 2sep2010
    //  alert("VPhr: testing vphract at "+vphract);  // 21jan2012
    if (vphract < 20) {  // threshold level also in MindForth; 26jun2011
      if (nphrnum == 0 || nphrnum == 1) {  // unk or sing. 5jul2011
        if (mfnflag > 0) {  // if masc. or fem.; 3aug2011
          WhoBe();  // ask WHO not WHAT; 3aug2011
          mfnflag = 0;  // reset after use; 3aug2011
          return;  // abandon rest of VerbPhrase; 3aug2011
        }  // end of test to ask WHO instead of WHAT; 3aug2011
        qusub = subjpsi;  // as set in NounPhrase; 29oct2011
        qusubnum = subjnum;  // parameter for WhatBe; 29oct2011
 //  alert("VerbPhrB: calling WhatBe");  // 19jan2012
        if (gencon == 0) {  // prevent double output; 19jan2012
          WhatBe();  // to ask a what-is question; 27jun2011
          return;  // abandon rest of VerbPhrase; 27jun2011
        }  // 19jan2012
      }  // arbitrarily asking what-is builds ontology; 27jun2011
      if (nphrnum == 2) {  // if plural subject; 27jun2011
        caller = "VerbPhrase";  // alert-diagnostic;  5jul2011
        topic = subjpsi;  // supersede any default;  7jul2011
        WhatSDo();  // Russian What do Subjects Do? 10jan2012
        topic = " ";  // reset for safety;  7jul2011
        yncon = 1;  // delay yes-or-no ? until after input; 27jun2011 
        return;  // abandon rest of VerbPhrase; 27jun2011
      }  // what-do-X-do as prelude to yes-or-no questions; 27jun2011
      else return;  // abort thought if number not known; 15aug2011
    }  // end of test for vphract below 20=threshold; 15aug2011
    if (negjux==250) {  // if negated with 250=NYE (not); 12jan2012
   // unk = motjuste;  // temporary holding for if-clauses; 15aug2011
   // if (unk != 57 && unk != 58 && unk != 66 && unk != 67) {
     // AuxVerb();  // to say "DO" or "DOES"; 29jun2011
        for (i = t; i>midway; i--) { // search backwards 29jun2011
          ruLexicon[i].ruExam();  // examine Russian lexicon; 5jan2012
          if (ru0 == 250) {  // if 250=Nye is found; 5jan2012
            aud = ru8;  // recall-vector of auditory engram;  4jan2012
            break;  // finding one "NOT" is enough; 29jun2011
          } // end of test for 12=NOT; 29jun2011
        }  // end of search of Russian lexicon; 5jan2012
        SpeechAct();  // speak or display the adverb "NOT"; 29jun2011
   // }  // end of test for no be-verb; 15aug2011 
    }  // end of test for 250=NOT negjux; 5jan2012
    unk = motjuste;  // temporary holding for if-clauses; 15aug2011
    if (unk != 57 && unk != 58 && unk != 66 && unk != 67) {
      if (nphrnum==1) {  // if singular; 2sep2010
        if (prsn==3) {  // 3rd person? 10may2011
          // Next code must change to Russian OutBuffer; 12jan2012
          flex1 = "S";  // xfer to SpeechAct(); 14sep2011
        }    // end of test for third-person; 10may2011
      }  // end of test for singular nphrnum; 2sep2010
    }  // end of test for absence of a be-verb; 15aug2011
    unk = motjuste;  // temporary holding for if-clauses; 29odt2011
    if (unk == 57 || unk == 58 || unk == 66 || unk == 67) {  // 29oct2011
      predflag = 1;  // for sake of NounPhrase; 29oct2011
    }  // end of two-step be-verb substitution; 29oct2011
 // if (motjuste==58) {  // 58=BE; 13aug2011
    if (motjuste==800) {  // 800=BWIT' (be); 11jan2012
      if (subjpsi==701) {  // 701=YA ("I"); 11jan2012
     // for (i = t; i>midway; i--) {  // search backwards; 13aug2011
     //   enLexicon[i].enExam();  // examine English lexicon; 13aug2011
     //   if (en0 == 57) {  // 57=AM; 13aug2011
     //     urpsi = 57;  // for PsiDamp; 15aug2011
     //     verbpsi = 57;  // for EnArticle; 14sep2011
     //     vphraud = en8;  // for call to SpeechAct;  4jan2012
     //     break;  // finding recent "AM" is enough; 13aug2011
     //   } // end of test for 57=AM; 13aug2011
     // }  // end of search of En array; 13aug2011
      }  // end of test for subject-psi 50=I; 13aug2011
   // if (subjpsi==56) {  // 56=YOU; 15aug2011
      if (subjpsi==707 || subjpsi==479) {  // fam. or formal; 11jan2012
     // for (i = t; i>midway; i--) {  // search backwards; 15aug2011
     //   enLexicon[i].enExam();  // examine English lexicon; 15aug2011
     //   if (en0 == 67) {  // 67=ARE; 15aug2011
     //     urpsi = 67;  // for PsiDamp; 15aug2011
     //     vphraud = en8;  // for call to SpeechAct;  4jan2012
     //     break;  // finding recent "ARE" is enough; 15aug2011
     //   } // end of test for 67=ARE; 15aug2011
     // }  // end of search of En array; 15aug2011
      }  // end of test for 56=YOU; 15aug2011 
    }  // end of test for 58=BE; 13aug2011
    vacpsi = motjuste;  // for VerbAct(); 18aug2011
    VerbAct();  // moved from below SpeechAct & old KB-inhib; 18aug2011
    aud = vphraud;  // transfer just before call; 28jun2011
    if (gencon == 0) {  // if no call to VerbGen(); 19jan2012
      SpeechAct(); // main call from VerbPhrase to SpeechAct; 2sep2010
    }  // prevent speaking extra verb after VerbGen(); 19jan2012
    flex1 = "";  // corrective measure; 27jun2011; 14sep2011
    gencon = 0;  // reset whether used or not; 19jan2012
    vphraud = 0;  // reset for safety; 28jun2011
  }  // End of test for positive motjuste; 2sep2010
  VerbClear();  // deactivate before inhibiting; 18aug2011
  // Next line inhibits 2nd engram of pair with old engram; 24may2011
  Psi[t].psiExam(); // expose all values to change one; 8jun2011
  Psi[t] = new psiNode(psi0,-48,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
  subjectflag = 0;  // for SpreadAct slosh-over; 18oct2010
  urpsi = motjuste;
  caller = "VerbPhrase";
  PsiDamp();  // MindForth wiki-page spelling; 15nov2010
  RuDamp();   // Wiki-page form of name; 5jan2012
  // Following lines inhibits old KB verb-node; 8jun2011
  Psi[tselv].psiExam(); // expose all values to change one; 8jun2011
  Psi[tselv] = new psiNode(psi0,-32,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
  tselv = 0;  // Reset after use; 24may2011; 8jun2011
  unk = motjuste;  // temporary holding for if-clauses; 15aug2011
  if (unk == 57 || unk == 58 || unk == 66 || unk == 67) {  // 15aug2011
    predflag = 1;  // 20sep2011
    if (negjux==250) {  // if 250=Nye negates the verb-node; 5jan2012
      for (i = t; i>midway; i--) { // search backwards in time; 9aug2011
        ruLexicon[i].ruExam();  // examine the Russian lexicon; 5jan2012
        if (ru0 == 250) {  // if 250=Nye is found; 5jan20p12
          aud = ru8;  // recall-vector of auditory engram; 5jan2012
          break;  // finding one "NOT" is enough; 9aug2011
        } // end of test for 250=Nye; 5jan2012
      }  // end of search of English lexicon; 9aug2011
      SpeechAct();  // speak or display the adverb "NOT"; 9aug2011
      negjux = 0;  // reset for safety; 13oct2011
    }  // end of test for 12=NOT negation; 9aug2011
  }  // end of test for a present-tense be-verb; 15aug2011
// if (motjuste == 57) {  // 57=AM; 9aug2011
//  if (negjux==12) {  // if 12=NOT negates the verb-node; 13oct2011
//    for (i = t; i>midway; i--) { // search backwards in time; 9aug2011
//      enLexicon[i].enExam();  // examine the English lexicon; 9aug2011
//      if (en0 == 12) {  // if 12=NOT is found; 9aug2011
//        aud = en8;  // recall-vector of auditory engram; 4jan2012
//        break;  // finding one "NOT" is enough; 9aug2011
//      } // end of test for 12=NOT; 9aug2011
//    }  // end of search of English lexicon; 9aug2011
//    SpeechAct();  // speak or display the adverb "NOT"; 9aug2011
//    negjux = 0;  // reset for safety; 13oct2011
//  }  // end of test for 12=NOT negation; 9aug2011
// }  // end of test for be-verb 57=AM; 9aug2011
//  motjuste = 0;
  psi = 0;
  pho = " ";
  dirobj = 1;
  if (subjpsi==50) {  // only for subject "50=I"; 25sep2011
    if (motjuste==62) {  // only for verb "62=SEE"; 25sep2011
      if (svo3==0) {  // if SEE has no direct object; 25sep2011
        VisRecog();  // a challenge for robot AI coders 25sep2011
        SpeechAct();  // say default from VisRecog; 25sep2011
        return;  // abandon rest of VerbPhrase; 25sep2011        
      }  // end of test for direct object; 25sep2011
    }  // end of test for "62=SEE" requiring VisRecog; 25sep2011
  }  // end of test for "50=I" subject of verb; 25sep2011
  if (motjuste == 57) {  // 14sep2011
   verbpsi = 57;  // 14sep2011
   predflag = 1; // 16sep2010
  }  // 14sep2011
  NounPhrase();
  predflag = 0;  // reset for safety; 16sep2010
  dirobj = 0;
  negjux = 0;  // reset for safety; 13oct2011
  nouncall = 0;
  tqv = 0;  // reset for safety; 25oct2011
  verblock = 0;  // after selection of NPhr seq-verb; 24oct2011
}  // End of VerbPhrase(); return to EnCog(); 29jun2011


function RuCog() {  // 5jan2012
  moot = 0;  // may have been set in previous thought; 24oct2011
  morphpsi = 0;  // reset; from MindForth English AI; 15jan2012
  nphrnum = 0;  // reset after previous thoughts;  5jul2011
  PsiDecay();  // for distribution of PsiDecay influence; 3jul2011
  tov = t;  // For sake of ReActivate & InHibition;  8jun2011
  if (yncon == 1) {  // set in VerbPhrase after WhatAuxSDo; 3jul2011
    AskUser();  // for yes-or-no query; 3jul2011
    return;  // abandon the rest of EnCog; 3jul2011
  }  // 3jul2011
  if (inert > 1) {  // if no input start thinking; 23oct2011
    qusub = topic;  // default for WhatBe; 27oct2011
    if (cogpsi>0) qusub=cogpsi;  // override; 27oct2011
    qusubnum = subjnum;  // default for WhatBe; 27oct2011
 // if (cognum>0) qusubnum = cognum;  // override; 27oct2011
    if (cognum > -1) qusubnum = cognum;  // override; 6nov2011
  if (cogpsi > 0) {  // if there is a question; 27oct2011
    artnum = qusubnum;  // parameter for EnArticle; 6nov2011
    WhatBe();  // ask question about a new concept; 18oct2011
  }  // end of test for presence of a query-subject; 27oct2011
    cognum = 0;  // reset for safety; 27oct2011
    cogpsi = 0;  // reset for safety; 18oct2011
    inert = 0;  // reset to resume counting; 18oct2011
    return;  // abandon the rest of EnCog; 18oct2011
  }  // end of arbitrary delay before initiating thought; 18oct2011
  document.all.cosmos.innerHTML = "";
  subjcall = 1;  // Set nouncall just before NounAct(); 21may2011
  audMemory[t].audExam();  // ReJuvenate test; 14jul2011
  audMemory[t] = new audNode(aud0,aud1,"{",aud3,aud4,aud5); // 14jul2011
  NounPhrase();
  subjcall = 0;  // Reset for safety; 21may2011
  verbnum = nphrnum;
  verbcall = 1;  
  VerbPhrase();  
  verbcall = 0;
  verbnum = 0;
  the1 = 0;
  the2 = 0;
  the3 = 0;
  the4 = 0;
  the5 = 0;
  the6 = 0;
  the7 = 0;
}  // End of RuCog(); return to ThInk(); 5jan2012
 
 
function ThInk() {
  PsiDecay();  // trying to reduce stray activation; 16oct2010
  PsiDecay();  // Sharply cutting high-activation concepts; 20may2011
  PsiDecay();  // trying to reduce stray activation;  8jun2011
  PsiDecay();  // trying to reduce stray activation;  8jun2011
  PsiDecay();  // test; remove; 3jul2011
  inert = (inert + 1); // but AudInput resets to zero; 18oct2011
  lurk = (lurk + 1); // AudListen() resets to zero; 29sep2010
  if (life==true) { // 29sep2010
 apb=("Thinking at time "+t+" NLP loop #"+lurk+" KbTraversal = "+kbtv);
    Voice(); // speak the all-points-bulletin "apb"; 29sep2010
  }  // 29sep2010
  abort = false;  
  if (quiet == true) {  
    pov = "#"; 
    output = ""; 
 // output = "";  // Commenting out as a test; 6nov2011
    outputplus = ""; 
 // outputplus = "";  // Commenting out as a test; 6nov2011
    if (glot == 1) {  // flag for polyglot AI;  9jul2011
      RuCog();  // think in Russian;  5jan2012
    }  // input of German might switch glot to two; 9jul2011
  }  // end of test for "quiet"; 13jul2011
  ordo = 0; 
  if (lurk > greet) {  // if no input by arbitrary time; 29sep2010
    kbtv = (kbtv + 1);  // increment as a trigger; 29sep2010
    KbTraversal();  // activate ideas as a greeting; 29sep2010
    lurk = 0;  // reset for safety; 29sep2010
  }  // end of test to launch greeting; 29sep2010
// output = "";  // Let AI thought persist during input; 6nov2011
// outputplus = "";  // Let AI thought persist during input; 6nov2011
  bias = 5;  // test ICW slosh-over; 15oct2010
}  // End of ThInk module.


function showSubject() {
  var kb = document.getElementById("cosmos");
  var seti = document.getElementById("star");
  var set = (document.getElementById("star").value);
  seti.value = set;
  if (brevity == 1) set = 1;
  if (brevity == 2) set = 2;
  if (brevity == 3) set = 3;
  if (brevity == 4) set = 4;
  if (brevity == 5) set = 5;
  if (brevity == 6) set = 6;
  if (brevity == 7) set = 7;
  if (brevity == 8) set = 8;
  if (brevity == 9) set = 9;
  if (brevity == 10) set = 10;
  if (brevity == 11) set = 11;
  if (brevity == 12) set = 12;
  if (brevity == 13) set = 13;
  if (brevity == 14) set = 14;
  if (brevity == 15) set = 15;
  if (brevity == 16) set = 16;
  if (brevity == 17) set = 17; // prevent ectopic rectangles; 29sep2010
  var sunset = "sun"+set;
  var fact = document.createElement("div");
  fact.setAttribute("id",sunset);
  fact.style.setAttribute('position', 'absolute');
  fact.style.setAttribute('left', '10');
  fact.style.setAttribute('top', '50');
  if (set==1) fact.style.setAttribute('top', '240');
  if (set==2) fact.style.setAttribute('top', '260');
  if (set==3) fact.style.setAttribute('top', '280');
  if (set==4) fact.style.setAttribute('top', '300');
  if (set==5) fact.style.setAttribute('top', '320');
  if (set==6) fact.style.setAttribute('top', '340');
  if (set==7) fact.style.setAttribute('top', '360');
  if (set==8) fact.style.setAttribute('top', '380');
  if (set==9) fact.style.setAttribute('top', '400');
  if (set==10) fact.style.setAttribute('top', '420');
  if (set==11) fact.style.setAttribute('top', '440');
  if (set==12) fact.style.setAttribute('top', '460');
  if (set==13) fact.style.setAttribute('top', '480');
  if (set==14) fact.style.setAttribute('top', '500');
  if (set==15) fact.style.setAttribute('top', '520');
  if (set==16) fact.style.setAttribute('top', '540');
  if (set==17) fact.style.setAttribute('top', '560'); // 29sep2010
  fact.style.setAttribute('width', '200');
  fact.style.setAttribute('height', '19');
  fact.style.setAttribute('backgroundColor', 'aqua');
  holdaud = aud;
  do {
    audMemory[aud].audExam();
    tsubject += aud0;
    ctu = aud4;
    aud = (aud + 1);
  }
  while (ctu == 1);
    if (ctu == 0) {
    pho = 32;
  }
  tsubject += " ";
  fact.innerHTML = " " + tsubject + " associates to " + engram;
  preview = "";
  seqverb = "";
  engram = "";
  aud = holdaud;
  tsubject = "";
  kb.appendChild(fact);
}

function showVerb() {
  var aha = document.getElementById("idea");
  var taxi = document.getElementById("node");
  var tax = (document.getElementById("node").value);
  taxi.value = tax;
  if (equity == 1) tax = 1;
  if (equity == 2) tax = 2;
  if (equity == 3) tax = 3;
  if (equity == 4) tax = 4;
  if (equity == 5) tax = 5;
  if (equity == 6) tax = 6;
  if (equity == 7) tax = 7;
  if (equity == 8) tax = 8;
  if (equity == 9) tax = 9;
  if (equity == 10) tax = 10;
  if (equity == 11) tax = 11;
  if (equity == 12) tax = 12;
  if (equity == 13) tax = 13;
  if (equity == 14) tax = 14;
  if (equity == 15) tax = 15;
  if (equity == 16) tax = 16;
// if (equity == 17) tax = 17; // prevent ectopic rectangles; 29sep2010
// if (equity == 18) tax = 18; // prevent ectopic rectangles; 29sep2010
  var syntax = "syn"+tax;
  var concept = document.createElement("div");
  concept.setAttribute("id",syntax);
  concept.style.setAttribute('position', 'absolute');
  concept.style.setAttribute('left', '216');
  concept.style.setAttribute('top', '60');
  if (tax==1) concept.style.setAttribute('top', '250');
  if (tax==2) concept.style.setAttribute('top', '270');
  if (tax==3) concept.style.setAttribute('top', '290');
  if (tax==4) concept.style.setAttribute('top', '310');
  if (tax==5) concept.style.setAttribute('top', '330');
  if (tax==6) concept.style.setAttribute('top', '350');
  if (tax==7) concept.style.setAttribute('top', '370');
  if (tax==8) concept.style.setAttribute('top', '390');
  if (tax==9) concept.style.setAttribute('top', '410');
  if (tax==10) concept.style.setAttribute('top', '430');
  if (tax==11) concept.style.setAttribute('top', '450');
  if (tax==12) concept.style.setAttribute('top', '470');
  if (tax==13) concept.style.setAttribute('top', '490');
  if (tax==14) concept.style.setAttribute('top', '510');
  if (tax==15) concept.style.setAttribute('top', '530');
  if (tax==16) concept.style.setAttribute('top', '550');
  if (tax==17) concept.style.setAttribute('top', '570'); // 29sep2010
  if (tax==18) concept.style.setAttribute('top', '590'); // 29sep2010
  if (tax==19) concept.style.setAttribute('top', '610'); // 29sep2010
  if (tax==20) concept.style.setAttribute('top', '630'); // 29sep2010
  concept.style.setAttribute('width', '220');
  concept.style.setAttribute('height', '19');
  concept.style.setAttribute('backgroundColor', 'pink');
  holdaud = aud;
  do {
    audMemory[aud].audExam();
    tverb += aud0;
    ctu = aud4;
    aud = (aud + 1);
  }
  while (ctu == 1);
    if (ctu == 0) {
    pho = 32;
  }
  tverb += " ";
  concept.innerHTML = tverb + " associates to " + sloshmark + engram;
  preview = "";
  engram = "";
  aud = holdaud;
  tverb = "";
  aha.appendChild(concept);
}
 
function showObject() {
  var query = document.getElementById("radar");
  var turi = document.getElementById("ufo");
  var tur = (document.getElementById("ufo").value);
  turi.value = tur;
  if (city == 1) tur = 1;
  if (city == 2) tur = 2;
  if (city == 3) tur = 3;
  if (city == 4) tur = 4;
  if (city == 5) tur = 5;
  if (city == 6) tur = 6;
  if (city == 7) tur = 7;
  if (city == 8) tur = 8;
  if (city == 9) tur = 9;
  if (city == 10) tur = 10;
  if (city == 11) tur = 11;
  if (city == 12) tur = 12;
  if (city == 13) tur = 13;
  if (city == 14) tur = 14;
  if (city == 15) tur = 15;
  if (city == 16) tur = 16;
  if (city == 17) tur = 17; // prevent ectopic rectangles; 29sep2010
  var abitur = "abi"+tur;
  var answer = document.createElement("div");
  answer.setAttribute("id",abitur);
  answer.style.setAttribute('position', 'absolute');
  answer.style.setAttribute('left', '440');
  answer.style.setAttribute('top', '50');
  if (tur==1) answer.style.setAttribute('top', '240');
  if (tur==2) answer.style.setAttribute('top', '260');
  if (tur==3) answer.style.setAttribute('top', '280');
  if (tur==4) answer.style.setAttribute('top', '300');
  if (tur==5) answer.style.setAttribute('top', '320');
  if (tur==6) answer.style.setAttribute('top', '340');
  if (tur==7) answer.style.setAttribute('top', '360');
  if (tur==8) answer.style.setAttribute('top', '380');
  if (tur==9) answer.style.setAttribute('top', '400');
  if (tur==10) answer.style.setAttribute('top', '420');
  if (tur==11) answer.style.setAttribute('top', '440');
  if (tur==12) answer.style.setAttribute('top', '460');
  if (tur==13) answer.style.setAttribute('top', '480');
  if (tur==14) answer.style.setAttribute('top', '500');
  if (tur==15) answer.style.setAttribute('top', '520');
  if (tur==16) answer.style.setAttribute('top', '540');
  if (tur==17) answer.style.setAttribute('top', '560'); // 29sep2010
  answer.style.setAttribute('width', '210');
  answer.style.setAttribute('height', '19');
  answer.style.setAttribute('backgroundColor', 'yellow');
  holdaud = aud;
  do {
    audMemory[aud].audExam();
    tobject += aud0;
    ctu = aud4;
    aud = (aud + 1);
  }
  while (ctu == 1);
    if (ctu == 0) {
    pho = 32;
  }
  tobject += " ";
  answer.innerHTML = "  " + tobject + " activates " + engram;
  preview = "";
  aud = holdaud;
  tobject = "";
  engram = "";
  query.appendChild(answer);
}
 
function wipeSubject(oldnouns) {
  var istr = document.getElementById("cosmos");
  var zilch = document.getElementById(oldnouns);
  istr.removeChild(zilch);
}
 
function wipeVerb(oldverbs) {
  var btdt = document.getElementById("idea");
  var rasa = document.getElementById(oldverbs);
  btdt.removeChild(rasa);
}
 
function wipeObject(oldobjects) {
  var scnr = document.getElementById("radar");
  var nada = document.getElementById(oldobjects);
  scnr.removeChild(nada);
}
 
function FreeWill() {
  apb = "Volition module has been called.";
  Voice();
}
 
function MotorOutput() {
  apb = "Motorium module has been called.";
  Voice();
}
 

function Diagnostic() {  // 22dec2011; 5jan2012
  psiList();  //  2jan2012
  ruList();   //  2jan2012
  audList();  // 22dec2011
  if (trouble == true) {  // 22dec2011
    document.all.psicolumn.innerHTML = psidata; //  2jan2012
    document.all.rucolumn.innerHTML = rudata;   //  2jan2012
    document.all.audcolumn.innerHTML = auddata; // 22dec2011
   }  // 22dec2011
  html = ""; // 22dec2011
  psidata = ("<b>" + "Psi mindcore concepts" + "<\/b>" + "<BR>");
  psidata += ("krt psi act num jux pre pos tqv seq rux"); // 2jan2012
  rudata = ("<b>" + "Russian lexical fibers" + "<\/b>" + "<BR>");
  rudata += ("krt nru act num mfn dba fex pos fin aud"); // 2jan2012
  auddata = ("<b>" + "Auditory memory nodes" + "<\/b>" + "<BR>");
  auddata += ("krt pho act pov beg ctu audpsi"); // 22dec2011
}  // end of Diagnostic(); 22dec2011; 5jan2012

 
function TuringTest() {
  if (document.all["cb3"].checked == true) {
    document.all["cb1"].checked = false;
    document.all.souvenir.innerHTML = "";
    document.all["cb2"].checked = false;
     tutor = false;
    trouble = true;
    fyi = 3;
  }
  if (document.all["cb3"].checked == false) {
    document.all.tabula.innerHTML = "";
    document.all.psicolumn.innerHTML = "";
    document.all.rucolumn.innerHTML = ""; // 5jan2012
    document.all.audcolumn.innerHTML = "";
    trouble = false;
  }
  if (document.all["cb1"].checked == true) {
    document.all["cb2"].checked = false;
     document.all["cb3"].checked = false;
    document.all.tabula.innerHTML = "";
    document.all.psicolumn.innerHTML = "";
    document.all.rucolumn.innerHTML = ""; // 5jan2012
    document.all.audcolumn.innerHTML = "";
    trouble = false;
    hardcopy = true;
    fyi = 1;
    now = new Date(); 
    adcopy=
("<font size='+2'>Dushka AI version "+vrsn+" on " +now+"<\/b><\/font>");
    document.all.souvenir.innerHTML = adcopy;  // 9jan2012
  }
  if (document.all["cb1"].checked == false) {
    document.all.souvenir.innerHTML = "";
    hardcopy = false;
    document.all.tabula.innerHTML = "";
  }
  if (hardcopy == true) {
    if (userline != "" || output != "" ) {
      Transcript();
    }
  }
  if (document.all["cb2"].checked == true) {
    document.all["cb1"].checked = false;
    document.all.souvenir.innerHTML = "";
    hardcopy = false;
    document.all["cb3"].checked = false;
    document.all.tabula.innerHTML = "";
    document.all.psicolumn.innerHTML = "";
    document.all.rucolumn.innerHTML = ""; // 5jan2012
    document.all.audcolumn.innerHTML = "";
    trouble = false;
    tutor = true;
    fyi = 2;
  }
  if (document.all["cb2"].checked == false) {
    tutor = false;
    if (fyi == 2) fyi = 0;
  }
  if (trouble == true) {
    Diagnostic();
  }
  if (life == true) {
    document.forms[1].ear.focus();
  }
}
 
 
function SeCurity() {
  TuringTest();
  if (t > 160)  nonce = vault;  // Diagnostic display of all thought.
// if (t > 160)  nonce = 1;  // Only while re-coding RuBoot; 9jan2012
  if (t > (cns-64)) ReJuvenate();
  if (life == true) {
apb=("AI 4U on KB psi #"+kbtv+" at t="+t+" is alive on cyc #"+rjc+" since " +dob+ ".");
      if (t > (cns-32)) {
      apb = "WARNING!  Consider clicking Refresh. ";
      apb += ("Only " + (cns-t) + " spaces are left."); 
    }
    Voice();
  } else {
    apb=("<font color='red'>"+"Mental function suspended."+"<\/font>");
    Voice();
  }
}
 
function MainLoop() {
  if (brevity > 0)  wipeSubject("sun" + 1);
  if (brevity > 1)  wipeSubject("sun" + 2);
  if (brevity > 2)  wipeSubject("sun" + 3);
  if (brevity > 3)  wipeSubject("sun" + 4);
  if (brevity > 4)  wipeSubject("sun" + 5);
  if (brevity > 5)  wipeSubject("sun" + 6);
  if (brevity > 6)  wipeSubject("sun" + 7);
  if (brevity > 7)  wipeSubject("sun" + 8);
  if (brevity > 8)  wipeSubject("sun" + 9);
  if (brevity > 9)  wipeSubject("sun" + 10);
  if (brevity > 10) wipeSubject("sun" + 11);
  if (brevity > 11) wipeSubject("sun" + 12);
  if (brevity > 12) wipeSubject("sun" + 13);
  if (brevity > 13) wipeSubject("sun" + 14);
  if (brevity > 14) wipeSubject("sun" + 15);
  if (brevity > 15) wipeSubject("sun" + 16);
  if (brevity > 16) wipeSubject("sun" + 17); // 1oct2010
  brevity = 0;
  star = 0; 
  if (equity > 0)  wipeVerb("syn" + 1);
  if (equity > 1)  wipeVerb("syn" + 2);
  if (equity > 2)  wipeVerb("syn" + 3);
  if (equity > 3)  wipeVerb("syn" + 4);
  if (equity > 4)  wipeVerb("syn" + 5);
  if (equity > 5)  wipeVerb("syn" + 6);
  if (equity > 6)  wipeVerb("syn" + 7);
  if (equity > 7)  wipeVerb("syn" + 8);
  if (equity > 8)  wipeVerb("syn" + 9);
  if (equity > 9)  wipeVerb("syn" + 10);
  if (equity > 10) wipeVerb("syn" + 11);
  if (equity > 11) wipeVerb("syn" + 12);
  if (equity > 12) wipeVerb("syn" + 13);
  if (equity > 13) wipeVerb("syn" + 14);
  if (equity > 14) wipeVerb("syn" + 15);
  if (equity > 15) wipeVerb("syn" + 16);
  if (equity > 16) wipeVerb("syn" + 17); // 1oct2010
  if (equity > 17) wipeVerb("syn" + 18); // 1oct2010
  if (equity > 18) wipeVerb("syn" + 19); // 1oct2010
  if (equity > 19) wipeVerb("syn" + 20); // 1oct2010
  if (equity > 20) wipeVerb("syn" + 21); // 1oct2010
  equity = 0;
  node = 0;
  if (city > 0)  wipeObject("abi" + 1);
  if (city > 1)  wipeObject("abi" + 2);
  if (city > 2)  wipeObject("abi" + 3);
  if (city > 3)  wipeObject("abi" + 4);
  if (city > 4)  wipeObject("abi" + 5);
  if (city > 5)  wipeObject("abi" + 6);
  if (city > 6)  wipeObject("abi" + 7);
  if (city > 7)  wipeObject("abi" + 8);
  if (city > 8)  wipeObject("abi" + 9);
  if (city > 9)  wipeObject("abi" + 10);
  if (city > 10) wipeObject("abi" + 11);
  if (city > 11) wipeObject("abi" + 12);
  if (city > 12) wipeObject("abi" + 13);
  if (city > 13) wipeObject("abi" + 14);
  if (city > 14) wipeObject("abi" + 15);
  if (city > 15) wipeObject("abi" + 16);
  if (city > 16) wipeObject("abi" + 17); // 1oct2010
  city = 0;
  ufo = 0;
  SeCurity();
  SensoryInput();
  brain = true;
  ThInk();  // reserving "inert" for cogpsi calling WhatBe; 18oct2011  
  if (life == true) {
  TID=window.setTimeout("MainLoop();",10000);
  }
}
 </script></head>
<!--*********AI code is above; visible Mind is below**********-->
<body bgcolor="white" onKeyUp="if(event.keyCode==9) Tab();" onLoad="RuBoot()">
<a name="top"></a>

<fieldset>
<legend><font color="navy"><b>
&#1059;&#1087;&#1088;&#1072;&#1074;&#1083;&#1077;&#1085;&#1080;&#1077; - 
 
 <a href="http://www.scn.org/~mentifex/Dushka.html"
 title="Dushka distribution source" 
 style="text-decoration:none;">
&#1044;&#1091;&#1096;&#1082;&#1072;</a> - 
 
 <a href="http://ai.obrazec.ru" 
 title="Club of amateurs and experts in AI" 
 style="text-decoration:none;">
&#1048;&#1089;&#1082;&#1091;&#1089;&#1089;&#1090;&#1074;&#1077;&#1085;&#1085;&#1099;&#1081; 
<!-- artificial -->
 &#1048;&#1085;&#1090;&#1077;&#1083;&#1083;&#1077;&#1082;&#1090;
 <!-- intelligence --></a> - 
 
 <a href="http://mind.sourceforge.net/theory5.html" 
 title="theory of mind for artificial intelligence" 
 style="text-decoration:none;">
&#1058;&#1077;&#1086;&#1088;&#1080;&#1103;
<!-- Theory --></a> - 
 
 <a href="http://www.scn.org/~mentifex/AiMind.html"
 title="AI Mind in English">
AiMind</a> - 
 
 <a href="http://code.google.com/p/mindforth/wiki/RuBoot" 
 title="Russian bootstrap module in JavaScript for MSIE">
RuBoot</a></b>
</font></legend>
<form name="modes">
<input type="checkbox" name="cb1" onClick="Transcript();"> 
 &#1055;&#1088;&#1086;&#1090;&#1086;&#1082;&#1086;&#1083; 
<!-- Protocol (Transcript) --> 

<input type="checkbox" name="cb2" onClick="Tutorial();"> 
 &#1054;&#1073;&#1091;&#1095;&#1077;&#1085;&#1080;&#1077; 
<!-- Tutorial -->

<input type="checkbox" name="cb3" onClick="TuringTest();" checked> 
 &#1044;&#1080;&#1072;&#1075;&#1085;&#1086;&#1089;&#1090;&#1080;&#1082;&#1072 - 
<!-- Diagnostic -->

<a href="http://www.russiankeyboards.com"
 target="_blank"><img border="0" 
 src="http://www.webideas.com/images/icons/free_kbd104x31.gif" 
 width="103" height="31" longdesc="RussianKeyboards.com" 
 alt="Get A Free Russian Keyboard from RussianKeyboards.com!"></a>

<input type="checkbox" name="cb4" onClick="Shutdown();">
<font color="fuchsia"><b>
&#1054;&#1089;&#1090;&#1072;&#1085;&#1086;&#1074;&#1082;&#1072;</b></font> -  
<!-- Halt -->

<input type="checkbox" name="cb5" onClick="Destroy();"> 
<font color="red"><b>
&#1047;&#1072;&#1074;&#1077;&#1088;&#1096;&#1080;&#1090;&#1100; - </font> 
<!-- Terminate --> 
(&#1079;&#1072;&#1082;&#1088;&#1099;&#1090;&#1100; <!-- close -->
 &#1086;&#1082;&#1085;&#1086;)</b><br /> <!-- window -->
</form>
</fieldset>

<div id="mouth" style="position:static; 
 background-color:silver; height:35">
&#1042;&#1089;&#1105;, <!-- All -->
 &#1095;&#1090;&#1086; <!-- what -->
 &#1091;&#1084; <!-- the mind -->
 &#1076;&#1091;&#1084;&#1072;&#1077;&#1090;, <!-- thinks -->
 &#1073;&#1091;&#1076;&#1077;&#1090; <!-- will be -->
 &#1079;&#1076;&#1077;&#1089;&#1100;. <!-- here. -->
</div>

<form onSubmit="if (this.submitted) return true; else {CR(); return false;};">
 <b>&#1053;&#1072;&#1087;&#1080;&#1096;&#1080; <!-- Write -->
 &#1079;&#1076;&#1077;&#1089;&#1100;, <!-- here, -->
 &#1095;&#1090;&#1086; <!-- what -->
 &#1090;&#1099; <!-- you --> 
 &#1076;&#1091;&#1084;&#1072;&#1077;&#1096;&#1100;.</b><br /><!-- think. -->
<input type="text" name="ear" value="" size="80" onKeyDown="AudListen()">
</form>

<div id="brain" style="position:static;
 background-color:lightgreen">
&#1057;&#1086;&#1074;&#1077;&#1090;&#1099; <!-- counsel -->
</div>
 
<noscript>
<p>The Robot AI Mind requires Microsoft Internet Explorer <br />
with JavaScript enabled.<br /></p></noscript>
 
<div id="souvenir" style="position:static; width:640;
 background-color:lightyellow">
MSIE/ View/ Source:  File/ Save As... C:\Dushka.html
</div>
 
<div id="tabula" style="position:static; width:640;
 background-color:clear">
Unclick Diagnostic prior to clicking on Transcript.
</div>
 
<!-- The Diagnostic columns are present but invisible. -->
<div id="psicolumn" style="position:absolute; left:1; top:310;
width:240; height:140; background-color:clear">
</div>
 
<div id="rucolumn" style="position:absolute; left:240; top:310;
width:240; height:140; background-color:clear">
</div>
 
<div id="audcolumn" style="position:absolute; left:480; top:310;
width:200; height:140; background-color:clear">
</div>
 
<div id="cosmos"> 
<font color="navy"><strong><pre>
   Subject associates to verb.   Verb associates to object.    Object free-associates.
  |--------------------------|  |--------------------------|  |----------------------|
  | CATS associates to CHASE |  | EAT associates to  BUGS  |  | FISH activates CATCH |
  | CATS associates to LOVE  |  | EAT associates to +FISH  |  | FISH activates LIKE  |
  | CATS associates to HATE  |  | EAT associates to  BIRDS |  | FISH activates EAT   |
  | CATS associates to EAT   |   --------------------------   | FISH activates CHASE |
  | CATS associates to NEED  |                                | FISH activates AVOID |
   --------------------------                                   ---------------------
</pre></strong></font></div>
 
<div id="idea"> </div>
 
<div id="radar"> </div>

<input type="hidden" value="0" id="star" />
<input type="hidden" value="0" id="node" />
<input type="hidden" value="0" id="ufo" />
 
</body><!-- Change Log comments of the HTML variety:
Tues.13dec2011 "ru111213" initiates the AI Mind Control Panel with links.
Sun.18dec2011 "ru111218" shows display of Russian output.
Tues.20dec2011 "ru111220" uses CP-1251 escape codes for Cyrillic.
Thurs.22dec2011 "ru111222" shows Russian words held in memory.
Wed.28dec2011 "ru111228" prepares a verb for OutBuffer manipulation.
Wed.28dec2011 "ru111229" uses OutBuffer to change verb-endings.
Mon.2jan2012 "ru120102" displays three arrays in Diagnostic mode.
Wed.4jan2012 "ru120104" has minimal RuBoot to test input/output.
Thurs.5jan2012 "ru120105" merges Russian and English AI Minds.
Fri.6jan2012 "ru120106" is first clean-up after merging of code.
Sat.7jan2012 "ru120107" solves the problem of word recognition.
Mon.9jan2012 "ru120109" has RuBoot with words for special modules.
Tues.10jan2012 "ru120110" with WhatBe() has AI asking what it is.
Wed.11jan2012 "ru120111" removes code pertinent to English.
Thurs.12jan2012 "ru120112" removes or deactivates all English code.
Thurs.12jan2012 "12jan12B" achieves recognition of verb-endings.
Sun.15jan2012 "ru120115" achieves recognition of verb-stems.
Tues.17jan2012 "ru120117" uses parameters to select output verb.
Thurs.19jan2012 "ru120119" generates a missing Russian verb-form.
Sat.21jan2012 "ru120121" enhances VerbGen for generating verbs.
(end of HTML Change Log comments) -->
</html>
```