# Uporabniške zgodbe

## US-01

- **Funkcionalnost:** Evidenca zaloge živil
- **Uporabniška vloga:** Član gospodinjstva

**User story:** Kot član gospodinjstva želim v zalogo dodati živilo s količino, mersko enoto in rokom uporabe, da imamo vsi v gospodinjstvu pregled nad tem, kaj imamo doma.

**Acceptance criteria:**

- Živilo se shrani samo, če so vnesena ime, količina in merska enota.
- Če količina ni večja od 0, sistem živila ne shrani in prikaže sporočilo »Količina mora biti večja od 0«.
- Dodano živilo se prikaže v zalogi z imenom, količino, enoto in rokom uporabe.
- Dodano živilo vidijo vsi člani istega gospodinjstva, uporabniki drugih gospodinjstev pa ne.
- Gost živila ne more dodati.

## US-02

- **Funkcionalnost:** Opozorila na bližajoči se rok uporabe
- **Uporabniška vloga:** Član gospodinjstva

**User story:** Kot član gospodinjstva želim videti živila, ki jim bo rok uporabe kmalu potekel ali je že potekel, da jih porabim pravočasno in jih ne zavržem.

**Acceptance criteria:**

- Živila v zalogi so razvrščena po roku uporabe, od najzgodnejšega do najpoznejšega.
- Živila z rokom uporabe danes ali v naslednjih 3 dneh imajo oznako »Kmalu poteče«.
- Živila z rokom uporabe pred današnjim dnem imajo oznako »Poteklo«.
- Če nobeno živilo ne poteče v naslednjih 3 dneh, sistem prikaže sporočilo »Nobeno živilo ne poteče v naslednjih 3 dneh«.

## US-03

- **Funkcionalnost:** Načrt obrokov s sestavinami iz zaloge
- **Uporabniška vloga:** Član gospodinjstva

**User story:** Kot član gospodinjstva želim za izbrani dan načrtovati obrok in mu določiti sestavine s količinami, da vnaprej vem, kaj bomo kuhali in ali imamo za to dovolj sestavin.

**Acceptance criteria:**

- Obrok se shrani samo, če ima ime, datum in vsaj eno sestavino s količino in mersko enoto.
- Načrtovani obroki so razvrščeni po datumu, od najbližjega dneva naprej.
- Pri vsaki sestavini je prikazana oznaka »Na zalogi«, če je v zalogi vsaj potrebna količina, sicer pa oznaka »Manjka«.
- Pri sestavini z oznako »Manjka« sistem prikaže manjkajočo količino (npr. »Manjka 200 g«).
- Gost načrt obrokov vidi, ne more pa dodajati ali urejati obrokov.

## US-04

- **Funkcionalnost:** Samodejni nakupovalni seznam za manjkajoče sestavine
- **Uporabniška vloga:** Član gospodinjstva

**User story:** Kot član gospodinjstva želim, da se manjkajoče sestavine načrtovanih obrokov samodejno dodajo na nakupovalni seznam, da jih ni treba ročno prepisovati in ničesar ne pozabim kupiti.

**Acceptance criteria:**

- Ko je obrok shranjen, sistem za vsako sestavino izračuna razliko med potrebno količino in količino v zalogi.
- Če je razlika večja od 0, se sestavina s to količino doda na nakupovalni seznam.
- Sestavine, ki jih je v zalogi dovolj, se na seznam ne dodajo.
- Če je ista sestavina potrebna v več obrokih, je na seznamu ena postavka s skupno manjkajočo količino.

## US-05

- **Funkcionalnost:** Samodejno odštevanje porabe ob pripravi obroka
- **Uporabniška vloga:** Član gospodinjstva

**User story:** Kot član gospodinjstva želim, da se ob označitvi obroka kot pripravljenega porabljene sestavine samodejno odštejejo od zaloge, da mi zaloge po kuhanju ni treba ročno popravljati.

**Acceptance criteria:**

- Ko je obrok označen kot pripravljen, se količine vseh njegovih sestavin odštejejo od zaloge.
- Živila, katerih količina pade na 0, se odstranijo iz zaloge.
- Če sestavine v zalogi ni dovolj, se odšteje samo razpoložljiva količina, tako da količina živila ne pade pod 0.
- Obroka, ki je že označen kot pripravljen, ni mogoče ponovno označiti kot pripravljenega.
- Gost obroka ne more označiti kot pripravljenega.

