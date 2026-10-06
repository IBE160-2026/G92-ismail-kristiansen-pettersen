# Tilbakemelding på product brief

| | |
|---|---|
| **Gruppe** | G92 – G92-ismail-kristiansen-pettersen |
| **Product brief** | `_bmad-output/planning-artifacts/briefs/brief-AI-Study-Buddy-2026-09-15/brief.md` (commit `fc7940d`) |
| **Tilbakemelding fra** | Faglærer i IBE160 (utarbeidet med KI-støtte) |
| **Dato** | 2026-10-06 |

Vurdert fil: `brief.md` i mappen `brief-AI-Study-Buddy-2026-09-15`, som er den eneste briefen. Repoet har også et PRD-utkast som er under arbeid, men ingen arkitektur eller epics.

## Samlet vurdering

- **Bør revideres før dere går videre.** Rett punktene markert «Endre» før dere lager PRD og arkitektur.

**Det som er bra:**

1. Dere skiller tydelig mellom det som er bekreftet og det som er uavklart. Det er ærlig, og listen «Open Decisions» viser nøyaktig hva som må besluttes.
2. Tabellen i «What Makes This Different» er god: sammenligningen med manuelle notater, ChatGPT, Anki/Quizlet og kollokvier er konkret, og poenget om kildebaserte svar med sidehenvisning er en reell styrke. Kravet om at hvert resultat skal ha en kilde- eller sidehenvisning er et godt og testbart prinsipp.

**De viktigste endringene:**

1. Ta beslutningene. Nesten alle deler av briefen ender med «Undecided», og løsningsdelen sier bare at appen «accepts the confirmed inputs and provides the confirmed output types». Det er i praksis forslagsteksten fra oppgavelisten. Før PRD bør dere bestemme minst: primært studiescenario (for eksempel eksamensforberedelse), om generering er automatisk eller valgt av studenten, om resultater lagres, og om én eller flere filer kan kombineres. PRD-utkastet har de samme hullene, så det lønner seg å rette briefen først.
2. Beskriv brukeropplevelsen. Hva gjør studenten steg for steg, og hva ser hen? For eksempel: last opp forelesningsfoiler i PDF → velg detaljnivå → få sammendrag, flashcards og quiz → øv på flashcards og ta quizen. Uten dette kan det ikke lages godt design eller gode stories.
3. Gjør briefen til deres egen. Velg en konkret primærbruker (for eksempel førsteårsstudenter ved Høgskolen i Molde i et bestemt emne) og et konkret eksempel på materiale dere vil teste med. Det gir også grunnlag for å vurdere om resultatene er riktige.

## Vanskelighetsgrad og gjennomførbarhet

### Vurdert vanskelighetsgrad

- **Enkel**

**Sammenlignbart med:** 1) AI Study Buddy (enkel). Briefen er dette forslaget. Kravet om side- og kildehenvisning for hvert resultat gjør det noe mer krevende enn 8) Foredragsnotater → Sammendrag & Quizgenerator, men ikke nok til å bli middels.

**Begrunnelse:**

| Faktor | Nivå (lav / middels / høy) | Kommentar |
|---|---|---|
| Domenelogikk – hvor mange og hvor kompliserte regler og beregninger må stemme? | Lav | Få egne regler. Logikken ligger i hvordan materialet deles opp og sendes til KI. |
| Datamodell – antall entiteter og relasjoner mellom dem | Lav til middels | Dokument, side/avsnitt, sammendrag, flashcard, quizspørsmål og begrep. Øker hvis resultater lagres per emne. |
| Brukere, roller og innlogging | Lav | Én studentrolle. Innlogging bare hvis materiale lagres, og det er ikke bestemt. |
| KI-funksjonalitet i appen, f.eks. kall til språkmodell, prompts i koden og håndtering av usikre svar | Middels | Fem typer resultater med kildehenvisning. Krever strukturert svar og kontroll mot oppdiktet innhold. |
| Integrasjoner og eksterne tjenester, f.eks. API-er, betaling og e-post | Lav til middels | Språkmodell-API. Valg mellom lokal og skybasert behandling er ikke tatt. |
| Sanntid, samtidighet eller flere brukere som påvirker hverandre | Lav | Ingen. |
| Filhåndtering, f.eks. opplasting, PDF-lesing og eksport | Middels | PDF-lesing med sidetall for henvisninger. Tabeller og figurer er nevnt som beslutningspunkt. Hold dem utenfor v1. |
| Sikkerhet og personvern | Lav til middels | Kursmateriale kan være opphavsrettsbeskyttet og sendes til en ekstern tjeneste. Bruk eget eller fritt tilgjengelig materiale i testing. |

