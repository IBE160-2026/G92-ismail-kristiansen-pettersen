# Tilbakemelding på PRD

| | |
|---|---|
| **Gruppe** | G92 – G92-ismail-kristiansen-pettersen |
| **PRD vurdert** | `_bmad-output/planning-artifacts/prds/prd-AI-Study-Buddy-2026-09-15/prd.md` (status `draft`, sist endret 2026-09-15, commit 4ffaa9f) |
| **Dato** | 2026-11-12 |
| **Type** | Formativ tilbakemelding, ikke karakter |

## 1. Samlet inntrykk

PRD-en er ryddig og ærlig: den skiller mellom det som er bekreftet og det som er «Undecided», og har ingen oppdiktede krav. Problemet er at nesten alt av substans ligger på «Undecided»-siden. Det står to FR-er igjen, og de sier lite mer enn at appen tar inn en fil og gir fem typer resultater. Slik den står nå kan ikke UX, arkitektur eller epics bygge på den uten at noen andre tar beslutningene for dere.

## 2. Dette fungerer godt

- **Ærlig skille mellom bekreftet og uavklart.** §9 «Open Questions» (10 punkter) og «None. This PRD contains no inferred requirements» i §10 viser at dere ikke har pyntet over hull. Det er en god utgangsposisjon for å ta beslutningene.
- **Glossaret er kort og brukes konsekvent.** «Curriculum Material», «Study Resources» og «Reference Pointer» brukes likt i UJ, FR og SM.
- **Ideen om Reference Pointer er en reell styrke.** «reference pointers to relevant sources or pages» (§1, FR-2) gjør at resultater kan kontrolleres mot kilden. Det er det mest testbare i hele PRD-en, og det kan bli tesen.

## 3. Oversikt per dimensjon

| Dimensjon | Vurdering | Kort begrunnelse |
|---|---|---|
| Beslutningsklarhet | mangelfull | Valg er listet som spørsmål, ikke tatt. «**Undecided:** Whether processing begins automatically…» |
| Substans | svak | Ikke boilerplate, men heller ikke fylt: ett persona-navn uten detaljer, ingen konkret bruker. |
| Strategisk sammenheng | mangelfull | Ingen tese. «A vision … beyond this course-project MVP is **Undecided**.» |
| Testbarhet | svak | FR-ene sier «includes summaries», uten grenser eller forventet resultat. |
| Scope og avgrensning | svak | §6/§7.2 utelater bare kjøp/salg og lærerroller. Alt annet er «Undecided». |
| Brukbarhet for neste fase | svak | Én brukerreise med uavklart start og slutt, to FR-er. For lite å hente fra. |
| Formtilpasning | svak | Brukerrettet app med én brukerreise uten skjermflyt. KI-delen er ikke behandlet som egen del. |

## 4. Viktigste forbedringer

### 4.1 Ta beslutningene i stedet for å liste dem
- **Alvorlighet:** kritisk
- **Hvor:** §9 «Open Questions» 1–4, 7, 10; §4.1 Notes («**Undecided:** Local versus cloud processing»)
- **Problem og hvorfor det betyr noe:** Seks av ti åpne spørsmål blokkerer UX, arkitektur og stories direkte. Uten valg om trigger, lagring og antall filer kan ingen tegne skjermbilder eller dele opp epics. Dette ble også påpekt i tilbakemeldingen på briefen, og PRD-en er ikke endret siden (se kap. 6).
- **Forslag:** Ta for eksempel disse valgene og skriv dem som krav med en kort begrunnelse: «Studenten laster opp én PDF- eller tekstfil per økt. Appen genererer alle fem Study Resources etter at studenten trykker *Generer*. Ingenting lagres etter at økten avsluttes. Språkmodell kalles fra serveren via skybasert API.» Hver «Undecided» blir da enten et valg eller en eksplisitt `[NON-GOAL for MVP]`.

### 4.2 Gjør FR-ene testbare
- **Alvorlighet:** høy
- **Hvor:** FR-2: «Study Resources include summaries. / include flashcards …»
- **Problem og hvorfor det betyr noe:** En tester kan ikke avgjøre om «includes summaries» er oppfylt. Det er ingen grenser for antall, format eller feilsituasjoner (tom fil, skannet PDF uten tekst, for stor fil). Stories og tester arver denne uklarheten.
- **Forslag:** Del FR-2 per ressurstype og gi hver målbare konsekvenser. Eksempel: «FR-2c: Appen genererer 5–15 flashcards fra opplastet materiale. Hvert flashcard har spørsmål, svar og ett Reference Pointer med sidetall. Hvis filen ikke inneholder lesbar tekst, viser appen en feilmelding og genererer ingenting.» Legg også til en FR for feil i FR-1 (filtype utenfor PDF/tekst, filstørrelse).

