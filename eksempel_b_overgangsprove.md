## Eksempel B - Overgangsprøven i matematikk for 4. trinn

Merk: For å forenkle eksempelomfanget så er det kun én oppgave (nr 23) som er modellert, men Overgangsprøven i regning inneholder selvsagt mange flere oppgaver. Informasjonen i eksempelet er til illustrasjon, og har blitt utarbeidet uten involvering fra Inspera (derfor er det sikkert enkelte unøyaktigheter, eksempelvis ID og navn på Feide-tjenesten som faktisk benyttes). Dataporten-ID'en til "actor" tilhører testeleven "Kari Nordmann" ved en av Utdanningsetatens testskoler. AVT-prosjektet presiserer at linjen "name": "Kari Nordmann", i "actor"-objektet IKKE skal inkluderes i xAPI-statementet, kun Dataporten-ID.


Skjermdump av oppgaven:
![](bilder/Eksempel%201%20-%20Overgangspr%C3%B8ven%20i%20regning%204.%20trinn%202017.jpg)


### Eksempler på respons

<a name="1"></a>
#### 1. Eleven har logget på "Overgangsprøve i regning 4. trinn 2017"
```json
{
    "id": "4d3e0af9-73c0-470a-9a36-b0728b11a9cd",
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
            "type": "http://adlnet.gov/expapi/activities/assessment"
        }
    },
    "context": {
        "registration": "3e62076b-27ad-498c-9587-cd26677e5320",
        "platform": "Inspera prøvemotor for Oslo",
        "language": "nb-NO",
        "contextActivities": {
            "grouping": [
                {
                    "objectType": "Activity",
                    "id": "https://api.feide.no/2/sp/1855493",
                    "definition": {
                        "name": {
                            "nb-NO": "Inspera Assessment"
                        },
                        "description": {
                            "nb-NO": "En skybasert prøve og eksamensløsning for skoler og universiteter. Lag og gjennomfør inspirerende prøver, og analyser resultatene for å hjelpe kandidaten til å lære mer"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/feide-sp-id"
                    }
                }
            ]
        }
    }
}
```

#### 2. Eleven har svart feil på en oppgave i "Overgangsprøve i regning 4. trinn 2017"
```json
{
    "id": "5bf516a4-c92c-491f-9d20-d3168d19e5dc",
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
            "description": {
                "nb-NO": "Sofie hoppet 2,7 m i lengde. Neste gang hoppet hun 3,4 m.\nHvor langt hoppet hun til sammen?"
            },
            "type": "http://adlnet.gov/expapi/activities/cmi.interaction",
            "interactionType": "choice",
            "choices": [
                {
                    "id": "A",
                    "description": {
                        "nb-NO": "5,1 m"
                    }
                },
                {
                    "id": "B",
                    "description": {
                        "nb-NO": "5,11 m"
                    }
                },
                {
                    "id": "C",
                    "description": {
                        "nb-NO": "6,1 m"
                    }
                },
                {
                    "id": "D",
                    "description": {
                        "nb-NO": "6,11 m"
                    }
                }
            ],
            "correctResponsesPattern": [
                "C"
            ]
        }
    },
    "result": {
        "duration": "PT62S",
        "response": "B",
        "success": false,
        "score": {
            "min": 0.0,
            "max": 1.0,
            "raw": 0.0,
            "scaled": 0.0
        }
    },
    "context": {
        "registration": "3e62076b-27ad-498c-9587-cd26677e5320",
        "platform": "Inspera prøvemotor for Oslo",
        "language": "nb-NO",
        "contextActivities": {
            "grouping": [
                {
                    "objectType": "Activity",
                    "id": "http://psi.udir.no/kl06/KM287",
                    "definition": {
                        "name": {
                            "nb-NO": "KM287"
                        },
                        "description": {
                            "nn-NO": "lage rekneuttrykk til praktiske situasjonar og finne praktiske situasjonar som passar til oppgitte rekneuttrykk"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/competence-objective"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://fagkart.no/avt/area-within-the-map/OFK10343",
                    "definition": {
                        "name": {
                            "nb-NO": "Plassverdisystemet"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/area-within-the-map"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://fagkart.no/avt/pisa/mathematical-competence-class/competence-class-2",
                    "definition": {
                        "name": {
                            "nb-NO": "Se forbindelser og kunne integrere informasjon som grunnlag for problemløsing"
                        },
                        "description": {
                            "nb-NO": "innebærer at elevene er i stand til å se sammenhenger mellom ulike områder av matematikken og bruke ulike representasjoner av samme fenomen, samt se sammenhenger mellom definisjoner, beviser, eksempler og påstander"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/mathematical-competence-class"
                    }
                },            
                {
                    "objectType": "Activity",
                    "id": "https://clientadmin.dataporten-api.no/clients/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                    "definition": {
                        "name": {
                            "nb-NO": "Inspera Assessment"
                        },
                        "description": {
                            "nb-NO": "En skybasert prøve og eksamensløsning for skoler og universiteter. Lag og gjennomfør inspirerende prøver, og analyser resultatene for å hjelpe kandidaten til å lære mer"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/feide-sp-id"
                    }
                }
            ]
        }
    }
}
```

#### 3. Når eleven svarer korrekt, blir eksempelet det samme som 2. med unntak av `"result"`
```json
    "result": {
        "duration": "PT2M45S",
        "response": "C",
        "success": true,
        "score": {
            "min": 0.0,
            "max": 1.0,
            "raw": 1.0,
            "scaled": 1.0
        }
    },
```

#### 4. Eleven har fullført alle oppgaver i "Overgangsprøve i regning 4. trinn 2017”, og leverer oppgavesettet.
```json
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
        "registration": "3e62076b-27ad-498c-9587-cd26677e5320",
        "platform": "Inspera prøvemotor for Oslo",
        "language": "nb-NO",
        "contextActivities": {
            "grouping": [
                {
                    "objectType": "Activity",
                    "id": "https://clientadmin.dataporten-api.no/clients/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                    "definition": {
                        "name": {
                            "nb-NO": "Inspera Assessment"
                        },
                        "description": {
                            "nb-NO": "En skybasert prøve og eksamensløsning for skoler og universiteter. Lag og gjennomfør inspirerende prøver, og analyser resultatene for å hjelpe kandidaten til å lære mer"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/feide-sp-id"
                    }
                }
            ]
        }
    }
}
```
