OutBuffer ParaMeter VerbPhrase

## Code from German DeKi.txt ##

```
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
```

## Function ##

The VerbGen module is called by VerbPhrase after first the "gencon" status-flag is set to "1" unity. The "gencon" flag serves to keep track of whether or not a verb-form is being generated, so that an extra verb-form will not be sent into the SpeechAct module.

The VerbGen module first fills in the AudBuffer by using "audbase" as the start of the auditory engram of the verb that needs to have its inflectional ending changed.

The "gencon" flag is set to "1" unity when VerbGen is called, so that the VerbPhrase module will not make its normal main call to SpeechAct that would result in the output of an extra verb-form.
