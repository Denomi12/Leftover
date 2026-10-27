# Svelte (SvelteKit) za frontend

## Kontekst in opis problema

Frontend aplikacije Leftover je sestavljen iz več interaktivnih pogledov. Osrednji je hladilnik s policami in opozorili o rokih uporabe, ob njem pa so še seznam živil z iskanjem, razvrščanjem in filtri, načrt obrokov in nakupovalni seznam. Ker aplikacijo razvijam sam, potrebujem ogrodje, v katerem lahko te poglede zgradim hitro, ki ga v kratkem času obvladam in ki že samo po sebi vodi k urejeni, modularni kodi, da projekt ostane pregleden tudi, ko bo zrasel.

## Obravnavane možnosti

* Svelte s SvelteKit
* React
* Next.js

## Odločitev

Izbrana možnost: »Svelte s SvelteKit«, ker najbolje združuje preprostost in urejeno strukturo projekta.

Svelte ima zelo preprost komponentni model. Reaktivnost je vgrajena v sam jezik, zato stanja ni treba upravljati ročno, komponente pa so kratke in berljive. Vsaka komponenta združuje svojo logiko, videz in sloge, zato je vsak del vmesnika zaključena celota, ki jo lahko ponovno uporabim.

SvelteKit k temu doda jasno in predpisano strukturo projekta. Ogrodje me že samo usmerja k modularni in urejeni kodi, zato mi strukture ni treba izumljati in vzdrževati sam. Vključuje tudi vse, kar je potrebno za osnovno delovanje, zato dodatnih knjižnic ne potrebujem.

React ima največji ekosistem in skupnost, vendar za enako funkcionalnost zahteva več kode, saj je treba stanje upravljati s hooki. Sam po sebi ne predpisuje strukture projekta in nima usmerjanja, zato bi moral oboje urediti sam. Next.js te pomanjkljivosti odpravi, saj je ogrodje nad Reactom z usmerjanjem in jasno strukturo. Ker pa ima aplikacija ločen backend, večine njegovih strežniških zmožnosti ne bi izkoristil, ostala pa bi mi vsa zahtevnost Reacta.

### Posledice

* Dobro, ker ima projekt že od začetka jasno in modularno strukturo map in datotek.
* Dobro, ker je vsaka komponenta zaključena celota, ki jo je lahko ponovno uporabiti in spreminjati.
* Dobro, ker je koda kratka in berljiva, razvoj pa zato hitrejši.
* Dobro, ker se Svelte prevede v majhen JavaScript brez navideznega DOM-a, zato je vmesnik odziven.
* Slabo, ker je izbira že pripravljenih knjižnic komponent manjša kot pri Reactu.
* Slabo, ker je na spletu na voljo manj primerov in odgovorov na pogosta vprašanja.
