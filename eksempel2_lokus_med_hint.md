## Eksempel 2 - Kapitteltest i matematikk fra Lokus.no, med visning av hint

Merk: For å forenkle eksempelomfanget så er det kun én oppgave (nr 6) som er modellert, men kapitteltesten inneholder selvsagt mange flere oppgaver. Informasjonen i eksempelet er til illustrasjon. Derfor er det sikkert enkelte unøyaktigheter, eksempelvis ID og navn på Feide-tjenesten som faktisk benyttes. Dataporten-ID'en til "actor" tilhører testeleven "Kari Nordmann" ved en av Utdanningsetatens testskoler. AVT-prosjektet presiserer at linjen "name": "Kari Nordmann", i "actor"-objektet IKKE skal inkluderes i xAPI-statementet, kun Dataporten-ID.

Oppgaven i eksempelet er tagged mot MAT01-05 -  matematikk 1.-10. trinn - https://www.udir.no/lk20/mat01-05.

Skjermdump av oppgaven (før hint vises):
![](bilder/Eksempel%203%20-%20Lokus%20kapitteltest%20oppgave%206.jpg)

Utsnitt av skjermbilde etter at hint er avdekket:
![](bilder/Eksempel%203%20-%20Hint.jpg)


### Oversikt over xAPI-statements for eksempel 2 (kapitteltest fra Lokus.no)

Nr.|Comment|Who (actor)|Did (verb)|What (object)|
---------|------------------|-------|---------|------|
|[1](#1)|Learner has answered a single question (without success) in "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus"|Kari Nordmann|besvarte|Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus: Oppgave 6|
|[2](#2)|Learner has answered a single question (after viewing a hint, so 1 point will be deducted from the score) in "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus"|Kari Nordmann|besvarte|Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus: Oppgave 6|

#### Eksempel på xAPI statement

<a name="1"></a>
#### 1. Learner has answered a single question (without success) in "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus"
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
        "id": "http://www.lokus.no/open/nummer/Nummer-8/4-Tall-og-algebra/Kapitteltest#oppgave-6",
        "definition": {
            "name": {
                "nb-NO": "4 Tall og algebra: Oppgave 6"
            },
            "type": "http://adlnet.gov/expapi/activities/cmi.interaction"
        }
    },
    "result": {
        "duration": "PT62S",
        "response": "A",
        "success": false,
        "score": {
            "min": 0.0,
            "max": 3.0,
            "raw": 0.0,
            "scaled": 0.0
        },
        "extensions": {
	        "https://w3id.org/xapi/avt/result-extensions/max-hints": 1,
	        "https://w3id.org/xapi/avt/result-extensions/hints-used": 0,
	        "https://w3id.org/xapi/avt/result-extensions/attempts": 1
        }
    },
    "context": {
        "registration": "e28fa121-91e1-43c7-9192-d9d6546bd76e",
        "platform": "Lokus",
        "language": "nb-NO",
        "contextActivities": {
            "grouping": [
                {
                    "objectType": "Activity",
                    "id": "https://fagkart.no/avt2/api/ontology/types/fagkart_tag/objects/cb8a4c86-9af7-5b54-9370-f750557e815e:4e425211-bf59-591e-9f87-93347e0bdcb1",
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
                    "id": "https://api.feide.no/2/sp/18554999",
                    "definition": {
                        "name": {
                            "nb-NO": "Lokus"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/feide-sp-id"
                    }
                }
            ]
        }
    }
}
```

<a name="2"></a>
#### 2. Learner has successfully answered a single question (but after viewing a hint, so 1 point will be deducted from the score) in "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus"
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
        "id": "http://www.lokus.no/open/nummer/Nummer-8/4-Tall-og-algebra/Kapitteltest#oppgave-6",
        "definition": {
            "name": {
                "nb-NO": "4 Tall og algebra: Oppgave 6"
            },
            "type": "http://adlnet.gov/expapi/activities/cmi.interaction"
        }
    },
    "result": {
        "duration": "PT2M45S",
        "response": "B,C,D",
        "success": true,
        "score": {
            "min": 0.0,
            "max": 3.0,
            "raw": 2.0,
            "scaled": 0.667
        },
        "extensions": {
	        "https://w3id.org/xapi/avt/result-extensions/max-hints": 1,
	        "https://w3id.org/xapi/avt/result-extensions/hints-used": 1,
	        "https://w3id.org/xapi/avt/result-extensions/attempts": 1
        }        
    },
    "context": {
        "registration": "e28fa121-91e1-43c7-9192-d9d6546bd76e",
        "platform": "Lokus",
        "language": "nb-NO",
        "contextActivities": {
            "grouping": [
                {
                    "objectType": "Activity",
                    "id": "https://fagkart.no/avt2/api/ontology/types/fagkart_tag/objects/cb8a4c86-9af7-5b54-9370-f750557e815e:4e425211-bf59-591e-9f87-93347e0bdcb1",
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
                    "id": "https://api.feide.no/2/sp/18554999",
                    "definition": {
                        "name": {
                            "nb-NO": "Lokus"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/feide-sp-id"
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

Hent Statements - bruker AND læreplan
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}&activity=http://psi.udir.no/kl06/MAT01-05&related_activities=true

Hent Statements - bruker AND kunnskapsomraade:algebra
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}&activity=https://fagkart.no/avt2/ontology/types/knowledge_area/objects/f39d563b-950d-5238-ba95-873b232f41bd&related_activities=true
```

REST API kall i eksemplene over vil returnere aktuelle xAPI statements.