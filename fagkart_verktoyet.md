## En kort beskrivelse av hvordan man bruker verktøyet Fagkart
---

Pålogging til Fagkart via Feide: https://fagkart.no/#/

Velg «Fagkartkoder verktøy» i nedtrekksmenyen.

I «Læreplan», velg «Matematikk 1–10».

Ti emner (fagkart elementer) vises hvor man kan velge fra nedtrekksmenyer.

I noen nedtrekksmenyer kan man velge én kode, i andre kan man velge flere. Dette fremgår tydelig av menyen.

Der skal velges koder fra et uttall emner, og en anbefalt rekkefølge er å velge følgende emner først:

	1 — Kunnskapsområde

	2 — Område i fagkart

	3 — Kompetansemål

	4 — Verb

Deretter velges emnene i vilkårlig rekkefølge, men som aller siste emne bør man velge «Kompetansemålsett». [Tabellen nederst på denne siden](#Emner-og-nødvendighet-med-tanke-på-tagging) angir hvorvidt emner er obligatoriske, ønskelige eller valgfrie.

Noen ganger vil man ikke finne et passende valg for «Grunnleggende ferdighet», og da kan man la dette stå åpent.

Trykk på **«PUBLISERE»** etter at alle valg er gjort.

---
Etter publisering vil man få nye valg.

For å kopiere tag URL: Trykk på symbolet for «Kopier tag-URL». URL-adressen for hele taggingen er nå kopiert til utklippstavlen, og kan kopieres inn i et regneark eller lignende. Hvis man undersøker URL i nettleser vil man se at JSON fil korresponderer med de valgene man har gjort ved tagging. 

For å vise fagkart informasjon som er tilpasset xAPI formatering/struktur, klikk på **{...}** ikonet. For å kopiere denne informasjonen, klikk på «Kopier og lukk» ikonet på høyre side. Denne informasjonen skal legges i xAPI struktur *context->contextActivities->grouping* (se [eksempler](eksempler.md)).

For å fjerne alle valg og starte med å tagge en ny oppgave, kan man i emnet «Læreplan» velge «Norsk», for deretter å velge «Matematikk 1–10» igjen.

---

### Emner og nødvendighet med tanke på tagging

| Emne (fagkart-element)| Nødvendighet|
|--------------|-----------:|
|Læreplan|Obligatorisk|
|Kompetansemål|Obligatorisk|
|Område i fagkart|Obligatorisk|
|Kompetanseklasse|Ønskelig|
|Kunnskapsområde|Valgfri|
|Verb|Obligatorisk|
|Kompetansemål sammenheng|Valgfri|
|Grunnleggende ferdigheter|Valgfri|
|Kjerneelement|Valgfri|
|Kompetansemålsett|Valgfri|