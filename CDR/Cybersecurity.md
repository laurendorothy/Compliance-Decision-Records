## Samenvatting

| Veld | Waarde |
|---|---|
| **Versie** | 0.1 |
| **Status** | PROPOSED / ~~ACCEPTED / REJECTED~~ |
| **Laatste aanpasdatum** | 24-08-2026 |
| **Aanpasser** | Lauren Challis |

## Beslissing

| Veld | Waarde |
|---|---|
| **Oordeel** | ~~COMPLIANT~~ / GEDEELTELIJK / ~~NON-COMPLIANT~~ |
| **Rationale** | Infrastructuurgerichte maatregelen zijn op orde. Een deel van de AI-specifieke dreigingen die Art. 15 AIV benoemt (ontwijkingsaanvallen, inversion-aanvallen/modeldiefstal, membership inference) is niet van toepassing, omdat het systeem geen LLM betreft. Op twee AI-specifieke punten resteert een concreet actiepunt:<br> - Data poisoning:  bescherming van trainingsdata en model hiertegen is niet ingevuld; uitgezet als openstaande vraag bij DBS.<br> - Jailbreaking: detectie is aanwezig op eigen hardware, maar onduidelijk of OpenHansken/copiloot hier ook onder valt; dit moet nog worden nagegaan. |
| **Openstaande acties** | Vraag 1. De CIS-controls-mapping is nog niet formeel getoetst; de risicobeoordeling moet verder worden uitgewerkt.<br>Vraag 5. Openstaande vraag voor DBS over bescherming van trainingsdata/model tegen data poisoning en manipulatie.<br>Vraag 9. Nagaan of en hoe OpenHansken/copiloot ondersteuning biedt bij het voorkomen van jailbreaking.<br>Vraag 14. Beleid voor veilige communicatie (encryptie, authenticatie, integriteitscontrole) moet nog worden opgesteld, ook al zijn de technische maatregelen zelf al geïmplementeerd. |
| **Beoordelaar** | Lauren Challis |
| **Datum beoordeling** | 24-08-2026 |


---

## Maatregelen

### Nauwkeurigheid

**1. Hoe zijn de cybersecurityrisico's van dit AI-systeem integraal beoordeeld, inclusief risico's die specifiek zijn voor AI zoals modelmanipulatie en data poisoning, en welke normen of frameworks zijn hierbij gehanteerd?**

_Bijv.: een penetratietest is uitgevoerd door een externe partij conform het PTES-framework; bevindingen zijn gecategoriseerd naar ernst (kritiek, hoog, middel, laag); alle kritieke bevindingen zijn binnen 30 dagen verholpen en gedocumenteerd in het securitydossier._

`▸ AIV Art. 15.1 · AIV Art. 15.3`

**Antwoord:**
"De cybersecurityrisico's van dit AI-systeem zijn beoordeeld door deze te mappen op de CIS-controls; deze mapping is echter nog niet (formeel) getoetst. Daarnaast worden pentesten en quickscans uitgevoerd, en op basis van de uitkomsten daarvan worden de risico's verder geïnventariseerd.

>**Bewijslast:**   
_Vul hier [link](www.github.com) naar de bewijslast toe._   
<br>   

**2. Welke beveiligingsmaatregelen zijn getroffen om ongeoorloofde wijzigingen en integriteitsschendingen van het systeem en zijn configuratie te detecteren en te voorkomen?**
_Bijv.: een integrity check vergelijkt modelgewichten dagelijks met de cryptografische hash van de goedgekeurde versie; elke configuratiewijziging vereist goedkeuring van twee beheerders; afwijkingen triggeren automatisch een beveiligingsalert aan de CISO._   

`▸ AIV Art. 15.1`