## US-06

- **Funkcionalnost:** Skupno gospodinjstvo z vlogami
- **Uporabniška vloga:** Registriran uporabnik

**User story:** Kot registriran uporabnik želim ustvariti svoje gospodinjstvo, da lahko začnem voditi zalogo živil, načrt obrokov in nakupovalni seznam.

**Acceptance criteria:**

- Gospodinjstvo se ustvari samo, če uporabnik vnese ime, dolgo od 1 do 50 znakov.
- Uporabnik, ki ustvari gospodinjstvo, v njem samodejno dobi vlogo lastnik.
- Novo gospodinjstvo ima prazno zalogo, prazen načrt obrokov in prazen nakupovalni seznam.
- Uporabnik je lahko član več gospodinjstev in med njimi preklaplja z izbiro gospodinjstva.

## US-07

- **Funkcionalnost:** Skupno gospodinjstvo z vlogami
- **Uporabniška vloga:** Lastnik gospodinjstva

**User story:** Kot lastnik gospodinjstva želim v gospodinjstvo povabiti sostanovalce in jim dodeliti vlogo član ali gost, da si z njimi delim zalogo, načrt obrokov in nakupovalni seznam.

**Acceptance criteria:**

- Lastnik povabi uporabnika z vnosom e-poštnega naslova in izbiro vloge član ali gost.
- Povabljeni uporabnik se po pridružitvi prikaže na seznamu članov z izbrano vlogo.
- Če e-poštni naslov ne pripada registriranemu uporabniku, sistem prikaže sporočilo »Uporabnik s tem e-naslovom ne obstaja«.
- Če je uporabnik s tem e-poštnim naslovom že član gospodinjstva, sistem prikaže sporočilo »Uporabnik je že član gospodinjstva«.
- Član in gost ne moreta vabiti novih uporabnikov.

## US-08

- **Funkcionalnost:** Evidenca zaloge živil
- **Uporabniška vloga:** Član gospodinjstva

**User story:** Kot član gospodinjstva želim živila v zalogi iskati po imenu in jih razvrščati, da hitro preverim, ali neko živilo že imamo doma.

**Acceptance criteria:**

- Iskanje prikaže vsa živila, katerih ime vsebuje vneseno besedilo, ne glede na velike in male črke (npr. »mle« najde »Mleko« in »Kislo mleko«).
- Seznam živil se posodablja med tipkanjem, brez klika na gumb.
- Zalogo je mogoče razvrstiti po imenu (od A do Ž) ali po roku uporabe, s ponovnim klikom na isti stolpec pa se vrstni red obrne.
- Najdena živila so razvrščena po izbranem stolpcu.
- Če nobeno živilo ne ustreza iskanju, sistem prikaže sporočilo »Živila »[iskano besedilo]« ni v zalogi«.

## US-09

- **Funkcionalnost:** Rezervacija živil za načrtovane obroke
- **Uporabniška vloga:** Član gospodinjstva

**User story:** Kot član gospodinjstva želim, da so količine živil, namenjene načrtovanim obrokom, označene kot rezervirane, da jih drugi člani ne porabijo za kaj drugega.

**Acceptance criteria:**

- Pri živilu v zalogi sta prikazani rezervirana in prosta količina.
- Rezervirana količina je vsota količin tega živila v vseh načrtovanih obrokih, ki še niso pripravljeni.
- Ko je obrok označen kot pripravljen ali izbrisan, se njegova rezervacija sprosti.
- Pri načrtovanju novega obroka se kot razpoložljiva upošteva samo prosta količina.

## US-10

- **Funkcionalnost:** Predlog porabe živil pred iztekom roka
- **Uporabniška vloga:** Član gospodinjstva

**User story:** Kot član gospodinjstva želim, da mi aplikacija med sestavljanjem novega obroka predlaga živila s kratkim rokom uporabe, da iz njih skuham obrok, namesto da jih zavržem.

**Acceptance criteria:**

