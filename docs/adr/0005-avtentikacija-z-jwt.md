# Avtentikacija z JWT

## Kontekst in opis problema

Uporabniki se v aplikacijo Leftover prijavijo z e-pošto in geslom. Ker sta frontend in backend ločeni aplikaciji, mora backend pri vsaki zahtevi ugotoviti, kdo jo pošilja, in preveriti, kakšno vlogo ima ta uporabnik v gospodinjstvu. Odločiti sem se moral, kako bo aplikacija prijavljala uporabnike in jih prepoznavala med posameznimi zahtevami.

## Obravnavane možnosti

- JWT
- OAuth
- Supabase Auth
- Keycloak

## Odločitev

Izbrana možnost: »JWT«, ker je za potrebe aplikacije povsem dovolj, ne zahteva nobene zunanje storitve in je že podprt v ogrodju NestJS.

Leftover ne hrani občutljivih podatkov, kot so plačilni ali zdravstveni podatki, zato ne potrebuje zahtevne rešitve za avtentikacijo. Zadošča preprosta prijava z e-pošto in geslom, pri čemer je geslo shranjeno varno zakodirano. Ob prijavi backend izda žeton z omejeno veljavnostjo, ki ga frontend nato pošilja pri vsaki zahtevi. Backend iz žetona prepozna uporabnika, zato mu ni treba hraniti podatkov o prijavljenih sejah. NestJS ima za to že pripravljeno podporo s knjižnico Passport, zato lahko prijavo in preverjanje vlog uredim hitro in na enem mestu.

OAuth bi uporabnikom omogočil prijavo z obstoječim računom, na primer Google, vendar bi aplikacijo naredil odvisno od zunanjega ponudnika, postavitev pa bi bila bolj zapletena, kot je za ta projekt potrebno. Supabase Auth in Keycloak sta celovita sistema za upravljanje uporabnikov, ki ponujata veliko več, kot aplikacija potrebuje. Za njuno uporabo bi moral vzdrževati ali uporabljati še eno ločeno storitev in nanjo povezati svoj backend, kar bi le povečalo zapletenost, ne da bi aplikaciji prineslo kakšno pravo korist.

### Posledice

- Dobro, ker aplikacija ni odvisna od nobene zunanje storitve.
- Dobro, ker je prijava preprosta in jo uredim v celoti znotraj svojega backenda.
- Dobro, ker NestJS in Passport podpirata JWT že sama po sebi.
- Dobro, ker backendu ni treba hraniti podatkov o prijavljenih uporabnikih.
- Slabo, ker izdanega žetona ni mogoče preprosto preklicati, preden mu poteče veljavnost.
- Slabo, ker za varnost gesel in žetonov skrbim sam, namesto da bi to prepustil specializirani storitvi.
