---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - json

includes:
  - errors

search: true
---

# Introdução

Seja bem-vindo(a) à documentação de referência da Registradora API! Nesta página você encontrará de forma detalhada os passos necessários para se autenticar na nossa API e utilizar os diversos endpoints disponíveis. 

Na barra lateral do lado esquerdo, você poderá encontrar o índice da documentação e uma caixa de pesquisa. Utilize-os para navegar pelas seções deste documento e para encontrar alguma informação específica.

Já na barra lateral do lado direito, é o lugar onde exibimos códigos de exemplo que você pode utilizar para testar a nossa API. Você pode selecionar em qual linguagem de programação os exemplos serão exibidos através do menu de seleção na parte superior.  

# Autenticação

> Este é um exemplo do cabeçalho de uma requisição contendo o token de autenticação do usuário:

```json
{
  "Authorization": "27cc4835-53e9-4dcc-a064-d6609549f9ea.QHrAqIvp4M8dxWmmQZ1h3P85Vww"
}
```

> Não se esqueça de substituir o valor do exemplo pelo seu token.

A Registradora utiliza tokens de autenticação para permitir o acesso de usuários cadastrados à API. Você pode gerar um novo token de autenticação através do nosso [portal](http://example.com/developers).

Após obter o seu token, basta incluí-lo no cabeçalho das requisições feitas à API para que seu acesso possa ser autorizado dentro do servidor. Consulte o formato do cabeçalho no painel de exemplo.

![Gerando um token pelo portal](images/autenticacao/gerar-token.gif)

# Duplicatas

## Cadastrar duplicata

> Este é um exemplo do objeto que deve ser passado no corpo da requisição:

```json
{
  "asset_trade_bill": {
    "acquired_at": "2020-03-15 17:20:35 -0300",
    "due_date": "2020-03-24",
    "emitted_at": "2020-03-19 08:27:03 -0300",
    "state": "draft",
    "value": "92.32",
    "kind": "goods",
    "assignor_attributes": {
      "address_attributes": {
        "city": "Piritiba",
        "complement": "Lote 50",
        "number": "7665",
        "neighborhood": "University Square",
        "state": "PR",
        "street": "Rua Thomas",
        "zip_code": "78596-060"
      },
      "asset_part_variant_attributes": {
        "city_registration_number": "9xbrf7ec0",
        "company_name": "Muniz-Bernardes",
        "contact_representative_kind": "contact",
        "contact_representative_name": "Talita Bernardes",
        "contact_representative_email": "chase.hills@dach.com",
        "contact_representative_phone": "(93) 91943-3443",
        "email": "johana.rogahn@graham.org",
        "name": "Rafaela Ouriques",
        "phone_number": "(34) 96506-3625",
        "state_registration_number": "4hceb2"
      },
      "document_number": "01054635668"
    },
    "guarantor_attributes": {
      "address_attributes": {
        "city": "Alto Rio Novo",
        "complement": "Quadra 33",
        "number": "121",
        "neighborhood": "Royal Court",
        "state": "ES",
        "street": "Viela Davi Cardoso",
        "zip_code": "51877-246"
      },
      "asset_part_variant_attributes": {
        "city_registration_number": "4r8batjlo",
        "company_name": "da Rosa-Simão",
        "contact_representative_kind": "contact",
        "contact_representative_name": "Gabriela Garcês",
        "contact_representative_email": "jack@ebertlueilwitz.com",
        "contact_representative_phone": "(47) 95106-2579",
        "email": "tonie_funk@terrywolff.name",
        "name": "Antonella Henriques",
        "phone_number": "(95) 92094-0120",
        "state_registration_number": "nsee1i"
      },
      "document_number": "02266451936"
    },
    "payer_attributes": {
      "address_attributes": {
        "city": "Santo Antônio do Içá",
        "complement": "Lote 24",
        "number": "s/n",
        "neighborhood": "Pine Place",
        "state": "MA",
        "street": "Rua João Gabriel",
        "zip_code": "50094-815"
      },
      "asset_part_variant_attributes": {
        "city_registration_number": "xfc9bwxu2",
        "company_name": "da Conceição, da Cunha e Amoreira",
        "contact_representative_kind": "contact",
        "contact_representative_name": "Lara Rodrigues",
        "contact_representative_email": "madeleine@daughertycrona.net",
        "contact_representative_phone": "(44) 97906-5743",
        "email": "melda_kuvalis@coleruecker.name",
        "name": "Luiz Henrique Brum Neto",
        "phone_number": "(86) 99680-0484",
        "state_registration_number": "n4o01n"
      },
      "document_number": "05713216152"
    },
    "asset_coverage_nfe_attributes": {
      "nfe_access_key": "35200248477780000191550010000033561442834725"
    }
  }
}
```

Este endpoint realiza o cadastro de um novo ativo do tipo duplicata na plataforma.

### HTTP Request

`POST /api/v1/assets/trade_bills`

### Request Parameters

A seguir apresentamos a definição dos parâmetros aceitos por este endpoint. O objeto JSON enviado na requisição deve possuir uma chave raiz chamada `asset_trade_bill` e todos os outros parâmetros devem estar contidos dentro desta chave.

### asset_trade_bill

Parâmetro | Tipo | Obrigatório? | Descrição
--------- | --------- | --------- | -----------
`acquired_at` | `datetime` | sim | Data e hora de aquisição do ativo.
`due_date` | `date` | sim | Data de vencimento do ativo.
`emitted_at` | `datetime` | sim | Data e hora de emissão do ativo.
`state` | `string` | sim | Situação atual do cadastro do ativo na plataforma. Consulte a seção [Status de duplicatas](#status-de-duplicatas) para a lista completa dos status possíveis. 
`value` | `decimal` | sim | Valor do ativo. 
`value` | `decimal` | sim | Valor, em dinheiro, do ativo. 
`kind` | `string` | sim | Tipo do ativo. 
`assignor_attributes` | `object` | sim | Dados do cedente do ativo. Consulte a seção [assignor_attributes](#assignor_attributes) para a relação completa dos parâmetros.
`guarantor_attributes` | `object` | não | Dados do avalista do ativo. Consulte a seção [guarantor_attributes](#guarantor_attributes) para a relação completa dos parâmetros. 
`payer_attributes` | `object` | sim | Dados do sacado do ativo. Consulte a seção [payer_attributes](#payer_attributes) para a relação completa dos parâmetros.
`asset_coverage_nfe_attributes` | `object` | sim | Dados da nota fiscal do ativo. Consulte a seção [asset_coverage_nfe_attributes](#asset_coverage_nfe_attributes) para a relação completa dos parâmetros.

### assignor_attributes

Parâmetro | Tipo | Obrigatório? | Descrição
--------- | --------- | --------- | -----------
`document_number` | `string` | sim | Número do documento do cedente, sem pontuação.
`address_attributes` | `object` | sim | Dados do endereço do cedente. Consulte a seção [address_attributes](#address_attributes) para a relação completa dos parâmetros.
`asset_part_variant_attributes` | `object` | sim | Dados do gerais sobre o cedente. Consulte a seção [asset_part_variant_attributes](#asset_part_variant_attributes) para a relação completa dos parâmetros.

### guarantor_attributes

Parâmetro | Tipo | Obrigatório? | Descrição
--------- | --------- | --------- | -----------
`document_number` | `string` | sim | Número do documento do avalista, sem pontuação.
`address_attributes` | `object` | sim | Dados do endereço do avalista. Consulte a seção [address_attributes](#address_attributes) para a relação completa dos parâmetros.
`asset_part_variant_attributes` | `object` | sim | Dados do gerais sobre o avalista. Consulte a seção [asset_part_variant_attributes](#asset_part_variant_attributes) para a relação completa dos parâmetros.

### payer_attributes

Parâmetro | Tipo | Obrigatório? | Descrição
--------- | --------- | --------- | -----------
`document_number` | `string` | sim | Número do documento do sacado, sem pontuação.
`address_attributes` | `object` | sim | Dados do endereço do sacado. Consulte a seção [address_attributes](#address_attributes) para a relação completa dos parâmetros.
`asset_part_variant_attributes` | `object` | sim | Dados do gerais sobre o sacado. Consulte a seção [asset_part_variant_attributes](#asset_part_variant_attributes) para a relação completa dos parâmetros.

### address_attributes

Parâmetro | Tipo | Obrigatório? | Descrição
--------- | --------- | --------- | -----------
`city` | `string` | sim | Nome da cidade.
`complement` | `string` | não | Complemento ou ponto de referência do endereço.
`number` | `string` | sim | Número do endereço.
`neighborhood` | `string` | sim | Nome do bairro.
`state` | `string` | sim | Nome do estado abreviado.
`street` | `string` | sim | Logradouro do endereço.
`zip_code` | `string` | sim | Número do CEP do endereço.

### asset_coverage_nfe_attributes

Parâmetro | Tipo | Obrigatório? | Descrição
--------- | --------- | --------- | -----------
`nfe_access_key` | `string` | sim | Adicionar descrição.

### asset_part_variant_attributes

Parâmetro | Tipo | Obrigatório? | Descrição
--------- | --------- | --------- | -----------
`city_registration_number` | `string` | não | Adicionar descrição.
`company_name` | `string` | não | Adicionar descrição.
`contact_representative_kind` | `string` | não | Adicionar descrição.
`contact_representative_name` | `string` | não | Adicionar descrição.
`contact_representative_email` | `string` | não | Adicionar descrição.
`contact_representative_phone` | `string` | não | Adicionar descrição.
`email` | `string` | não | Adicionar descrição.
`name` | `string` | sim | Adicionar descrição.
`phone_number` | `string` | não | Adicionar descrição.
`state_registration_number` | `string` | não | Adicionar descrição.

## Consultar duplicata

> Este é um exemplo do objeto retornado na resposta deste endpoint:

```json
{
    "data": {
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
}
```
Este endpoint retorna as informações de um ativo específico do tipo duplicata vinculado ao seu cadastro na plataforma.

### HTTP Request

`GET /api/v1/assets/trade_bills/<id>`

### URL Parameters

Parâmetro | Obrigatório? | Descrição
--------- | ----------- | -----------
`id` | sim | Identificador do ativo do tipo duplicata registrado na plataforma

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

# Consultas avançadas

## Paginação de resultados
## Filtros de pesquisa
## Ordenação de resultados
