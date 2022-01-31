## Eksempel 1 - Overgangsprøven i matematikk for 4. trinn

Merk: For å forenkle eksempelomfanget så er det kun én oppgave (nr 23) som er modellert, men Overgangsprøven i regning inneholder selvsagt mange flere oppgaver. Informasjonen i eksempelet er til illustrasjon, og har blitt utarbeidet uten involvering fra Inspera (derfor er det sikkert enkelte unøyaktigheter, eksempelvis ID og navn på Feide-tjenesten som faktisk benyttes). Dataporten-ID'en til "actor" tilhører testeleven "Kari Nordmann" ved en av Utdanningsetatens testskoler. AVT-prosjektet presiserer at linjen "name": "Kari Nordmann", i "actor"-objektet IKKE skal inkluderes i xAPI-statementet, kun Dataporten-ID.


Skjermdump av oppgaven:
![](bilder/Eksempel%201%20-%20Overgangspr%C3%B8ven%20i%20regning%204.%20trinn%202017.jpg)

### Oversikt over xAPI-statements for eksempel 1 (Overgangsprøven i regning)

Nr.|Comment|Who (actor)|Did (verb)|What (object)|
---------|------------------|-------|---------|------|
|[1](#1)|Learner has answered a single question (without success) in "Overgangsprøve i regning 4. trinn 2017"|Kari Nordmann|besvarte|Overgangsprøve i regning 4. trinn 2017: Oppgave 23|
|[2](#2)|Learner has answered a single question (with success) in "Overgangsprøve i regning 4. trinn"|Kari Nordmann|besvarte|Overgangsprøve i regning 4. trinn 2017: Oppgave 23|

#### Eksempel på xAPI statement

<a name="1"></a>
#### 1. Learner has answered a single question (without success) in "Overgangsprøve i regning 4. trinn 2017"
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
        },
        "extensions": {
	        "https://w3id.org/xapi/avt/result-extensions/max-hints": 0,
	        "https://w3id.org/xapi/avt/result-extensions/hints-used": 0,
	        "https://w3id.org/xapi/avt/result-extensions/attempts": 1
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

<a name="2"></a>
#### 2. Learner has answered a single question (with success) in "Overgangsprøve i regning 4. trinn"
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
        },
        "extensions": {
	        "https://w3id.org/xapi/avt/result-extensions/max-hints": 0,
	        "https://w3id.org/xapi/avt/result-extensions/hints-used": 0,
	        "https://w3id.org/xapi/avt/result-extensions/attempts": 1
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

### Eksempel på xAPI kall (for leverandører med egen LRS)

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

REST API kall i eksemplene over vil returnere aktuelle xAPI statements fra LRS.