# Eksempler på xAPI datastruktur, samt API kall for leverandører med egen LRS
Deltakende leverandører i AVT-prosjektet forholder seg til dette dokumentet i stedet for tidligere utsendte dokumenter. Det er her gjort noen forenklinger av xAPI syntaks og valg av xAPI verb, noe som ideelt vil gjøre det mindre arbeidskrevende for leverandører å levere data.

Det er valgt ut to eksempler, 1) fra en tenkt besvarelse av en matematikk-oppgave i "Overgangsprøven i matematikk for 4. trinn" som benyttes i grunnskolen i Oslo, og 2) fra en tenkt kapitteltest på Lokus.no.

NB: Eksemplene er laget ut i fra hva som kanskje kunne vært mulig dersom verktøyene støttet å generere læringsaktiviteter i xAPI format, men ingen av de to systemene gjør dette per i dag.

Eksemplene er formatert på en måte som reflekterer hvordan det er ment at leverandører skal levere data (f.eks. med tanke på vokabular).

Eksemplene på xAPI-utsagn inkluderer å vise muligheter for følgende informasjon:
- hvordan verb og aktivitetstyper fremkommer i xAPI-utsagn
- hvordan en aktør (en elev) kan identifiseres via en ID (brukernavn) fra Feide/Dataporten
- hvordan en skole og skoleeier kan identifiseres via organisasjonsnummeret mot nasjonalt skoleregister
- hvordan man kan inkludere knytninger mellom læringsaktiviteten og kompetansemål fra GREP inn i xAPI-utsagnene
- hvordan man kan inkludere knytninger mellom læringsaktiviteten og AVT-prosjektets ferdighetsstruktur
- hvordan man kan inkludere både «spørsmål» og «svar» på en oppgave, samt varighet (duration) og skåre (result.score)

## [Eksempel 1 - Overgangsprøven i matematikk for 4. trinn](eksempel1_overgangsprove.md)

## [Eksempel 2 - Kapitteltest på Lokus.no](eksempel2_lokus_med_hint.md)