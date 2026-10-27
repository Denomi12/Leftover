# NestJS za backend

## Kontekst in opis problema

Backend aplikacije Leftover vsebuje večino poslovne logike. Skrbi za gospodinjstva in vloge članov, zalogo živil, načrt obrokov, nakupovalni seznam in statistiko, poleg tega pa mora pri vsaki zahtevi preveriti, ali ima uporabnik pravico do dejanja, in preveriti vhodne podatke. Ker aplikacijo razvijam sam, potrebujem ogrodje, ki mi že samo da urejeno strukturo, da koda ostane pregledna tudi, ko bo aplikacija rasla.

## Obravnavane možnosti

- NestJS
- Express
- Next.js
- Go

## Odločitev

Izbrana možnost: »NestJS«, ker kodo že samo po sebi razdeli na jasno ločene dele.

NestJS aplikacijo razdeli na module, pri čemer vsak skrbi za svoj del domene, na primer zalogo ali obroke. Znotraj modula je jasno ločeno, kaj sprejema zahteve in kaj vsebuje poslovno logiko. Tako ima vsak del aplikacije svoje mesto in projekt ostane urejen. Ogrodje ima vgrajeno tudi preverjanje pravic, preverjanje vhodnih podatkov in samodejno dokumentacijo API-ja, zato tega ni treba sestavljati iz posameznih knjižnic. Ker teče na Node.js in uporablja TypeScript, pišem frontend in backend v istem jeziku.

Express je zelo preprost in razširjen, vendar ne predpisuje nobene strukture. Organizacijo kode, preverjanje pravic in dokumentacijo bi moral urediti sam, kar se pri večji aplikaciji hitro spremeni v neurejeno kodo. Next.js omogoča tudi pisanje API-ja, vendar je predvsem ogrodje za React frontend. Ker je frontend napisan v Svelte, bi ga uporabljal samo za backend, za kar ni namenjen in ne ponuja dovolj strukture za obsežnejšo poslovno logiko. Go je hiter in zanesljiv, a bi pomenil drug jezik kot na frontendu, prav tako pa bi moral strukturo projekta in večino dodatnih funkcionalnosti urediti sam.

### Posledice

- Dobro, ker ima vsak del domene svoj modul in je koda enotno organizirana.
- Dobro, ker so preverjanje pravic, preverjanje vhodnih podatkov in dokumentacija API-ja že vgrajeni.
- Dobro, ker frontend in backend pišem v istem jeziku.
- Dobro, ker se dobro poveže z izbrano knjižnico za dostop do baze in avtentikacijo.
- Slabo, ker se je treba na začetku naučiti več konceptov kot pri Expressu.
- Slabo, ker je za čisto preproste stvari potrebne nekoliko več kode.
