tölvutækni og forritun - samantekt og glósur
---

# gömul próf
ætla fara í gegnum gömul próf og reyna að svara öllu, ég vísa stundum í forrit til þess að prufa útkomur úr gefnum föllum
## dæmi um keyrslu
```bash
# þýða
gcc progs/s1.2020.c -o progs/s1.2020

#keyra
progs/s1.2020       # keyrir með "default" gildi, held það sé 146

#eða

progs/s1.2020 3     # keyrir með n = 3
```

það eina sem er komið á þessum tíma er fyrstu tvær spurningar úr [lokaprófi 2020](lokaprof.2020.md)

# hlutir til að setja á glósublað
## conditional codes
þessir kóðar fara á endann á `cmov` skipunum þ.e. `cmov--` í línu eftir að eitthvað er testað eins og í dæmi
```asm
testb   $7, %dl
cmove   $1, %rax
```
þetta er pínu fucked dæmi því `e` flaggið í `cmove` stendur fyrir `equal` nema hvað við erum actually að athuga hvort útkomugildið sé `0`, þ.e. að enginn af neðstu 3 bitunum sé `1`, þá er gott að muna að `e` er jafngilt `z` 

þessi kóði færir `1` inn í `%rax` ef neðstu þrír bitar `%dl` eru ekki `111`

| cc     | condition                       | dæmi  |
| ------ | ------------------------------- | ----- |
| o      | overflow                        | cmovo |
| no     | no overflow                     |
| b, nae | below, not above or equal       |
| nb, ae | not below, above or equal       |
| e, z   | equal (zero)                    |
| ne, nz | not equal, (not zero)           |
| na, be | not above, below or equal       |
| a, nbe | above, not below or equal       |
| s      | sign                            |
| ns     | no sign                         |
| p      | parity                          |
| np     | no parity                       |
| l, nge | less, not greater than or equal |
| nl     | not less, greater than or equal |
| ng, le | not greater, less than or equal |
| g, nle | greater, not less than or equal |
