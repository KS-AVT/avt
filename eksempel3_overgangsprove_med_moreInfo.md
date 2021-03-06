## Eksempel 3 - Overgangsprøven i matematikk for 4. trinn, med bruk av moreInfo

Dette eksempelet er som eksempel 1, men med den forskjellen at informasjonselementet `moreInfo` er benyttet (til å angi en URL til en webside som viser hva oppgaven gikk ut på) i stedet for at detaljer om selve oppgaven og dens svaralternativer er angitt i hvert xAPI-utsagn for oppgaven.

Det er mulig å angi en "moreInfo"-lenke (URL) i alle definition-objekter i xAPI-utsagn, hvor nettsiden som `moreInfo` peker på kan være offentlig tilgjengelig eller kan befinne seg bak en påloggingsmekanisme. Lenken er ment til å gi menneskelig lesbar informasjon om hva læringsobjektet går ut på. Dette kan f.eks. være informasjon om en hel læringsressurs/prøve (som f.eks. denne overgangsprøven i regning), eller en forklaring (og eventuelt skjermbilde eller annen supplerende informasjon) om hva en enkelt oppgave/øvelse har gått ut på.

En fordel ved dette er at leverandørene slipper å oversende/eksportere den samme oppgaveteksten igjen og igjen for den samme oppgaven. I tillegg slipper man at selve oppgavetekstene (som antakelig er opphavsbeskyttet) blir lagret mange steder.

Dersom oppgaven endrer seg bør også ID'en (URI'en) og moreInfo-lenken til oppgaven endres, slik at en lenke angitt i et moreInfo element i et xAPI-utsagt forblir historisk riktig (altså viser oppgaven slik den var på det tidspunktet da oppgaven ble fremvist til eleven).

