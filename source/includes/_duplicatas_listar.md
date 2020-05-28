## Listar duplicatas

> Este é um exemplo do objeto retornado na resposta deste endpoint:

```json
{
  "data": [
    {
      "id": "1",
      "type": "asset",
      "attributes": {
        "asset_register_id": 1,
        "asset_register_type": "AssetTradeBill",
        "created_at": "2020-05-28T18:56:05.082-03:00",
        "due_date": "2020-05-25T01:47:48.000-03:00",
        "emitted_at": "2020-05-23T23:49:27.000-03:00",
        "kind": "goods",
        "state": "rejected",
        "updated_at": "2020-05-28T18:56:05.469-03:00",
        "uuid": "7c5a4293-da34-4040-b349-9581ab9a961d",
        "value": "167270.35",
        "operations": [
          {
            "data": {
              "id": "1",
              "type": "operation",
              "attributes": {
                "acquired_at": "2020-05-25T16:50:31.000-03:00",
                "due_date": "2020-05-25T01:47:48.000-03:00",
                "acquisition_value": "99281.86",
                "paid_value": "489194.14",
                "value": "167270.35",
                "installments": [
                  {
                    "data": {
                      "id": "1",
                      "type": "installment",
                      "attributes": {
                        "acquisition_value": "44694.37",
                        "due_date": "2020-05-25T01:47:48.000-03:00",
                        "original_due_date": "2020-05-26T17:48:15.000-03:00",
                        "original_value": "72122.15",
                        "paid_value": "185486.81",
                        "value": "97516.71",
                        "payments": [
                          {
                            "data": {
                              "id": "1",
                              "type": "payment",
                              "attributes": {
                                "performed_at": "2020-05-27T23:31:48.000-03:00",
                                "value": "93020.51"
                              }
                            }
                          },
                          {
                            "data": {
                              "id": "2",
                              "type": "payment",
                              "attributes": {
                                "performed_at": "2020-05-22T01:10:19.000-03:00",
                                "value": "51311.61"
                              }
                            }
                          },
                          {
                            "data": {
                              "id": "3",
                              "type": "payment",
                              "attributes": {
                                "performed_at": "2020-05-23T04:19:50.000-03:00",
                                "value": "41154.69"
                              }
                            }
                          }
                        ]
                      }
                    }
                  },
                  {
                    "data": {
                      "id": "2",
                      "type": "installment",
                      "attributes": {
                        "acquisition_value": "24866.73",
                        "due_date": "2020-05-22T22:56:54.000-03:00",
                        "original_due_date": "2020-05-23T16:54:01.000-03:00",
                        "original_value": "54648.79",
                        "paid_value": "160293.38",
                        "value": "43188.95",
                        "payments": [
                          {
                            "data": {
                              "id": "4",
                              "type": "payment",
                              "attributes": {
                                "performed_at": "2020-05-26T05:51:44.000-03:00",
                                "value": "44673.15"
                              }
                            }
                          },
                          {
                            "data": {
                              "id": "5",
                              "type": "payment",
                              "attributes": {
                                "performed_at": "2020-05-25T23:37:32.000-03:00",
                                "value": "45419.69"
                              }
                            }
                          },
                          {
                            "data": {
                              "id": "6",
                              "type": "payment",
                              "attributes": {
                                "performed_at": "2020-05-27T09:07:16.000-03:00",
                                "value": "70200.54"
                              }
                            }
                          }
                        ]
                      }
                    }
                  },
                  {
                    "data": {
                      "id": "3",
                      "type": "installment",
                      "attributes": {
                        "acquisition_value": "29720.76",
                        "due_date": "2020-05-21T11:04:45.000-03:00",
                        "original_due_date": "2020-05-24T22:34:11.000-03:00",
                        "original_value": "96588.35",
                        "paid_value": "143413.95",
                        "value": "26564.69",
                        "payments": [
                          {
                            "data": {
                              "id": "7",
                              "type": "payment",
                              "attributes": {
                                "performed_at": "2020-05-25T23:28:51.000-03:00",
                                "value": "53370.73"
                              }
                            }
                          },
                          {
                            "data": {
                              "id": "8",
                              "type": "payment",
                              "attributes": {
                                "performed_at": "2020-05-24T22:09:28.000-03:00",
                                "value": "54196.28"
                              }
                            }
                          },
                          {
                            "data": {
                              "id": "9",
                              "type": "payment",
                              "attributes": {
                                "performed_at": "2020-05-26T10:03:08.000-03:00",
                                "value": "35846.94"
                              }
                            }
                          }
                        ]
                      }
                    }
                  }
                ],
                "operation_parts": [
                  {
                    "data": {
                      "id": "1",
                      "type": "operation_part",
                      "attributes": {
                        "document_number": "30601800000129",
                        "role": "assignor",
                        "part_variant": {
                          "data": {
                            "id": "1",
                            "type": "part_variant",
                            "attributes": {
                              "city_registration_number": "uvvmlxp8h",
                              "company_name": "Bomdia, Godins e Madeira",
                              "contact_representative_kind": "contact",
                              "contact_representative_name": "Eduarda Duarte",
                              "contact_representative_email": "woodrow@boscoklein.biz",
                              "contact_representative_phone": "(69) 95759-5198",
                              "document_number": "30601800000129",
                              "email": "elsie@schmitt.com",
                              "name": "Helena da Veiga",
                              "phone_number": "(61) 99721-6729",
                              "state_registration_number": "u90bxg",
                              "address": {
                                "data": {
                                  "id": "3",
                                  "type": "address",
                                  "attributes": {
                                    "city": "Brasnorte",
                                    "complement": "Casa 6",
                                    "number": "52493",
                                    "neighborhood": "Autumn Oaks",
                                    "state": "RR",
                                    "street": "Travessa João Samuel Dorneles",
                                    "zip_code": "44899-600"
                                  }
                                }
                              },
                              "part": {
                                "data": {
                                  "id": "1",
                                  "type": "part",
                                  "attributes": {
                                    "document_number": "30601800000129"
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  },
                  {
                    "data": {
                      "id": "2",
                      "type": "operation_part",
                      "attributes": {
                        "document_number": "52502608000118",
                        "role": "guarantor",
                        "part_variant": {
                          "data": {
                            "id": "2",
                            "type": "part_variant",
                            "attributes": {
                              "city_registration_number": "s83s3uvdp",
                              "company_name": "da Barra-Chaves",
                              "contact_representative_kind": "contact",
                              "contact_representative_name": "Dr. Elisa da Penha",
                              "contact_representative_email": "frederic@gerlach.com",
                              "contact_representative_phone": "(94) 98855-9067",
                              "document_number": "52502608000118",
                              "email": "rhett@feest.biz",
                              "name": "Dr. Arthur Rocha",
                              "phone_number": "(43) 95606-0774",
                              "state_registration_number": "r8hppx",
                              "address": {
                                "data": {
                                  "id": "4",
                                  "type": "address",
                                  "attributes": {
                                    "city": "Uruará",
                                    "complement": "Quadra 25",
                                    "number": "20215",
                                    "neighborhood": "Royal Gardens",
                                    "state": "AM",
                                    "street": "Rua Pedro",
                                    "zip_code": "93510-997"
                                  }
                                }
                              },
                              "part": {
                                "data": {
                                  "id": "2",
                                  "type": "part",
                                  "attributes": {
                                    "document_number": "52502608000118"
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  },
                  {
                    "data": {
                      "id": "3",
                      "type": "operation_part",
                      "attributes": {
                        "document_number": "40950656000190",
                        "role": "payer",
                        "part_variant": {
                          "data": {
                            "id": "3",
                            "type": "part_variant",
                            "attributes": {
                              "city_registration_number": "hj2kx2k78",
                              "company_name": "Cavalcanti LTDA",
                              "contact_representative_kind": "contact",
                              "contact_representative_name": "Sra. Theo Rios",
                              "contact_representative_email": "evan.mayert@pfannerstill.com",
                              "contact_representative_phone": "(68) 98580-4818",
                              "document_number": "40950656000190",
                              "email": "norberto_nienow@sauerwill.net",
                              "name": "Srta. Erick Ramos",
                              "phone_number": "(43) 99641-1928",
                              "state_registration_number": "ppu8x5",
                              "address": {
                                "data": {
                                  "id": "5",
                                  "type": "address",
                                  "attributes": {
                                    "city": "Mutuípe",
                                    "complement": "Apto. 927",
                                    "number": "s/n",
                                    "neighborhood": "Pine Creek",
                                    "state": "PA",
                                    "street": "Rua Giulia Diegues",
                                    "zip_code": "54178-684"
                                  }
                                }
                              },
                              "part": {
                                "data": {
                                  "id": "3",
                                  "type": "part",
                                  "attributes": {
                                    "document_number": "40950656000190"
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  },
                  {
                    "data": {
                      "id": "4",
                      "type": "operation_part",
                      "attributes": {
                        "document_number": "77482889000972",
                        "role": "creditor",
                        "part_variant": {
                          "data": {
                            "id": "4",
                            "type": "part_variant",
                            "attributes": {
                              "city_registration_number": "xrwryd1yu",
                              "company_name": "Souza-Ferraço",
                              "contact_representative_kind": "contact",
                              "contact_representative_name": "Nicolas da Rocha Neto",
                              "contact_representative_email": "kathrine.brown@kunzeruecker.io",
                              "contact_representative_phone": "(75) 98708-1402",
                              "document_number": "77482889000972",
                              "email": "georgiana@lowewilliamson.co",
                              "name": "Gúbio Carvalho",
                              "phone_number": "(44) 98652-0492",
                              "state_registration_number": "pbfdn8",
                              "address": {
                                "data": {
                                  "id": "6",
                                  "type": "address",
                                  "attributes": {
                                    "city": "Anamã",
                                    "complement": "Sobrado 68",
                                    "number": "3054",
                                    "neighborhood": "Royal Oaks",
                                    "state": "PA",
                                    "street": "Rua Esther",
                                    "zip_code": "71097-112"
                                  }
                                }
                              },
                              "part": {
                                "data": {
                                  "id": "4",
                                  "type": "part",
                                  "attributes": {
                                    "document_number": "77482889000972"
                                  }
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
        ],
        "coverage_registers": [
          {
            "data": {
              "id": "1",
              "type": "coverage_register",
              "attributes": {
                "state": "invalid",
                "state_invalid_reason": "assignor_document_mismatch",
                "coverage_item": {
                  "data": {
                    "id": "1",
                    "type": "coverage_register_nfe",
                    "attributes": {
                      "nfe_access_key": "35200248477780000191550010000033561442834725"
                    }
                  }
                }
              }
            }
          }
        ]
      }
    }
  ]
}
```

Este endpoint lista todos os ativos do tipo duplicata vinculados ao seu cadastro na plataforma.

### HTTP Request

`GET /api/v1/assets/trade_bills`

