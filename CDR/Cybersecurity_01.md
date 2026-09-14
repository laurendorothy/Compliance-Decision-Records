## 1. Besluiten

Per beslissing zijn de context, overwogen opties en het genomen besluit vastgelegd. Alternatieven zijn alleen opgenomen waar deze zijn gedocumenteerd; overige alternatieven zijn aangemerkt als niet gedocumenteerd.

## B1: CIS Controls als risicoanalyse-raamwerk

*M1: Passend niveau van cybersecurity en consistentie | Grondslag: Art. 15.1*

### Context and Problem Statement

Hansken verwerkt gevoelige forensische data en is geclassificeerd als hoog-risico AI-systeem. Om te bepalen welke beveiligingsmaatregelen noodzakelijk zijn, moet een systematische risicoanalyse worden uitgevoerd. Vraag: welk framework wordt gehanteerd om cybersecurityrisico's integraal te beoordelen en de consistentie van beveiligingsconfiguraties in de loop van de tijd te waarborgen?

### Considered Options

* CIS Controls als risicoanalyse-raamwerk

### Decision Outcome

Chosen option: "B1: CIS Controls als risicoanalyse-raamwerk", omdat de cybersecurityrisico's zijn beoordeeld door deze te mappen op de CIS Controls. De mapping is uitgevoerd maar nog niet formeel getoetst (zie Openstaande acties, punt 1).

### Consequences

* Good, because: *niet gedocumenteerd, nader in te vullen*
* Bad, because: *niet gedocumenteerd, nader in te vullen*

## B2: Externe pentests als primaire aanvalssimulatie

*M1: Passend niveau van cybersecurity en consistentie · M4: Bescherming adversariele aanvallen | Grondslag: Art. 15.1, 15.5*

### Context and Problem Statement

Software-applicaties kunnen kwetsbaarheden bevatten die niet via interne code-analyse worden gevonden. Vraag: door wie en hoe vaak wordt het systeem extern getest op kwetsbaarheden?

### Considered Options

* Periodieke externe pentests, uitgevoerd bij grote wijzigingen of jaarlijks. Bevindingen gaan naar de proceseigenaar/systeemeigenaar. Er is beleid over termijnen waarbinnen geconstateerde kwetsbaarheden worden verholpen.

### Decision Outcome

Chosen option: "B2: Externe pentests als primaire aanvalssimulatie", omdat er pentests worden uitgevoerd door een externe partij. Bevindingen worden gecategoriseerd en binnen vastgestelde termijnen opgevolgd.

### Consequences

* Good, because: *niet gedocumenteerd, nader in te vullen*
* Bad, because: *niet gedocumenteerd, nader in te vullen*

## B3: CVE-scanning voor kwetsbaarheden in componenten

*M1: Passend niveau van cybersecurity en consistentie · M2: Bestand tegen ongeoorloofd gebruik en integriteitsschendingen | Grondslag: Art. 15.1, 15.5*

### Context and Problem Statement

Hansken maakt gebruik van externe software-componenten en bibliotheken. Vraag: hoe wordt Hansken geïnformeerd over nieuw ontdekte kwetsbaarheden in gebruikte componenten?

### Considered Options

* Geautomatiseerde CVE-scanning op de software-componenten van Hansken.

### Decision Outcome

Chosen option: "B3: CVE-scanning voor kwetsbaarheden in componenten", omdat CVE-scanning is ingericht om bekende kwetsbaarheden in gebruikte componenten te detecteren.

### Consequences

* Good, because: *niet gedocumenteerd, nader in te vullen*
* Bad, because: *niet gedocumenteerd, nader in te vullen*

## B4: OWASP dependency scan voor applicatie-afhankelijkheden

*M1: Passend niveau van cybersecurity en consistentie · M10: Bescherming side-channel aanvallen | Grondslag: Art. 15.1, 15.5*

### Context and Problem Statement

Naast CVE-scanning worden ook kwetsbaarheden in de applicatie-afhankelijkheden systematisch in kaart gebracht. Vraag: hoe worden kwetsbaarheden in de afhankelijkheden van de applicatie bijgehouden?

### Considered Options

* OWASP dependency scan, uitgevoerd naast CVE-scanning.

### Decision Outcome

Chosen option: "B4: OWASP dependency scan voor applicatie-afhankelijkheden", omdat een OWASP dependency scan is geïmplementeerd als aanvullende maatregel op de CVE-scanning.

### Consequences

* Good, because: *niet gedocumenteerd, nader in te vullen*
* Bad, because: *niet gedocumenteerd, nader in te vullen*

## B5: SAST-tooling voor beveiligingsproblemen in broncode

