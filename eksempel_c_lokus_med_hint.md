## Eksempel 3 - Kapitteltest i matematikk fra Lokus.no, med visning av hint

Merk: For å forenkle eksempelomfanget så er det kun én oppgave (nr 6) som er modellert, men kapitteltesten inneholder selvsagt mange flere oppgaver. Informasjonen i eksempelet er til illustrasjon. Derfor er det sikkert enkelte unøyaktigheter, eksempelvis ID og navn på Feide-tjenesten som faktisk benyttes. Dataporten-ID'en til "actor" tilhører testeleven "Kari Nordmann" ved en av Utdanningsetatens testskoler. AVT-prosjektet presiserer at linjen "name": "Kari Nordmann", i "actor"-objektet IKKE skal inkluderes i xAPI-statementet, kun Dataporten-ID.

xAPI statements i dette eksempelet er veldig likt Eksempel 1, men med unntak av at xAPI statement nr 3 i dette eksempelet viser at et hint har blitt avdekket.
Utsagnet er basert på "xAPI recipe / oppskrift" hentet fra https://wiki.visualcatch.org/en/assessment.html#readF

Forskjellen mellom xAPI statement nummer 2 og 3 er at nr 3 benytter verbet "leste / read" og at hint-teksten er lagt inn som en extension av "object", samt at "result" objektet kun inneholder et tidsstempel (duration) for når hintet ble avdekket, og inneholder ikke selve svaret.
xAPI statement nr 4 inneholder det samme som i nummer 2, men denne gang med riktige svar og inkluderer også hintet som er benyttet i en extension av "object".

NB: Vi må bli enige om hvilken IRI vi skal benytte for verbet "leste / read", verbet er definert i flere vokabularer (men ikke i ADL-vokabularet).

Vi har i dette eksempelet valgt å vise hele responsene, selv om store deler er identiske med hverandre.

Skjermdump av oppgaven (før hint vises):
![](bilder/Eksempel%203%20-%20Lokus%20kapitteltest%20oppgave%206.jpg)


Utsnitt av skjermbilde etter at hint er avdekket:
![](bilder/Eksempel%203%20-%20Hint.jpg)


### Eksempeler på respons

#### 1. Eleven har logget på "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus"
```json
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
                    "id": "https://clientadmin.dataporten-api.no/clients/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                    "definition": {
                        "name": {
                            "nb-NO": "Lokus"
                        },
                        "description": {
                            "nb-NO": ""
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/feide-clientinfo"
                    }
                }
            ]
        }
    }
}
```

#### 2. Eleven har svart feil på en oppgave i "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus"
```json
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
                    "id": "http://psi.udir.no/kl06/KM221",
                    "definition": {
                        "name": {
                            "nb-NO": "KM221"
                        },
                        "description": {
                            "nn-NO": "lage, løyse og forklare likningar knytte til praktiske situasjonar"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/competence-objective"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://fagkart.no/avt/area-within-the-map/OFK10230",
                    "definition": {
                        "name": {
                            "nb-NO": "Likninger"
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
                            "nb-NO": "Lokus"
                        },
                        "description": {
                            "nb-NO": ""
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/feide-clientinfo"
                    }
                }
            ]
        }
    }
}
```

#### 3. Eleven viser (leser) et hint for å lettere finne riktig svar

```json
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
                    "id": "http://psi.udir.no/kl06/KM221",
                    "definition": {
                        "name": {
                            "nb-NO": "KM221"
                        },
                        "description": {
                            "nn-NO": "lage, løyse og forklare likningar knytte til praktiske situasjonar"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/competence-objective"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://fagkart.no/avt/area-within-the-map/OFK10230",
                    "definition": {
                        "name": {
                            "nb-NO": "Likninger"
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
                            "nb-NO": "Lokus"
                        },
                        "description": {
                            "nb-NO": ""
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/feide-clientinfo"
                    }
                }
            ]
        }
    }
}
```

#### 4. Eleven svarer nå rett på "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus"
Responsen er nå identisk med 2., med unntak av "result"-delen
Denne har nå "success": true, men siden hun har brukt et hint for å svare er nå et poeng trukket fra ("score.raw": 2 i stedet for 3).
```json
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
                    "id": "http://psi.udir.no/kl06/KM221",
                    "definition": {
                        "name": {
                            "nb-NO": "KM221"
                        },
                        "description": {
                            "nn-NO": "lage, løyse og forklare likningar knytte til praktiske situasjonar"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/competence-objective"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://fagkart.no/avt/area-within-the-map/OFK10230",
                    "definition": {
                        "name": {
                            "nb-NO": "Likninger"
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
                            "nb-NO": "Lokus"
                        },
                        "description": {
                            "nb-NO": ""
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/feide-clientinfo"
                    }
                }
            ]
        }
    }
}
```

#### 5. Eleven har fullført alle oppgaver i "Kapitteltest / 4 Tall og algebra / Nummer 8 / Nummer - Lokus”
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
                    "id": "https://clientadmin.dataporten-api.no/clients/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                    "definition": {
                        "name": {
                            "nb-NO": "Lokus"
                        },
                        "description": {
                            "nb-NO": ""
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/feide-clientinfo"
                    }
                }
            ]
        }
    }
}
```