**Antwoord:**   
"Om ongeoorloofde wijzigingen en integriteitsschendingen te detecteren en te voorkomen wordt het systeem gescand op bekende kwetsbaarheden (CVE-scanning). Wijzigingen zijn herleidbaar doordat de ontwikkeling in Git plaatsvindt, en er wordt gebruikgemaakt van een SBOM (Software Bill of Materials) om de samenstelling van het systeem inzichtelijk te maken. Het systeem draait in containers, waarbij artifacts worden gesigneerd om de integriteit ervan te waarborgen. Daarnaast wordt gewerkt met een access list om toegang te beperken, en wordt het vierogen- respectievelijk zesogenprincipe gehanteerd om wijzigingen door meerdere personen te laten controleren."

>**Bewijslast:**   
_Vul hier [link](www.github.com) naar de bewijslast toe._   
<br>   

### Ongeoorloofd gebruik en datamanipulatie

**3. Welke mechanismen zijn ingebouwd om ongeoorloofd of afwijkend gebruik van het systeem te detecteren en te voorkomen, en hoe zijn integriteitscontroles opgezet?**
_Bijv.: het systeem controleert bij elke aanroep of de gebruiker een actieve, geautoriseerde sessie heeft; afwijkend gebruik (ongebruikelijke uren, hoog volume, onbekend IP-adres) triggert een automatische blokkade en alert aan de beveiligingsofficier._
`▸ AIV Art. 15.5`

**Antwoord:**
"Ongeoorloofd of afwijkend gebruik wordt gedetecteerd via audit logging, waarbij op dit moment nog geen alertering is ingericht. Binnen Hansken is geen 2FA (tweefactorauthenticatie) beschikbaar; wel staat Hansken SSO (single sign-on) toe."

