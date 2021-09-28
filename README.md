# Aktivitetsdata for Vurdering og Tilpasning (AVT2)
Dette repositoriet dokumenterer hvordan AVT2-prosjektet bruker xAPI-rammeverket.

Her finnes eksempler på xAPI datastruktur, xAPI minimumskrav, xAPI  dataoverføring og xAPI kall (for leverandører med LRS).

## xAPI-profil
Prosjektet inkluderer xAPI-profil med nye konsepter:
- Referanse til områder i AVT2-prosjektets fagkart
- Referanse til skoleeier
- Referanse til skole
- Referanse til FEIDE-klient (Nye Feide, OAuth2/OIDC)

[Profil](avt.jsonld)

## xAPI minimumskrav
Prosjektet definerer et sett av xAPI minimumskrav som er nødvendig for å sikre god dataintegrasjon mellom systemer:
* [Minimumskrav](avt_xapi_minimumskrav.md) for xAPI statements i AVT2- prosjektet

## Eksempler på xAPI-utsagn
Prosjektet reviderer dokumentet "Eksempler på læringsaktiviteter som «Experience API»-utsagn" (dokument nr. N032) som ble publisert av Standard Norge (SN/K 186 Læringsteknologi-komiteen) september 2017. Endringene er basert på innspill fra deltakende leverandør i AVT2-prosjektet og går på:
- Referanse til skoler og skoleeier endres til å benytte Utdanningsdirektoratets nye API'er mot Nasjonalt Skoleregister i tråd med ny profil
- Beskrivelse av kompleksitetsnivå legges til i tråd med ny profil
- Referanse til nasjonale kompetansemål legges til i tråd med ny profil
- Referanse til områder i AVT2-prosjektets fagkart legges til i tråd med ny profil
- Referanse til tjenestetilbyder eller applikasjon legges til i tråd med ny profil
- Syntaks for kallene som gir responsene i eksemplene legges til

[Eksempler](eksempler.md)