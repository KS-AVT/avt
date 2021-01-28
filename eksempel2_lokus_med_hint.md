## Eksempel 2 - Kapitteltest i matematikk fra Lokus.no, med visning av hint

Merk: For å forenkle eksempelomfanget så er det kun én oppgave (nr 6) som er modellert, men kapitteltesten inneholder selvsagt mange flere oppgaver. Informasjonen i eksempelet er til illustrasjon. Derfor er det sikkert enkelte unøyaktigheter, eksempelvis ID og navn på Feide-tjenesten som faktisk benyttes. Dataporten-ID'en til "actor" tilhører testeleven "Kari Nordmann" ved en av Utdanningsetatens testskoler. AVT-prosjektet presiserer at linjen "name": "Kari Nordmann", i "actor"-objektet IKKE skal inkluderes i xAPI-statementet, kun Dataporten-ID.

Oppgaven i eksempelet er tagged mot MAT01-05 -  matematikk 1.-10. trinn - https://www.udir.no/lk20/mat01-05.

xAPI statements i dette eksempelet er veldig likt Eksempel 1, men med unntak av at xAPI statement nr 3 i dette eksempelet viser at et hint har blitt avdekket.
Utsagnet er basert på "xAPI recipe / oppskrift" hentet fra https://wiki.visualcatch.org/en/assessment.html#readF

Forskjellen mellom xAPI statement nummer 2 og 3 er at nr 3 benytter verbet "leste / read" og at hint-teksten er lagt inn som en extension av "object", samt at "result" objektet kun inneholder et tidsstempel (duration) for når hintet ble avdekket, og inneholder ikke selve svaret.
xAPI statement nr 4 inneholder det samme som i nummer 2, men denne gang med riktige svar og inkluderer også hintet som er benyttet i en extension av "object".

NB: Vi må bli enige om hvilken IRI vi skal benytte for verbet "leste / read", verbet er definert i flere vokabularer (men ikke i ADL-vokabularet).


Skjermdump av oppgaven (før hint vises):
![](bilder/Eksempel%203%20-%20Lokus%20kapitteltest%20oppgave%206.jpg)


Utsnitt av skjermbilde etter at hint er avdekket:
![](bilder/Eksempel%203%20-%20Hint.jpg)


### Oversikt over xAPI-statements for eksempel 3 (kapitteltest fra Lokus.no)

