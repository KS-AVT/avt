## Eksempel 2 - Fysikkoppgave på Viten.no

Merk: Informasjonen i eksempelet er til illustrasjon, og har blitt utarbeidet uten involvering fra viten.no (derfor er det sikkert enkelte unøyaktigheter, eksempelvis (URI) på object).

Skjermdump av oppgaven:
![](bilder/Eksempel%202%20-%20Viten%20-%20Fysikk%201%20-%20Bevegelse%20-%20Fritt%20fall-regn%20ut%20-%20A.jpg)

### Oversikt over xAPI-statements for eksempel 2 (fysikkoppgave fra Viten.no)

Nr.|Comment|Who (actor)|Did (verb)|What (object)|
---------|------------------|-------|---------|------|
|[1](#1)|An LMS is conforming to the cmi5 xAPI spec and a learner has launched an assignable unit at viten.no|Kari Nordmann|igangsatte|Viten.no > Oppgaver for Fysikk 1 > Bevegelse > Fritt fall - regn ut > A|
|[2](#2)|Viten.no has received the request and has initialized in the learner’s web browser (there always must be an initialization statement and a termination statement when using cmi5)|Kari Nordmann|startet|Viten.no > Oppgaver for Fysikk 1 > Bevegelse > Fritt fall - regn ut > A|
|[3](#3)|The learner noticed the instructional simulation and clicked play|Kari Nordmann|startet (verb er ikke fra ADL)|Fallende rød ball (oppgave A)|
|4|The learner clicked to pause the instructional simulation|Kari Nordmann|pauset|Fallende rød ball (oppgave A)|
|5|The learner clicked play again to see the full simulation|Kari Nordmann|spolte tilbake|Fallende rød ball (oppgave A)|
|6|The learner clicked play again to see the full simulation|Kari Nordmann|startet|Fallende rød ball (oppgave A)|
|[7](#7)|The learner guessed a wrong answer, perhaps due to a misconception|Kari Nordmann|besvarte|Viten.no > Oppgaver for Fysikk 1 > Bevegelse > Fritt fall - regn ut > A|
|8|The learner answered correctly|Kari Nordmann|besvarte|Viten.no > Oppgaver for Fysikk 1 > Bevegelse > Fritt fall - regn ut > A|
|9|The learner has passed this assignable unit|Kari Nordmann|besto|Viten.no > Oppgaver for Fysikk 1 > Bevegelse > Fritt fall - regn ut > A|
|10|The learner has completed this assignable unit (actually both passed and completed is not required in the cmi5 specification)|Kari Nordmann|fullførte|Viten.no > Oppgaver for Fysikk 1 > Bevegelse > Fritt fall - regn ut > A|
|11|The learner terminated the learning tool (there always must be an initialization statement and a termination statement when using cmi5)|Kari Nordmann|avsluttet|Viten.no > Oppgaver for Fysikk 1 > Bevegelse > Fritt fall - regn ut > A|
|12|The LMS reports that the learner now has satisfied all assignable units in the whole course related to "Oppgaver for Fysikk 1"|Kari Nordmann|tilfredsstilte|Viten.no > Oppgaver for Fysikk 1 > Bevegelse|

#### Eksempel på kall

```javascript
Hent Statements - bruker
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}

Hent Statements - bruker AND kompetansemål
GET ~/statements?agent={"account":{"name":"76a7a061-3c55-430d-8ee0-6f82ec42501f","homePage":"https://docs.dataporten.no"}}&activity=http://data.udir.no/kl06/K10695&related_activities=true
```

#### Eksempel på respons

<a name="1"></a>
#### 1. An LMS is conforming to the cmi5 xAPI spec and a learner has launched an assignable unit at viten.no
``` Javascript
{
    "id": "f73a639e-2a27-4981-a6b9-9fc134b49d8a",
    "timestamp": "2017-08-29T09:00:00Z",
    "actor": {
        "objectType": "Agent",
        "name": "Kari Nordmann",
        "account": {
            "homePage": "https://docs.dataporten.no",
            "name": "76a7a061-3c55-430d-8ee0-6f82ec42501f"
        }
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/launched",
        "display": {
            "en-US": "launched",
            "nb-NO": "igangsatte"
        }
    },
    "object": {
        "objectType": "Activity",
        "id": "http://www.viten.no/vitenprogram/vis.html?prgid=uuid%3A503EE615-769C-7189-33A4-000076D6E3B1&tid=1653861&grp=#FrittFallRegnUt-A",
        "definition": {
            "name": {
                "nb-NO": "Viten.no > Oppgaver for Fysikk 1 > Bevegelse > Fritt fall - regn ut > A"
            },
            "type": "http://id.tincanapi.com/activitytype/school-assignment"
        }
    },
    "context": {
        "registration": "67c7d43a-7304-4a0a-b09b-21ddfd3e2b1c",
        "platform": "Skolens LMS? ",
        "language": "nb-NO",
        "contextActivities": {
            "grouping": [
                {
                    "objectType": "Activity",
                    "id": "http://data.udir.no/kl06/K10707",
                    "definition": {
                        "name": {
                            "nb-NO": "K10707"
                        },
                        "description": {
                            "nb-NO": "bruke parameterframstilling til å beskrive rettlinjet bevegelse for en partikkel, og bruke derivasjon til å regne ut fart og akselerasjon når posisjonen er kjent, både med og uten digitale verktøy"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/competence-objective"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "http://data.udir.no/kl06/K10695",
                    "definition": {
                        "name": {
                            "nb-NO": "K10695"
                        },
                        "description": {
                            "nb-NO": "identifisere kontaktkrefter og gravitasjonskrefter som virker på legemer, tegne kraftvektorer og bruke Newtons tre lover"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/competence-objective"
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
                    "id": "https://api.feide.no/2/sp/456",
                    "definition": {
                        "name": {
                            "nb-NO": "Skolens LMS?"
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
#### 2. Viten.no has received the request and has initialized in the learner’s web browser (there always must be an initialization statement and a termination statement when using cmi5)
``` Javascript
{
    "id": "4aefa863-1167-41c6-a9be-e646f2c9bb2f",
    "timestamp": "2017-08-29T09:00:01Z",
    "actor": {
        "objectType": "Agent",
        "name": "Kari Nordmann",
        "account": {
            "homePage": "https://docs.dataporten.no",
            "name": "76a7a061-3c55-430d-8ee0-6f82ec42501f"
        }
    },
    "verb": {
        "id": "http://adlnet.gov/expapi/verbs/initialized",
        "display": {
            "en-US": "initialized",
            "nb-NO": "startet"
        }
    },
    "object": {
        "objectType": "Activity",
        "id": "http://www.viten.no/vitenprogram/vis.html?prgid=uuid%3A503EE615-769C-7189-33A4-000076D6E3B1&tid=1653861&grp=#FrittFallRegnUt-A",
        "definition": {
            "name": {
                "nb-NO": "Viten.no > Oppgaver for Fysikk 1 > Bevegelse > Fritt fall - regn ut > A"
            },
            "type": "http://adlnet.gov/expapi/activities/assessment"
        }
    },
    "context": {
        "registration": "67c7d43a-7304-4a0a-b09b-21ddfd3e2b1c",
        "platform": "Viten.no",
        "language": "nb-NO",
        "contextActivities": {
            "grouping": [
                {
                    "objectType": "Activity",
                    "id": "http://data.udir.no/kl06/K10707",
                    "definition": {
                        "name": {
                            "nb-NO": "K10707"
                        },
                        "description": {
                            "nb-NO": "bruke parameterframstilling til å beskrive rettlinjet bevegelse for en partikkel, og bruke derivasjon til å regne ut fart og akselerasjon når posisjonen er kjent, både med og uten digitale verktøy"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/competence-objective"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "http://data.udir.no/kl06/K10695",
                    "definition": {
                        "name": {
                            "nb-NO": "K10695"
                        },
                        "description": {
                            "nb-NO": "identifisere kontaktkrefter og gravitasjonskrefter som virker på legemer, tegne kraftvektorer og bruke Newtons tre lover"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/competence-objective"
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
                    "id": "https://api.feide.no/2/sp/96534",
                    "definition": {
                        "name": {
                            "nb-NO": "viten.no"
                        },
                        "description": {
                            "nb-NO": "viten.no tilbyr gratis nettbaserte læringsressurser i naturfag - de fleste for ungdomstrinn og videregående skole"
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
#### 3. The learner noticed the instructional simulation and clicked play
``` Javascript
{
    "id": "a50d8993-318a-4649-b928-c8780480796d",
    "timestamp": "2017-08-29T09:00:10Z",
    "actor": {
        "objectType": "Agent",
        "name": "Kari Nordmann",
        "account": {
            "homePage": "https://docs.dataporten.no",
            "name": "76a7a061-3c55-430d-8ee0-6f82ec42501f"
        }
    },
    "verb": {
        "id": "https://w3id.org/xapi/video/started",
        "display": {
            "en-US": "started",
            "nb-NO": "startet"
        }
    },
    "object": {
        "objectType": "Activity",
        "id": "http://www.viten.no/vitenprogram/vis.html?prgid=uuid%3A503EE615-769C-7189-33A4-000076D6E3B1&tid=1653861&grp=#simulationvideo1",
        "definition": {
            "name": {
                "nb-NO": "Fallende rød ball (oppgave A)"
            },
            "type": "http://adlnet.gov/expapi/activities/media"
        }
    },
    "context": {
        "registration": "67c7d43a-7304-4a0a-b09b-21ddfd3e2b1c",
        "platform": "Viten.no",
        "language": "nb-NO",
        "contextActivities": {
            "grouping": [
                {
                    "objectType": "Activity",
                    "id": "http://data.udir.no/kl06/K10707",
                    "definition": {
                        "name": {
                            "nb-NO": "K10707"
                        },
                        "description": {
                            "nb-NO": "bruke parameterframstilling til å beskrive rettlinjet bevegelse for en partikkel, og bruke derivasjon til å regne ut fart og akselerasjon når posisjonen er kjent, både med og uten digitale verktøy"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/competence-objective"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "http://data.udir.no/kl06/K10695",
                    "definition": {
                        "name": {
                            "nb-NO": "K10695"
                        },
                        "description": {
                            "nb-NO": "identifisere kontaktkrefter og gravitasjonskrefter som virker på legemer, tegne kraftvektorer og bruke Newtons tre lover"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/competence-objective"
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
                    "id": "https://api.feide.no/2/sp/96534",
                    "definition": {
                        "name": {
                            "nb-NO": "viten.no"
                        },
                        "description": {
                            "nb-NO": "viten.no tilbyr gratis nettbaserte læringsressurser i naturfag - de fleste for ungdomstrinn og videregående skole"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/application"
                    }
                }
            ]
        }
    }
}
```

<a name="7"></a>
#### 7. The learner guessed a wrong answer, perhaps due to a misconception
``` Javascript
{
    "id": "ead650c5-aa20-470d-b0a7-f35b6eef5fe6",
    "timestamp": "2017-08-29T09:01:00Z",
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
        "id": "http://www.viten.no/vitenprogram/vis.html?prgid=uuid%3A503EE615-769C-7189-33A4-000076D6E3B1&tid=1653861&grp=#FrittFallRegnUt-A",
        "definition": {
            "name": {
                "nb-NO": "Viten.no > Oppgaver for Fysikk 1 > Bevegelse > Fritt fall - regn ut > A"
            },
            "description": {
                "nb-NO": "Den røde steinen trilles utfor stupet og faller rett ned (g = 9,8 m/s^2). Klokka starter når steinen begynner å falle. Finn farten til steinen i det den treffer vannet. Skriv svaret med tre gjeldende siffer."
            },
            "type": "http://adlnet.gov/expapi/activities/cmi.interaction",
            "interactionType": "numeric",
            "correctResponsesPattern": [
                "108"
            ]
        }
    },
    "result": {
        "duration": "PT2M4S",
        "response": "9,8",
        "success": false,
        "score": {
            "min": 0.0,
            "max": 3.0,
            "raw": 0.0,
            "scaled": 0.0
        }
    },
    "context": {
        "registration": "67c7d43a-7304-4a0a-b09b-21ddfd3e2b1c",
        "platform": "Viten.no",
        "language": "nb-NO",
        "contextActivities": {
            "grouping": [
                {
                    "objectType": "Activity",
                    "id": "http://data.udir.no/kl06/K10707",
                    "definition": {
                        "name": {
                            "nb-NO": "K10707"
                        },
                        "description": {
                            "nb-NO": "bruke parameterframstilling til å beskrive rettlinjet bevegelse for en partikkel, og bruke derivasjon til å regne ut fart og akselerasjon når posisjonen er kjent, både med og uten digitale verktøy"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/competence-objective"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "http://data.udir.no/kl06/K10695",
                    "definition": {
                        "name": {
                            "nb-NO": "K10695"
                        },
                        "description": {
                            "nb-NO": "identifisere kontaktkrefter og gravitasjonskrefter som virker på legemer, tegne kraftvektorer og bruke Newtons tre lover"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/competence-objective"
                    }
                },
                {
                    "objectType": "Activity",
                    "id": "https://lmbase.no/xapi/avt/frameworks/area-within-the-map/OFKnnnnnn",
                    "definition": {
                        "name": {
                            "nb-NO": "OFKnnnnnn"
                        },
                        "description": {
                            "nb-NO": "misoppfatning om at hastighet i vakum er eksakt lik gravitasjonskraften"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/area-within-the-map"
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
                    "id": "https://api.feide.no/2/sp/96534",
                    "definition": {
                        "name": {
                            "nb-NO": "viten.no"
                        },
                        "description": {
                            "nb-NO": "viten.no tilbyr gratis nettbaserte læringsressurser i naturfag - de fleste for ungdomstrinn og videregående skole"
                        },
                        "type": "https://w3id.org/xapi/avt/activity-types/application"
                    }
                }
            ]
        }
    }
}
```
