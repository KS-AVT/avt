## xAPI Minimumskrav

Listen under spesifiserer minimumskrav for xAPI statements i AVT prosjektet.

* Man må ha med Required-elementene fra selve xAPI-spesifikasjonen ([se her for mer info](https://github.com/adlnet/xAPI-Spec/blob/master/xAPI-Data.md#24-statement-properties)).

* Respons:
  * Actor: Må være en “Nye feide”- (aka Dataporten-) bruker. Tjenesten må altså være en dataporten tjeneste.
  * Verb:
    * Required: [Answered](http://adlnet.gov/expapi/verbs/answered). Dette blir vanligvis brukt om enkeltitems (enkeltoppgaver).
    For et læremiddel med sider (pages) kan man bruke [Completed](http://adlnet.gov/expapi/verbs/completed), men man kan også være pragmatisk og bruke Answered også her.
  * Object:
    * Required: Id og definisjon (med navn og type).
  * Result:
    * Required: Score (min, max, raw, scaled) og success.
    * Eksempel: I noen tilfeller vil min være 0, max være 1, raw være 0 (om item/oppgave ikke er fullført) eller 1 (om item/oppgave er riktig fullført) og også scaled være 0/1.
  * Context:
    * Required: Skoleeier, skole og tjenesteleverandør (feide-clientinfo).
    * Recommended: Hver activity bør helst ha med informasjon om fagkart (tagget ved hjelp av verktøyet [Fagkart](https://fagkart.no/#/)). Det kan dog være tilfeller der en activity mangler fagkartinformasjon fordi aktivitetens områder ikke er dekket av fagkartet ennå. Da kan man legge til annen relatert informasjon om aktiviteten. Det er en fordel å merke så detaljert som mulig.


[AVT eksemplene](https://github.com/KS-AVT/avt/blob/AVT2/eksempler.md) viser hvordan minimumkravene kan overholdes i praksis.

For å sjekke at xAPI statements er strukturert i henhold til standarden kan man bruke en validator, for eksempel [denne](https://lrs.io/ui/tools/xapi-statement-validator/).