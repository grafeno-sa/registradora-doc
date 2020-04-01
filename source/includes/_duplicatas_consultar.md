## Consultar duplicata

> Este é um exemplo do objeto retornado na resposta deste endpoint:

```json
{
  "data": {
    "id": "2",
    "type": "assetTradeBill",
    "attributes": {
      "acquiredAt": "2020-03-26T13:00:41.000-03:00",
      "createdAt": "2020-04-01T11:52:27.192-03:00",
      "dueDate": "2020-04-06",
      "emittedAt": "2020-03-27T12:33:58.000-03:00",
      "kind": "goods",
      "state": "draft",
      "updatedAt": "2020-04-01T11:52:27.192-03:00",
      "value": "98.45",
      "assetCoverageNfe": {
        "data": {
          "id": "2",
          "type": "assetCoverageNfe",
          "attributes": {
            "nfeAccessKey": "35200248477780000191550010000033561442834725"
          }
        }
      },
      "assetOperationParts": {
        "data": [
          {
            "id": "4",
            "type": "assetOperationPart",
            "attributes": {
              "role": "assignor",
              "assetPartVariant": {
                "data": {
                  "id": "4",
                  "type": "assetPartVariant",
                  "attributes": {
                    "cityRegistrationNumber": "k3ws8ih8k",
                    "companyName": "Coqueiro, Álvares e Paiva",
                    "contactRepresentativeKind": "contact",
                    "contactRepresentativeName": "Víctor Guedes Jr.",
                    "contactRepresentativeEmail": "willow@macgyver.com",
                    "contactRepresentativePhone": "(34) 92289-1937",
                    "email": "lashaun_bogisich@moore.net",
                    "name": "Pedro da Veiga",
                    "phoneNumber": "(53) 92053-2427",
                    "stateRegistrationNumber": "84xae7",
                    "address": {
                      "data": {
                        "id": "7",
                        "type": "address",
                        "attributes": {
                          "city": "Ibitirama",
                          "complement": "Lote 54",
                          "number": "623",
                          "neighborhood": "Royal Creek",
                          "state": "MT",
                          "street": "Viela Leonardo da Barra",
                          "zipCode": "30625-581"
                        }
                      }
                    },
                    "assetPart": {
                      "data": {
                        "id": "4",
                        "type": "assetPart",
                        "attributes": {
                          "documentNumber": "08459883361"
                        }
                      }
                    }
                  }
                }
              }
            }
          },
          {
            "id": "5",
            "type": "assetOperationPart",
            "attributes": {
              "role": "guarantor",
              "assetPartVariant": {
                "data": {
                  "id": "5",
                  "type": "assetPartVariant",
                  "attributes": {
                    "cityRegistrationNumber": "myvcfce39",
                    "companyName": "Veles-Melo",
                    "contactRepresentativeKind": "contact",
                    "contactRepresentativeName": "Ana Laura Fernandes",
                    "contactRepresentativeEmail": "casie@walter.io",
                    "contactRepresentativePhone": "(19) 90416-8347",
                    "email": "nickolas@bauch.org",
                    "name": "Maria Sophia Araújo",
                    "phoneNumber": "(41) 91309-3038",
                    "stateRegistrationNumber": "uixb6b",
                    "address": {
                      "data": {
                        "id": "8",
                        "type": "address",
                        "attributes": {
                          "city": "Mucugê",
                          "complement": "Casa 2",
                          "number": "696",
                          "neighborhood": "Park Oaks",
                          "state": "RR",
                          "street": "Viela Nathan Ferreira",
                          "zipCode": "12566-627"
                        }
                      }
                    },
                    "assetPart": {
                      "data": {
                        "id": "5",
                        "type": "assetPart",
                        "attributes": {
                          "documentNumber": "07781191900"
                        }
                      }
                    }
                  }
                }
              }
            }
          },
          {
            "id": "6",
            "type": "assetOperationPart",
            "attributes": {
              "role": "payer",
              "assetPartVariant": {
                "data": {
                  "id": "6",
                  "type": "assetPartVariant",
                  "attributes": {
                    "cityRegistrationNumber": "hoz2x0s8g",
                    "companyName": "Neves, Moreno e Arriaga",
                    "contactRepresentativeKind": "contact",
                    "contactRepresentativeName": "Luiz Gustavo Barros",
                    "contactRepresentativeEmail": "judy_cummings@lind.com",
                    "contactRepresentativePhone": "(49) 98845-6675",
                    "email": "adaline_marks@wiegand.io",
                    "name": "Eloah Almeida",
                    "phoneNumber": "(84) 90249-0713",
                    "stateRegistrationNumber": "wz73gd",
                    "address": {
                      "data": {
                        "id": "9",
                        "type": "address",
                        "attributes": {
                          "city": "Areias",
                          "complement": "Sobrado 68",
                          "number": "4657",
                          "neighborhood": "Paradise Pointe",
                          "state": "SP",
                          "street": "Ponte Valentina",
                          "zipCode": "01225-088"
                        }
                      }
                    },
                    "assetPart": {
                      "data": {
                        "id": "6",
                        "type": "assetPart",
                        "attributes": {
                          "documentNumber": "02670411878"
                        }
                      }
                    }
                  }
                }
              }
            }
          },
          {
            "id": "7",
            "type": "assetOperationPart",
            "attributes": {
              "role": "creditor",
              "assetPartVariant": {
                "data": {
                  "id": "7",
                  "type": "assetPartVariant",
                  "attributes": {
                    "cityRegistrationNumber": "a7y3yf7td",
                    "companyName": "Camacho e Associados",
                    "contactRepresentativeKind": "contact",
                    "contactRepresentativeName": "Sr. Fabiano Simão",
                    "contactRepresentativeEmail": "nelda@rice.org",
                    "contactRepresentativePhone": "(64) 93109-5973",
                    "email": "jaunita@cummerata.co",
                    "name": "Salvador da Bandeira",
                    "phoneNumber": "(53) 95554-0357",
                    "stateRegistrationNumber": "n8e96u",
                    "address": {
                      "data": {
                        "id": "10",
                        "type": "address",
                        "attributes": {
                          "city": "Santa Rosa de Lima",
                          "complement": "Sobrado 18",
                          "number": "s/n",
                          "neighborhood": "Pine Pointe",
                          "state": "MS",
                          "street": "Rua João Victor Castanheira",
                          "zipCode": "33775-295"
                        }
                      }
                    },
                    "assetPart": {
                      "data": {
                        "id": "7",
                        "type": "assetPart",
                        "attributes": {
                          "documentNumber": "02851562509"
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
}
```
Este endpoint retorna as informações de um ativo específico do tipo duplicata vinculado ao seu cadastro na plataforma.

### HTTP Request

`GET /api/v1/assets/trade_bills/<id>`

### URL Parameters

Parâmetro | Obrigatório? | Descrição
--------- | ----------- | -----------
`id` | sim | Identificador do ativo do tipo duplicata registrado na plataforma
