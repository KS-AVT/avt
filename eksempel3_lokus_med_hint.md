## Eksempel 3 - Kapitteltest i matematikk fra Lokus.no, med visning av hint

Merk: For å forenkle eksempelomfanget så er det kun én oppgave (nr 6) som er modellert, men kapitteltesten inneholder selvsagt mange flere oppgaver. Informasjonen i eksempelet er til illustrasjon. Derfor er det sikkert enkelte unøyaktigheter, eksempelvis ID og navn på Feide-tjenesten som faktisk benyttes. Dataporten-ID'en til "actor" tilhører testeleven "Kari Nordmann" ved en av Utdanningsetatens testskoler. AVT-prosjektet presiserer at linjen "name": "Kari Nordmann", i "actor"-objektet IKKE skal inkluderes i xAPI-statementet, kun Dataporten-ID.

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

```javascript
Hent Statements - bruker
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}

Hent Statements - bruker AND kompetansemål
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}&activity=http://data.udir.no/kl06/K15170&related_activities=true

Hent Statements - bruker AND kompetansemål AND vanskegrad
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}&activity=http://data.udir.no/kl06/K15170&activity=https://lmbase.no/xapi/avt/frameworks/pisa/mathematical-literacy/competence-level-2&related_activities=true

Hent Statements - bruker AND fagkart
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}&activity=https://lmbase.no/xapi/avt/frameworks/area-within-the-map/OFK100001&related_activities=true

Hent Statements - bruker AND fagkart AND vanskegrad
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}&activity=https://lmbase.no/xapi/avt/frameworks/area-within-the-map/OFK100001&activity=https://lmbase.no/xapi/avt/frameworks/pisa/mathematical-literacy/competence-level-2&related_activities=true
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
                        "type": "https://w3id.org/xapi/avt/activity-types/application"
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
                        "type": "https://w3id.org/xapi/avt/activity-types/competence-objective"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://lmbase.no/xapi/avt/frameworks/area-within-the-map/OFKnnnnnn",
                    "definition": {
                        "name": {
                            "nb-NO": "Desimaltallsaddisjon med overgang"
                        },
                        "description": {
                            "nb-NO": "Ett eller flere av leddene i addisjonen har desimaltall og utregningen inneholder en eller flere tier-overganger"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/area-within-the-map"
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
                    "id": "https://api.feide.no/2/sp/18554999",
                    "definition": {
                        "name": {
                            "nb-NO": "Lokus"
                        },
                        "description": {
                            "nb-NO": ""
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
                        "type": "https://w3id.org/xapi/avt/activity-types/competence-objective"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://lmbase.no/xapi/avt/frameworks/area-within-the-map/OFKnnnnnn",
                    "definition": {
                        "name": {
                            "nb-NO": "Desimaltallsaddisjon med overgang"
                        },
                        "description": {
                            "nb-NO": "Ett eller flere av leddene i addisjonen har desimaltall og utregningen inneholder en eller flere tier-overganger"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/area-within-the-map"
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
                    "id": "https://api.feide.no/2/sp/18554999",
                    "definition": {
                        "name": {
                            "nb-NO": "Lokus"
                        },
                        "description": {
                            "nb-NO": ""
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
                        "type": "https://w3id.org/xapi/avt/activity-types/competence-objective"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://lmbase.no/xapi/avt/frameworks/area-within-the-map/OFKnnnnnn",
                    "definition": {
                        "name": {
                            "nb-NO": "Desimaltallsaddisjon med overgang"
                        },
                        "description": {
                            "nb-NO": "Ett eller flere av leddene i addisjonen har desimaltall og utregningen inneholder en eller flere tier-overganger"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/area-within-the-map"
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
                    "id": "https://api.feide.no/2/sp/18554999",
                    "definition": {
                        "name": {
                            "nb-NO": "Lokus"
                        },
                        "description": {
                            "nb-NO": ""
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/application"
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
        "id": "http://www.lokus.no/open/nummer/Nummer-8/4-Tall-og-algebra/Kapitteltest#oppgave-6",
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
                        "type": "https://w3id.org/xapi/avt/activity-types/application"
                    }
                }
            ]
        }
    }
}
```
