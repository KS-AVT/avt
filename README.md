# Aktivitetsdata for Vurdering og Tilpasning (AVT)

Ler mer om AVT-prosjektet [her](avt-about.md).

Dette repositoriet dokumenterer hvordan AVT-prosjektet bruker xAPI-rammeverket og den tekniske løsning (AVT-HUB) som prosjektet utvikler. </br></br>NB! Fullstendig oversikt over datastruktur, kall og responser vil bli publisert fortløpende i dette repositoriet.

## AVT-HUB
Informasjon om hvordan integrere mot AVT-HUB finner du på [denne siden](avt-hub.md).

## Referanser til andre ressurser
- AVT sin profil er basert på xAPI-spesifikasjonen, mer info om denne her: [xAPI-spesifikasjon](https://github.com/adlnet/xAPI-Spec)
- Det finnes forskjellige valideringsmotorer for xAPI som kan brukes for å validere at statements som genereres er ihht standard. F.eks. [denne på lrs.io](https://lrs.io/ui/tools/xapi-statement-validator/)
- Lrs.io har også andre nyttige verktøy, f.eks. statement generators og en del teknisk dokumentasjon: [Link](https://lrs.io/ui/tools/)

## xAPI-profil
Prosjektet registrerer en ny xAPI-profil med seks nye konsepter:
- Referanse til nasjonale kompetansemål
- Referanse til områder i AVT-prosjektets fagkart.
- Kompetanseklasse i matematikk etter PISA-skalaen 
- Referanse til skoleeier
- Referanse til skole
- Referanse til FEIDE-tjeneste/-leverandør

[Profil](avt.jsonld)

## Eksempler på xAPI-utsagn
Prosjektet reviderer også dokumentet "Eksempler på læringsaktiviteter som «Experience API»-utsagn" (dokument nr. N032) som ble publisert av Standard Norge (SN/K 186 Læringsteknologi-komiteen) september 2017. Endringene er basert på innspill fra deltakende leverandør i AVT-prosjektet og går på:
- Referanse til skoler og skoleeier endres til å benytte Utdanningsdirektoratets nye API'er mot Nasjonalt Skoleregister i tråd med ny profil.
- Beskrivelse av kompleksitetsnivå legges til i tråd med ny profil
- Referanse til nasjonale kompetansemål legges til i tråd med ny profil
- Referanse til områder i AVT-prosjektets fagkart legges til i tråd med ny profil
- Referanse til tjenestetilbyder eller applikasjon legges til i tråd med ny profil
- Syntaks for kallene som gir responsene i eksemplene legges til

[Eksempler](eksempler.md)