Nr.|Comment|Who (actor)|Did (verb)|What (object)|
---------|------------------|-------|---------|------|
|[1](#1)|Learner has logged in to "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus"|Kari Nordmann|logget inn|Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus|
|[2](#2)|Learner has answered a single question (without success) in "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus"|Kari Nordmann|besvarte|Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus: Oppgave 6|
|[3](#3)|Learner reveals (reads) a hint to better understand what to answer|Kari Nordmann|leste|Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus: Oppgave 6 - Hint|
|[4](#4)|Learner has answered a single question (with success, but after viewing a hint so 1 point will be deducted from the score) in "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus"|Kari Nordmann|besvarte|Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus: Oppgave 6|
|[5](#5)|Learner has completed all questions in "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus"|Kari Nordmann|fullførte|Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus|

#### Eksempel på kall

```
Hent Statements - bruker
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}

Hent Statements - bruker AND læreplan
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}&activity=http://psi.udir.no/kl06/MAT01-05&related_activities=true

Hent Statements - bruker AND kunnskapsomraade:algebra
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}&activity=https://fagkart.no/avt2/ontology/types/knowledge_area/objects/f39d563b-950d-5238-ba95-873b232f41bd&related_activities=true
```

#### Eksempel på respons

<a name="1"></a>
#### 1. Learner has logged in to "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus"
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
        "id": "http://www.lokus.no/open/nummer/Nummer-8/4-Tall-og-algebra/Kapitteltest",
        "definition": {
            "name": {
                "nb-NO": "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus"
            },
            "type": "http://adlnet.gov/expapi/activities/assessment"
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
                  "id": "https://fagkart.no/avt2/api/ontology/types/fagkart_tag/objects/5ab58270-19ee-5a2b-bbf5-6c2989e4b849:d4571543-71b6-51f2-949d-d0ff4207d874",
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
                        "description": {
                            "nb-NO": ""
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
#### 2. Learner has answered a single question (without success) in "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus"
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
            "description": {
                "nb-NO": "Hvilke er ligninger?"
            },
            "type": "http://adlnet.gov/expapi/activities/cmi.interaction",
            "interactionType": "choice",
            "choices": [
                {
                    "id": "A",
                    "description": {
                        "nb-NO": "4 - 3 * (2 - x)"
                    }
                },
                {
                    "id": "B",
                    "description": {
                        "nb-NO": "1 = 5 - (8 - y)"
                    }
                },
                {
                    "id": "C",
                    "description": {
                        "nb-NO": "4 - 3 * (2 - x) = 1"
                    }
                },
                {
                    "id": "D",
                    "description": {
                        "nb-NO": "x = 5"
                    }
                }
            ],
            "correctResponsesPattern": [
                "B,C,D"
            ]
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
        }
    },
    "context": {
        "registration": "e28fa121-91e1-43c7-9192-d9d6546bd76e",
        "platform": "Lokus",
        "language": "nb-NO",
        "contextActivities": {
            "parent": [
                {
                    "objectType": "Activity",
                    "id": "http://www.lokus.no/open/nummer/Nummer-8/4-Tall-og-algebra/Kapitteltest",
                    "definition": {
                        "name": {
                            "nb-NO": "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus"
                        },
                        "type": "http://adlnet.gov/expapi/activities/assessment"
                    }
                }
            ],
            "grouping": [
                {
                    objectType: "Activity",
                    id: "https://fagkart.no/avt2/api/ontology/types/fagkart_tag/objects/cb8a4c86-9af7-5b54-9370-f750557e815e:4e425211-bf59-591e-9f87-93347e0bdcb1",
                    definition: {
                        name: {
                            en: "A set of parameters that link an exercise/item to one or more reference models tagged using the fagkartkoder tool (see fagkart.no)",
                            nb: "Et sett med parametere som knytter en oppgave/item til en eller flere referansemodeller som er merket ved bruk av Fagkartkoderverktøyet (se fagkart.no)"
                        },
                        type: "https://w3id.org/xapi/avt/activity-types/fagkart_tag"
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
                        "description": {
                            "nb-NO": ""
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/feide-sp-id"
                    }
                }
            ]
        }
    }
}
```

<a name="3"></a>
#### 3. Learner reveals (reads) a hint to better understand what to answer
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
        "id": "https://w3id.org/xapi/adb/verbs/read",
        "display": {
            "en-US": "read",
            "nb-NO": "leste"
        }
    },
    "object": {
        "objectType": "Activity",
        "id": "http://www.lokus.no/open/nummer/Nummer-8/4-Tall-og-algebra/Kapitteltest#oppgave-6",
        "definition": {
            "name": {
                "nb-NO": "4 Tall og algebra: Oppgave 6"
            },
            "description": {
                "nb-NO": "Hvilke er ligninger?"
            },
            "type": "http://adlnet.gov/expapi/activities/cmi.interaction",
            "interactionType": "choice",
            "choices": [
                {
                    "id": "A",
                    "description": {
                        "nb-NO": "4 - 3 * (2 - x)"
                    }
                },
                {
                    "id": "B",
                    "description": {
                        "nb-NO": "1 = 5 - (8 - y)"
                    }
                },
                {
                    "id": "C",
                    "description": {
                        "nb-NO": "4 - 3 * (2 - x) = 1"
                    }
                },
                {
                    "id": "D",
                    "description": {
                        "nb-NO": "x = 5"
                    }
                }
            ],
            "correctResponsesPattern": [
                "B,C,D"
            ],
            "extensions": {
                "https://w3id.org/xapi/acrossX/extensions/supplemental-info": "I alle likninger finner du likhetstegnet (=)"
            }
        }
    },
    "result": {
        "duration": "PT2M40S"
    },
    "context": {
        "registration": "e28fa121-91e1-43c7-9192-d9d6546bd76e",
        "platform": "Lokus",
        "language": "nb-NO",
        "contextActivities": {
            "parent": [
                {
                    "objectType": "Activity",
                    "id": "http://www.lokus.no/open/nummer/Nummer-8/4-Tall-og-algebra/Kapitteltest",
                    "definition": {
                        "name": {
                            "nb-NO": "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus"
                        },
                        "type": "http://adlnet.gov/expapi/activities/assessment"
                    }
                }
            ],
            "grouping": [
                {
                    objectType: "Activity",
                    id: "https://fagkart.no/avt2/api/ontology/types/fagkart_tag/objects/cb8a4c86-9af7-5b54-9370-f750557e815e:4e425211-bf59-591e-9f87-93347e0bdcb1",
                    definition: {
                        name: {
                            en: "A set of parameters that link an exercise/item to one or more reference models tagged using the fagkartkoder tool (see fagkart.no)",
                            nb: "Et sett med parametere som knytter en oppgave/item til en eller flere referansemodeller som er merket ved bruk av Fagkartkoderverktøyet (se fagkart.no)"
                        },
                        type: "https://w3id.org/xapi/avt/activity-types/fagkart_tag"
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
                        "description": {
                            "nb-NO": ""
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/feide-sp-id"
                    }
                }
            ]
        }
    }
}
```

<a name="4"></a>
#### 4. Learner has answered a single question (with success, but after viewing a hint so 1 point will be deducted from the score) in "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus"
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
            "description": {
                "nb-NO": "Hvilke er ligninger?"
            },
            "type": "http://adlnet.gov/expapi/activities/cmi.interaction",
            "interactionType": "choice",
            "choices": [
                {
                    "id": "A",
                    "description": {
                        "nb-NO": "4 - 3 * (2 - x)"
                    }
                },
                {
                    "id": "B",
                    "description": {
                        "nb-NO": "1 = 5 - (8 - y)"
                    }
                },
                {
                    "id": "C",
                    "description": {
                        "nb-NO": "4 - 3 * (2 - x) = 1"
                    }
                },
                {
                    "id": "D",
                    "description": {
                        "nb-NO": "x = 5"
                    }
                }
            ],
            "correctResponsesPattern": [
                "B,C,D"
            ],
            "extensions": {
                "https://w3id.org/xapi/acrossX/extensions/supplemental-info": "I alle likninger finner du likhetstegnet (=)"
            }
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
        }
    },
    "context": {
        "registration": "e28fa121-91e1-43c7-9192-d9d6546bd76e",
        "platform": "Lokus",
        "language": "nb-NO",
        "contextActivities": {
            "parent": [
                {
                    "objectType": "Activity",
                    "id": "http://www.lokus.no/open/nummer/Nummer-8/4-Tall-og-algebra/Kapitteltest",
                    "definition": {
                        "name": {
                            "nb-NO": "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus"
                        },
                        "type": "http://adlnet.gov/expapi/activities/assessment"
                    }
                }
            ],
            "grouping": [
                {
                    objectType: "Activity",
                    id: "https://fagkart.no/avt2/api/ontology/types/fagkart_tag/objects/cb8a4c86-9af7-5b54-9370-f750557e815e:4e425211-bf59-591e-9f87-93347e0bdcb1",
                    definition: {
                        name: {
                            en: "A set of parameters that link an exercise/item to one or more reference models tagged using the fagkartkoder tool (see fagkart.no)",
                            nb: "Et sett med parametere som knytter en oppgave/item til en eller flere referansemodeller som er merket ved bruk av Fagkartkoderverktøyet (se fagkart.no)"
                        },
                        type: "https://w3id.org/xapi/avt/activity-types/fagkart_tag"
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
                        "description": {
                            "nb-NO": ""
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/feide-sp-id"
                    }
                }
            ]
        }
    }
}
```

<a name="5"></a>
#### 5. Learner has completed all questions in "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus”
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
        "id": "http://www.lokus.no/open/nummer/Nummer-8/4-Tall-og-algebra/Kapitteltest",
        "definition": {
            "name": {
                "nb-NO": "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus"
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
            "max": 18.0,
            "raw": 17.0,
            "scaled": 0.944
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
                  "id": "https://fagkart.no/avt2/api/ontology/types/fagkart_tag/objects/5ab58270-19ee-5a2b-bbf5-6c2989e4b849:d4571543-71b6-51f2-949d-d0ff4207d874",
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
                        "description": {
                            "nb-NO": ""
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/feide-sp-id"
                    }
                }
            ]
        }
    }
}
```