*M1: Passend niveau van cybersecurity en consistentie · M4: Bescherming adversariele aanvallen | Grondslag: Art. 15.1, 15.5*

### Context and Problem Statement

Beveiligingsproblemen kunnen tijdens de ontwikkeling in de broncode worden geïntroduceerd. Vraag: hoe worden beveiligingsproblemen in de broncode vroegtijdig gedetecteerd?

### Considered Options

* SAST-tooling (Static Application Security Testing), ingezet bij grote wijzigingen of jaarlijks.

### Decision Outcome

Chosen option: "B5: SAST-tooling voor beveiligingsproblemen in broncode", omdat SAST-tooling is ingericht voor het detecteren van beveiligingsproblemen in de broncode van Hansken.

### Consequences

* Good, because: *niet gedocumenteerd, nader in te vullen*
* Bad, because: *niet gedocumenteerd, nader in te vullen*

## B6: SBOM als dataleveranciersregister en transparantie-instrument

*M2: Bestand tegen ongeoorloofd gebruik en integriteitsschendingen · M3: Voorkomen manipulatie datasets | Grondslag: Art. 15.5 (raakt ook Art. 10.5)*

### Context and Problem Statement

Om de samenstelling van het systeem en de ingezette databronnen transparant te maken, is een register nodig. Vraag: hoe worden de samenstelling van Hansken en de databronnen in kaart gebracht?

### Considered Options

* SBOM (Software Bill of Materials) als centraal register, tevens dienend als dataleveranciersregister. Checksumcontroles op binnenkomende data waarborgen de integriteit van databronnen.

### Decision Outcome

Chosen option: "B6: SBOM als dataleveranciersregister en transparantie-instrument", omdat de bronnen van dataverzameling zijn in kaart gebracht via de SBOM, die tevens dient als dataleveranciersregister. De betrouwbaarheid van binnenkomende data wordt gewaarborgd door checksumcontroles.

### Consequences

* Good, because: *niet gedocumenteerd, nader in te vullen*
* Bad, because: *niet gedocumenteerd, nader in te vullen*

## B7: Container-signing voor integriteitsborging van uitrol

*M2: Bestand tegen ongeoorloofd gebruik en integriteitsschendingen | Grondslag: Art. 15.5*

### Context and Problem Statement

Hansken wordt uitgerold via containers. Vraag: hoe wordt geborgd dat alleen geautoriseerde en ongemanipuleerde containers worden uitgerold?

### Considered Options

* Container-signing: uitgerolde artefacten worden gesigneerd om de integriteit te waarborgen.

### Decision Outcome

Chosen option: "B7: Container-signing voor integriteitsborging van uitrol", omdat het systeem draait in containers waarbij artefacten worden gesigneerd om de integriteit te waarborgen.

### Consequences

* Good, because: *niet gedocumenteerd, nader in te vullen*
* Bad, because: *niet gedocumenteerd, nader in te vullen*

## B8: Vierogen-/zesogenprincipe voor wijzigingsbeheer

*M2: Bestand tegen ongeoorloofd gebruik en integriteitsschendingen | Grondslag: Art. 15.5*

### Context and Problem Statement

Een individuele medewerker kan onbedoeld of opzettelijk kwetsbare wijzigingen doorvoeren. Vraag: hoe wordt voorkomen dat een enkele medewerker zonder controle wijzigingen aanbrengt?

### Considered Options

* Vierogen-/zesogenprincipe: wijzigingen vereisen goedkeuring van meerdere personen, geborgd via Git.

### Decision Outcome

Chosen option: "B8: Vierogen-/zesogenprincipe voor wijzigingsbeheer", omdat het vierogen- respectievelijk zesogenprincipe wordt gehanteerd om wijzigingen door meerdere personen te laten controleren. Wijzigingen zijn herleidbaar doordat de ontwikkeling in Git plaatsvindt.

### Consequences

* Good, because: *niet gedocumenteerd, nader in te vullen*
* Bad, because: *niet gedocumenteerd, nader in te vullen*

## B9: SSO zonder 2FA als authenticatiemechanisme

*M2: Bestand tegen ongeoorloofd gebruik en integriteitsschendingen | Grondslag: Art. 15.5*

### Context and Problem Statement

Hansken is toegankelijk voor medewerkers van opsporingsdiensten. Vraag: welk authenticatiemechanisme wordt ingezet voor toegang tot Hansken?

### Considered Options

* SSO (single sign-on) zonder 2FA.
* SSO met 2FA (niet geïmplementeerd: binnen Hansken is geen 2FA beschikbaar).

### Decision Outcome

