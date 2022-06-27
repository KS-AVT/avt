## xAPI Dataoverføring

xAPI data  fra de ulike leverandørene i AVT prosjektet lagres sentralt i AVT prosjektet sin Learning Record Store (LRS). Overføring av leverandørdata til AVT prosjektet kan gjøres på to ulike måter:

1) Den anbefalte metoden er å bruke (secure) FTP. Leverandør får da tidsbegrenset tilgang til FTP server for å laste opp data i xAPI/json format. Overføring må skje etter avtale med AVT prosjektet, ideelt med daglig overføring. Denne løsningen krever ikke LRS hos leverandør. Et lite minus ved metoden er at den ikke muliggjør real-time overføring av data. Bildet under illustrerer prosessen.

    ![FTP](./bilder/ftp%20dataoverfoering.png)
    
    **Filformat (FTP overføring)** 

    AVT prosjektet ønsker å motta en JSONL fil per dag (alternativt kan filen deles opp hvis ønskelig). Med tanke på bl.a. reduksjon av filstørrelse og dataintegritet bør man bruke tar og gzip for henholdsvis arkivering og komprimering av filer. 
    
    AVT ber om følgende navngiving av leverte filer: *YYYY-MM-DD_\<timestamp\>.tar.gz*.

    - *YYYY-MM-DD* er da datoen for hendelsene (læringsaktivitetene) som er fanget opp i xAPI statementene.
    - *\<timestamp\>* er "unix timestamp", i sekunder, og representerer når arkivet (tar.gz filen) ble generert.
    \
    \
    &nbsp;
    
2) En annen mulighet er at xAPI data overføres fra leverandør til AVT prosjektet gjennom leverandørs egen LRS. Da må AVT prosjektet gis tilgang til å autentisere mot leverandør LRS slik at data kan hentes ned med jevne og deretter lagres i AVT prosjektets egen LRS. Denne metoden krever at leverandør har sin egen LRS, som igjen implementerer et sett av RESTful HTTP metoder. [REST API](https://github.com/adlnet/xAPI-Spec/blob/master/xAPI-Communication.md#20-resources) er spesifisert i xAPI dokumentasjonen. 

    Det finnes et antall mulige LRS, f.eks. er [LearningLocker](https://docs.learninglocker.net/welcome/#) og [Yet Analytics](https://www.yetanalytics.com/news/yet-analytics-releases-sql-lrs-a-new-open-source-xapi-learning-record-store) open source alternativer. En annen mulighet er at leverandører kan bygge LRS funksjonalitet oppå eksisterende lagringsløsninger, ved å implementere [REST API-ene](https://github.com/adlnet/xAPI-Spec/blob/master/xAPI-Communication.md#20-resources) som utdypes i xAPI spesifikasjonen. xAPI spesifikasjonen gir i tillegg til implementasjonsdetaljer også en oversikt over de nødvendige [endepunkter](https://github.com/adlnet/xAPI-Spec/blob/master/xAPI-Communication.md#appendix-b-table-of-all-resources) som er påkrevd.

    [AVT xAPI eksemplene](./eksempler.md) illustrerer et utvalg xAPI REST API kall (se nederst i eksemplene).