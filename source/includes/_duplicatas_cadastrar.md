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
