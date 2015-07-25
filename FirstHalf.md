
```
<html>
<head>
<title>Artificial General Intelligence</title>
<meta name="description" 
 content="English tutorial version of polyglot Mentifex AGI" />
<meta name="keywords" 
 content="AGI, AiMind, artificial intelligence, javascript, 
 machine learning, mind control, modular AI, neural inhibition, 
 prior art, robots, spreading activation, strong AI, tutorial" />
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
var audbase = 0;  // from RuAi; recall-vector for VerbGen(); 17oct2012
var auddata = ("<b>" + "Auditory memory nodes" + "<\/b>" + "<BR>");
auddata += ("krt pho act pov beg ctu audpsi");  // 8dec2009
var audjuste = 0;
var audme = 0;
var audnum = 0;  // de-globalizing the "num" variable;  4nov2012
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
var b16 = "?";  // for OutBuffer(); 4jan2012
var beact = 0;  // for discrimination during BeVerb; 13aug2010
var beg = 0;
var bias = 5;
var binc = 0;  // "b" increment for AudBuffer; 18oct2012
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
// var cns = 768;  // prevent bog-down; 15oct2010
var cns = 1024;  // accommodate enlarged EnBoot; 26oct2012
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
var gencon = 0;  // status-con flag when calling VerbGen; 17oct2012
var ghost = 0;
var glot = 1;  // flag for which language to think in; 9jul2011
// var greet = 10;  // greeting-trigger; 17nov2010
var greet = 5;  // for speedier testing; 29oct2011
var hardcopy = false;
var holdaud = 0;
var holdnum = 0;  // transfer from subject to verb;  4nov2012
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
var nonce = 661;  // for quick loading; 25oct2012
var nounaud = 0;
var nouncall = 0;  // Try not to show articles as subjects; 21may2011
var nounduck = 0; // Disregard prepositional-phrase nouns as subjects.
var nounlock = 0;  // for a verb to lock onto a seq-noun; 13oct2011
var nounval = 0;
var nphrnum = 0;
var nphrpos = 0;  // for testing in EnCog; 13aug2010
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
var output = "";
var pho = "";
var phodex = 0;  // pho-index for AudBuffer(); 4jan2012
var pos = 0;
var posflag = 0;  // AskUser discriminand; 13aug2010
var pov = "#";
var prc = 0;  // possible shortener for "provrec"; 18oct2012
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
var prox1 = 0;  // first proximate concept of input cluster; 14sep2011
var prox2 = 0;  // for determining association among engrams; 14sep2011
var prox3 = 0;  // for disparate reactivation in ReActivate; 14sep2011
var proxcon = 0;  // flag to indicate usage of prox variables; 14sep2011
var prsn = 0;  // 1st, 2nd, 3rd person; 2sep2010
var psi = 0;
var psi0 = 0;
var psi1 = 0;
var psi8 = 0;  // test; 13oct2011
var psibase = 0;
var psidata = ("<b>" + "Psi mindcore concepts" + "<\/b>" + "<BR>");
psidata += ("krt psi act num jux pre pos tqv seq enx"); // 13oct2011
var putnum = 0;  // putative num(ber) for subj-verb agreement; 24oct2011
var questype = 0;
var quiet = true;
var quobj = 0;  // query-object for yes-or-no questions; 22jun2011
var qus = 0;  // provisional query-subject in advance of queries
var qusub = 0; // query subject in more readable code; 2oct2010
var qusubnum = 0;  // num(ber) of query-subject; 27oct2011
var quverb = 0;  // query-verb for yes-or-no questions; 22jun2011
var recnum = 0;  // recognized number of a recognized word 20jul2011
var recon = 0;
var residuum = 0;
var rjc = 0;
var rsvp = 1000;
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
var snu = 0;  // subject-number verb-selection parameter; 18oct2012
var spike = 0;
var spt = 0;
var star = 0;  // For tutorial slosh-over showSubject() display.
var stemgap = 0;
var subjcall = 0;  // To avoid showSubject() of articles; 21may2011
var subjectflag = 0;  // 9dec2009 For NounPhrase to call SelfRef.
var subjnum = 0;  // for agreement with predicate nominative; 18may2011
var subjold = 0;  // old subject as default candidate 29sep2010
var subjprsn = 0; // possible holder of "dba" for input verbs; 31oct2012
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
var vault = 611; // size of EnBoot; 25oct2011
var verblock = 0;  // for subject-noun to lock onto seq-verb; 13oct2011
var verbnum = 0;
var verbpsi = 0;  // for transit into WhatAuxSVerb() 14jun2011
var verbval = 0;
var verbcall = 0;
var vip = 0;  // special ID for verb created by VerbGen; 17oct2012
var vphract = 0;  // verb phrase activation level 22jun2011
var vphraud = 0;  // holds aud-fetch for SpeechAct; 28jun2011
var vrsn = "5dec12A"; // for Transcript mode; wed5dec2012
var vpos = 0;
var wxdflag = 0;  // for inhibition of what-do-X-DO queries; 16sep2010
var wxvflag = 0;  // for inhibition of what-do-X-VERB queries; 16sep2010
var whoskip = 0;
var xthe = 0;
var yncon = 0;  // a statuscon to trigger yes-or-no query; 27jun2011
var ynverb = 0;  // yes-or-no verb for AskUser; 29jun2011
var zone = 0;

// defaultStatus="Click on View...Source to save AiMind.html"

Psi = new Array(cns);
for (i = 0; i < cns; i++) {
  Psi[i] = new psiNode(" "," "," "," "," "," "," "," "," "); // 13oct2011
}

enLexicon = new Array(cns);
for (i = 0; i < cns; i++) { // extra " " for "dba"; 4jan2012
  enLexicon[i] = new enNode(" "," "," "," "," "," "," "," "," ");
  // nen,act,num,mfn,dba,fex,pos,fin,aud since "dba" on 4jan2012
}

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
    document.all.encolumn.innerHTML = "";
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
      if (psi0 == 117) psi1 = 0;   //  117=THE; 24oct2012
      if (psi0 == 781) psi1 = 0;  // 781=WHAT; 23oct2012
      if (psi0 == 830) psi1 = 0;  // 830=DO; 23oct2012
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
  for (i = t; i>midway; --i) {
    Psi[i].psiExam();
     if (urpsi > 0) {  // 20sep2006 To prevent needless dampings.
      if (psi0==urpsi) { 
    // if (psi1 > 0) {  // positive activation?; 8sep2010
       if (psi1 > -1) {  // positive activation?; 27oct2011
    Psi[i] = new psiNode(psi0,residuum,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
       }  // end of test to avoid inhibited concepts; 8sep2010
      }
     }
  }
  residuum = 0;
  PsiDecay();  // Testing to see if new version works well; 25may2011
}  // End of PsiDamp(); 15nov2010


function EnDamp() {  // Wiki-page form of name; 4may2011
  for (i = (t + 1); i>midway; --i) {
    enLexicon[i].enExam();
    enLexicon[i] = new enNode(en0,"0",en2,en3,en4,en5,en6,en7,en8);
  }
}

function audDamp() {
  for (i = t; i > midway; --i) {
    audMemory[i].audExam();
    if (aud4 == 1) aud5 = 0;
    audMemory[i] = new audNode(aud0,0,aud2,aud3,aud4,aud5);
  }
}

function Shutdown() {
  if (document.all["cb4"].checked == true) {
    life = false;
apb = "You have halted the AI Mind at Rejuvenation cycle #"+rjc+".";
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
    document.all.encolumn.innerHTML = "";
    document.all.audcolumn.innerHTML = "";
    trouble = false;
    hardcopy = true;
    fyi = 1;
    now = new Date(); 
    adcopy=("<font size='+2'>AiMind version "+vrsn+" on " +now+"<\/b><\/font>");
    document.all.souvenir.innerHTML = adcopy;
  }
  Transcribe();
  if (hardcopy == true) {
    document.all.psicolumn.innerHTML = "";
    document.all.encolumn.innerHTML = "";
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

function enList() {  // adding en8; 4jan2012
  for (i = nonce; i < (t +1); i++) {
    enLexicon[i].enExam();
    endata += ("<BR>"+i+". <b>" +en0+"<\/b> "+en1+" "+en2+" ");
    endata += (en3+" "+en4+" "+en5+" "+en6+" "+en7+" "+en8);
  }
}

function audList() {
  for (i = nonce; i < (t +1); i++) {
    audMemory[i].audExam();
    auddata += ("<BR>" + i + ". <b>");
    if (aud2 == "*") auddata += ("<font color='red'>");
    auddata += (aud0 + "<\/b> ");
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
          psi1 = (psi1 + 8);  // from MindForth; for queries; 15aug2012
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
                      enLexicon[k].enExam();
                      if (seq7enx == en0) {
                        seq7aud = en8; // aud for psi7 "seq";  4jan2012
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
                      enLexicon[k].enExam();
                      if (oldpsi == en0) {
                        svo5aud = en8; // 4jan2012
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
        if (psi0 == 781) {  // 781=WHAT; 23oct2012
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
          if (seqpsi == 791) {  // 791=who; 23oct2012
            spike = 1;  // de-activate 791=WHO; 23oct2012
          }  // end of test for 791=WHO; 23oct2012
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
 // if (vacpsi==57) vacpsi = 800;  //  AM becomes BE; 21oct2012
 // if (vacpsi==66) vacpsi = 800;  //  IS becomes BE; 21oct2012
 // if (vacpsi==67) vacpsi = 800;  // ARE becomes BE; 21oct2012
    for (i=(t + 1); i>midway; --i) {
      Psi[i].psiExam();
      if (psi0 == vacpsi) {  // deglobalized; 1oct2010
         if (psi1 > -1) { // avoid inhibited nodes;  7jun2011
          if (moot==0) {  // deprive queries of tags; 22aug2011
           psi1 = (psi1 + verbval); // CUMULATIVE for slosh-over; 7jun2011
          }  // end of test for a moot query input; 22aug2011
         }  // end of test to skip inhibited nodes;  7jun2011
         if (psi0 == 781) {  // 781=WHAT; 23oct2012
           psi1 = 0;  // Set WHAT at zero activation; 7jun2011
         }  // End of test for 781=WHAT; 23oct2012
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
 // for (i=(t + 1); i>midway; --i) {
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
        if (firstword==781) psi1 = 48;  // 781=WHAT; 31oct2012
        if (psi0 == 781) psi1 =  0; // 781=WHAT; 23oct2012
        if (psi0 == 791) psi1 =  0; // 791=WHO; 23oct2012
        if (psi0 == 830) psi1 = 0; // 830=DO; 23oct2012
        if (psi0 == 66) psi1 =  8; // suppress 66=IS; 19jun2011
        if (psi0 == 95) psi1 =  8; // suppress 95=IT; 19jun2011
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
        prepsi = psi4;  // deglobalized; 1oct2010
        seqpsi = psi7;  // psi6 is changing to "tqv"; 13oct2011
        zone = i;
        pre = precand;
        psi1 = 0;
        seqpsi = 0;  // deglobalized; 1oct2010
        spike = 1;
       }  // End of test for external "*" POV; 10may2011 
      }
    }
  }
}  // end of ReActivate() 1oct2010


function InNativate() { // quasi-instantiate EnBoot sequence; 23oct2011
  Psi[t] = new psiNode(psi,0,num,0,pre,pos,tqv,seq,enx);
}  // end of InNativate(); 23oct2011


function OutBuffer() {  // for manipulation of SpeechAct words; 4jan2012
  if (c16>"") {  // if the AudBuffer full; 4jan2012
    b16=c16; b15=c15; b14=c14; b13=c13; b12=c12; b11=c11; 
    b10=c10; b09=c09; b08=c08; b07=c07; b06=c06; b05=c05; 
    b04=c04; b03=c03; b02=v02; b01=c01;  // 4jan2012
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 16-character word; 4jan2012
  if (c15>"") {  
    b16=c15; b15=c14; b14=c13; b13=c12; b12=c11; b11=c10;
    b10=c09; b09=c08; b08=c07; b07=c06; b06=c05; b05=c04; 
    b04=c03; b03=c02; b02=c01; b01="";  // 4jan2012
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 15-character word; 4jan2012
  if (c14>"") {
    b16=c14; b15=c13; b14=c12; b13=c11; b12=c10; b11=c09;
    b10=c08; b09=c07; b08=c06; b07=c05; b06=c04; b05=c03;
    b04=c02; b03=c01; b02="";  b01="";  // 4jan2012
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 14-character word; 4jan2012
  if (c13>"") {
    b16=c13; b15=c12; b14=c11; b13=c10; b12=c09; b11=c08;
    b10=c07; b09=c06; b08=c05; b07=c04; b06=c03; b05=c02;
    b04=c01; b03="";  b02="";  b01="";  // 4jan2012
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 13-character word; 4jan2012
  if (c12>"") {
    b16=c12; b15=c11; b14=c10; b13=c09; b12=c08; b11=c07;
    b10=c06; b09=c05; b08=c04; b07=c03; b06=c02; b05=c01;
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
    return;  // abandon remainder of function; 
  }  // end of transfer of a 12-character word; 4jan2012
  if (c11>"") {
    b16=c11; b15=c10; b14=c09; b13=c08; b12=c07; b11=c06;
    b10=c05; b09=c04; b08=c03; b07=c02; b06=c01; b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of an 11-character word; 4jan2012
  if (c10>"") {
    b16=c10; b15=c09; b14=c08; b13=c07; b12=c06; b11=c05;
    b10=c04; b09=c03; b08=c02; b07=c01; b06="";  b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 10-character word; 4jan2012
  if (c09>"") {
    b16=c09; b15=c08; b14=c07; b13=c06; b12=c05; b11=c04;
    b10=c03; b09=c02; b08=c01; b07="";  b06="";  b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 9-character word; 4jan2012
  if (c08>"") {
    b16=c08; b15=c07; b14=c06; b13=c05; b12=c04; b11=c03;
    b10=c02; b09=c01; b08="";  b07="";  b06="";  b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of an 8-character word; 4jan2012
  if (c07>"") {
    b16=c07; b15=c06; b14=c05; b13=c04; b12=c03; b11=c02;
    b10=c01; b09="";  b08="";  b07="";  b06="";  b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 7-character word; 4jan2012
  if (c06>"") {
    b16=c06; b15=c05; b14=c04; b13=c03; b12=c02; b11=c01;
    b10="";  b09="";  b08="";  b07="";  b06="";  b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 6-character word; 4jan2012
  if (c05>"") {
    b16=c05; b15=c04; b14=c03; b13=c02; b12=c01; b11="";
    b10="";  b09="";  b08="";  b07="";  b06="";  b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 5-character word; 4jan2012
  if (c04>"") {
    b16=c04; b15=c03; b14=c02; b13=c01; b12="";  b11="";
    b10="";  b09="";  b08="";  b07="";  b06="";  b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 4-character word; 4jan2012
  if (c03>"") {
    b16=c03; b15=c02; b14=c01; b13=""; b12="";  b11="";
    b10="";  b09="";  b08="";  b07="";  b06="";  b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 3-character word; 4jan2012
  if (c02>"") {
    b16=c02; b15=c01; b14="";  b13=""; b12="";  b11="";
    b10="";  b09="";  b08="";  b07="";  b06="";  b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 2-character word; 4jan2012
  if (c01>"") {
    b16=c01; b15=""; b14="";  b13=""; b12="";  b11="";
    b10="";  b09="";  b08="";  b07="";  b06="";  b05="";
    b04="";  b03="";  b02="";  b01="";  // 4jan2012
    return;  // abandon remainder of function; 4jan2012
  }  // end of transfer of a 1-character word; 4jan2012
}  // end of OutBuffer; 28dec2011


function AudBuffer() {  // for transfer of words to OutBuffer; 4jan2012
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
}  // end of AudBuffer(); 4jan2012


function psiExam() {
  psi0 = this.psi;
  psi1 = this.act;
  psi2 = this.num;
  psi3 = this.jux;
  psi4 = this.pre;
  psi5 = this.pos;
  psi6 = this.tqv;  // time-point for "verblock" or "nounlock"
  psi7 = this.seq;  // subSEQuent concept; 13oct2011
  psi8 = this.enx;  // English-transfer tag; 13oct2011
}

function psiNode(psi,act,num,jux,pre,pos,tqv,seq,enx) {
  this.psi = psi;
  this.act = act;
  this.num = num;
  this.jux = jux;
  this.pre = pre;
  this.pos = pos;
  this.tqv = tqv;  // Adding "tqv" on 13oct2011.
  this.seq = seq;
  this.enx = enx;
  this.psiExam = psiExam;
}

function InStantiate() {
// if (seqneed == 0) seqneed = 5;  // for dir.obj. of verb; 15aug2012
  if (seqneed == 0 && dirobj == 1) seqneed = 5;  // RuAi; 22oct2012
  if (precand > 0) pre = precand;
  if (ordo == 1) prevtag = 0;
  if (firstword==781) moot = 1;  // "781=WHAT"; 23oct2012
  if (firstword==830 || firstword==833) {  // 830=DO; 833=DOES; 23oct2011
    moot = 1;  // deprive queries of "pre" and "seq" tags; 23oct2012
  }  // end of test for a DO-query; 23oct2012
  if (lastword == true) {
    seq = 0;
    lastword = false;
  }
  if (psi == 117) {  // Test for 117=THE article; 31oct2012
    prevtag = 0;  // Prevent a definite association; 31oct2012
    seq = 0;  // Prevent a definite association; 31oct2012
  }  // End of test for "THE" from EnArticle(); 31oct2012
  if (pos==6) nounduck = 1;  // Preposition? 31oct2012
  if (nounduck == 0) {  // If no preposition precedes; 31oct2012
    if (pos == 5) {  // If psi is a noun; 31oct2012
      presubj = psi; // Pick only nouns as presubj; 31oct2012
    }  // End of test for a noun; 31oct2012
  }  // End of test of prep-phrase-noun avoidance flag.
  if (presubj > 0) {
    if (pos == 8) {
      prevtag = presubj;
      presubj = 0;
      if (nounduck == 1) nounduck = 0;
    }
  }
  if (psi == 791) {  // 791=WHO; 23oct2012
    whoskip = 1;
    act = 0;
  }
  if (t > 201) {  // Obsolete trick to avoid EnBoot; 31oct2012
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
  //  num = 1;  // even if previously "0" by default; 6nov2011
  //  num = 1;  // Commenting out as a test; 2nov2012
      singflag = 0;  // reset after use; 6nov2011
    }  // end of test for a noun; 6nov2011
  }  // end of test of singularity-flag; 6nov2011
  if (psi==101 || psi==102) singflag = 1;  // after a(n); 24oct2012
  if (psi==781) {  // Special handling of psi #781 WHAT; 23oct2012
   indefartcon = 1;  // Set indefinite article condition; 19apr2011
    act = 0; // suppress "what" in queries; 16sep2010 
  }  // Changing from one line to multiple lines; 19apr2011
  if (psi==791) {  // Special handling of psi #791 WHO; 23oct2012
    defartcon = 1;  // Set definite article condition; 19apr2011
    act = 0;  // To suppress "WHO" during answer; 19apr2011
  }  // End of test for psi #791 WHO; 23oct2012
  if (pov == "*") {  // If POV is external; 20jul2011
    if (pos == 5) {  // If external noun comes in; 20jul2011
       quobj = psi;  // query-object for AskUser; 18aug2011
    }  // End of test for a noun; 20jul2011
  }  // End of test for external "*" point-of-view; 20jul2011
  if (pov == "#") {  // If POV is ASCII 35 "#" internal; 1may2011
    act = 0; // 0 activation for ReEntry concepts; 1may2011
  }  // End of test for "#" internal POV;  1may2011
  if (seq == 0) tqv = 0; // avoid spurious carry-overs; 15aug2012
  num = audnum;  // pass for storage;  4nov2012 
  if (psi==701 || psi==707) num = 1; // sing. I or YOU 31oct2012
  if (psi==713 || psi==719 || psi==725) num=1; // HE or SHE or IT
  if (psi==731 || psi==737 || psi==743) num=2;  // WE; YOU; THEY 
  if (pos==8 && holdnum > 0) num = holdnum;  // agreement; 5nov2012
  Psi[t] = new psiNode(psi,act,num,jux,prevtag,pos,tqv,seq,enx);
  act = 0;  // reset for safety; 27oct2011
  inhibcon = 0;  // reset for safety; 27oct2011
  instnum = num;  // instantiation num(ber); 27oct2011
  if (jux == 250) jux = 0;  // reset after use; 23oct2012
  if (prejux == 250) { // 250=NOT from OldConcept; 23oct2012
    jux = 250;  // set jux for next instantiand; 23oct2012
    prejux = 0;  // reset for safety; 24jul2011
  }  // end of post-instantiation test; 24jul2011
  if (mfn == 1 || mfn == 2) {  // for calling WhoBe; 3aug2011
    mfnflag = mfn;  // both positive and specific; 3aug2011
  }  // end of test to set mfnflag; 3aug2011
  if (mfn == 0) mfnflag = 0;  // reset for safety; 3aug2011 
  preset = 0;
  prevtag = psi;
  if (psi != 830) {  // skip auxiliary verb "830=DO"; 23oct2012
    if (psi != 833) {  // skip auxiliary verb "833=DOES"; 23oct2012
      if (seqneed==8) {  // if looking for a verb; 4oct2011
        if (pos==8) {  // if part-of-speech is verb; 4oct2011
          seq = psi;  // because a verb has arrived; 4oct2011
          seqpos = pos;  // possibly for tqv; 4oct2011
          seqneed = 0;  // zero out after use; 4oct2011
        }  // end of test for 8=pos verb; 4oct2011
        for (i=(t-2); i>vault; --i) {  // find noun needing seq; 4oct2011
          Psi[i].psiExam();  // examine the Psi concept array; 4oct2011
            if (psi5==5 || psi5==7) {  // noun or pronoun? 4oct2011
             if (moot==0) {  // deprive queries of tags; 4oct2011
           Psi[i] = new psiNode(psi0,psi1,psi2,psi3,psi4,psi5,psi6,seq,psi8);
               if (seqpos==8) {  // a verb? 25oct2011
                 tqv = t;  // assign "tqv" value; 25oct2011
                 Psi[i].psiExam();  // 25oct2011
           Psi[i] = new psiNode(psi0,psi1,psi2,psi3,psi4,psi5,t,psi7,psi8);
               }  // end of seqpos=verb test; 25oct2011
             }  // end of test for a moot query input; 4oct2011
             break;  // Change only one seq; 4oct2011
            }  // end of test for subject noun or pronoun; 4oct2011      
        }  // end of backwards loop; 4oct2011
      }  // end of test for needing a verb; 4oct2011
    }  // end of skipping auxiliary verb "833=DOES"; 23oct2012
  }  // end of skipping auxiliary verb "830=DO"; 23oct2012
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
  if (pos==5 || pos==7) seqneed = 8;  // if noun need verb; 4oct2011
  if (pos==6) seqneed = 5;  // if preposition need noun; 4oct2011
  if (psi != 830) {  // skip auxiliary verb "830=DO"; 23oct2012
    if (psi != 833) {  // skip auxiliary "833=DOES"; 23oct2012
      if (pos==8) seqneed = 5;  // if verb need noun; 4oct2011
    }  // end of test to skip auxiliary DOES; 7oct2011
  }  // end of test to skip auxiliary DO; 7oct2011
  dba = 0;  // from RuAi; reset for safety; 19oct2012
  recnum = 0;  // lest carry-over to other words; 20jul2011
  seq = 0;
} // End of InStantiate(); 4sep2010


function enExam() {
  en0 = this.nen;
  en1 = this.act;
  en2 = this.num;
  en3 = this.mfn; // new gender flag; 5apr2010
  en4 = this.dba; // case or person; 4jan2012
  en5 = this.fex; // moved down one; 4jan2012
  en6 = this.pos; // moved down one; 4jan2012
  en7 = this.fin; // moved down one; 4jan2012
  en8 = this.aud; // moved down one; 4jan2012
}

function enNode(nen,act,num,mfn,dba,fex,pos,fin,aud) {
  this.nen = nen;
  this.act = act;
  this.num = num;
  this.dba = dba; // new case or person flag; 4jan2012
  this.mfn = mfn; // new gender flag; 5apr2010
  this.fex = fex;
  this.pos = pos;
  this.fin = fin;
  this.aud = aud;
  this.enExam = enExam;
}


function EnVocab() { // storing "act" and "dba"; 4jan2012
  enLexicon[t] = new enNode(nen,act,num,mfn,dba,fex,pos,fin,aud);
  dba = 0;  // reset for safety; 20oct2012
}


function EnParser() {
 // bias = 5; 
  act = 30;  // MindForth: Activate lower than ReActivate; 8jun2011
  if (pov == "*") {  // only during external input; 15oct2010
    act = (act - ordo); // reduce S-V-O act's; 15oct2010
  }  // end of test for external POV; 15oct2010
  InStantiate();
  if (pos == 5 || pos == 7) bias = 8;  // 4nov2012
  if (pos == 8) bias = 5;
}  // End of EnParser()


function EnReify() {
  for (i = t; i>midway; --i) {  // from MindForth; test; 8jun2011
    Psi[i].psiExam();
    if (psi1 > 0) {
      lexact = psi1;  // from MindForth;  8jun2011
      enLexicon[i].enExam();  // examine English array; 9aug2011
      enLexicon[i] = new enNode(en0,lexact,en2,en3,en4,en5,en6,en7,en8);
    }  // end of test for a psi with positive activation; 9aug2011
    lexact = 0;  // reset for safety; 8jun2011
  }  // end of looping through the Psi concept array;  9aug2011
}  // End of EnReify(); return to NounPhrase or VerbPhrase; 5jul2011


function KbRetro() {  // for yes-or-no answers; 29jun2011
  if (oldpsi == 432 || oldpsi == 404) {  // if yes or no; 23oct2012
    if (oldpsi == 404) {  // 404=NO; 23oct2012
      Psi[tkbv].psiExam(); // expose all values to change two; 3jul2011
      Psi[tkbv] = new psiNode(psi0,64,psi2,12,psi4,psi5,psi6,psi7,psi8);
    }  // End of test for "no" answer; 29jun2011
    if (oldpsi == 432) { // 432=YES; 23oct2012
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
  for (i=t; i>midway; --i) {
    enLexicon[i].enExam();
    if (en0 == oldpsi) {  // conformance with MindForth; 8jul2011
   // if (en2 > 0) unk = en2; // 18jun2011
   // if (en2 > 0) num = en2; //  2nov2012
   // if (en2 > 0) recnum = en2; // test; 19oct2012
   // if (en2 > 0) Excommenting above as test; 2nov2012
      if (en3 > 0) mfn = en3; // 14jun2011
      if (en5 > 0) fex = en5; //  4jan2012
      if (en6 > 0) pos = en6; //  4jan2012
      if (en7 > 0) fin = en7; //  4jan2012
    break;
    }
  }
  if (pos == 5 || pos == 7) { // making a group; test; 27oct2012
    dba = 1; // default before changes; 19oct2012
    if (subjectflag == 1) dba = 1;  // nominative for subject; 19oct2012
    if (dirobj == 1) dba = 4;  // acc. for direct objects; 19oct2012
    if (predflag == 1) dba = 1;  // for predicate nominatives; 20oct2012
    subjprsn = 3;  // default before conditional changes;  2nov2012
    if (oldpsi==701) subjprsn = 1;  // "I" for EnVocab();  1nov2012
    if (oldpsi==707) subjprsn = 2;  // YOU for EnVocab();  1nov2012
    if (oldpsi==713) subjprsn = 3;  //  HE for EnVocab();  1nov2012
    if (oldpsi==719) subjprsn = 3;  // SHE for EnVocab();  1nov2012
    if (oldpsi==725) subjprsn = 3;  //  IT for EnVocab();  1nov2012
    if (oldpsi==731) subjprsn = 1;  //  WE for EnVocab();  1nov2012
    if (oldpsi==737) subjprsn = 2;  // YOU for EnVocab();  1nov2012
    if (oldpsi==743) subjprsn = 3; // THEY for EnVocab();  1nov2012
  }  // end of co-dependent group to circumvent verbs; 27oct2012
  if (oldpsi==800) tbev = t;  // 800=BE; 21oct2012
  if (oldpsi==800) predflag = 1;  // 800=BE; to affect "dba"; 21oct2012
  if (pov == "*") {  // Only during "*" external POV;  1nov2012
    if (pos == 8) {  // if part-of-speech is verb; 31oct2012
      dba = 3;  // a default; test; 1nov2012
      if (subjprsn==1) dba = 1;  // 1st prsn I or WE;  1nov2012
      if (subjprsn==2) dba = 2;  // 2nd prsn "YOU"; 1nov2012
      if (subjprsn==3) dba = 3;  // 3rd prsn; 2nov2012
     } // end of test for a verb;  2nov2012
  }  // end of test for external POV; 2nov2012
  num = audnum;  // pass for storage;  5nov2012
  if (pos==8) num = holdnum;  //  4nov2012
  if (pos==5) holdnum = audnum;  // transfer to verb;  4nov2012
  enLexicon[t] = new enNode(oldpsi,"0",num,mfn,dba,fex,pos,fin,aud);
  if (pov == "{") oldpsi = fex;  // deglobalizing psi; 3jul2011
  if (pov == "#") oldpsi = fex;  // deglobalizing psi; 3jul2011
  if (pov == "}") oldpsi = fex;  // deglobalizing psi; 3jul2011
  if (pov == "*") oldpsi = fin;  // deglobalizing psi; 3jul2011
  enx = oldpsi;  // deglobalizing psi; 3jul2011
  if (oldpsi==250) {  // 250=NOT; 23oct2012
     if (tbev > 0) {  // 15aug2011
       Psi[tbev].psiExam();  // examine Psi array at "tbev"; 15aug2011
       psi3 = 250;  // set verb "jux" to 250=NOT; 23oct2012
       Psi[tbev] = new psiNode(psi0,psi1,psi2,psi3,psi4,psi5,psi6,psi7,psi8);
       tbev = 0;  // reset for safety; 15aug2011
     }  // end of test for positive time-of-beverb; 15aug2011
  }  // end of test for 250=NOT; 23oct2012
  if (oldpsi == 370) {  // 370=WHY; 31oct2012
    act = 8;  // subactivate question "why".
    questype = 370;  // 31oct2012: Keep track of "why" being asked,
    // so that ConJoin() may provide the conjunction "because".
  }  // End of test to deal with "why" questions.
  if (oldpsi == 117) act = 0;  // 117=THE; 31oct2012
  if (kbcon > 0) {  // if user answers yes-or-no question; 3jul2011
    KbRetro();  // retroactively adjust knowledge base; 3jul2011
    kbcon = 0;  // reset for safety; 3jul2011
  }  // User has had one chance to answer yes-or-no question.
  if (oldpsi == 781) act = 0;  // suppress WHAT for queries; 23oct2012
  if (oldpsi == 791) act = 0;  // Subactivate question "who"; 23oct2012
  if (oldpsi == 830) act = 8; // Sub-activate auxiliary 830=DO 23oct2012
  if (oldpsi == 250) {  // upon recognition of 250=NOT; 23oct2012
    prejux = 250;  // flag for concept to be negated; 23oct2012
  }  // end of test for input or ReEntry of 250=NOT; 23oct2012
  psi = oldpsi;  // from MindForth; 3jul2011
  if (pos==5) num = audnum;  // 5nov2012
  if (pos==8) num = holdnum;  //  4nov2012
  if (pos==5) holdnum = audnum;  // transfer to verb;  4nov2012
  EnParser();  // leads to psiNode storage by InStantiate()
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
  dba = 0;  // Reset to prevent carry-over; 19oct2012
  if (pos == 8) {  // if a verb; 30jun2011
    quverb = psi;  // for yes-or-no question; 30jun2011
  }  // end of test for incoming verb; 30jun2011
  num = 0;  // test; remove; 18jun2011
  psi = 0;  // test; remove; 30jun2011
}  // End of OldConcept; return to AudInput(); 22aug2011


function NewConcept() {
  nen = (nen + 1);
  psi = nen;
  fex = nen;
  fin = nen;
  act = 24;
  pos = bias;
  if (predflag == 1 && pos == 5) dba = 1;  // noun; 20oct2012
  if (pov == "*") {  // if new psi, probably external POV anyway
    if (pos == 5) {  // 6nov2012
      dba = 1;  // a default at first;  6nov2012
    }  // end of test for noun or pronoun; 6nov2012
    if (pos == 8) {  // if part-of-speech is verb; 1nov2012
      dba = 3;  // a default; test; 1nov2012
      if (subjprsn==1) dba = 1;  // 1st prsn I or WE;  1nov2012
      if (subjprsn==2) dba = 2;  // 2nd prsn 707=YOU;  1nov2012
      if (subjprsn==3) dba = 3;  // 3rd prsn;  2nov2012
    }  // end of test for input of a verb;  1nov2012
  }  // end of test for external POV; 1nov2012
  if (pos==5) num = audnum;  // pass for storage;  4nov2012
  if (pos==8) num = holdnum;  //  4nov2012
  if (pos==5) holdnum = audnum;  // transfer to verb;  4nov2012
  EnVocab();  // creates new enLexicon node;  6nov2012
  dba = 0;  // reset after storing value; 19oct2012
  fin = 0;
  fex = 0;
  enx = nen;
  if (pos==5) num = audnum;  // pass for storage;  4nov2012
  if (pos==8) num = holdnum;  //  4nov2012
  if (pos==5) holdnum = audnum;  // transfer to verb;  4nov2012
  EnParser();  // leads to psiNode storage by InStantiate()
  if (pos == 5) {
    cogpsi = nen;  // for WhatBe; 18oct2011
    cognum = instnum;  // from InStantiate; 27oct2011
    recon = 1;
    topic = nen;  // potentially a query "topic";  7jul2011
    quobj = nen;  // for AskUser; test; 22jun2011
//  bias = 8;  // to expect a verb;  4nov2012
  }
  if (pos == 8) quverb = nen;  // for AskUser; test; 22jun2011
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
      enLexicon[i].enExam();  // examine the English lexicon; 25sep2011
   // if (en0 == 51) {  // 51=NOTHING  25sep2011
      if (en0 == 760) {  // 760=NOTHING (without a camera);  2nov2012
        aud = en8; // hold address for SpeechAct;  4jan2011
        break;  // search no further after finding engram; 25sep2011
      }  // end of test for default "760=NOTHING";  2nov2012
    }  // end of English lexicon search loop; 25sep2011
  }  // end of test for zero direct object; 25sep2011
}  // End of VisRecog(); return to VerbPhrase(); 25sep2011


function AudRecog() {
  psi = 0;
  act = 8;
  actbase = 0;
  for (i=spt; i>midway; i--) {
    audMemory[i].audExam();
    if (aud0 == pho) {
      if (aud1 == 0) {
        if (aud3 == 1) {  // if beg=1 on matching no-act aud engram;
         if (audrun < 2) {  // If comparing start of word; 13jul2010
          if (aud4 == 1) {  // If beg-aud0 has ctu=1 continuing,
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
          psi = 0;
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
 // else num = 1;  // Commenting out on 6nov2011
 //  else num = 0;  // a default quasi-singular; 6nov2011
    else num = 1;  // a default quasi-singular;  2nov2012
 // if (recnum > 0) num = recnum;  // override; 20jul2011
  }
  audpsi = psi;  // 9dec2009 For transfer from AudRecog() to AudMem()
  stemgap = 0;  // safety measure; 25sep2011
}  // End of AudRecog()


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
}


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
    pho = String.fromCharCode(c);
    if (hardcopy == true) {
      inbuffer += pho; 
    }
    ++t;
    if (eot == 13) {
      beg = 1;
      c = 32;
  // output = "";  // end on-screen persistence of output; 6nov2011
  // outputplus = "";  // end on-screen persistence of output; 6nov2011
    }
    if (c == 32) { // From CR or space-bar; 12jul2010.
      audrun = 1;  // Reset to 1 at end of word; 12jul2010.
      ordo = (ordo + 1);  // 22aug2011
      if (ordo==1) firstword = audpsi;  // 22aug2011
      AudInput();  // To register a space-bar; 12jul2010.
    }  // End of expanded if-clause; 12jul2010.
    beg = 1;
    ctu = 1;
    pho = pho.toUpperCase();
    if (bias == 5) {  // If expecting a noun; 27may2011
   // num = 1;  // start with default singular; 2nov2012
      if (c == 83 || c == 115) { // "s" or "S"; 27may2011
        num = 2;  // Set num(ber) to plural; 27may2011
        audnum = 2;  // Set num(ber) to plural; 4nov2012
      }  // End of test for "s" or "S"; 27may2011
      if (c > 0) {  // Disregard empty pho; 27may2011
        if (c != 32) {  //  Disregard SPACE; 27may2011
          if (c != 13) {  // Disregard CR; 27may2011
            if (c != 115) {  // If not "s"; 27may2011
              if (c != 83) {  // If not "S"; 27may2011
             // num = 1;  // Assume singular number; 27may2011
             // num = 0;  // Default singular is 0; 6nov2011
                num = 1;  // Assume singular number; 2nov2012
                audnum = 1;  // Assume singular;  4nov2012
              }  // If last letter not "S"; 27may2011
            }  // If last letter not "s"; 27may2011
          }  // End of test for carriage-return; 27may2011
        }  // End of test for SPACE; 27may2011
      }  // End of test for empty pho; 27may2011
    }  // End of test for bias towards a noun; 27may2011
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
}  // End of event-driven AudListen(); 4nov2012


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
    document.all.encolumn.innerHTML = "";
    document.all.audcolumn.innerHTML = "";
    document.all["cb1"].checked = true;
   }
  if (fyi == 2) {
    document.all["cb1"].checked = false;
    document.all.psicolumn.innerHTML = "";
    document.all.encolumn.innerHTML = "";
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
    document.all.encolumn.innerHTML = "";
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
  holdnum = 0;  // reset for safety;  4nov2012
  c = 32;   // as if SPACE-BAR "32" were pressed
  AudInput();
  eot = 0;
  firstword = 0;  // not valid beyond current input; 1nov2011
  moot = 0;  // assuming end of moot user queries; 1nov2011
  ordo = 0;
  quiet = true;
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
      audMemory[tult] = new audNode(aud0,aud1,aud2,aud3,aud4,audpsi);
    }
    if (the1 == 0) { 
      the1 = audpsi;  // 8dec2009 "audpsi" replacing "psi"
    } 
    else if (the2 == 0) { 
      the2 = audpsi;  // 8dec2009 "audpsi" replacing "psi"
    }
    else if (the3 == 0) { 
      the3 = audpsi; // 8dec2009 "audpsi" replacing "psi
    }
    else if (the4 == 0) { 
      the4 = audpsi; // 8dec2009 "audpsi" replacing "psi
    }
    else if (the5 == 0) {
      the5 = audpsi; // 8dec2009 "audpsi" replacing "psi
    } 
    else if (the6 == 0) {
      the6 = audpsi; // 8dec2009 "audpsi" replacing "psi
    }
    else if (the7 == 0) {
      the7 = audpsi; // 8dec2009 "audpsi" replacing "psi
    }
    else  {
      xthe = xthe;
    }
    oldpsi = audpsi;  // for conformance with MindForth; 3jul2011
    OldConcept();
    psi = 0;
    audpsi = 0;  // 8dec2009 de-globalizing "psi"
    aud = 0;
    dba = 0;  // From RuAi; reset for safety; 19oct2012
  } else {  // i.e., if AudRecog has not recognized word; 12may2011
    if (len > 0) {
      aud = onset;
      NewConcept();  // AudInput() calls NewConcept(); 12may2011
      audMemory[tult].audExam();
      if (aud4 == 0) {
        audMemory[tult] = new audNode(aud0,aud1,aud2,aud3,aud4,nen);
      }
    }
  }
  audDamp();
  len = 0;
  onset = 0;
  predflag = 0;  // prevent carry-over; 5dec2012
  aud = 0;
} // End of AudInput; return to AudListen(), CR() or ReEntry().


function SensoryInput() {
  // navigator.geolocation.getCurrentPosition(lost,found) // 16oct2010
  if (life == true) {
    document.forms[1].ear.focus();
  }
}


function EnBoot() {
TuringTest();
act = 0;    // 8dec2009
jux = 0;    // 8dec2009
pov = "#";  // 8dec2009
t = 0;      // 8dec2009
spt = t;    // 8dec2009
// ERROR -- first word so any bug will announce itself 
t=1;pho="E"; beg=1; ctu=1; audpsi=0; AudMem();
t=2;pho="R"; beg=0; ctu=1; audpsi=0; AudMem();
t=3;pho="R"; beg=0; ctu=1; audpsi=0; AudMem();
t=4;pho="O"; beg=0; ctu=1; audpsi=0; AudMem();
t=5;pho="R"; beg=0; ctu=0; audpsi=586; AudMem();  // 25oct2012
nen=586; mfn=3; dba=0; fex=586; pos=5; fin=586; aud=1;
psi=586; num=1; pre=0; seq=0; enx=586; EnVocab(); InNativate();

// A -- En(glish) Article for EnArticle module 
t=7;pho="A"; beg=1; ctu=0; audpsi=101; AudMem();  // 25oct2012
nen=101; mfn=0; dba=0; fex=101; pos=1; fin=101; aud=7;
psi=101; num=1; pre=0; seq=0; enx=101; EnVocab(); InNativate();

// ALL -- for machine reasoning logic 
t=9; pho="A"; beg=1; ctu=1; audpsi=0; AudMem();
t=10; pho="L"; beg=0; ctu=1; audpsi=0; AudMem();
t=11; pho="L"; beg=0; ctu=0; audpsi=123; AudMem(); // 25oct2012
nen=123; mfn=0; dba=0; fex=123; pos=1; fin=123; aud=9;
psi=123; num=0; pre=0; seq=0; enx=123; EnVocab(); InNativate();

// AN -- to be selected instead of "A" before a vowel 
t=13;pho="A"; beg=1; ctu=1; audpsi=0; AudMem();
t=14;pho="N"; beg=0; ctu=0; audpsi=102; AudMem();  // 25oct2012
nen=102; mfn=0; dba=0; fex=102; pos=1; fin=102; aud=13;
psi=102; num=1; pre=0; seq=0; enx=102; EnVocab(); InNativate();

// AND -- for machine reasoning logic 
t=16; pho="A"; beg=1; ctu=1; audpsi=0; AudMem();
t=17; pho="N"; beg=0; ctu=1; audpsi=0; AudMem();
t=18; pho="D"; beg=0; ctu=0; audpsi=302; AudMem(); // 25oct2012
nen=302; mfn=0; dba=0; fex=302; pos=3; fin=302; aud=16;
psi=302; num=0; pre=0; seq=0; enx=302; EnVocab(); InNativate();

// ANY -- for machine reasoning logic 
t=20; pho="A"; beg=1; ctu=1; audpsi=0; AudMem();
t=21; pho="N"; beg=0; ctu=1; audpsi=0; AudMem();
t=22; pho="Y"; beg=0; ctu=0; audpsi=111; AudMem(); // 25oct2012
nen=111; mfn=0; dba=0; fex=111; pos=1; fin=111; aud=20;
psi=111; num=0;  pre=0; seq=0; enx=111; EnVocab(); InNativate();

// ANYTHING -- a default direct object for AskUser()
t=24; pho="A"; beg=1; ctu=1; audpsi=0; AudMem();
t=25; pho="N"; beg=0; ctu=1; audpsi=0; AudMem();
t=26; pho="Y"; beg=0; ctu=1; audpsi=0; AudMem();
t=27; pho="T"; beg=0; ctu=1; audpsi=0; AudMem();
t=28; pho="H"; beg=0; ctu=1; audpsi=0; AudMem();
t=29; pho="I"; beg=0; ctu=1; audpsi=0; AudMem();
t=30; pho="N"; beg=0; ctu=1; audpsi=0; AudMem();
t=31; pho="G"; beg=0; ctu=0; audpsi=711; AudMem(); // 11nov2012
nen=711; mfn=0; dba=4; fex=711; pos=7; fin=711; aud=24;
psi=711; num=1; pre=0; seq=0; enx=711; EnVocab(); InNativate();

// BAD -- adjective for EnAdjective module 
t=33; pho="B"; beg=1; ctu=1; audpsi=0; AudMem();
t=34; pho="A"; beg=0; ctu=1; audpsi=0; AudMem();
t=35; pho="D"; beg=0; ctu=0; audpsi=186; AudMem(); // 25oct2012
nen=186; mfn=0; dba=0; fex=186; pos=1; fin=186; aud=33;
psi=186; num=0; pre=0; seq=0; enx=186; EnVocab(); InNativate();

// BE -- infinitive impersonal form of 800=BE; 25oct2012
t=37;pho="B"; beg=1; ctu=1; audpsi=0; AudMem();
t=38;pho="E"; beg=0; ctu=0; audpsi=800; AudMem(); // 21oct2012
nen=800; mfn=0; dba=0; fex=800; pos=8; fin=800; aud=37; 
psi=800; num=0; pre=0; seq=0; enx=800; EnVocab(); InNativate();

// AM -- 1st person singular I-form of 800=BE; 25oct2012
t=40;pho="A"; beg=1; ctu=1; audpsi=0; AudMem();
t=41;pho="M"; beg=0; ctu=0; audpsi=800; AudMem();  // 11nov2012
nen=800; mfn=0; dba=1; fex=800; pos=8; fin=800; aud=40; 
psi=800;num=1;pre=0;tqv=0;seq=0;enx=800;EnVocab();InNativate();

// ARE -- 2nd person singular YOU-form of 800=BE; 25oct2012
t=43; pho="A"; beg=1; ctu=1; audpsi=0; AudMem();
t=44; pho="R"; beg=0; ctu=1; audpsi=0; AudMem();
t=45; pho="E"; beg=0; ctu=0; audpsi=800; AudMem();  // 21oct2012
nen=800; mfn=0; dba=2; fex=800; pos=8; fin=800; aud=43; 
psi=800; num=1; pre=0; seq=0; enx=800; EnVocab(); InNativate();

// IS -- 3rd person singular HE-SHE-IT-form of 800=BE; 25oct2012
t=47;pho="I"; beg=1; ctu=1; audpsi=0; AudMem();
t=48;pho="S"; beg=0; ctu=0; audpsi=800; AudMem();  // 22oct2012
nen=800; mfn=0; dba=3; fex=800; pos=8; fin=800; aud=47; 
psi=800; num=1; pre=0; seq=0; enx=800; EnVocab(); InNativate();

// ARE -- 1st person plural WE-form of 800=BE; 25oct2012
t=50; pho="A"; beg=1; ctu=1; audpsi=0; AudMem();
t=51; pho="R"; beg=0; ctu=1; audpsi=0; AudMem();
t=52; pho="E"; beg=0; ctu=0; audpsi=800; AudMem();  // 21oct2012
nen=800; mfn=0; dba=1; fex=800; pos=8; fin=800; aud=50; 
psi=800; num=2;  pre=0; seq=0; enx=800; EnVocab(); InNativate();

// ARE -- 2nd person plural YOU-form of 800=BE; 25oct2012
t=54; pho="A"; beg=1; ctu=1; audpsi=0; AudMem();
t=55; pho="R"; beg=0; ctu=1; audpsi=0; AudMem();
t=56; pho="E"; beg=0; ctu=0; audpsi=800; AudMem();  // 25oct2012
nen=800; mfn=0; dba=2; fex=800; pos=8; fin=800; aud=54; 
psi=800; num=2;  pre=0; seq=0; enx=800; EnVocab(); InNativate();

// ARE -- 3rd person plural THEY-form of 800=BE; 25oct2012
t=58; pho="A"; beg=1; ctu=1; audpsi=0; AudMem();
t=59; pho="R"; beg=0; ctu=1; audpsi=0; AudMem();
t=60; pho="E"; beg=0; ctu=0; audpsi=800; AudMem();  // 25oct2012
nen=800; mfn=0; dba=3; fex=800; pos=8; fin=800; aud=58; 
psi=800; num=2;  pre=0; seq=0; enx=800; EnVocab(); InNativate();

// BECAUSE -- conjunction for machine reasoning logic 
t=62;pho="B"; beg=1; ctu=1; audpsi=0; AudMem();
t=63;pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=64;pho="C"; beg=0; ctu=1; audpsi=0; AudMem();
t=65;pho="A"; beg=0; ctu=1; audpsi=0; AudMem();
t=66;pho="U"; beg=0; ctu=1; audpsi=0; AudMem();
t=67;pho="S"; beg=0; ctu=1; audpsi=0; AudMem();
t=68;pho="E"; beg=0; ctu=0; audpsi=344; AudMem(); // 25oct2012
nen=344; mfn=0; dba=0; fex=344; pos=3; fin=344; aud=62;
psi=344; num=0; pre=0; seq=0; enx=344; EnVocab(); InNativate();

// BECOME -- essential intransitive verb 
t=70;pho="B"; beg=1; ctu=1; audpsi=0; AudMem();
t=71;pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=72;pho="C"; beg=0; ctu=1; audpsi=0; AudMem();
t=73;pho="O"; beg=0; ctu=1; audpsi=0; AudMem();
t=74;pho="M"; beg=0; ctu=1; audpsi=0; AudMem();
t=75;pho="E"; beg=0; ctu=0; audpsi=808; AudMem(); // 25oct2012
nen=808; mfn=0; dba=0; fex=808; pos=8; fin=808; aud=70;
psi=808; num=0; pre=0; seq=0; enx=808; EnVocab(); InNativate();

// BOY -- always masculine noun for use with gender flags 
t=77;pho="B"; beg=1; ctu=1; audpsi=0; AudMem();
t=78;pho="O"; beg=0; ctu=1; audpsi=0; AudMem();
t=79;pho="Y"; beg=0; ctu=0; audpsi=589; AudMem(); // 11nov2012
nen=589; mfn=1; dba=0; fex=589; pos=5; fin=589; aud=77; 
psi=589; num=1; pre=0; seq=0; enx=589; EnVocab(); InNativate();

// BUT -- conjunction for ConJoin module 
t=81; pho="B"; beg=1; ctu=1; audpsi=0; AudMem();
t=82; pho="U"; beg=0; ctu=1; audpsi=0; AudMem();
t=83; pho="T"; beg=0; ctu=0; audpsi=305; AudMem(); // 11nov2012
nen=305; mfn=0; dba=0; fex=305; pos=3; fin=305; aud=81;
psi=305; num=0; pre=0; seq=0; enx=305; EnVocab(); InNativate();

// CHESS -- important singular AI noun ending in "S"
t=85; pho="C"; beg=1; ctu=1; audpsi=0; AudMem();
t=86; pho="H"; beg=0; ctu=1; audpsi=0; AudMem();
t=87; pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=88; pho="S"; beg=0; ctu=1; audpsi=0; AudMem();
t=89; pho="S"; beg=0; ctu=0; audpsi=564; AudMem(); // 25oct2012
nen=564; mfn=0; dba=0; fex=564; pos=5; fin=564; aud=85;
psi=564; num=1; pre=0; seq=0; enx=564; EnVocab(); InNativate();

// CHILD -- example of irregular noun for a polyglot AI Mind
t=91; pho="C"; beg=1; ctu=1; audpsi=0; AudMem();
t=92; pho="H"; beg=0; ctu=1; audpsi=0; AudMem();
t=93; pho="I"; beg=0; ctu=1; audpsi=0; AudMem();
t=94; pho="L"; beg=0; ctu=1; audpsi=0; AudMem();
t=95; pho="D"; beg=0; ctu=0; audpsi=525; AudMem(); // 25oct2012
nen=525; mfn=0; dba=0; fex=525; pos=5; fin=525; aud=91;
psi=525; num=1; pre=0; seq=0; enx=525; EnVocab(); InNativate();

// CHILDREN -- irregular plural for retrieval by parameters
t=97; pho="C"; beg=1; ctu=1; audpsi=0; AudMem();
t=98; pho="H"; beg=0; ctu=1; audpsi=0; AudMem();
t=99; pho="I"; beg=0; ctu=1; audpsi=0; AudMem();
t=100; pho="L"; beg=0; ctu=1; audpsi=0; AudMem();
t=101; pho="D"; beg=0; ctu=1; audpsi=0; AudMem();
t=102; pho="R"; beg=0; ctu=1; audpsi=0; AudMem();
t=103; pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=104; pho="N"; beg=0; ctu=0; audpsi=526; AudMem(); // 25oct2012
nen=526; mfn=0; dba=0; fex=526; pos=5; fin=526; aud=97;
psi=526; num=2; pre=0; seq=0; enx=526; EnVocab(); InNativate();

// DATA -- always plural noun in correction of modern usage 
t=106;pho="D"; beg=1; ctu=1; audpsi=0; AudMem();
t=107;pho="A"; beg=0; ctu=1; audpsi=0; AudMem();
t=108;pho="T"; beg=0; ctu=1; audpsi=0; AudMem();
t=109;pho="A"; beg=0; ctu=0; audpsi=599; AudMem(); // 25oct2012
nen=599; mfn=0; dba=0; fex=599; pos=5; fin=599; aud=106;
psi=599; num=2; pre=0; seq=0; enx=599; EnVocab(); InNativate();

// DO -- infinitive form of verb essential for AuxVerb module 
t=111;pho="D"; beg=1; ctu=1; audpsi=0; AudMem();
t=112;pho="O"; beg=0; ctu=0; audpsi=830; AudMem(); // 25oct2012
nen=830; mfn=0; dba=0; fex=830; pos=8; fin=830; aud=111;
psi=830; num=0; pre=0; seq=0; enx=830; EnVocab(); InNativate();

// DO -- 1st person singular I-form of auxiliary verb
t=114;pho="D"; beg=1; ctu=1; audpsi=0; AudMem();
t=115;pho="O"; beg=0; ctu=0; audpsi=830; AudMem(); // 25oct2012
nen=830; mfn=0; dba=1; fex=830; pos=8; fin=830; aud=114;
psi=830; num=1; pre=0; seq=0; enx=830; EnVocab(); InNativate();

// DO -- 2nd person singular YOU-form of auxiliary verb
t=117;pho="D"; beg=1; ctu=1; audpsi=0; AudMem();
t=118;pho="O"; beg=0; ctu=0; audpsi=830; AudMem(); // 25oct2012
nen=830; mfn=0; dba=2; fex=830; pos=8; fin=830; aud=117;
psi=830; num=1; pre=0; seq=0; enx=830; EnVocab(); InNativate();

// DOES -- 3rd person singular HE-SHE-IT-form of auxiliary verb
t=120;pho="D"; beg=1; ctu=1; audpsi=0; AudMem();
t=121;pho="O"; beg=0; ctu=1; audpsi=0; AudMem();
t=122;pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=123;pho="S"; beg=0; ctu=0; audpsi=833; AudMem(); // 25oct2012
nen=833; mfn=0; dba=3; fex=833; pos=8; fin=833; aud=120;
psi=833;  num=1; pre=0; seq=0; enx=833; EnVocab(); InNativate();

// DO -- 1st person plural WE-form of auxiliary verb
t=125;pho="D"; beg=1; ctu=1; audpsi=0; AudMem();
t=126;pho="O"; beg=0; ctu=0; audpsi=830; AudMem(); // 25oct2012
nen=830; mfn=0; dba=1; fex=830; pos=8; fin=830; aud=125; 
psi=830; num=2; pre=0; seq=0; enx=830; EnVocab(); InNativate();

// DO -- 2nd person plural YOU-form of auxiliary verb
t=128;pho="D"; beg=1; ctu=1; audpsi=0; AudMem();
t=129;pho="O"; beg=0; ctu=0; audpsi=830; AudMem(); // 25oct2012
nen=830; mfn=0; dba=2; fex=830; pos=8; fin=830; aud=128;
psi=830; num=2; pre=0; seq=0; enx=830; EnVocab(); InNativate();

// DO -- 3rd person plural THEY-form of auxiliary verb
t=131;pho="D"; beg=1; ctu=1; audpsi=0; AudMem();
t=132;pho="O"; beg=0; ctu=0; audpsi=830; AudMem(); // 25oct2012
nen=830; mfn=0; dba=3; fex=830; pos=8; fin=830; aud=131;
psi=830; num=2; pre=0; seq=0; enx=830; EnVocab(); InNativate();

// DOING -- high word-frequency verb participle  
t=134;pho="D"; beg=1; ctu=1; audpsi=0; AudMem();
t=135;pho="O"; beg=0; ctu=1; audpsi=0; AudMem();
t=136;pho="I"; beg=0; ctu=1; audpsi=0; AudMem();
t=137;pho="N"; beg=0; ctu=1; audpsi=0; AudMem();
t=138;pho="G"; beg=0; ctu=0; audpsi=183; AudMem(); // 25oct2012
nen=183; mfn=0; dba=0; fex=183; pos=1; fin=183; aud=134;
psi=183; num=0; pre=0; seq=0; enx=183; EnVocab(); InNativate();

// ELSE -- adverb for machine reasoning logic; 11nov2012
t=140;pho="E"; beg=1; ctu=1; audpsi=0; AudMem();
t=141;pho="L"; beg=0; ctu=1; audpsi=0; AudMem();
t=142;pho="S"; beg=0; ctu=1; audpsi=0; AudMem();
t=143;pho="E"; beg=0; ctu=0; audpsi=266; AudMem(); // 25oct2012
nen=266; mfn=0; dba=0; fex=266; pos=2; fin=266; aud=140;
psi=266; num=0; pre=0; seq=0; enx=266; EnVocab(); InNativate();

// FOR -- preposition for EnPrep module 
t=145; pho="F"; beg=1; ctu=1; audpsi=0; AudMem();
t=146; pho="O"; beg=0; ctu=1; audpsi=0; AudMem();
t=147; pho="R"; beg=0; ctu=0; audpsi=640; AudMem(); // 25oct2012
nen=640; mfn=0; dba=0; fex=640; pos=6; fin=640; aud=145;
psi=640; num=0; pre=0; seq=0; enx=640; EnVocab(); InNativate();

// FRIEND -- for coding assignment of ad-hoc gender tags
t=149;pho="F"; beg=1; ctu=1; audpsi=0; AudMem();
t=150;pho="R"; beg=0; ctu=1; audpsi=0; AudMem();
t=151;pho="I"; beg=0; ctu=1; audpsi=0; AudMem();
t=152;pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=153;pho="N"; beg=0; ctu=1; audpsi=0; AudMem();
t=154;pho="D"; beg=0; ctu=0; audpsi=517; AudMem(); // 25oct2012
nen=517; mfn=0; dba=0; fex=517; pos=5; fin=517; aud=149;
psi=517; num=1; pre=0; seq=0; enx=517; EnVocab(); InNativate();

// GIRL -- always feminine noun for use with gender flags )
t=156;pho="G"; beg=1; ctu=1; audpsi=0; AudMem();
t=157;pho="I"; beg=0; ctu=1; audpsi=0; AudMem();
t=158;pho="R"; beg=0; ctu=1; audpsi=0; AudMem();
t=159;pho="L"; beg=0; ctu=0; audpsi=510; AudMem(); // 11nov2012
nen=510; mfn=2; dba=0; fex=510; pos=5; fin=510; aud=156;
psi=510; num=1; pre=0; seq=0; enx=510; EnVocab(); InNativate();

// GOD -- masculine noun important for philosophy of AI
t=161;pho="G"; beg=1; ctu=1; audpsi=0; AudMem();
t=162;pho="O"; beg=0; ctu=1; audpsi=0; AudMem();
t=163;pho="D"; beg=0; ctu=0; audpsi=533; AudMem(); // 25oct2012
nen=533; mfn=1; dba=0; fex=533; pos=5; fin=533; aud=161;
psi=533; num=1; pre=0; seq=0; enx=533; EnVocab(); InNativate();

// GOOD -- adjective for EnAdjective module 
t=165;pho="G"; beg=1; ctu=1; audpsi=0; AudMem();
t=166;pho="O"; beg=0; ctu=1; audpsi=0; AudMem();
t=167;pho="O"; beg=0; ctu=1; audpsi=0; AudMem();
t=168;pho="D"; beg=0; ctu=0; audpsi=140; AudMem(); // 25oct2012
nen=140; mfn=0; fex=140; pos=1; fin=140; aud=165;
psi=140; num=0; pre=0; seq=0; enx=140; EnVocab(); InNativate();

// HAVE -- irregular high word-frequency verb  
t=170;pho="H"; beg=1; ctu=1; audpsi=0; AudMem();
t=171;pho="A"; beg=0; ctu=1; audpsi=0; AudMem();
t=172;pho="V"; beg=0; ctu=1; audpsi=0; AudMem();
t=173;pho="E"; beg=0; ctu=0; audpsi=810; AudMem(); // 25oct2012
nen=810; mfn=0; dba=0; fex=810; pos=8; fin=810; aud=170;
psi=810;  num=0; pre=0; seq=0; enx=810; EnVocab(); InNativate();

// HAS -- high word-frequency irregular verb form 
t=175; pho="H"; beg=1; ctu=1; audpsi=0; AudMem();
t=176; pho="A"; beg=0; ctu=1; audpsi=0; AudMem();
t=177; pho="S"; beg=0; ctu=0; audpsi=810; AudMem(); // 23oct2012
nen=810; mfn=0; dba=3; fex=810; pos=8; fin=810; aud=175; 
psi=810; num=1;  pre=0; seq=0; enx=810; EnVocab(); InNativate();

// HE -- nominative form of high word-frequency pronoun  
t=179;pho="H"; beg=1; ctu=1; audpsi=0; AudMem();
t=180;pho="E"; beg=0; ctu=0; audpsi=713; AudMem(); // 25oct2012
nen=713; mfn=1; dba=1; fex=713; pos=7; fin=713; aud=179; 
psi=713; num=1; pre=0; seq=0; enx=713; EnVocab(); InNativate();

// HIS -- genitive form of personal pronoun  
t=182; pho="H"; beg=1; ctu=1; audpsi=0; AudMem();
t=183; pho="I"; beg=0; ctu=1; audpsi=0; AudMem();
t=184; pho="S"; beg=0; ctu=0; audpsi=113; AudMem(); // 25oct2012
nen=113; mfn=1; dba=2; fex=113; pos=1; fin=113; aud=182; 
psi=113; num=1; pre=0; seq=0; enx=113; EnVocab(); InNativate();

// HIM -- dative indirect-object form of personal pronoun
t=186; pho="H"; beg=1; ctu=1; audpsi=0; AudMem();
t=187; pho="I"; beg=0; ctu=1; audpsi=0; AudMem();
t=188; pho="M"; beg=0; ctu=0; audpsi=713; AudMem(); // 25oct2012
nen=713; mfn=1; dba=3; fex=713; pos=7; fin=713; aud=186; 
psi=713; num=1; pre=0; seq=0; enx=713; EnVocab(); InNativate();

// HIM -- accusative direct-object form of personal pronoun
t=190; pho="H"; beg=1; ctu=1; audpsi=0; AudMem();
t=191; pho="I"; beg=0; ctu=1; audpsi=0; AudMem();
t=192; pho="M"; beg=0; ctu=0; audpsi=713; AudMem(); // 25oct2012
nen=713; mfn=1; dba=4; fex=713; pos=7; fin=713; aud=190; 
psi=713; num=1; pre=0; seq=0; enx=713; EnVocab(); InNativate();

// HELLO -- interjection for human-computer interaction 
t=194;pho="H"; beg=1; ctu=1; audpsi=0; AudMem();
t=195;pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=196;pho="L"; beg=0; ctu=1; audpsi=0; AudMem();
t=197;pho="L"; beg=0; ctu=1; audpsi=0; AudMem();
t=198;pho="O"; beg=0; ctu=0; audpsi=450; AudMem(); // 25oct2012
nen=450; mfn=0; dba=0; fex=450; pos=4; fin=450; aud=194;
psi=450; num=0; pre=0; seq=0; enx=450; EnVocab(); InNativate();

// HERE -- adverb for discussion of physical location
t=200;pho="H"; beg=1; ctu=1; audpsi=0; AudMem();
t=201;pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=202;pho="R"; beg=0; ctu=1; audpsi=0; AudMem();
t=203;pho="E"; beg=0; ctu=0; audpsi=201; AudMem(); // 25oct2012
nen=201; mfn=0; dba=0; fex=201; pos=2; fin=201; aud=200; 
psi=201; num=0; pre=0; seq=0; enx=201; EnVocab(); InNativate();

// HOW -- adverb for EnAdverb module 
t=205; pho="H"; beg=1; ctu=1; audpsi=0; AudMem();
t=206; pho="O"; beg=0; ctu=1; audpsi=0; AudMem();
t=207; pho="W"; beg=0; ctu=0; audpsi=209; AudMem(); // 25oct2012
nen=209; mfn=0; fex=209; pos=2; fin=209; aud=205;
psi=209; num=0;  pre=0; seq=0; enx=209; EnVocab(); InNativate();

// I -- nominative subject-form of personal pronoun; 25oct2012
t=209;pho="I"; beg=1; ctu=0; audpsi=701; AudMem(); // 25oct2012
nen=701; mfn=0; dba=1; fex=701; pos=5; fin=707; aud=209; 
psi=701;num=1;pre=0;tqv=399;seq=800;enx=701;EnVocab();InNativate();

// MINE -- genitive form of personal pronoun; 25oct2012
t=211;pho="M"; beg=1; ctu=1; audpsi=0; AudMem();
t=212;pho="I"; beg=0; ctu=1; audpsi=0; AudMem();
t=213;pho="N"; beg=0; ctu=1; audpsi=0; AudMem();
t=214;pho="E"; beg=0; ctu=0; audpsi=701; AudMem(); // 11nov2012
nen=701; mfn=0; dba=2; fex=701; pos=7; fin=707; aud=211; 
psi=701; num=1; pre=0; seq=0; enx=701; EnVocab(); InNativate();

// ME -- dative indirect-object form of personal pronoun; 25oct2012
t=216;pho="M"; beg=1; ctu=1; audpsi=0; AudMem();
t=217;pho="E"; beg=0; ctu=0; audpsi=701; AudMem(); // 25oct2012
nen=701; mfn=0; dba=3; fex=701; pos=7; fin=707; aud=216;
psi=701;num=1;pre=0;tqv=0;seq=0;enx=701;EnVocab();InNativate();

// ME -- accusative direct-object form of personal pronoun
t=219;pho="M"; beg=1; ctu=1; audpsi=0; AudMem();
t=220;pho="E"; beg=0; ctu=0; audpsi=701; AudMem(); // 25oct2012
nen=701; mfn=0; dba=4; fex=701; pos=7; fin=707; aud=219;
psi=701;num=1;pre=0;tqv=0;seq=0;enx=701;EnVocab();InNativate();

// IF -- for machine reasoning logic 
t=222;pho="I"; beg=1; ctu=1; audpsi=0; AudMem();
t=223;pho="F"; beg=0; ctu=0; audpsi=390; AudMem(); // 23oct2012
nen=390; mfn=0; dba=0; fex=390; pos=3; fin=390; aud=222;
psi=390; num=0; pre=0; seq=0; enx=390; EnVocab(); InNativate();

// IN -- preposition for EnPrep module 
t=225;pho="I"; beg=1; ctu=1; audpsi=0; AudMem();
t=226;pho="N"; beg=0; ctu=0; audpsi=639; AudMem(); // 25oct2012
nen=639; mfn=0; fex=639; pos=6; fin=639; aud=225;
psi=639; num=0; pre=0; seq=0; enx=639; EnVocab(); InNativate();

// IT -- nominative subject-form of personal pronoun; 25oct2012
t=228;pho="I"; beg=1; ctu=1; audpsi=0; AudMem();
t=229;pho="T"; beg=0; ctu=0; audpsi=725; AudMem(); // 25oct2012
nen=725; mfn=3; dba=1; fex=725; pos=7; fin=725; aud=228; 
psi=725; num=1; pre=0; seq=0; enx=725; EnVocab(); InNativate();

// ITS -- genitive form of personal pronoun; 25oct2012
t=231;pho="I"; beg=1; ctu=1; audpsi=0; AudMem();
t=232;pho="T"; beg=0; ctu=1; audpsi=0; AudMem();
t=233;pho="S"; beg=0; ctu=0; audpsi=725; AudMem(); // 25oct2012
nen=725; mfn=3; dba=2; fex=725; pos=7; fin=725; aud=231; 
psi=725; num=1; pre=0; seq=0; enx=725; EnVocab(); InNativate();

// IT -- dative indirect-object form of personal pronoun; 25oct2012 
t=235;pho="I"; beg=1; ctu=1; audpsi=0; AudMem();
t=236;pho="T"; beg=0; ctu=0; audpsi=725; AudMem(); // 25oct2012
nen=725; mfn=3; dba=3; fex=725; pos=7; fin=725; aud=235; 
psi=725; num=1; pre=0; seq=0; enx=725; EnVocab(); InNativate();

// IT -- accusative direct-object form of personal pronoun
t=238;pho="I"; beg=1; ctu=1; audpsi=0; AudMem();
t=239;pho="T"; beg=0; ctu=0; audpsi=725; AudMem(); // 25oct2012
nen=725; mfn=3; dba=4; fex=725; pos=7; fin=725; aud=238; 
psi=725; num=1; pre=0; seq=0; enx=725; EnVocab(); InNativate();

// KNOW -- germane to artificial intelligence 
t=241;pho="K"; beg=1; ctu=1; audpsi=0; AudMem();
t=242;pho="N"; beg=0; ctu=1; audpsi=0; AudMem();
t=243;pho="O"; beg=0; ctu=1; audpsi=0; AudMem();
t=244;pho="W"; beg=0; ctu=0; audpsi=850; AudMem(); // 25oct2012
nen=850; mfn=0; dba=0; fex=850; pos=8; fin=850; aud=241;
psi=850; num=0; pre=0; seq=0; enx=850; EnVocab(); InNativate();

// MAN -- always masculine noun for use with gender flags 
t=246;pho="M"; beg=1; ctu=1; audpsi=0; AudMem();
t=247;pho="A"; beg=0; ctu=1; audpsi=0; AudMem();
t=248;pho="N"; beg=0; ctu=0; audpsi=543; AudMem(); // 25oct2012
nen=543; mfn=1; dba=1; fex=543; pos=5; fin=543; aud=246;
psi=543; num=1; pre=0; seq=0; enx=543; EnVocab(); InNativate();

// MEN -- irregular plural for retrieval by parameters
t=250;pho="M"; beg=1; ctu=1; audpsi=0; AudMem();
t=251;pho="E"; beg=0; ctu=0; audpsi=0; AudMem();
t=252;pho="N"; beg=0; ctu=0; audpsi=543; AudMem(); // 25oct2012
nen=543; mfn=1; dba=0; fex=543; pos=5; fin=543; aud=250;
psi=543; num=2; pre=0; seq=0; enx=543; EnVocab(); InNativate();

// MAYBE -- adverb response as alternative to YES or NO
t=254;pho="M"; beg=1; ctu=1; audpsi=0; AudMem();
t=255;pho="A"; beg=0; ctu=1; audpsi=0; AudMem();
t=256;pho="Y"; beg=0; ctu=1; audpsi=0; AudMem();
t=257;pho="B"; beg=0; ctu=1; audpsi=0; AudMem();
t=258;pho="E"; beg=0; ctu=0; audpsi=270; AudMem(); // 25oct2012
nen=270; mfn=0; dba=0; fex=270; pos=2; fin=270; aud=254;
psi=270; num=0; pre=0; seq=0; enx=270; EnVocab(); InNativate();

// MEDIA -- always plural noun in correction of modern usage 
t=260;pho="M"; beg=1; ctu=1; audpsi=0; AudMem();
t=261;pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=262;pho="D"; beg=0; ctu=1; audpsi=0; AudMem();
t=263;pho="I"; beg=0; ctu=1; audpsi=0; AudMem();
t=264;pho="A"; beg=0; ctu=0; audpsi=584; AudMem(); // 25oct2012
nen=584; mfn=0; dba=0; fex=584; pos=5; fin=584; aud=260;
psi=584; num=2; pre=0; seq=0; enx=584; EnVocab(); InNativate();

// MY -- adjective for personal pronoun "I"; 25oct2012
t=266;pho="M"; beg=1; ctu=1; audpsi=0; AudMem();
t=267;pho="Y"; beg=0; ctu=0; audpsi=181; AudMem(); // 25oct2012
nen=181; mfn=0; dba=0; fex=181; pos=1; fin=182; aud=266;
psi=181; num=0; pre=0; seq=0; enx=181; EnVocab(); InNativate();

// NO -- interjection for human-computer interaction 
t=269;pho="N"; beg=1; ctu=1; audpsi=0; AudMem();
t=270;pho="O"; beg=0; ctu=0; audpsi=404; AudMem(); // 25oct2012
nen=404; mfn=0; dba=0; fex=404; pos=4; fin=404; aud=269;
psi=404; num=0; pre=0; seq=0; enx=404; EnVocab(); InNativate();

// NOT -- for machine reasoning logic 
t=272; pho="N"; beg=1; ctu=1; audpsi=0; AudMem();
t=273; pho="O"; beg=0; ctu=1; audpsi=0; AudMem();
t=274; pho="T"; beg=0; ctu=0; audpsi=250; AudMem(); // 25oct2012
nen=250; mfn=0; dba=0; fex=250; pos=2; fin=250; aud=272;
psi=250; num=0;  pre=0; seq=0; enx=250; EnVocab(); InNativate();

// NOTHING --  VisRecog default for what the AI Mind sees
t=276; pho="N"; beg=1; ctu=1; audpsi=0; AudMem();
t=277; pho="O"; beg=0; ctu=1; audpsi=0; AudMem();
t=278; pho="T"; beg=0; ctu=1; audpsi=0; AudMem();
t=279; pho="H"; beg=0; ctu=1; audpsi=0; AudMem();
t=280; pho="I"; beg=0; ctu=1; audpsi=0; AudMem();
t=281; pho="N"; beg=0; ctu=1; audpsi=0; AudMem();
t=282; pho="G"; beg=0; ctu=0; audpsi=760; AudMem(); // 25oct2012
nen=760; mfn=0; dba=0; fex=760; pos=7; fin=760; aud=276;
psi=760; num=1; pre=0; seq=0; enx=760; EnVocab(); InNativate();

// OF -- preposition for EnPrep module 
t=284;pho="O"; beg=1; ctu=1; audpsi=0; AudMem();
t=285;pho="F"; beg=0; ctu=0; audpsi=604; AudMem(); // 25oct2012
nen=604; mfn=0; fex=604; pos=6; fin=604; aud=284;
psi=604;  num=0; pre=0; seq=0; enx=604; EnVocab(); InNativate();

// OR -- for machine reasoning logic  
t=287;pho="O"; beg=1; ctu=1; audpsi=0; AudMem();
t=288;pho="R"; beg=0; ctu=0; audpsi=324; AudMem(); // 25oct2012
nen=324; mfn=0; dba=0; fex=324; pos=3; fin=324; aud=287;
psi=324; num=0; pre=0; seq=0; enx=324; EnVocab(); InNativate();

// OUR -- adjective for personal pronoun "WE"; 25oct2012
t=290; pho="O"; beg=1; ctu=1; audpsi=0; AudMem();
t=291; pho="U"; beg=0; ctu=1; audpsi=0; AudMem();
t=292; pho="R"; beg=0; ctu=0; audpsi=186; AudMem(); // 25oct2012
nen=186; mfn=0; dba=0; fex=186; pos=1; fin=182; aud=290;
psi=186; num=0; pre=0; seq=0; enx=186; EnVocab(); InNativate();

// PEOPLE -- establish as plural for EnParser 
t=294;pho="P"; beg=1; ctu=1; audpsi=0; AudMem();
t=295;pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=296;pho="O"; beg=0; ctu=1; audpsi=0; AudMem();
t=297;pho="P"; beg=0; ctu=1; audpsi=0; AudMem();
t=298;pho="L"; beg=0; ctu=1; audpsi=0; AudMem();
t=299;pho="E"; beg=0; ctu=0; audpsi=587; AudMem(); // 25oct2012
nen=587; mfn=0; dba=0; fex=587; pos=5; fin=587; aud=294; 
psi=587; num=2; pre=0; seq=0; enx=587; EnVocab(); InNativate();

// PERSON -- for ad-hoc gender tags and robot philosophy 
t=301;pho="P"; beg=1; ctu=1; audpsi=0; AudMem();
t=302;pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=303;pho="R"; beg=0; ctu=1; audpsi=0; AudMem();
t=304;pho="S"; beg=0; ctu=1; audpsi=0; AudMem();
t=305;pho="O"; beg=0; ctu=1; audpsi=0; AudMem();
t=306;pho="N"; beg=0; ctu=0; audpsi=537; AudMem(); // 25oct2012
nen=537; mfn=0; dba=0; fex=537; pos=5; fin=537; aud=301;
psi=537; num=1; pre=0; seq=0; enx=537; EnVocab(); InNativate();

// PLEASE -- interjection for human-computer interaction 
t=308;pho="P"; beg=1; ctu=1; audpsi=0; AudMem();
t=309;pho="L"; beg=0; ctu=1; audpsi=0; AudMem();
t=310;pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=311;pho="A"; beg=0; ctu=1; audpsi=0; AudMem();
t=312;pho="S"; beg=0; ctu=1; audpsi=0; AudMem();
t=313;pho="E"; beg=0; ctu=0; audpsi=410; AudMem(); // 25oct2012
nen=410; mfn=0; fex=410; pos=4; fin=410; aud=308;
psi=410;  num=0; pre=0; seq=0; enx=410; EnVocab(); InNativate();

// SEE -- lets VisRecog report non-KB direct objects.
t=315; pho="S"; beg=1; ctu=1; audpsi=0; AudMem();
t=316; pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=317; pho="E"; beg=0; ctu=0; audpsi=820; AudMem(); // 25oct2012
nen=820; mfn=0; dba=0; fex=820; pos=8; fin=820; aud=315;
psi=820; num=0; pre=0; seq=0; enx=820; EnVocab(); InNativate();

// SHE -- nominative subject-form of personal pronoun; 25oct2012
t=319; pho="S"; beg=1; ctu=1; audpsi=0; AudMem();
t=320; pho="H"; beg=0; ctu=1; audpsi=0; AudMem();
t=321; pho="E"; beg=0; ctu=0; audpsi=719; AudMem(); // 25oct2012
nen=719; mfn=2; dba=1; fex=719; pos=7; fin=719; aud=319; 
psi=719; num=1; pre=0; seq=0; enx=719; EnVocab(); InNativate();

// HERS -- genitive form of personal pronoun; 25oct2012
t=323; pho="H"; beg=1; ctu=1; audpsi=0; AudMem();
t=324; pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=325; pho="R"; beg=0; ctu=1; audpsi=0; AudMem();
t=326; pho="S"; beg=0; ctu=0; audpsi=719; AudMem(); // 25oct2012
nen=719; mfn=2; dba=2; fex=719; pos=7; fin=719; aud=323; 
psi=719; num=1;  pre=0; seq=0; enx=719; EnVocab(); InNativate();

// HER -- dative indirect-object form of pers. pron. 25oct2012
t=328; pho="H"; beg=1; ctu=1; audpsi=0; AudMem();
t=329; pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=330; pho="R"; beg=0; ctu=0; audpsi=719; AudMem(); // 25oct2012
nen=719; mfn=2; dba=3; fex=719; pos=7; fin=719; aud=328; 
psi=719; num=1;  pre=0; seq=0; enx=719; EnVocab(); InNativate();

// HER -- accusative direct-object form of pers. pron. 25oct2012 
t=332; pho="H"; beg=1; ctu=1; audpsi=0; AudMem();
t=333; pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=334; pho="R"; beg=0; ctu=0; audpsi=719; AudMem(); // 25oct2012
nen=719; mfn=2; dba=4; fex=719; pos=7; fin=719; aud=332; 
psi=719; num=1;  pre=0; seq=0; enx=719; EnVocab(); InNativate();

// SOME -- adjective for machine reasoning logic 
t=336;pho="S"; beg=1; ctu=1; audpsi=0; AudMem();
t=337;pho="O"; beg=0; ctu=1; audpsi=0; AudMem();
t=338;pho="M"; beg=0; ctu=1; audpsi=0; AudMem();
t=339;pho="E"; beg=0; ctu=0; audpsi=123; AudMem(); // 25oct2012
nen=123; mfn=0; dba=0; fex=123; pos=1; fin=123; aud=336; 
psi=123; num=0; pre=0; seq=0; enx=123; EnVocab(); InNativate();

// THAT -- high word-frequency pronoun  
t=341;pho="T"; beg=1; ctu=1; audpsi=0; AudMem();
t=342;pho="H"; beg=0; ctu=1; audpsi=0; AudMem();
t=343;pho="A"; beg=0; ctu=1; audpsi=0; AudMem();
t=344;pho="T"; beg=0; ctu=0; audpsi=745; AudMem(); // 25oct2012
nen=745; mfn=0; dba=0; fex=745; pos=7; fin=745; aud=341; 
psi=745; num=1; pre=0; seq=0; enx=745; EnVocab(); InNativate();

// THE -- EnArticle highest-frequency English word 
t=346;pho="T"; beg=1; ctu=1; audpsi=0; AudMem();
t=347;pho="H"; beg=0; ctu=1; audpsi=0; AudMem();
t=348;pho="E"; beg=0; ctu=0; audpsi=117; AudMem(); // 25oct2012
nen=117; mfn=0; fex=117; pos=1; fin=117; aud=346;
psi=117; num=0; pre=0; seq=0; enx=117; EnVocab(); InNativate();

// THEIR -- adjective for personal pronoun "THEY"; 25oct2012
t=350;pho="T"; beg=1; ctu=1; audpsi=0; AudMem();
t=351;pho="H"; beg=0; ctu=1; audpsi=0; AudMem();
t=352;pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=353;pho="I"; beg=0; ctu=1; audpsi=0; AudMem();
t=354;pho="R"; beg=0; ctu=0; audpsi=188; AudMem(); // 25oct2012
nen=188; mfn=0; dba=0; fex=188; pos=1; fin=188; aud=350;
psi=188; num=0; pre=0; seq=0; enx=188; EnVocab(); InNativate();

// THEN -- for machine reasoning logic  
t=356;pho="T"; beg=1; ctu=1; audpsi=0; AudMem();
t=357;pho="H"; beg=0; ctu=1; audpsi=0; AudMem();
t=358;pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=359;pho="N"; beg=0; ctu=0; audpsi=213; AudMem(); // 25oct2012
nen=213; mfn=0; dba=0; fex=213; pos=2; fin=213; aud=356;
psi=213; num=0; pre=0; seq=0; enx=213; EnVocab(); InNativate();

// THERE -- adverb for discussion of physical location 
t=361;pho="T"; beg=1; ctu=1; audpsi=0; AudMem();
t=362;pho="H"; beg=0; ctu=1; audpsi=0; AudMem();
t=363;pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=364;pho="R"; beg=0; ctu=1; audpsi=0; AudMem();
t=365;pho="E"; beg=0; ctu=0; audpsi=205; AudMem(); // 25oct2012
nen=205; mfn=0; dba=0; fex=205; pos=2; fin=205; aud=361;
psi=205; num=0; pre=0; seq=0; enx=205; EnVocab(); InNativate();

// THEY -- nominative subject-form of pers. pronoun; 25oct2012
t=367;pho="T"; beg=1; ctu=1; audpsi=0; AudMem();
t=368;pho="H"; beg=0; ctu=1; audpsi=0; AudMem();
t=369;pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=370;pho="Y"; beg=0; ctu=0; audpsi=743; AudMem(); // 23oct2012
nen=743; mfn=0; dba=1; fex=743; pos=7; fin=743; aud=367; 
psi=743;  num=2; pre=0; seq=0; enx=743; EnVocab(); InNativate();

// THEIRS -- genitive form of personal pronoun; 25oct2012 
t=372;pho="T"; beg=1; ctu=1; audpsi=0; AudMem();
t=373;pho="H"; beg=0; ctu=1; audpsi=0; AudMem();
t=374;pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=375;pho="I"; beg=0; ctu=1; audpsi=0; AudMem();
t=376;pho="R"; beg=0; ctu=1; audpsi=0; AudMem();
t=377;pho="S"; beg=0; ctu=0; audpsi=743; AudMem(); // 31oct2012
nen=743; mfn=0; dba=2; fex=743; pos=7; fin=743; aud=372;
psi=743; num=2; pre=0; seq=0; enx=743; EnVocab(); InNativate();

// THEM -- dative indirect-object form of pers. pron. 25oct2012
t=379;pho="T"; beg=1; ctu=1; audpsi=0; AudMem();
t=380;pho="H"; beg=0; ctu=1; audpsi=0; AudMem();
t=381;pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=382;pho="M"; beg=0; ctu=0; audpsi=743; AudMem(); // 31oct2012
nen=743; mfn=0; dba=3; fex=743; pos=7; fin=743; aud=379;
psi=743; num=2; pre=0; seq=0; enx=743; EnVocab(); InNativate();

// THEM -- acc. direct-object form of pers. pron. 25oct2012
t=384;pho="T"; beg=1; ctu=1; audpsi=0; AudMem();
t=385;pho="H"; beg=0; ctu=1; audpsi=0; AudMem();
t=386;pho="E"; beg=0; ctu=1; audpsi=0; AudMem();
t=387;pho="M"; beg=0; ctu=0; audpsi=743; AudMem(); // 31oct2012
nen=743; mfn=0; dba=4; fex=743; pos=7; fin=743; aud=384;
psi=743; num=2; pre=0; seq=0; enx=743; EnVocab(); InNativate();

// THINK -- germane to artificial intelligence  
t=389;pho="T"; beg=1; ctu=1; audpsi=0; AudMem();
t=390;pho="H"; beg=0; ctu=1; audpsi=0; AudMem();
t=391;pho="I"; beg=0; ctu=1; audpsi=0; AudMem();
t=392;pho="N"; beg=0; ctu=1; audpsi=0; AudMem();
t=393;pho="K"; beg=0; ctu=0; audpsi=840; AudMem(); // 25oct2012
nen=840; mfn=0; dba=0; fex=840; pos=8; fin=840; aud=389;
psi=840; num=0; pre=0; seq=0; enx=840; EnVocab(); InNativate();

// WE -- nominative subject-form of personal pronoun; 25oct2012
t=395;pho="W"; beg=1; ctu=1; audpsi=0; AudMem();
t=396;pho="E"; beg=0; ctu=0; audpsi=731; AudMem(); // 25oct2012
nen=731; mfn=0; dba=1; fex=731; pos=7; fin=737; aud=395; 
psi=731; num=2; pre=0; seq=0; enx=731; EnVocab(); InNativate();

// OURS -- genitive form of personal pronoun; 25oct2012
t=398;pho="O"; beg=1; ctu=1; audpsi=0; AudMem();
t=399;pho="U"; beg=0; ctu=1; audpsi=0; AudMem();
t=400;pho="R"; beg=0; ctu=1; audpsi=0; AudMem();
t=401;pho="S"; beg=0; ctu=0; audpsi=731; AudMem(); // 31oct2012
nen=731; mfn=0; dba=2; fex=731; pos=7; fin=737; aud=398; 
psi=731; num=2; pre=0; seq=0; enx=731; EnVocab(); InNativate();

```