### 4.3 Behandle KI-bruken, testmodus og personvern som krav
- **Alvorlighet:** høy
- **Hvor:** §4.1 Notes («LLM choice and confidence-level behavior»), §5.1, §8 («Measurable standards … No thresholds»)
- **Problem og hvorfor det betyr noe:** Appens kjerne er et språkmodellkall, men PRD-en sier ingenting om hva som skjer når svaret er usikkert eller oppdiktet, hva det koster, eller hvordan appen kan testes og kjøres uten betalt nøkkel. Dette er det vanskeligste å legge til sent, og personvern (opplasting av pensum til ekstern tjeneste) er heller ikke omtalt.
- **Forslag:** Legg til tre krav. «FR-A: Hvert Reference Pointer peker til en side som finnes i opplastet fil; ellers merkes resultatet *ikke verifisert*.» «FR-B: Med `MOCK_AI=true` returnerer appen faste eksempelsvar uten API-kall.» «FR-C: Appen viser før opplasting at materialet sendes til en ekstern tjeneste, og lagrer det ikke.»

### 4.4 Gjør brukerreisen konkret
- **Alvorlighet:** høy
- **Hvor:** §2.2 UJ-1: «Entry state: **Undecided.**» og «Resolution: **Undecided.**»
- **Problem og hvorfor det betyr noe:** Start og slutt er uavklart, og «Alex» har ingen fagsituasjon. Climax («uses them as learning support») sier ikke hva studenten faktisk gjør i appen. Det er derfor vanskelig å lage skjermbilder eller en interaktiv del.
- **Forslag:** Skriv scenen ut: «Alex, førsteårsstudent, har 40 foilsider i et emne og eksamen om en uke. Hen laster opp PDF-en, velger *kort* detaljnivå og norsk, trykker *Generer*, ser sammendrag og begreper, blar flashcards og tar en quiz med poengsum. Hvert spørsmål lenker til kildesiden.» Lag gjerne UJ-2 for feilsituasjonen.

### 4.5 Skjerp scope og suksessmål
- **Alvorlighet:** medium
- **Hvor:** §7.2 («Other possible exclusions remain **Undecided**»), §8 SM-1
- **Problem og hvorfor det betyr noe:** §6 og §7.2 gjentar de samme to punktene. SM-1 («can provide … and receive») er bare «virker det i det hele tatt», og har ingen motmåling.
- **Forslag:** Ta inn utelatelser som sannsynligvis gjelder: innlogging, lagring, tabeller og figurer, flere filer. Erstatt SM-1 med noe målbart: «SM-1: På et fast testdokument (eget eller åpent materiale) har ≥ 90 % av Reference Pointers riktig side.» Legg til en motmåling, for eksempel at svartiden ikke får øke bare for å gi flere kort.

## 5. Mekaniske funn

- ID-er er sammenhengende (UJ-1, FR-1–2, SM-1), og krysshenvisningene løser seg. Det er likevel for få elementer til at det sier mye.
- §10 sier «None» om assumptions, mens «Undecided» fungerer som skjulte åpne punkter. Bruk `[ASSUMPTION]` for valg dere tar uten bekreftelse, og indekser dem.
- Teksten «*Draft in progress…*» under tittelen og `status: draft` bør oppdateres når dere reviderer.
- Ingen sensitive opplysninger funnet.

## 6. Før dere går videre

**Må avklares før UX, arkitektur og epics:**
- Trigger for generering, antall filer per økt, og om noe lagres (spørsmål 2, 3, 10).
- Skybasert eller lokal behandling, og at appen får en testmodus uten nøkkel (spørsmål 4, 7).
- Primærbruker og scenario (spørsmål 1), og målbare krav til Reference Pointer (spørsmål 8).

**Kan vente:** Tabeller og figurer (6), detaljert summary-granularitet (5), langsiktig retning (9). Skriv dem som `[NON-GOAL for MVP]`.

**Oppfølging av tilbakemeldingen på product brief:** **Nei.** PRD-en er sist endret 2026-09-15, før tilbakemeldingen (2026-10-06), og de samme punktene står fortsatt som «Undecided»: primærscenario, trigger, lagring, én eller flere filer, og testmodus. Brukerreisen er heller ikke beskrevet steg for steg.

## 7. Refleksjonsspørsmål

1. Mange «Undecided» kom trolig fordi KI-assistenten ikke skulle finne på krav for dere. Hva hindret dere i å ta valgene selv, og hvem i gruppen bør eie hvert av dem?
2. Hvordan skal dere vite at et Reference Pointer faktisk er riktig, når språkmodellen kan finne på en sidehenvisning? Hva er det enkleste dere kan sjekke manuelt mot et testdokument dere kjenner?

_Vurdert mot kvalitetsrubrikken i bmad-prd. Dette er veiledning, ikke sensur._
