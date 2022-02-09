## xAPI Minimumskrav

Listen under spesifiserer minimumskrav for xAPI statements i AVT prosjektet.

* Man må ha med Required-elementene fra selve xAPI-spesifikasjonen ([se her for mer info](https://github.com/adlnet/xAPI-Spec/blob/master/xAPI-Data.md#24-statement-properties)).

* xAPI datastruktur:
  * Id: Hver xAPI statement skal ha en unik [statement ID](https://github.com/adlnet/xAPI-Spec/blob/master/xAPI-Data.md#241-id). Basert på xAPI spesifikasjonen skal statement id være en UUID i henhold til variant 2 av RFC 4122.
  * Actor: Må være en “Nye feide”- (aka Dataporten-) bruker. Tjenesten må altså være en dataporten tjeneste.
  * Verb:
    * Required: [Answered](http://adlnet.gov/expapi/verbs/answered). Dette blir vanligvis brukt om enkeltitems (enkeltoppgaver).
    For et læremiddel med sider (pages) kan man bruke verbet Completed, men i dette tilfellet vil vi være pragmatisk og bruke Answered også her.
  * Object:
    * Required: [Id](https://github.com/adlnet/xAPI-Spec/blob/master/xAPI-Data.md#acturi) og [definition (name, description og type)](https://github.com/adlnet/xAPI-Spec/blob/master/xAPI-Data.md#activity-definition). Det er viktig at at name og description er henholdsvis klart og beskrivende for det aktuelle objektet (f.eks. en enkeltitem eller page).

  * Result:
    * Required: [Score (min, max, raw, scaled)](https://github.com/adlnet/xAPI-Spec/blob/master/xAPI-Data.md#2451-score) og [success](https://github.com/adlnet/xAPI-Spec/blob/master/xAPI-Data.md#details-12).
    * Required extensions: Dersom man har informasjon om elevers bruk av hint og antall forsøk (attempts) på en oppgave er denne informasjonen også påkrevd informasjon. Informasjonen legges inn ved hjelp av extensions definert av AVT prosjektet: 
      * https://w3id.org/xapi/avt/result-extensions/max-hints (maks antall hint - mulig for oppgave)
      * https://w3id.org/xapi/avt/result-extensions/hints-used (faktiske hint brukt for oppgave)
      * https://w3id.org/xapi/avt/result-extensions/attempts (antall oppgaveforsøk)
      * Se eksempler for mer informasjon om bruk av disse extensions.
  * Context:
    * Required: Skoleeier, skole og tjenesteleverandør (feide-clientinfo) i context.
    * Required: Hver xAPI statement må ha med informasjon om fagkart i context (tagget ved hjelp av verktøyet [Fagkart](https://fagkart.no/#/)).
    * Required: Hvert object som er en del av context gjennom contextActivities må ha med definition->name, og gjerne også definition->description.

[AVT eksemplene](./eksempler.md) viser hvordan minimumkravene kan overholdes i praksis.

For å sjekke at xAPI statements er strukturert i henhold til standarden kan man bruke en xAPI validator, for eksempel [denne](https://lrs.io/ui/tools/xapi-statement-validator/). _NB! Slike validatorer tester i henhold til den generelle xAPI standarden, men tar ikke hensyn til ytterligere minimumskrav som er definert av AVT prosjektet._