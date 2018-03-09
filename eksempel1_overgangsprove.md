## Eksempel 1 - Overgangsprøven i matematikk for 4. trinn

Merk: For å forenkle eksempelomfanget så er det kun én oppgave (nr 23) som er modellert, men Overgangsprøven i regning inneholder selvsagt mange flere oppgaver. Informasjonen i eksempelet er til illustrasjon, og har blitt utarbeidet uten involvering fra Inspera (derfor er det sikkert enkelte unøyaktigheter, eksempelvis ID og navn på Feide-tjenesten som faktisk benyttes).

Skjermdump av oppgaven:
![](bilder/Eksempel%201%20-%20Overgangspr%C3%B8ven%20i%20regning%204.%20trinn%202017.jpg)

### Oversikt over xAPI-statements for eksempel 1 (Overgangsprøven i regning)

Nr.|Comment|Who (actor)|Did (verb)|What (object)|
---------|------------------|-------|---------|------|
|[1](#1)|Learner has logged in to "Overgangsprøve i regning 4. trinn 2017"|Kari Nordmann|logget inn|Overgangsprøve i regning 4. trinn 2017|
|[2](#2)|Learner has answered a single question (without success) in "Overgangsprøve i regning 4. trinn 2017"|Kari Nordmann|besvarte|Overgangsprøve i regning 4. trinn 2017: Oppgave 23|
|[3](#3)|Learner has answered a single question (with success) in "Overgangsprøve i regning 4. trinn"|Kari Nordmann|besvarte|Overgangsprøve i regning 4. trinn 2017: Oppgave 23|
|[4](#4)|Learner has completed all questions in "Overgangsprøve i regning 4. trinn 2017”|Kari Nordmann|fullførte|Overgangsprøve i regning 4. trinn 2017|

#### Eksempel på kall

```javascript
Hent Statements - bruker
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}

Hent Statements - bruker AND kompetansemål
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}&activity=http://data.udir.no/kl06/K15170&related_activities=true

Hent Statements - bruker AND kompetansemål AND vanskegrad
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}&activity=http://data.udir.no/kl06/K15170&activity=https://lmbase.no/xapi/avt/frameworks/pisa/mathematical-literacy/competence-level-2&related_activities=true

Hent Statements - bruker AND ferdighetsstruktur
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}&activity=https://lmbase.no/xapi/avt/frameworks/learning-objective/LM100001&related_activities=true

Hent Statements - bruker AND ferdighetsstruktur AND vanskegrad
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}&activity=https://lmbase.no/xapi/avt/frameworks/learning-objective/LM100001&activity=https://lmbase.no/xapi/avt/frameworks/pisa/mathematical-literacy/competence-level-2&related_activities=true
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
        "name": "Kari Nordmann",
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
                    "id": "https://api.feide.no/2/sp/1855493",
                    "definition": {
                        "name": {
                            "nb-NO": "Inspera Assessment"
                        },
                        "description": {
                            "nb-NO": "En skybasert prøve og eksamensløsning for skoler og universiteter. Lag og gjennomfør inspirerende prøver, og analyser resultatene for å hjelpe kandidaten til å lære mer"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/application"
                    }
                }
            ]
        }
    }
}
```

<a name="2"></a>
#### 2. Learner has answered a single question (without success) in "Overgangsprøve i regning 4. trinn 2017"
``` Javascript
{
    "id": "a0dbae37-c87a-4965-b09b-c25d6a997eac",
    "timestamp": "2018-05-10T11:31:02Z",
    "actor": {
        "objectType": "Agent",
        "name": "Kari Nordmann",
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
                    "id": "http://data.udir.no/kl06/K15170",
                    "definition": {
                        "name": {
                            "nb-NO": "K15170"
                        },
                        "description": {
                            "nb-NO": "beskrive og bruke plassverdisystemet for de hele tallene, bruke positive og negative hele tall, enkle brøker og desimaltall i praktiske sammenhenger og uttrykke tallstørrelser på varierte måter"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/competence-aim"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://lmbase.no/xapi/avt/frameworks/learning-objective/LM100001",
                    "definition": {
                        "name": {
                            "nb-NO": "Desimaltallsaddisjon med overgang"
                        },
                        "description": {
                            "nb-NO": "Ett eller flere av leddene i addisjonen har desimaltall og utregningen inneholder en eller flere tier-overganger"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/learning-objective"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://lmbase.no/xapi/avt/frameworks/pisa/mathematical-literacy/competence-level-2",
                    "definition": {
                        "name": {
                            "nb-NO": "Se forbindelser og kunne integrere informasjon som grunnlag for problemløsing"
                        },
                        "description": {
                            "nb-NO": "innebærer at elevene er i stand til å se sammenhenger mellom ulike områder av matematikken og bruke ulike representasjoner av samme fenomen, samt se sammenhenger mellom definisjoner, beviser, eksempler og påstander"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/complexity-level"
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
                    "id": "https://api.feide.no/2/sp/1855493",
                    "definition": {
                        "name": {
                            "nb-NO": "Inspera Assessment"
                        },
                        "description": {
                            "nb-NO": "En skybasert prøve og eksamensløsning for skoler og universiteter. Lag og gjennomfør inspirerende prøver, og analyser resultatene for å hjelpe kandidaten til å lære mer"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/application"
                    }
                }
            ]
        }
    }
}
```

<a name="3"></a>
#### 3. Learner has answered a single question (with success) in "Overgangsprøve i regning 4. trinn"
``` Javascript
{
    "id": "2741f96e-5701-4def-97f9-6761241ee29d",
    "timestamp": "2018-05-10T11:32:42Z",
    "actor": {
        "objectType": "Agent",
        "name": "Kari Nordmann",
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
                "nb-NO": "Sofie hoppet 2,7 m i lengde. Neste gang hoppet hun 3,4 m. Hvor langt hoppet hun til sammen?"
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
                    "id": "http://data.udir.no/kl06/K15170",
                    "definition": {
                        "name": {
                            "nb-NO": "K15170"
                        },
                        "description": {
                            "nb-NO": "beskrive og bruke plassverdisystemet for de hele tallene, bruke positive og negative hele tall, enkle brøker og desimaltall i praktiske sammenhenger og uttrykke tallstørrelser på varierte måter"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/competence-aim"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://lmbase.no/xapi/avt/frameworks/learning-objective/LM100001",
                    "definition": {
                        "name": {
                            "nb-NO": "Desimaltallsaddisjon med overgang"
                        },
                        "description": {
                            "nb-NO": "Ett eller flere av leddene i addisjonen har desimaltall og utregningen inneholder en eller flere tier-overganger"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/learning-objective"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://lmbase.no/xapi/avt/frameworks/pisa/mathematical-literacy/competence-level-2",
                    "definition": {
                        "name": {
                            "nb-NO": "Se forbindelser og kunne integrere informasjon som grunnlag for problemløsing"
                        },
                        "description": {
                            "nb-NO": "innebærer at elevene er i stand til å se sammenhenger mellom ulike områder av matematikken og bruke ulike representasjoner av samme fenomen, samt se sammenhenger mellom definisjoner, beviser, eksempler og påstander"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/complexity-level"
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
                    "id": "https://api.feide.no/2/sp/1855493",
                    "definition": {
                        "name": {
                            "nb-NO": "Inspera Assessment"
                        },
                        "description": {
                            "nb-NO": "En skybasert prøve og eksamensløsning for skoler og universiteter. Lag og gjennomfør inspirerende prøver, og analyser resultatene for å hjelpe kandidaten til å lære mer"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/application"
                    }
                }
            ]
        }
    }
}
```

<a name="4"></a>
#### 4. Learner has completed all questions in "Overgangsprøve i regning 4. trinn 2017”
``` Javascript
{
    "id": "ab2b8bed-98c0-46d5-a432-c9646f638a58",
    "timestamp": "2018-05-10T11:50:00Z",
    "actor": {
        "objectType": "Agent",
        "name": "Kari Nordmann",
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
                    "id": "https://api.feide.no/2/sp/1855493",
                    "definition": {
                        "name": {
                            "nb-NO": "Inspera Assessment"
                        },
                        "description": {
                            "nb-NO": "En skybasert prøve og eksamensløsning for skoler og universiteter. Lag og gjennomfør inspirerende prøver, og analyser resultatene for å hjelpe kandidaten til å lære mer"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/application"
                    }
                }
            ]
        }
    }
}
```
