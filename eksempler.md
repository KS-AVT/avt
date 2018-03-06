# Eksempler på kall mot og respons fra leverandørenes aktivitetsdata-API
Deltakende leverandører i AVT-prosjektet forholder seg til dette dokumentet i stedet for det som ble sendt til dem i forbindelse med invitasjon til deltakelse ("Eksempler på læringsaktiviteter som «Experience API»-utsagn", dokument nr. N032,  publisert av Standard Norge SN/K 186 Læringsteknologi-komiteen i september 2017)

Det er valgt ut to eksempler, et fra en tenkt besvarelse av en matematikk-oppgave i "Overgangsprøven i matematikk for 4. trinn" som benyttes i grunnskolen i Oslo, samt et eksempel fra en tenkt oppgaveløsning i fysikk på viten.no.

NB: Eksemplene er laget ut i fra hva som kanskje kunne vært mulig dersom verktøyene støttet å generere læringsaktiviteter i xAPI format, men ingen av de to systemene gjør dette per i dag.

Eksemplene på xAPI-utsagn inkluderer å vise muligheter for følgende informasjon:
- hvordan verb og aktivitetstyper fremkommer i noen xAPI-utsagn
- hvordan en aktør (en elev) kan identifiseres via en ID (brukernavn) fra Feide/Dataporten
- hvordan en skole og skoleeier kan identifiseres via organisasjonsnummeret mot nasjonalt skoleregister
- hvordan man kan inkludere knytninger mellom læringsaktiviteten og kompetansemål fra GREP inn i xAPI-utsagnene
- hvordan man kan inkludere knytninger mellom læringsaktiviteten og AVT-prosjektets ferdighetsstruktur
- hvordan man kan inkludere både «spørsmål» og «svar» på en oppgave, samt varighet (duration) og skåre (result.score)

## Eksempel 1 - Overgangsprøven i matematikk for 4. trinn

Merk: For å forenkle eksempelomfanget så er det kun én oppgave (nr 23) som er modellert, men Overgangsprøven i regning inneholder selvsagt mange flere oppgaver. Informasjonen i eksempelet er til illustrasjon, og har blitt utarbeidet uten involvering fra Inspera (derfor er det sikkert enkelte unøyaktigheter, eksempelvis ID og navn på Feide-tjenesten som faktisk benyttes).

Skjermdump av oppgaven:
![](bilder/Eksempel%201%20-%20Overgangspr%C3%B8ven%20i%20regning%204.%20trinn%202017.jpg)

### Oversikt over xAPI-statements for eksempel 1 (Overgangsprøven i regning)

|REFERANSE<br/>Navn på xAPIstatement, for referanse i dette dokumentet|KOMMENTAR / SCENARIO<br/>Beskrivelse av hendelse|HVEM…<br/>Actor.Name|GJORDE…<br/>Verb (nb-NO)|HVA…<br/>Object Definition Name (nb-NO)|
| ------------- | ------------- | ------------- | ------------- | ------------- |
|OV_MAT4_1|Learner is logging in to “Overgangsprøven i regning 4. trinn2018”|Kari Nordmann|logget inn|Overgangsprøven i regning, 4. trinn 2017/2018|
|OV_MAT4_2|Answering a single question (but without success) in “Overgangsprøven i regning 4. trinn”, oppgave 23.|Kari Nordmann|besvarte|Overgangsprøven i regning, 4. trinn: Oppgave 23|
|OV_MAT4_3|Answering a single question (with success) in “Overgangsprøven i regning 4. trinn”, oppgave 23.|Kari Nordmann|besvarte|Overgangsprøven i regning, 4. trinn: Oppgave 23|
|OV_MAT4_4|The learner has completed all questions in “Overgangsprøven i regning 4. trinn”|Kari Nordmann|ferdigstilte|Overgangsprøven i regning, 4. trinn 2017/2018|

### Eksempel på kall
<Torleif fyller inn>