Chosen option: "B9: SSO zonder 2FA als authenticatiemechanisme", omdat binnen Hansken geen 2FA beschikbaar is; wel staat Hansken SSO toe. Toegang wordt verder beperkt via een access list. Het risico van ontbrekende 2FA wordt bij de eerstvolgende herziening opnieuw beoordeeld.

### Consequences

* Good, because: *niet gedocumenteerd, nader in te vullen*
* Bad, because: *niet gedocumenteerd, nader in te vullen*

## B10: Audit logging zonder real-time alertering

*M2: Bestand tegen ongeoorloofd gebruik en integriteitsschendingen | Grondslag: Art. 15.5*

### Context and Problem Statement

Om afwijkend of ongeautoriseerd gebruik te detecteren, is monitoring van systeemgebruik nodig. Vraag: hoe wordt het gebruik van Hansken gemonitord?

### Considered Options

* Audit logging zonder real-time alertering. Afwijkend gebruik wordt achteraf gedetecteerd.

### Decision Outcome

Chosen option: "B10: Audit logging zonder real-time alertering", omdat ongeoorloofd of afwijkend gebruik wordt gedetecteerd via audit logging, waarbij op dit moment nog geen alertering is ingericht.

### Consequences

* Good, because: *niet gedocumenteerd, nader in te vullen*
* Bad, because: *niet gedocumenteerd, nader in te vullen*

## B11: Aanpak bescherming trainingsdata en model tegen data poisoning

*M3: Voorkomen manipulatie datasets · M5: Bescherming systeemdefecten AI-systeem zelf | Grondslag: Art. 15.5*

### Context and Problem Statement

De AI-modellen in Hansken zijn getraind op forensische data. Als trainingsdata of het model worden gemanipuleerd, kunnen uitkomsten onbetrouwbaar worden. Vraag: hoe wordt het model beschermd tegen manipulatie van trainingsdata en het model zelf?

### Considered Options

* Het model wordt niet meer geüpdatet. De ontwikkelaars van het model (DBS) zijn niet dezelfde partij als degenen die het model in Hansken integreren (NFI).

### Decision Outcome

Chosen option: "B11: Aanpak bescherming trainingsdata en model tegen data poisoning", omdat het model niet meer wordt geüpdatet. De scheiding tussen de modellerende partij (DBS) en de integrerende partij (NFI) biedt een organisatorische beveiligingslaag. De exacte beschermingsmaatregelen bij DBS zijn nog niet bevestigd (zie Openstaande acties, punt 2).

### Consequences

* Good, because: *niet gedocumenteerd, nader in te vullen*
* Bad, because: *niet gedocumenteerd, nader in te vullen*

## B12: Jailbreak-detectie op eigen hardware

*M8: Bescherming jailbreak-aanvallen | Grondslag: Art. 15.5*

### Context and Problem Statement

Hansken bevat een copiloot-component. Jailbreaking kan ertoe leiden dat het systeem buiten zijn bedoelde grenzen wordt gebruikt. Vraag: welke maatregelen worden getroffen om jailbreaking te voorkomen en te detecteren?

### Considered Options

* Op eigen hardware worden softwareproducten ingezet voor de detectie van jailbreaking.

### Decision Outcome

Chosen option: "B12: Jailbreak-detectie op eigen hardware", omdat op eigen hardware softwareproducten zijn ingezet voor jailbreak-detectie. Of OpenHansken en de copiloot hier inherent in voorzien is nog niet nagegaan (zie Openstaande acties, punt 3).

### Consequences

* Good, because: *niet gedocumenteerd, nader in te vullen*
* Bad, because: *niet gedocumenteerd, nader in te vullen*

## B13: Social engineering maatregelen voor operators

*M11: Bescherming social engineering | Grondslag: Art. 15.5*

### Context and Problem Statement

Operators van Hansken kunnen worden misleid via social engineering. Vraag: welke maatregelen beschermen operators tegen social engineering?

### Considered Options

* Combinatie van: VGB-B screening, lokaal inloggen, e-learning, MFA en een time-out.

### Decision Outcome

Chosen option: "B13: Social engineering maatregelen voor operators", omdat hiertegen de volgende maatregelen zijn getroffen: een VGB-B screening, de mogelijkheid om alleen lokaal in te loggen, e-learning, MFA en een time-out. Communicatiebeleid is nog in opbouw (zie Openstaande acties, punt 4).

### Consequences

* Good, because: *niet gedocumenteerd, nader in te vullen*
* Bad, because: *niet gedocumenteerd, nader in te vullen*

## 2. Maatregelen niet van toepassing

De onderstaande maatregelen zijn na beoordeling als niet van toepassing beschouwd voor de architectuur en het gebruik van Hansken. Per maatregel is de motivering opgenomen.