- Na obrazcu za nov obrok je razdelek »Predlagamo, da porabite« z največ 5 živili, ki jim rok uporabe poteče danes ali v naslednjih 3 dneh.
- S klikom na predlagano živilo se to doda med sestavine obroka s celotno količino iz zaloge, ki jo lahko uporabnik zmanjša.
- Živilo, ki je že dodano med sestavine obroka, se iz predlogov odstrani.
- Če nobeno živilo ne poteče v naslednjih 3 dneh, razdelek »Predlagamo, da porabite« ni prikazan.

## US-11

- **Funkcionalnost:** Minimalna zaloga osnovnih živil
- **Uporabniška vloga:** Član gospodinjstva

**User story:** Kot član gospodinjstva želim za osnovna živila nastaviti minimalno količino, da mi živila, ki jih želim imeti vedno doma, ne zmanjkajo.

**Acceptance criteria:**

- Za živilo je mogoče nastaviti minimalno količino, ki mora biti večja od 0.
- Ko količina živila v zalogi pade pod minimalno količino, se živilo samodejno doda na nakupovalni seznam.
- Količina na seznamu je razlika med minimalno količino in trenutno količino v zalogi.
- Če je živilo že na nakupovalnem seznamu, se ne doda ponovno.

## US-12

- **Funkcionalnost:** Evidenca zavržene hrane
- **Uporabniška vloga:** Član gospodinjstva

**User story:** Kot član gospodinjstva želim celotno živilo ali samo del živila označiti kot zavrženo namesto porabljeno, da imamo pregled nad tem, koliko hrane gre v smeti.

**Acceptance criteria:**

- Pri živilu v zalogi je na voljo možnost »Zavrzi«, kjer uporabnik vnese zavrženo količino (privzeto je izpolnjena celotna količina).
- Zavržena količina mora biti večja od 0 in ne sme biti večja od količine v zalogi, sicer sistem prikaže sporočilo »Vnesite količino med 0 in [količina v zalogi]«.
- Ob delnem zavrženju se zavržena količina odšteje od zaloge, preostanek pa ostane v zalogi (npr. od 500 g jogurta zavržem 200 g, v zalogi ostane 300 g).
- Če uporabnik zavrže celotno količino, se živilo odstrani iz zaloge.
- Za vsako zavrženje se shranijo ime živila, zavržena količina, enota in datum zavrženja.

## US-13

- **Funkcionalnost:** Statistika porabe in zavržene hrane
- **Uporabniška vloga:** Član gospodinjstva

**User story:** Kot član gospodinjstva želim videti mesečni pregled porabljenih in zavrženih živil, da ugotovim, katera živila najpogosteje zavržemo, in jih v prihodnje kupim manj.

**Acceptance criteria:**

- Pregled za izbrani mesec prikaže število porabljenih in število zavrženih živil.
- Pregled prikaže 5 najpogosteje zavrženih živil v izbranem mesecu.
- Privzeto je izbran tekoči mesec.
- Če za izbrani mesec ni podatkov, sistem prikaže sporočilo »Za izbrani mesec ni podatkov«.

## US-14

- **Funkcionalnost:** Zgodovina sprememb zaloge
- **Uporabniška vloga:** Lastnik gospodinjstva

**User story:** Kot lastnik gospodinjstva želim videti, kdo je kdaj dodal, porabil ali zavrgel posamezno živilo, da lahko preverim, kako se je zaloga spreminjala.

**Acceptance criteria:**

- Vsako dodajanje, poraba in zavrženje živila ustvari zapis v zgodovini.
- Vsak zapis vsebuje datum in uro, uporabnika, vrsto spremembe, ime živila in količino.
- Zapisi so razvrščeni od najnovejšega do najstarejšega.
- Zapisov v zgodovini ni mogoče urejati ali brisati.

## US-15

- **Funkcionalnost:** Shranjeni obroki
- **Uporabniška vloga:** Član gospodinjstva

**User story:** Kot član gospodinjstva želim pogosto pripravljene obroke shraniti skupaj s sestavinami, da jih lahko hitro ponovno dodam v načrt obrokov.

**Acceptance criteria:**

- Načrtovani obrok je mogoče shraniti z imenom in sestavinami.
- Shranjeni obrok je mogoče dodati v načrt za izbrani datum, pri čemer se kopirajo vse njegove sestavine.
- Spremembe sestavin v načrtovanem obroku ne spremenijo shranjenega obroka.
- Shranjeni obrok je mogoče izbrisati, kar ne vpliva na že načrtovane obroke.
