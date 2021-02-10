# Tarmkreftscreening
Opprettelse av FHIR profiler for oversendelse av data til det nye registeret for tarmkreftscreening.
Vi vil bruke en **Bundle** av type **Composition** (Bundle of type Composition)

### Kort oppsummert prosjektet og use-case
Et nasjonalt program for tarmscreening innføres i Norge med oppstart høsten 2021. Helseforetakene utfører koloskopier, mens Kreftregisteret har ansvar for administrasjon (innkalling mv) og monitorering (kvalitetsovervåkning) av programmet.<br>
Ved screeningsentrene vil legene dokumentere koloskopier i en strukturert journal. Et uttrekk av data sendes til Tarmscreeningprogrammet v/Kreftregisteret ( IKT-løsningen benevnt «ScreenIT»).<br>
Transporten av data skal skje ved hjelp av FHIR. Der det er hensiktsmessig kodes variabler og verdisett (valg) med begrep fra SNOMED CT, fortrinnsvis [norsk versjon](https://ehelse.no/kodeverk/snomed-ct).

Tilsvarende data skal sendes til det nasjonale kvalitetsregisteret [Gastronet](https://www.sthf.no/helsefaglig/gastronet), som vil etablere et eget mottak for formålet, også dette på FHIR-format. Definisjonen av FHIR-datasettet vil ta utgangspunkt i denne definisjonen. 

**Dataflyt**
![Datafly](https://github.com/HL7Norway/Tarmkreftscreening/blob/main/Dataflyt%20Tarmkreftregisteret%20FHIR%20SCREENIT%20feb_2021.png)
[BizTalk brukes for integrasjon]

### Inkluderte resursser i Bundle-en
Alt er under utarbeidelse, og kan derfor virke uferdig. Ikke alle profilene er påbegynt, og Terminologi og kodeverk er ikke fastsatt enda.

![Bundle](https://github.com/HL7Norway/Tarmkreftscreening/blob/main/FHIR%20bundle%20Tarmkreftscreening%2010-02-21.png)

- **Patient**:<br> 
  Ikke laget, men vil basere seg på den norske basisprofilen [no-basis patient](https://simplifier.net/HL7Norwayno-basis/NoBasisPatient/~overview)<br>
  Extentions: ..X..
  
- **Practitioner**:<br> 
  Ikke laget, men vil basere seg på den norske basisprofilen [no-basis practitioner](https://simplifier.net/hl7norwayno-basis/nobasispractitioner)<br>
  Extentions: ..X..

- **Procedure**: Profil [Colonoscopy](https://simplifier.net/norwegiancolonoscopyreport/colonoscopy)  <br>
  Extentions: ..X..  

- **DiagnosticReport**: Profil [ColonoscopyDiagnosticReport](https://simplifier.net/norwegiancolonoscopyreport/colonoscopydiagnosticreport)  <br>
  Extentions: ..X..

- **Observation**: 
  - Profil [Colonoscopy Report Lesion](https://simplifier.net/norwegiancolonoscopyreport/colonoscopyreportlesion) <br>
    Extentions: ..X..
    
  - Profil [Colonoscopy Report Mucosa](https://simplifier.net/norwegiancolonoscopyreport/colonoscopyreportmucosa) <br>
    Extentions: ..X..

- **MedicationStatement**: Profil [Colonoscopy Report MedicationStatement](https://simplifier.net/norwegiancolonoscopyreport/colonoscopymedicationstatement) <br>
Usikkert hvorvidt hvordan/om den skal brukes

- **QuestionnairResponse**: Profil ikke laget
Kommer til å innebefatte spørsmål som ikke nødvendigvis passer seg som delkomponenter eller extentions av en av de andre profilene, som f.eks: "Fotodokumentasjon på at cøkum er nådd? (Ja, Nei). For de fleste av disse,  kan man argumentere for at de kan høre hjemme som en ekstensjon i en profil, men av praktiske årsaker gjør vi det ikke. Hvor mange av spørsmålene som ender opp som QuestionnairResponse gjenstår å se. 
