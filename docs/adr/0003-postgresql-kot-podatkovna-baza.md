# PostgreSQL kot podatkovna baza

## Kontekst in opis problema

Aplikacija Leftover hrani podatke o uporabnikih, gospodinjstvih, zalogi živil, načrtovanih obrokih in nakupovalnem seznamu. Ti podatki ne stojijo vsak zase, ampak so tesno prepleteni. Uporabnik je lahko član več gospodinjstev in ima v vsakem drugo vlogo, gospodinjstvo ima svojo zalogo in svoje obroke, obroki pa so sestavljeni iz sestavin, ki jih primerjam z zalogo. Potrebujem bazo, ki takšne podatke shranjuje pregledno, omogoča enostavno povezovanje med njimi in poskrbi, da ostanejo pravilni.

## Obravnavane možnosti

- PostgreSQL
- MySQL
- MongoDB

## Odločitev

Izbrana možnost: »PostgreSQL«, ker so podatki v aplikaciji po naravi relacijski, PostgreSQL pa je zanesljiva relacijska baza, ki je dobro podprta v ogrodju NestJS.

Za relacijsko bazo sem se odločil, ker ima vsaka vrsta podatkov v aplikaciji vnaprej znano in stalno obliko. Vsako živilo ima ime, količino, enoto in rok uporabe, vsak obrok ima datum in sestavine, in to se med uporabo ne spreminja. Skoraj vsaka funkcionalnost aplikacije temelji na povezovanju podatkov iz več tabel. Nakupovalni seznam nastane tako, da sestavine načrtovanih obrokov primerjam z zalogo, statistika združuje porabljena in zavržena živila skozi čas, pri vsaki zahtevi pa preverim, ali je uporabnik sploh član gospodinjstva, do katerega dostopa. Relacijska baza je ustvarjena prav za takšne poizvedbe.

Relacijska baza poleg tega sama skrbi za pravilnost podatkov. Povezave med podatki so del strukture baze, zato na primer ne more obstajati živilo, ki ne pripada nobenemu gospodinjstvu. S transakcijami se več sprememb izvede skupaj, zato se ob pripravi obroka zaloga vseh sestavin odšteje v celoti ali pa sploh ne, tudi če jo hkrati spreminja več članov gospodinjstva.

Med relacijskima bazama sem izbral PostgreSQL, ker je odprtokoden, zelo zanesljiv in ima odlično podporo v ogrodju NestJS, ki ga uporabljam za backend. MySQL bi bil prav tako primeren, vendar za ta projekt ne prinaša nobene prednosti, PostgreSQL pa strožje upošteva standard SQL in ponuja več vgrajenih podatkovnih tipov. MongoDB je dokumentna baza, ki je primerna za podatke s spremenljivo obliko, kar za Leftover ne velja. Povezav med podatki ne preverja sama, zato bi moral za to skrbeti v kodi, poizvedbe, ki združujejo več vrst podatkov, pa so v njej bolj zapletene.

### Posledice

- Dobro, ker se povezani podatki enostavno združujejo v poizvedbah za nakupovalni seznam, statistiko in preverjanje pravic.
- Dobro, ker baza sama skrbi, da so povezave med podatki vedno veljavne.
- Dobro, ker transakcije preprečijo napačno stanje zaloge, tudi kadar jo hkrati spreminja več uporabnikov.
- Dobro, ker se PostgreSQL brez težav poveže z ogrodjem NestJS.
- Slabo, ker je treba strukturo podatkov določiti vnaprej in jo ob vsaki spremembi nadzorovano posodobiti.
- Slabo, ker mora za razvoj ves čas teči strežnik baze.