>**Bewijslast:**
_Vul hier [link](https://www.github.com) naar de bewijslast toe._
<br>


**4. Zijn de bronnen van dataverzameling in kaart gebracht, en welke beveiligingscontroles waarborgen de betrouwbaarheid van data uit externe bronnen?**
_Bijv.: een dataleveranciersregister beschrijft voor elke databron de herkomst, het verificatieproces en de beveiligingsafspraken; data uit externe bronnen wordt altijd geverifieerd via een checksumcontrole vóór opname in de trainingsset._
`▸ AIV Art. 15.5`

**Antwoord:**
"De bronnen van dataverzameling zijn in kaart gebracht via de SBOM, die daarmee tevens dient als dataleveranciersregister. De betrouwbaarheid van binnenkomende data bij Hansken wordt gewaarborgd door middel van checksumcontroles."

>**Bewijslast:**
_Vul hier [link](https://www.github.com) naar de bewijslast toe._
<br>


**5. Hoe zijn de trainingsdata en het model beschermd tegen data poisoning en manipulatie, inclusief toegangscontroles, versleuteling, anomaliedetectie en logging?**
_Bijv.: toegang tot de trainingsdata vereist twee-factor-authenticatie en is beperkt tot drie data-engineers; data is versleuteld opgeslagen (AES-256); een anomaliedetectiesysteem signaleert ongebruikelijke wijzigingspatronen; alle wijzigingen worden gelogd in een audittrail._
`▸ AIV Art. 15.5`

**Antwoord:**
"Het model wordt niet meer geüpdatet. De ontwikkelaars van het model zijn niet dezelfde partij als degenen die het model in Hansken integreren."

***Actiepunt: Dit is een openstaande vraag voor DBS.***

>**Bewijslast:**
_Vul hier [link](https://www.github.com) naar de bewijslast toe._
<br>

### Aanvalsbescherming

**6. Hoe is het systeem getest en gehardend tegen vijandige aanvallen, en welke detectie- en mitigatiemechanismen zijn ingebouwd om manipulatie van invoer te signaleren?**   
_Bijv.: maandelijks voert het security-team een adversarial attack simulatie uit; invoer met statistische kenmerken die sterk afwijken van de trainingsdistributie wordt automatisch gemarkeerd als 'verdacht' en doorgestuurd naar een analist voor beoordeling._   
`▸ AIV Art. 15.5` 

**Antwoord:**   
"Op binnenkomende data wordt een cleaner uitgevoerd. Daarnaast wordt het systeem getest en gehard door middel van pentesten, een OWASP dependency scan, CVE-scanning en SAST-tooling (Static Application Security Testing). Dit gebeurt in principe bij grote wijzigingen of jaarlijks."   

>**Bewijslast:**   
_Vul hier [link](https://www.github.com) naar de bewijslast toe._   
<br>

**7. Welke mechanismen zijn geïmplementeerd om ontwijkingsaanvallen te detecteren, pogingen om via aangepaste invoer de AI-beslissing te omzeilen, en hoe effectief zijn deze gebleken?**   
_Bijv.: elk kwartaal voert een intern red team een gecontroleerde aanvalssimulatie uit; bevindingen worden gecategoriseerd en verwerkt in de volgende patchcyclus; resultaten worden besproken in het maandelijkse securityoverleg._   
`▸ AIV Art. 15.5`   

**Antwoord:**   
"Hiervoor zijn geen mechanismen aanwezig, of dit is regelmatig niet van toepassing."   

>**Bewijslast:**   
_Vul hier [link](https://www.github.com) naar de bewijslast toe._   
<br>

**8. Worden er regelmatig vijandige aanvalsoefeningen of red-teaming sessies uitgevoerd om de weerbaarheid van het systeem te testen, en hoe zijn bevindingen verwerkt?**   
_Bijv.: het systeem vergelijkt elk inkomend datapunt met een statistische baseline; afwijkingen boven een drempelwaarde worden geblokkeerd en gelogd; in de afgelopen zes maanden zijn vier echte ontwijkingspogingen gedetecteerd en tegengehouden._   
`▸ AIV Art. 15.5`   

**Antwoord:**   
"Er worden pentesten uitgevoerd door een externe partij; de bevindingen hiervan gaan naar de proceseigenaar/systeemeigenaar. Er is beleid over binnen welke termijn een geconstateerde kwetsbaarheid opgelost moet zijn."   

>**Bewijslast:**   
_Vul hier [link](https://www.github.com) naar de bewijslast toe._   
<br>

**9. Welke maatregelen zijn ontwikkeld om jailbreaking te voorkomen, pogingen om beperkingen of veiligheidsmechanismen van het systeem te omzeilen, en hoe is de effectiviteit hiervan getest?**   
_Bijv.: het systeem heeft een inputvalidatielaag die bekende jailbreak-patronen filtert; verificatiemechanismen controleren bij elke aanroep of de output binnen de gedefinieerde veiligheidsgrenzen valt; effectiviteit is getest via red-teaming oefeningen._   
`▸ AIV Art. 15.5`   

**Antwoord:**   
"Op eigen hardware worden softwareproducten ingezet voor de detectie van jailbreaking."   

***Actiepunt: Nagaan of en hoe OpenHansken/copiloot hier inherent iets in ondersteunt.***   

>**Bewijslast:**   
_Vul hier [link](https://www.github.com) naar de bewijslast toe._   
<br>


### Privacy-aanvallen en side-channel risico's

**10. Is beoordeeld of het systeem zelf specifieke cybersecurityrisico's introduceert, en hoe zijn inversion aanvallen en modeldiefstal voorkomen via maskering, versleuteling of componentscheiding?**   
_Bijv.: modelgewichten zijn versleuteld en alleen benaderbaar via een beveiligde API; directe toegang tot het model is onmogelijk; componentscheiding voorkomt dat een aanvaller via één gecompromitteerd onderdeel het volledige model kan reconstrueren._   
`▸ AIV Art. 15.5`   
**Antwoord:**   
"Dit is niet beoordeeld, omdat dit grotendeels niet van toepassing is: gebruikers beschikken al over autorisatie."   
>**Bewijslast:**   
_Vul hier [link](https://www.github.com) naar de bewijslast toe._   
<br>

**11. Zijn de functies, tools en externe bibliotheken die het systeem gebruikt geanalyseerd op side-channel kwetsbaarheden, en hoe zijn deze beheersmatig of technisch gemitigeerd?**   
 _Bijv.: een membership inference attack test toonde aan dat het model met 53% kans (near-random, dus acceptabel) kon voorspellen of een datapunt in de trainingsset zat; ter aanvullende bescherming is differential privacy toegepast met ε = 1,0 bij de modeltraining._   
 
`▸ AIV Art. 15.5`   
**Antwoord:**   
"Er wordt een dependency scan geïmplementeerd. Daarnaast voorkomt een firewall dat data wordt geëxfiltreerd."   
>**Bewijslast:**   
_Vul hier [link](https://www.github.com) naar de bewijslast toe._   
<br>

**12. In hoeverre is het systeem kwetsbaar voor membership inference-aanvallen, waarbij een aanvaller probeert te achterhalen of een specifiek datapunt in de trainingsset zat en welke privacybeschermingstechnieken zijn toegepast?**   
_Bijv.: een inventaris van alle externe bibliotheken toont welke onbeheerde of verouderde componenten risico's introduceren; kwetsbare bibliotheken zijn vervangen of geïsoleerd; timing-side-channels zijn gemitigeerd door constante-tijd implementaties te gebruiken._  

`▸ AIV Art. 15.5 · AIV Art. 10.5`   
**Antwoord:**   
"Dit is grotendeels niet van toepassing, omdat gebruikers al over autorisatie beschikken."   
>**Bewijslast:**   
_Vul hier [link](https://www.github.com) naar de bewijslast toe._   
<br>

### Social engineering en incidentrespons

**13. Is beoordeeld of het systeem kwetsbaar is voor social engineering, pogingen om via misleiding van menselijke operators ongeautoriseerde acties te bewerkstelligen, en welke maatregelen zijn getroffen?**   
_Bijv.: operators zijn getraind om verdachte verzoeken via het systeem te herkennen; het systeem vraagt altijd een tweede autorisatie bij acties buiten de normale workflow; een communicatieprotocol beschrijft welke verzoeken nooit via automatische berichten worden gedaan._   
`▸ AIV Art. 15.5`   
**Antwoord:**   
"Hiertegen zijn de volgende maatregelen getroffen: een VGB-B screening, de mogelijkheid om alleen lokaal in te loggen, e-learning, MFA (multifactorauthenticatie) en een time-out."   
>**Bewijslast:**   
_Vul hier [link](https://www.github.com) naar de bewijslast toe._   
<br>

**14. Hoe is veilige en betrouwbare communicatie gewaarborgd tussen het systeem en zijn gebruikers, beheerders en externe systemen, incl. encryptie, authenticatie en integriteitscontrole van berichten?**   
_Bijv.: alle communicatie verloopt via TLS 1.3; API-aanroepen worden geauthenticeerd via OAuth 2.0 met korte tokenlevensduur (15 minuten); de integriteit van berichten wordt gewaarborgd via HMAC-signing._   
`▸ AIV Art. 15.5`   
**Antwoord:**   
"Hier wordt nog beleid voor opgesteld. Encryptie, authenticatie en integriteitscontrole van berichten zijn al geïmplementeerd, en interne communicatie maakt gebruik van signing en hashing."   
>**Bewijslast:**   
_Vul hier [link](https://www.github.com) naar de bewijslast toe._   
<br>

**15. Hoe zijn toegangscontroles, authenticatie en sessiebeheer ingericht om modeldiefstal en reverse engineering te voorkomen, en welke responsprotocollen zijn er voor specifieke cybersecurity-incidenten?**   
_Bijv.: alleen gecertificeerde onderzoekers met NFI-badge en MFA kunnen inloggen; sessies verlopen na 30 minuten inactiviteit; procedure 'SEC-03' beschrijft drie escalatieniveaus: bij kritieke incidenten wordt het systeem direct offline gehaald en start de Art. 73-meldingsprocedure._   
`▸ AIV Art. 15.5 · AIV Art. 73.1`   
**Antwoord:**   
"Het eerste deel (toegangscontroles, authenticatie en sessiebeheer ter voorkoming van modeldiefstal en reverse engineering) is weinig van toepassing. Voor het tweede deel geldt dat er incident response-beleid aanwezig is."   
>**Bewijslast:**   
_Vul hier [link](https://www.github.com) naar de bewijslast toe._   
<br>