Her er [mer informasjon](https://github.com/adlnet/xAPI-Spec/blob/3089bad9feb57c59e0c9c88991adb1efd7aadcc9/xAPI-Data.md#activity-definition) om `moreInfo` fra xAPI-spesifikasjonen, og et eksempel kan ses dersom du scroller noen linjer opp fra [denne lenken](https://github.com/adlnet/xAPI-Spec/blob/3089bad9feb57c59e0c9c88991adb1efd7aadcc9/xAPI-Data.md#appendix-b-examples-of-statements-objects-of-different-types).

### Utdrag som viser bruken av moreInfo i et xAPI object
Nedenfor vises et eksempel på bruk av `moreInfo`, som i dette tilfellet har en verdi som er en fiktiv URL.
URL'en er ment å navigere brukeren til en [forklaring og illustrasjon av oppgaven](bilder/Eksempel%201%20-%20Overgangspr%C3%B8ven%20i%20regning%204.%20trinn%202017.jpg) (men kanskje med mer informasjon).
```
    "object": {
        "objectType": "Activity",
        "id": "https://osloprovene.inspera.no/ov-mat-4/task/123456",
        "definition": {
            "name": {
                "nb-NO": "Overgangsprøven i regning, 4. trinn: Oppgave 23"
            },
            "moreInfo": "https://osloprovene.inspera.no/ov-mat-4/task/123456/this-can-be-a-human-readable-webpage-explaining-the-task"
        }
    }
```


### Det er kun en oppgave i hele prøven som er med i eksempel 4 (dette gjelder også for eksempel 1)
Merk: For å forenkle eksempelomfanget så er det kun én oppgave (nr 23) som er modellert, men Overgangsprøven i regning inneholder selvsagt mange flere oppgaver. Informasjonen i eksempelet er til illustrasjon, og har blitt utarbeidet uten involvering fra Inspera (derfor er det sikkert enkelte unøyaktigheter, eksempelvis ID og navn på Feide-tjenesten som faktisk benyttes). Dataporten-ID'en til "actor" tilhører testeleven "Kari Nordmann" ved en av Utdanningsetatens testskoler. AVT-prosjektet presiserer at linjen "name": "Kari Nordmann", i "actor"-objektet IKKE skal inkluderes i xAPI-statementet, kun Dataporten-ID.


### Oversikt over xAPI-statements for eksempel 4 (Overgangsprøven i regning)

Nr.|Comment|Who (actor)|Did (verb)|What (object)|
---------|------------------|-------|---------|------|
|[1](#1)|Learner has logged in to "Overgangsprøve i regning 4. trinn 2017"|Kari Nordmann|logget inn|Overgangsprøve i regning 4. trinn 2017|
|[2](#2)|Learner has answered a single question (without success) in "Overgangsprøve i regning 4. trinn 2017". The details of the question and it's alternatives can be seen when navigating to the URL mentioned in the moreInfo-attribute.|Kari Nordmann|besvarte|Overgangsprøve i regning 4. trinn 2017: Oppgave 23|
|[3](#3)|Learner has answered a single question (with success) in "Overgangsprøve i regning 4. trinn". The details of the question and it's alternatives can be seen when navigating to the URL mentioned in the moreInfo-attribute.|Kari Nordmann|besvarte|Overgangsprøve i regning 4. trinn 2017: Oppgave 23|
|[4](#4)|Learner has completed all questions in "Overgangsprøve i regning 4. trinn 2017”|Kari Nordmann|fullførte|Overgangsprøve i regning 4. trinn 2017|

#### Eksempel på kall

```
Hent Statements - bruker
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}

Hent Statements - bruker AND kompetansemål
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}&activity=http://psi.udir.no/kl06/KM246&related_activities=true

Hent Statements - bruker AND kompetansemål AND kompetanse klasse
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}&activity=http://psi.udir.no/kl06/KM246&activity=http://fagkart.no/avt2/ontology/types/competence_class/objects/easy&related_activities=true

Hent Statements - bruker AND omrade i fagkart
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}&activity=https://fagkart.no/avt2/ontology/types/area_in_subject_maps/objects/121ba096-2bee-5a4c-8e0c-c7f781fa2075&related_activities=true

Hent Statements - bruker AND omrade i fagkart AND kompetanse klasse
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}&activity=https://fagkart.no/avt2/ontology/types/area_in_subject_maps/objects/121ba096-2bee-5a4c-8e0c-c7f781fa2075&activity=http://fagkart.no/avt2/ontology/types/competence_class/objects/easy&related_activities=true
```

#### Eksempel på respons

<a name="1"></a>
#### 1. Learner has logged in to "Overgangsprøve i regning 4. trinn 2017"
``` Javascript
{
    "id": "7772699b-1867-428c-9f3c-4c34aac6dc96",
    "timestamp": "2018-05-10T11:30:00Z",
    "actor": {
        "objectType": "Agent",
        "account": {
            "homePage": "https://docs.dataporten.no",
            "name": "76a7a061-3c55-430d-8ee0-6f82ec42501f"
        }
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/logged-in",
        "display": {
            "en-US": "logged-in",
            "nb-NO": "logget inn"
        }
    },
    "object": {
        "objectType": "Activity",
        "id": "https://osloprovene.inspera.no/ov-mat-4/test/123",
        "definition": {
            "name": {
                "nb-NO": "Overgangsprøve i regning 4. trinn 2017"
            },
            "type": "http://adlnet.gov/expapi/activities/assessment",
            "moreInfo": "https://osloprovene.inspera.no/ov-mat-4/test/123/valgfri-fiktiv-URL-med-info-om-prøven"
        }
    },
    "context": {
        "registration": "e28fa121-91e1-43c7-9192-d9d6546bd76e",
        "platform": "Inspera prøvemotor for Oslo",
        "language": "nb-NO",
        "contextActivities": {
            "grouping": [
                {
                    "objectType": "Activity",
                    "id": "https://data-nsr.udir.no/enhet/976820037",
                    "definition": {
                        "name": {
                            "nb-NO": "Oslo kommune Utdanningsetaten"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/school-owner"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://data-nsr.udir.no/enhet/974589648",
                    "definition": {
                        "name": {
                            "nb-NO": "Abildsø skole"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/school"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://clientadmin.dataporten-api.no/clients/cc2b2720-4dae-4220-8258-1f6ac8c6dd4f",
                    "definition": {
                        "name": {
                            "nb-NO": "Inspera"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/feide-clientinfo"
                    }
                }
            ]
        }
    }
}
```

<a name="2"></a>
#### 2. Learner has answered a single question (without success) in "Overgangsprøve i regning 4. trinn 2017". The details of the question and it's alternatives can be seen when navigating to the URL mentioned in the moreInfo-attribute, and is not included in this xAPI-statement.
``` Javascript
{
    "id": "a0dbae37-c87a-4965-b09b-c25d6a997eac",
    "timestamp": "2018-05-10T11:31:02Z",
    "actor": {
        "objectType": "Agent",
        "account": {
            "homePage": "https://docs.dataporten.no",
            "name": "76a7a061-3c55-430d-8ee0-6f82ec42501f"
        }
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/answered",
        "display": {
            "en-US": "answered",
            "nb-NO": "besvarte"
        }
    },
    "object": {
        "objectType": "Activity",
        "id": "https://osloprovene.inspera.no/ov-mat-4/task/123456",
        "definition": {
            "name": {
                "nb-NO": "Overgangsprøven i regning, 4. trinn: Oppgave 23"
            },
            "moreInfo": "https://osloprovene.inspera.no/ov-mat-4/task/123456/this-can-be-a-human-readable-webpage-explaining-the-task"
        }
    },
    "result": {
        "duration": "PT62S",
        "response": "B",
        "success": false,
        "score": {
            "min": 0.0,
            "max": 3.0,
            "raw": 0.0,
            "scaled": 0.0
        }
    },
    "context": {
        "registration": "e28fa121-91e1-43c7-9192-d9d6546bd76e",
        "platform": "Inspera prøvemotor for Oslo",
        "language": "nb-NO",
        "contextActivities": {
            "grouping": [
                {
                  "objectType": "Activity",
                  "id": "https://fagkart.no/avt2/api/ontology/types/fagkart_tag/objects/cb8a4c86-9af7-5b54-9370-f750557e815e:b302a00d-e3dd-5791-891c-7cb409bdf50e",
                  "definition": {
                    "name": {
                      "en": "A set of parameters that link an exercise/item to one or more reference models tagged using the fagkartkoder tool (see fagkart.no)",
                      "nb": "Et sett med parametere som knytter en oppgave/item til en eller flere referansemodeller som er merket ved bruk av Fagkartkoderverktøyet (se fagkart.no)"
                    },
                    "type": "https://w3id.org/xapi/avt/activity-types/fagkart_tag"
                  }
                },            
                {
                    "objectType": "Activity",
                    "id": "https://data-nsr.udir.no/enhet/976820037",
                    "definition": {
                        "name": {
                            "nb-NO": "Oslo kommune Utdanningsetaten"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/school-owner"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://data-nsr.udir.no/enhet/974589648",
                    "definition": {
                        "name": {
                            "nb-NO": "Abildsø skole"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/school"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://clientadmin.dataporten-api.no/clients/cc2b2720-4dae-4220-8258-1f6ac8c6dd4f",
                    "definition": {
                        "name": {
                            "nb-NO": "Inspera"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/feide-clientinfo"
                    }
                }
            ]
        }
    }
}
```

<a name="3"></a>
#### 3. Learner has answered a single question (with success) in "Overgangsprøve i regning 4. trinn". The details of the question and it's alternatives can be seen when navigating to the URL mentioned in the moreInfo-attribute, and is not included in this xAPI-statement.
``` Javascript
{
    "id": "2741f96e-5701-4def-97f9-6761241ee29d",
    "timestamp": "2018-05-10T11:32:42Z",
    "actor": {
        "objectType": "Agent",
        "account": {
            "homePage": "https://docs.dataporten.no",
            "name": "76a7a061-3c55-430d-8ee0-6f82ec42501f"
        }
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/answered",
        "display": {
            "en-US": "answered",
            "nb-NO": "besvarte"
        }
    },
    "object": {
        "objectType": "Activity",
        "id": "https://osloprovene.inspera.no/ov-mat-4/task/123456",
        "definition": {
            "name": {
                "nb-NO": "Overgangsprøven i regning, 4. trinn: Oppgave 23"
            },
            "moreInfo": "https://osloprovene.inspera.no/ov-mat-4/task/123456/this-can-be-a-human-readable-webpage-explaining-the-task"
        }
    },
    "result": {
        "duration": "PT2M45S",
        "response": "C",
        "success": true,
        "score": {
            "min": 0.0,
            "max": 3.0,
            "raw": 3.0,
            "scaled": 1.0
        }
    },
    "context": {
        "registration": "e28fa121-91e1-43c7-9192-d9d6546bd76e",
        "platform": "Inspera prøvemotor for Oslo",
        "language": "nb-NO",
        "contextActivities": {
            "grouping": [
                {
                  "objectType": "Activity",
                  "id": "https://fagkart.no/avt2/api/ontology/types/fagkart_tag/objects/cb8a4c86-9af7-5b54-9370-f750557e815e:b302a00d-e3dd-5791-891c-7cb409bdf50e",
                  "definition": {
                    "name": {
                      "en": "A set of parameters that link an exercise/item to one or more reference models tagged using the fagkartkoder tool (see fagkart.no)",
                      "nb": "Et sett med parametere som knytter en oppgave/item til en eller flere referansemodeller som er merket ved bruk av Fagkartkoderverktøyet (se fagkart.no)"
                    },
                    "type": "https://w3id.org/xapi/avt/activity-types/fagkart_tag"
                  }
                },             
                {
                    "objectType": "Activity",
                    "id": "https://data-nsr.udir.no/enhet/976820037",
                    "definition": {
                        "name": {
                            "nb-NO": "Oslo kommune Utdanningsetaten"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/school-owner"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://data-nsr.udir.no/enhet/974589648",
                    "definition": {
                        "name": {
                            "nb-NO": "Abildsø skole"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/school"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://clientadmin.dataporten-api.no/clients/cc2b2720-4dae-4220-8258-1f6ac8c6dd4f",
                    "definition": {
                        "name": {
                            "nb-NO": "Inspera"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/feide-clientinfo"
                    }
                }
            ]
        }
    }
}
```

<a name="4"></a>
#### 4. Learner has completed all questions in "Overgangsprøve i regning 4. trinn 2017". (This statement is exactly as in example 1)
``` Javascript
{
    "id": "ab2b8bed-98c0-46d5-a432-c9646f638a58",
    "timestamp": "2018-05-10T11:50:00Z",
    "actor": {
        "objectType": "Agent",
        "account": {
            "homePage": "https://docs.dataporten.no",
            "name": "76a7a061-3c55-430d-8ee0-6f82ec42501f"
        }
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/completed",
        "display": {
            "en-US": "completed",
            "nb-NO": "fullførte"
        }
    },
    "object": {
        "objectType": "Activity",
        "id": "https://osloprovene.inspera.no/ov-mat-4/test/123",
        "definition": {
            "name": {
                "nb-NO": "Overgangsprøve i regning 4. trinn 2017"
            },
            "type": "http://adlnet.gov/expapi/activities/assessment"
        }
    },
    "result": {
        "duration": "PT38M44S",
        "completion": true,
        "success": true,
        "score": {
            "min": 0.0,
            "max": 45.0,
            "raw": 38.0,
            "scaled": 0.844
        }
    },
    "context": {
        "registration": "e28fa121-91e1-43c7-9192-d9d6546bd76e",
        "platform": "Inspera prøvemotor for Oslo",
        "language": "nb-NO",
        "contextActivities": {
            "grouping": [
                {
                    "objectType": "Activity",
                    "id": "https://data-nsr.udir.no/enhet/976820037",
                    "definition": {
                        "name": {
                            "nb-NO": "Oslo kommune Utdanningsetaten"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/school-owner"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://data-nsr.udir.no/enhet/974589648",
                    "definition": {
                        "name": {
                            "nb-NO": "Abildsø skole"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/school"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://clientadmin.dataporten-api.no/clients/cc2b2720-4dae-4220-8258-1f6ac8c6dd4f",
                    "definition": {
                        "name": {
                            "nb-NO": "Inspera"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/feide-clientinfo"
                    }
                }
            ]
        }
    }
}
```
