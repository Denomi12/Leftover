# Ločen frontend in backend, ki komunicirata prek REST API-ja

## Kontekst in opis problema

Leftover ima netrivialno poslovno logiko: preverjanje vlog v gospodinjstvu, izračun manjkajočih sestavin za nakupovalni seznam, rezervacijo zaloge za načrtovane obroke in odštevanje porabe ob pripravi obroka. Ta pravila morajo veljati enako ne glede na to, od kod pride zahteva. Odločiti sem se moral, ali bosta vmesnik in poslovna logika del ene aplikacije ali dveh ločenih, ter kako bosta komunicirala.

## Obravnavane možnosti

- Ločen frontend in backend, ki komunicirata prek REST API-ja
- Monolitna full-stack aplikacija (SvelteKit s strežniško logiko v API rutah)

## Odločitev

Izbrana možnost: »Ločen frontend in backend, ki komunicirata prek REST API-ja«, ker je tako vsa poslovna logika zbrana na enem mestu in jasno ločena od vmesnika.

Backend je edini, ki pozna pravila aplikacije in dostopa do baze, frontend pa skrbi samo za prikaz in vnose. Zato pravil ni mogoče obiti ali po pomoti podvojiti v vmesniku, isti API pa lahko brez sprememb uporablja tudi drug odjemalec. Za vsak del lahko izberem ogrodje, ki mu najbolj ustreza.

REST sem izbral, ker se podatki naravno delijo na vire, kot so živila, obroki in nakupovalni seznam, vsak pogled pa potrebuje vnaprej znane podatke. Uporablja standardne metode in statusne kode HTTP, končne točke pa lahko testiram neposredno, brez vmesnika.

Monolit v SvelteKit bi bil na začetku najhitrejši, vendar bi bila logika razpršena po rutah vmesnika, brez modulov in vgrajenega preverjanja pravic, ter tesno vezana na frontend.

### Posledice

- Dobro, ker je poslovna logika na enem mestu in je ni treba podvajati.
- Dobro, ker do baze dostopa samo backend, zato pravil ni mogoče obiti.
- Dobro, ker lahko API testiram neposredno (Playwright `request`), neodvisno od vmesnika.
- Dobro, ker je backend pripravljen za druge odjemalce.
- Slabo, ker sta dve aplikaciji, ki ju je treba nastaviti in zagnati (to rešim z Docker Compose).
- Slabo, ker je treba urediti CORS in usklajevati obliko podatkov med frontendom in backendom.
