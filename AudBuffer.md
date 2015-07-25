AudInput OutBuffer VerbGen

## Code from German DeKi.txt ##

```
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
```
