# Tarmkreftscreening
Opprettelse av FHIR profiler for oversendelse av data til det nye registeret for tarmkreftscreening.
Vi vil bruke en **Bundle** av type **Composition** (Bundle of type Composition)

### Kort oppsummert prosjektet og use-case
Det skal opprettes et nytt register for tarmkreftscreening, oppstart høsten 2021. Data registreres i fagsystemer og oversendes registeret med FHIR. 
Fagsystemene vil pr. oppstart ikke være FHIR baserte. 

Dataflyten beskrevet forenklet: 

[Bilde]

### Inkluderte resursser i Bundle-en
Alt er under utarbeidelse, og kan derfor virke uferdig. Terminologi og kodeverk er ikke fastsatt enda.

- **Patient**:<br> 
  Ikke laget, men vil basere seg på den norske basisprofilen [no-basis patient](https://simplifier.net/HL7Norwayno-basis/NoBasisPatient/~overview)<br>
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