**Hva vanskelighetsgraden betyr for dere:**

- _Enkel:_ Et enkelt prosjekt gir stor sjanse for å bli ferdig. Vanskelighetsgraden inngår likevel i vurderingen, så for å nå helt opp må dere vise mer i gjennomføringen. Det betyr særlig et gjennomarbeidet design, grundig testing, en tydelig dokumentert prosess og en README som virker.

### Gjennomførbarhet med BMAD og Claude Code

| Spørsmål | Vurdering (OK / risiko / stor risiko) | Kommentar |
|---|---|---|
| **Tid og omfang** – kan v1 realistisk bli ferdig og stabil i løpet av semesteret, med tid til flere iterasjoner? | OK | Ja, kjerneflyten er overkommelig. Risikoen er tid brukt på planlegging som ikke konkluderer. |
| **BMAD-flyten** – er briefen konkret nok til at PRD, arkitektur og stories kan lages uten store hull, og blir det overkommelig mange stories? | Stor risiko | Nei, ikke ennå. Mange «Undecided» gjør at PRD-en også blir full av hull, slik PRD-utkastet allerede viser. |
| **Egnet for Claude Code** – bruker løsningen en vanlig, godt dokumentert teknologistakk som Claude Code håndterer godt, eller krever den nisjeteknologi, spesialmaskinvare eller mye manuell konfigurasjon? | OK | Webapp med PDF-opplasting og API-kall er godt egnet. Lokal kjøring av språkmodell vil derimot gi mye oppsett. Velg skybasert med testmodus. |
| **Kontroll på KI-ens arbeid** – kan gruppen selv avgjøre om koden gjør det riktige? Krever domenet kunnskap gruppen ikke har, f.eks. avanserte beregninger eller fagregler, så er det vanskelig å kvalitetssikre. | Risiko | Kildehenvisningene gjør det mulig å kontrollere svarene. Velg testmateriale fra et emne dere kjenner godt. |
| **Testbarhet** – finnes det tydelige regler og forventede resultater som tester kan skrives mot? | Risiko | «Hvert resultat har en sidehenvisning» kan testes. Resten mangler konkrete mål. Lag faste testdokumenter med forventede begreper og sider. |
| **Kjørbar for sensor** – kan appen kjøres lokalt etter README, uten gruppens nøkler, betalte kontoer eller egen infrastruktur? | Risiko | Ikke beskrevet. Planlegg testmodus med ferdige eksempelsvar. |
| **Avhengigheter og kostnader** – krever løsningen betalte API-er, f.eks. språkmodeller, og finnes det en plan for kostnad, testmodus eller mock-data? | Risiko | Valg av språkmodell er uavklart, og det finnes ingen plan for kostnad eller testmodus. |

**Konklusjon om gjennomførbarhet:**

- **Gjennomførbart med justert omfang.** Se forslagene under.

**Forslag til justering av omfang eller vanskelighetsgrad:**

1. Ta disse valgene for v1: én PDF eller tekstfil per økt, automatisk generering av alle fem resultattyper, bare tekst (ikke tabeller og figurer), skybasert språkmodell med testmodus, og ingen innlogging til å begynne med.
2. Legg til én interaktiv funksjon som gir noe å vise frem og teste, for eksempel at studenten kan bla i flashcards og ta quizen med poengsum, og at hvert spørsmål lenker til siden det kommer fra. Lagring per emne kan komme i neste trinn.

## Hvorfor product brief er viktig for mappen

Product brief er utgangspunktet for PRD, arkitektur, stories og til slutt koden. Del 1 av mappen vurderes blant annet på om sensor kan følge en sporbar vei fra plan til ferdig app. Den vurderes også på om appen gjør det dere har beskrevet, om den er testet, om den er godt designet, og om den kan kjøres etter README. Et uklart, for stort eller for lite brief gjør alt dette vanskeligere senere. Det er mye enklere å rette nå enn sent i semesteret.

## 1. Gjennomgang av briefens deler