### Eksempel på respons
Merk: Responsen skal inkludere alle utsagnene i tabellen over, men for enkelhets skyld er det gjort et utvalg her.
<Torleif fyller inn>

## Eksempel 2 - Fysikkoppgave på Viten.no

Merk: Informasjonen i eksempelet er til illustrasjon, og har blitt utarbeidet uten involvering fra viten.no (derfor er det sikkert enkelte unøyaktigheter, eksempelvis (URI) på object).


Skjermdump av oppgaven:
![](bilder/Eksempel%202%20-%20Viten%20-%20Fysikk%201%20-%20Bevegelse%20-%20Fritt%20fall-regn%20ut%20-%20A.jpg)

### Oversikt over xAPI-statements for eksempel 2 (fysikkoppgave fra Viten.no)

|REFERANSE<br/>Navn på xAPIstatement, for referanse i dette dokumentet|KOMMENTAR / SCENARIO<br/>Beskrivelse av hendelse|HVEM…<br/>Actor.Name|GJORDE…<br/>Verb (nb-NO)|HVA…<br/>Object Definition Name (nb-NO)|
| ------------- | ------------- | ------------- | ------------- | ------------- |
|VITEN_1|An LMS is conforming to the cmi5 xAPI spec and a learner has launched an assignable unit at viten.no|Kari Nordmann|påbegynte|Viten.no > Oppgaver for Fysikk 1 > Bevegelse > Fritt fall - regn ut > A|
|VITEN_2|Viten.no has received the request and has initialized in the learner’s web browser (there always must be an initialization statement and a termination statement when using cmi5)|Kari Nordmann|startet (engelsk: initialized)|Viten.no > Oppgaver for Fysikk 1 > Bevegelse > Fritt fall - regn ut > A|
|VITEN_3|The learner noticed the instructional simulation and clicked play|Kari Nordmann|startet (engelsk: started, verb er ikke fra ADL)|Fallende rød ball (oppgave A)|
|VITEN_4|The learner clicked to pause the instructional simulation|Kari Nordmann|pauset|Fallende rød ball (oppgave A)|
|VITEN_5|The learner clicked play again to see the full simulation|Kari Nordmann|spolte tilbake|Fallende rød ball (oppgave A)|
|VITEN_6|The learner clicked play again to see the full simulation|Kari Nordmann|startet|Fallende rød ball (oppgave A)|
|VITEN_7|The learner guessed a wrong answer, perhaps due to a misconception|Kari Nordmann|besvarte|Viten.no > Oppgaver for Fysikk 1 > Bevegelse > Fritt fall - regn ut > A|
|VITEN_11|The learner answered correctly|Kari Nordmann|besvarte|Viten.no > Oppgaver for Fysikk 1 > Bevegelse > Fritt fall - regn ut > A|
|VITEN_14|The learner has passed this assignable unit|Kari Nordmann|besto|Viten.no > Oppgaver for Fysikk 1 > Bevegelse > Fritt fall - regn ut > A|
|VITEN_15|The learner has completed this assignable unit (actually both passed and completed is not required in the cmi5 specification)|Kari Nordmann|fullførte|Viten.no > Oppgaver for Fysikk 1 > Bevegelse > Fritt fall - regn ut > A|
|VITEN_16|The learner terminated the learning tool (there always must be an initialization statement and a termination statement when using cmi5)|Kari Nordmann|avsluttet|Viten.no > Oppgaver for Fysikk 1 > Bevegelse > Fritt fall - regn ut > A|
|VITEN_17|The LMS reports that the learner now has satisfied all assignable units in the whole course related to “Oppgaver for Fysikk 1”|Kari Nordmann|tilfredsstilte|Viten.no > Oppgaver for Fysikk 1 > Bevegelse|

### Eksempel på kall
<Torleif fyller inn>

### Eksempel på respons
Merk: Responsen skal inkludere alle utsagnene i tabellen over, men for enkelhets skyld er det gjort et utvalg her.
<Torleif fyller inn>
