AudBuffer RetroSet VerbGen

## Code from German Deki.txt ##

```
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
```