| Del av brief | Status | Kommentar |
|---|---|---|
| Executive Summary – er det klart hva appen er, og hvilket problem den løser? | Juster | Sier hva appen er, men handler mest om at det er et kursprosjekt. Beskriv hva studenten får gjort. |
| The Problem – er problemet konkret, med reelle situasjoner og brukere? | Juster | Generelt formulert, og primærscenarioet er uavklart. Velg et konkret scenario, for eksempel repetisjon før eksamen. |
| The Solution – beskriver løsningen brukeropplevelsen, ikke bare teknologi? | Endre | Løsningen gjentar bare input og output fra oppgaven, og fem sentrale valg er uavklart. Beskriv flyten steg for steg. |
| What Makes This Different – er vurderingen ærlig og realistisk? | OK | God og ærlig sammenligning. Bekreft den som gruppens egen vurdering. |
| Who This Serves – er primærbrukerne tydelige, og vet vi hva de trenger? | Juster | «Higher-education students» er bredt. Velg et konkret segment og beskriv hva en vellykket bruk er. |
| Success Criteria – kan kriteriene faktisk sjekkes eller testes? | Juster | Kildehenvisning per resultat er testbart. Resten er forslag som må bekreftes og gjøres konkrete, for eksempel med faste testdokumenter. |
| Scope – er det klart hva som er med i første versjon, og hva som ikke er det? | Endre | Bare kjøp/salg og lærer-/adminroller er utelatt. Alt annet er «undecided, not excluded». Del tydelig i «med i v1» og «ikke i v1». |
| Vision – henger visjonen sammen med resten uten å blåse opp omfanget? | OK | God trinnvis visjon (nå, neste, 2–3 år) som holder seg til kjerneproblemet. |

## 2. Utgangspunkt for del 1 av mappen

Punktene følger kriteriene i sensorveiledningen for del 1. Vektene i parentes viser hvor mye hvert kriterium teller i del 1.

| Kriterium i del 1 | Hva briefen bør legge til rette for | Status | Kommentar |
|---|---|---|---|
| **1. Prosess og KI-styring** (30 %) | Brief som er presis nok til at PRD og stories kan bygges direkte på den, slik at krav kan spores fra brief til kode. | Endre | Commit-historikken viser at dere jobber iterativt med briefen, og det er bra. Men uavklarte valg gjør at krav ikke kan spores videre. Ta beslutningene, og dokumenter hvorfor. |
| **2. Funksjonalitet og omfang** (20 %) | Realistisk omfang for gruppen og semesteret: en tydelig kjerneflyt som kan bli ferdig og stabil, og nok innhold til å vise reell funksjonalitet. | Juster | Fem resultattyper gir nok innhold, men kjerneflyten er ikke beskrevet. Legg til en interaktiv del. |
| **3. Kvalitetssikring og testing** (15 %) | Suksesskriterier og funksjoner som er konkrete nok til å bli testtilfeller. | Juster | Kildehenvisning er et godt testkrav. Lag testdokumenter med forventede resultater og mock-svar for automatiske tester. |
| **4. Design og brukeropplevelse** (10 %) | Tydelige brukere og brukssituasjoner som designet kan bygges rundt, gjerne med de viktigste skjermbildene eller flytene skissert. | Endre | Uten beskrevet flyt og konkret bruker er det vanskelig å designe. Skisser opplasting, resultatvisning og flashcard/quiz. |
| **5. Kodekvalitet og arkitektur** (10 %) | Teknologivalg som er begrunnet og ikke mer komplekse enn appen trenger. | Juster | Valg av språkmodell og lokal eller skybasert behandling er åpne. Velg det enkleste: skybasert API kalt fra serveren. |
| **6. README og kjørbarhet** (10 %) | Løsning som andre kan kjøre lokalt uten betalte kontoer, og uten tilgang til gruppens egne tjenester og nøkler. | Juster | Planlegg testmodus slik at sensor kan prøve appen uten deres nøkkel. |
| **7. Ryddighet i repoet** (5 %) | En plan for hvor hemmeligheter, testdata og dokumentasjon skal ligge. | Juster | BMAD-strukturen er ryddig. Bestem hvor testdokumenter ligger, og hold API-nøkkelen i `.env` utenfor Git. |

## 3. Neste steg for gruppen

1. Gå gjennom «Open Decisions» sammen og ta et valg for hvert punkt. Skriv valget og en kort begrunnelse inn i briefen.
2. Beskriv kjerneflyten steg for steg, med en konkret primærbruker og et konkret testdokument.
3. Del Scope i «med i v1» og «ikke i v1», bestem språkmodell og testmodus, og oppdater deretter PRD-utkastet.

Oppdater product brief i repoet når dere har gjort endringene, slik at historikken viser hvordan planen utviklet seg. Det er en del av prosessen sensor ser etter.
