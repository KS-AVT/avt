# Aktivitetsdata for Vurdering og Tilpasning (AVT2)
Dette repositoriet dokumenterer hvordan AVT2-prosjektet bruker xAPI-rammeverket.

Her finnes eksempler på xAPI datastruktur og kall (for leverandører med egen LRS), samt informasjon om xAPI minimumskrav og xAPI dataoverføring. I tillegg er det informasjon om hvordan man bruker verktøyet Fagkart.

## xAPI-profil
Prosjektet inkluderer xAPI-profil med nye konsepter:
- Referanse til områder i AVT2-prosjektets fagkart
- Referanse til skoleeier
- Referanse til skole
- Referanse til FEIDE-klient (Nye Feide, OAuth2/OIDC)

[Profil](avt.jsonld)

## Eksempler på xAPI-utsagn og kall
Prosjektet reviderer dokumentet "Eksempler på læringsaktiviteter som «Experience API»-utsagn" (dokument nr. N032) som ble publisert av Standard Norge (SN/K 186 Læringsteknologi-komiteen) september 2017. Endringene er basert på innspill fra deltakende leverandør i AVT2-prosjektet og går på:
- Referanse til skoler og skoleeier endres til å benytte Utdanningsdirektoratets nye API'er mot Nasjonalt Skoleregister i tråd med ny profil
- Beskrivelse av kompleksitetsnivå legges til i tråd med ny profil
- Referanse til nasjonale kompetansemål legges til i tråd med ny profil
- Referanse til områder i AVT2-prosjektets fagkart legges til i tråd med ny profil
- Referanse til tjenestetilbyder eller applikasjon legges til i tråd med ny profil
- Syntaks for xAPI kall legges til (aktuelt for leverandører med egen LRS)

Eksemplene inneholder også eksempler på xAPI kall (for leverandører med egen LRS).

[Eksempler](eksempler.md)

## xAPI minimumskrav
AVT2-prosjektet definerer et sett av minimumskrav for xAPI utsagn som er nødvendig for å sikre god dataintegrasjon mellom systemer.

[Minimumskrav](avt_xapi_minimumskrav.md)

## xAPI dataoverføring
Overføring av xAPI data fra leverandører til AVT prosjektet kan gjøres ved 1) SFTP overføring; eller ved 2) overføring fra leverandørs LRS (kun mulig for leverandører med egen LRS som opererer i henhold til xAPI standarden).

[Dataoverføring](./avt_xapi_dataoverf%C3%B8ring.md)

## Verktøyet Fagkart
Verktøyet Fagkart muliggjør tagging av læringsressurser slik at disse kan knyttes til AVT prosjektets fagkart.

[Verktøyet Fagkart](./fagkart_verktoyet.md)

Når taggene er publisert og man har hentet ut relevant informasjon gjennom Verktøyet Fagkart kan taggene knyttes til læringsressursene som en del av xAPI utsagnene. Som vist i [eksemplene](eksempler.md) legges da fagkart tag informasjonen til innenfor *context->contextActivities->grouping* i xAPI utsagnene.