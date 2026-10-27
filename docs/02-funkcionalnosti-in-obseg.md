# Funkcionalnosti in obseg

## Uporabniške vloge

Vloge se določajo na ravni gospodinjstva. Isti uporabnik je lahko v enem gospodinjstvu lastnik, v drugem pa član ali gost.

### Lastnik gospodinjstva (`OWNER`)

Uporabnik, ki je gospodinjstvo ustvaril in zanj skrbi.

**Lahko:**

- vabi nove uporabnike v gospodinjstvo in jih odstranjuje,
- določa in spreminja vloge članov,
- ureja nastavitve gospodinjstva (npr. ime),
- ima vse pravice člana: upravlja zalogo, načrt obrokov in nakupovalni seznam.

**Ne more:**

- dostopati do podatkov gospodinjstev, v katera ni včlanjen,

### Član gospodinjstva (`MEMBER`)

Običajen sostanovalec ali družinski član, ki aktivno uporablja skupni hladilnik.

**Lahko:**

- dodaja živila v zalogo, ureja njihove količine in roke uporabe,
- prejema opozorila o živilih, ki jim poteka rok,
- načrtuje obroke za prihodnje dni,
- ureja nakupovalni seznam in kupljena živila prenese v zalogo.

**Ne more:**

- vabiti ali odstranjevati drugih uporabnikov,
- spreminjati vlog članov,
- spreminjati nastavitev gospodinjstva ali ga izbrisati.

### Gost (`GUEST`)

Občasni uporabnik, npr. varuška, gost na obisku ali družinski član, ki samo pomaga pri nakupu.

**Lahko:**

- pregleduje zalogo živil in njihove roke uporabe,
- pregleduje načrt obrokov,
- pregleduje nakupovalni seznam in na njem označi kupljena živila.

**Ne more:**

- dodajati, urejati ali brisati živil v zalogi,
- spreminjati načrta obrokov ali označiti obroka kot pripravljenega,
- upravljati članov ali nastavitev gospodinjstva.

## Predvidene funkcionalnosti

1. **[MVP] Evidenca zaloge živil** – uporabnik vnese živilo s količino, mersko enoto in rokom uporabe. Zaloga je skupna celotnemu gospodinjstvu.
2. **[MVP] Opozorila na bližajoči se rok uporabe** – sistem živila razvrsti glede na rok uporabe in izpostavi tista, ki jih je treba porabiti v naslednjih nekaj dneh, ter tista, ki so že pretekla.
3. **[MVP] Načrt obrokov s sestavinami iz zaloge** – uporabnik načrtuje obroke za prihodnje dni in vsakemu določi potrebne sestavine in količine. Sistem sproti pokaže, ali je posamezne sestavine dovolj v zalogi.
4. **[MVP] Samodejni nakupovalni seznam za manjkajoče sestavine** – sistem primerja sestavine načrtovanih obrokov z zalogo in razliko samodejno doda na nakupovalni seznam.
5. **[MVP] Samodejno odštevanje porabe ob pripravi obroka** – ko uporabnik obrok označi kot pripravljen, se porabljene količine sestavin odštejejo od zaloge. Porabljena živila se odstranijo.
6. **[MVP] Skupno gospodinjstvo z vlogami** – lastnik povabi člane in jim dodeli vlogo, s čimer si vsi delijo isto zalogo, načrt obrokov in nakupovalni seznam.
7. **Prenos kupljenih živil v zalogo** – ko uporabnik na nakupovalnem seznamu označi živilo kot kupljeno, ga lahko z enim klikom (in vnosom roka uporabe) prenese v zalogo.
8. **Rezervacija živil za načrtovane obroke** – količine, ki so namenjene načrtovanim obrokom, se prikažejo kot rezervirane, da jih drugi člani ne porabijo za kaj drugega.
9. **Predlog porabe živil pred iztekom roka** – pri načrtovanju obrokov sistem izpostavi živila, ki jim bo rok potekel v naslednjih nekaj dneh, da jih uporabnik vključi v obroke.
10. **Minimalna zaloga osnovnih živil** – uporabnik za živila, ki jih želi imeti vedno doma (npr. mleko, jajca), nastavi minimalno količino. Ko zaloga pade pod to mejo, se živilo samodejno doda na nakupovalni seznam.
11. **Evidenca zavržene hrane** – uporabnik lahko živilo označi kot zavrženo namesto porabljeno, kar omogoča spremljanje, koliko hrane gre v smeti.
12. **Statistika porabe in zavržene hrane** – mesečni pregled porabljenih in zavrženih živil ter najpogosteje zavrženih izdelkov.
13. **Zgodovina sprememb zaloge** – pregled, kdo je kdaj dodal, porabil ali zavrgel posamezno živilo.
14. **Shranjeni obroki** – pogosto pripravljene obroke s sestavinami lahko uporabnik shrani in jih nato hitro ponovno doda v načrt.

## Kasnejše nadgradnje

- Integracija z zunanjim API-jem za recepte.
- Primerjava sestavin receptov z zalogo (z normalizacijo imen sestavin) in priporočanje receptov, za katere ima uporabnik že večino sestavin.
- Dodajanje izbranega recepta v načrt obrokov in samodejno ustvarjanje nakupovalnega seznama iz receptov.
- Izračun kalorij in makrohranil za načrtovane obroke.
- Skeniranje črtnih kod pri vnosu živil.

## Out of scope

- Spletno naročanje in plačevanje živil.
- Dostava živil.
- Spremljanje in primerjava cen med trgovinami.
- Prepoznavanje živil s kamero.
- Povezava s pametnimi hladilniki in drugimi napravami.
- Lastna baza receptov oziroma AI-generiranje receptov.
- Zdravstveno oziroma medicinsko prehransko svetovanje.
- Upravljanje zalog za poslovne uporabnike (restavracije, trgovine, kuhinje).