## M6: Bescherming inversieaanvallen en modeldiefstal

*Motivering:* Niet van toepassing. Hansken is geen open-API systeem waarbij een aanvaller via herhaalde modeluitvraag het model kan reconstrueren. Toegang tot Hansken vereist autorisatie en is niet publiek beschikbaar.

## M7: Bescherming ontwijkingsaanvallen

*Motivering:* Niet van toepassing. Hansken is geen classificerend of generatief systeem waarbij invoermanipulatie leidt tot een andere classificatie of output ten gunste van de aanvaller.

## M9: Bescherming membership inference

*Motivering:* Niet van toepassing. Gebruikers beschikken over autorisatie en de gesloten architectuur van Hansken maakt het risico op membership inference minimaal.

## 3. Motivering ten opzichte van de wettelijke eis
| Maatregel | Omschrijving | Grondslag | Besluiten | Status | Toelichting |
|---|---|---|---|---|---|
| M1 | Passend niveau van cybersecurity en consistentie | Art. 15.1 | B1, B2, B3, B4, B5 | Gedeeltelijk | CIS Controls-mapping aanwezig maar niet formeel getoetst. Consistentieprocedures nog niet formeel vastgelegd. |
| M2 | Bestand tegen ongeoorloofd gebruik en integriteitsschendingen | Art. 15.5 | B3, B6, B7, B8, B9, B10 | Gedeeltelijk | CVE, SBOM, container-signing, vierogen-principe, SSO, access list aanwezig. Geen real-time alertering. |
| M3 | Voorkomen manipulatie datasets | Art. 15.5 | B6, B11 | Gedeeltelijk | SBOM en checksumcontroles aanwezig. Data poisoning bescherming bij DBS nog open (actie 2). |
| M4 | Bescherming adversariele aanvallen | Art. 15.5 | B2, B5 | Gedeeltelijk | Pentests en SAST aanwezig. Geen adversarial attack-oefeningen of red teaming. |
| M5 | Bescherming systeemdefecten AI-systeem zelf | Art. 15.5 | B11 | Gedeeltelijk | Gedeeltelijk beoordeeld; afhankelijk van antwoord DBS (actie 2). |
| M6 | Bescherming inversieaanvallen en modeldiefstal | Art. 15.5 | N.v.t. | N.v.t. | Niet van toepassing. Hansken is geen open-API systeem; gebruikers beschikken over autorisatie. |
| M7 | Bescherming ontwijkingsaanvallen | Art. 15.5 | N.v.t. | N.v.t. | Niet van toepassing. Geen classificerend/generatief systeem waarbij invoermanipulatie tot andere output leidt. |
| M8 | Bescherming jailbreak-aanvallen | Art. 15.5 | B12 | Gedeeltelijk | Detectie op eigen hardware aanwezig. Status OpenHansken/copiloot nog open (actie 3). |
| M9 | Bescherming membership inference | Art. 15.5 | N.v.t. | N.v.t. | Niet van toepassing. Gesloten architectuur; gebruikers beschikken over autorisatie. |
| M10 | Bescherming side-channel aanvallen | Art. 15.5 | B4 | Gedeeltelijk | OWASP dependency scan en firewall aanwezig. Volledige inventarisatie niet afgerond. |
| M11 | Bescherming social engineering | Art. 15.5 | B13 | Geadresseerd | VGB-B, e-learning, MFA, SSO, time-out, lokale toegang aanwezig. Communicatiebeleid in opbouw (actie 4). |

## 4. Openstaande acties

1. **CIS Controls-mapping formeel toetsen**, de uitgevoerde mapping van Hansken op de CIS Controls is nog niet formeel gevalideerd. Actie: laten reviewen door een onafhankelijke partij of intern toetsingskader.
2. **Beschermingsmaatregelen bij DBS navragen**, de maatregelen die DBS treft ter bescherming van de trainingsdata en het model zijn nog niet bevestigd. Actie: schriftelijke bevestiging opvragen bij DBS.
3. **Jailbreak-detectie OpenHansken en copiloot nagaan**, of OpenHansken en de copiloot-component inherent voorzien in jailbreak-detectie is nog niet onderzocht. Actie: navragen bij de technisch eigenaar van de copiloot.
4. **Communicatiebeleid social engineering afronden**, het beleid voor veilige communicatie tussen klanten en toezichthoudende medewerkers is nog in opbouw. Actie: afronden en vastleggen als onderdeel van de beveiligingsrichtlijnen.
5. **Scope OpenHansken bevestigen**, of OpenHansken en de copiloot expliciet onder de scope van deze CA vallen dient formeel te worden bevestigd door de systeemeigenaar.


