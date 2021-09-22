# Eksempler på kall mot og respons fra leverandørenes aktivitetsdata-API
Deltakende leverandører i AVT-prosjektet forholder seg til dette dokumentet i stedet for det som ble sendt til dem i forbindelse med invitasjon til deltakelse ("Eksempler på læringsaktiviteter som «Experience API»-utsagn", dokument nr. N032,  publisert av Standard Norge SN/K 186 Læringsteknologi-komiteen i september 2017)

Det er valgt ut flere eksempler, bl.a. fra en tenkt besvarelse av en matematikk-oppgave i "Overgangsprøven i matematikk for 4. trinn" som benyttes i grunnskolen i Oslo (eksempel 1 *uten* og eksempel 4 *med* bruk av `moreInfo`-attributt), et eksempel fra en tenkt oppgaveløsning i fysikk på viten.no og et fra en tenkt oppgaveløsning på lokus.no (med bruk av hint).

NB: Eksemplene er laget ut i fra hva som kanskje kunne vært mulig dersom verktøyene støttet å generere læringsaktiviteter i xAPI format, men ingen av de to systemene gjør dette per i dag.

Eksemplene på xAPI-utsagn inkluderer å vise muligheter for følgende informasjon:
- hvordan verb og aktivitetstyper fremkommer i noen xAPI-utsagn
- hvordan en aktør (en elev) kan identifiseres via en ID (brukernavn) fra Feide/Dataporten
- hvordan en skole og skoleeier kan identifiseres via organisasjonsnummeret mot nasjonalt skoleregister
- hvordan man kan inkludere knytninger mellom læringsaktiviteten og kompetansemål fra GREP inn i xAPI-utsagnene
- hvordan man kan inkludere knytninger mellom læringsaktiviteten og AVT-prosjektets ferdighetsstruktur
- hvordan man kan inkludere både «spørsmål» og «svar» på en oppgave, samt varighet (duration) og skåre (result.score)
- hvordan man kan benytte `moreInfo` for å slippe å inkludere detaljert beskrivelse av oppgaver/læringsressurser, og i stedet referere til en slik beskrivelse på en annen nettside

## [Eksempel 1 - Overgangsprøven i matematikk for 4. trinn](eksempel1_overgangsprove.md)

## [Eksempel 2 - Kapitteltest på Lokus.no](eksempel2_lokus_med_hint.md)