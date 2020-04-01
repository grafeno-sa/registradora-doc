## Listar duplicatas

> Este é um exemplo do objeto retornado na resposta deste endpoint:

```json
{
    "data": [
        {
            "id": "5",
            "type": "assetTradeBill",
            "attributes": {
                "acquiredAt": "2020-03-16T04:13:38.000-03:00",
                "createdAt": "2020-03-22T22:10:02.556-03:00",
                "dueDate": "2020-03-24",
                "emittedAt": "2020-03-21T00:50:12.000-03:00",
                "kind": "goods",
                "state": "draft",
                "updatedAt": "2020-03-22T22:10:02.556-03:00",
                "value": "54.59",
                "assetCoverageNfe": {
                    "data": {
                        "id": "3",
                        "type": "assetCoverageNfe",
                        "attributes": {
                            "nfeAccessKey": "35200248477780000191550010000033561442834725"
                        }
                    }
                },
                "assetOperationParts": {
                    "data": [
                        {
                            "id": "7",
                            "type": "assetOperationPart",
                            "attributes": {
                                "role": "assignor",
                                "assetPartVariant": {
                                    "data": {
                                        "id": "7",
                                        "type": "assetPartVariant",
                                        "attributes": {
                                            "cityRegistrationNumber": "953k8mizk",
                                            "companyName": "de Sá, de Lara e Castelo",
                                            "contactRepresentativeKind": "contact",
                                            "contactRepresentativeName": "Marli Teixeira",
                                            "contactRepresentativeEmail": "lynwood_rosenbaum@zemlak.name",
                                            "contactRepresentativePhone": "(38) 99247-7565",
                                            "email": "evan_brown@darecormier.org",
                                            "name": "Norberto Veloso",
                                            "phoneNumber": "(33) 96202-8383",
                                            "stateRegistrationNumber": "ynn9rb",
                                            "address": {
                                                "data": {
                                                    "id": "25",
                                                    "type": "address",
                                                    "attributes": {
                                                        "city": "Limoeiro",
                                                        "complement": "Lote 41",
                                                        "number": "82196",
                                                        "neighborhood": "Paradise Square",
                                                        "state": "GO",
                                                        "street": "Rodovia Isadora Siqueiro",
                                                        "zipCode": "52540-655"
                                                    }
                                                }
                                            },
                                            "assetPart": {
                                                "data": {
                                                    "id": "8",
                                                    "type": "assetPart",
                                                    "attributes": {
                                                        "documentNumber": "00187107602"
                                                    }
                                                }
                                            }
                                        }
                                    }
                                }
                            }
                        },
                        {
                            "id": "8",
                            "type": "assetOperationPart",
                            "attributes": {
                                "role": "guarantor",
                                "assetPartVariant": {
                                    "data": {
                                        "id": "8",
                                        "type": "assetPartVariant",
                                        "attributes": {
                                            "cityRegistrationNumber": "kzvrq2lcp",
                                            "companyName": "Barros, Sanches e Geraldes",
                                            "contactRepresentativeKind": "contact",
                                            "contactRepresentativeName": "João Gabriel Monteira",
                                            "contactRepresentativeEmail": "darell@grimesmacgyver.io",
                                            "contactRepresentativePhone": "(85) 92014-4051",
                                            "email": "timmy@howeleffler.com",
                                            "name": "Ryan Vimaranes Jr.",
                                            "phoneNumber": "(62) 99116-0506",
                                            "stateRegistrationNumber": "00fz08",
                                            "address": {
                                                "data": {
                                                    "id": "26",
                                                    "type": "address",
                                                    "attributes": {
                                                        "city": "Rio Bananal",
                                                        "complement": "Apto. 168",
                                                        "number": "497",
                                                        "neighborhood": "Eagle Court",
                                                        "state": "RN",
                                                        "street": "Rodovia Arthur Guedes",
                                                        "zipCode": "21886-071"
                                                    }
                                                }
                                            },
                                            "assetPart": {
                                                "data": {
                                                    "id": "9",
                                                    "type": "assetPart",
                                                    "attributes": {
                                                        "documentNumber": "08752688542"
                                                    }
                                                }
                                            }
                                        }
                                    }
                                }
                            }
                        },
                        {
                            "id": "9",
                            "type": "assetOperationPart",
                            "attributes": {
                                "role": "payer",
                                "assetPartVariant": {
                                    "data": {
                                        "id": "9",
                                        "type": "assetPartVariant",
                                        "attributes": {
                                            "cityRegistrationNumber": "wz2tt8d4u",
                                            "companyName": "Bonfim-Roriz",
                                            "contactRepresentativeKind": "contact",
                                            "contactRepresentativeName": "Maya Mendes",
                                            "contactRepresentativeEmail": "von_crist@turnerjerde.net",
                                            "contactRepresentativePhone": "(99) 94857-5017",
                                            "email": "monique@cronadickinson.co",
                                            "name": "Ricardo Goulart",
                                            "phoneNumber": "(99) 91677-0397",
                                            "stateRegistrationNumber": "mfsfmh",
                                            "address": {
                                                "data": {
                                                    "id": "27",
                                                    "type": "address",
                                                    "attributes": {
                                                        "city": "São Tiago",
                                                        "complement": "Quadra 90",
                                                        "number": "810",
                                                        "neighborhood": "Eagle Crossing",
                                                        "state": "DF",
                                                        "street": "Viela Cauã",
                                                        "zipCode": "41192-548"
                                                    }
                                                }
                                            },
                                            "assetPart": {
                                                "data": {
                                                    "id": "10",
                                                    "type": "assetPart",
                                                    "attributes": {
                                                        "documentNumber": "07903828819"
                                                    }
                                                }
                                            }
                                        }
                                    }
                                }
                            }
                        }
                    ]
                }
            }
        }
    ]
}
```

Este endpoint lista todos os ativos do tipo duplicata vinculados ao seu cadastro na plataforma.

### HTTP Request

`GET /api/v1/assets/trade_bills`

### Query Parameters

Parâmetro | Default | Obrigatório? | Descrição
--------- | ------- | ------- | -----------
`p` | '' | não | Define os critérios de paginação do resultado da consulta. Consulte a seção [Paginação de resultados](#paginacao-de-resultados) para entender melhor como este parâmetro funciona.
`q` | '' | não | Define filtros de pesquisa que devem ser aplicados na consulta. Consulte a seção [Filtros de pesquisa](#filtros-de-pesquisa) para entender melhor como este parâmetro funciona.
`s` | '' | não | Define os critérios de ordenação do resultado da consulta. Consulte a seção [Ordenação de resultados](#ordenacao-de-resultados) para entender melhor como este parâmetro funciona.
