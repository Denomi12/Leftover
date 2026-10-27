# TypeORM za dostop do baze

## Kontekst in opis problema

Backend mora shranjevati in brati podatke iz baze PostgreSQL. Pri tem mora znati izvesti več sprememb skupaj, na primer ob pripravi obroka odšteti zalogo vseh sestavin hkrati. Ker se bo struktura baze med razvojem spreminjala, potrebujem tudi nadzorovan način za njeno posodabljanje, da je baza vedno v pravilnem stanju. Odločiti sem se moral, na kakšen način bo backend komuniciral z bazo.

## Obravnavane možnosti

- TypeORM
- Prisma
- Čisti SQL

## Odločitev

Izbrana možnost: »TypeORM«, ker se najbolj naravno vključi v ogrodje NestJS in pokrije vse, kar od dostopa do baze potrebujem.

TypeORM je uradno podprt v ogrodju NestJS, zato ga lahko uporabim brez dodatnega povezovanja. Podatke iz baze opišem v istem jeziku in na enak način kot preostanek backenda, zato je koda enotna in pregledna. Ker TypeORM pozna obliko podatkov, me urejevalnik opozori na napake, še preden aplikacijo zaženem. Podpira tudi transakcije, ki jih potrebujem pri odštevanju zaloge, in postopne posodobitve strukture baze, s katerimi se baza spreminja nadzorovano in ostane enaka v vseh okoljih.

Prisma je sodobna in zelo priljubljena knjižnica z odličnim preverjanjem podatkov, vendar uporablja svoj način opisovanja podatkov, ki se razlikuje od preostanka backenda. Z NestJS se zato poveže manj naravno. Pri čistem SQL bi imel popoln nadzor nad poizvedbami, a bi moral pretvarjanje podatkov med bazo in kodo ter posodabljanje strukture baze urejati povsem sam, kar pomeni veliko dodatnega dela.

### Posledice

- Dobro, ker se TypeORM brez težav vključi v NestJS in je koda backenda enotna.
- Dobro, ker so napake v obliki podatkov opazne že med pisanjem kode.
- Dobro, ker se struktura baze spreminja nadzorovano in je enaka v vseh okoljih.
- Slabo, ker so zapletenejše poizvedbe, na primer za statistiko, lahko manj pregledne kot v čistem SQL.
- Slabo, ker TypeORM skrije del dogajanja v bazi, kar lahko ob nepazljivosti vodi v počasne poizvedbe.
