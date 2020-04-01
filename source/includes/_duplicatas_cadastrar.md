## Cadastrar duplicata

> Este é um exemplo do objeto que deve ser passado no corpo da requisição:

```json
{
  "asset_trade_bill": {
    "acquired_at": "2020-03-26T13:00:41.000-03:00",
    "due_date": "2020-04-06",
    "emitted_at": "2020-03-27T12:33:58.000-03:00",
    "state": "draft",
    "value": "98.45",
    "kind": "goods",
    "type": "AssetTradeBill",
    "assignor_attributes": {
      "address_attributes": {
        "city": "Ibitirama",
        "complement": "Lote 54",
        "number": "623",
        "neighborhood": "Royal Creek",
        "state": "MT",
        "street": "Viela Leonardo da Barra",
        "zip_code": "30625-581"
      },
      "asset_part_variant_attributes": {
        "city_registration_number": "k3ws8ih8k",
        "company_name": "Coqueiro, Álvares e Paiva",
        "contact_representative_kind": "contact",
        "contact_representative_name": "Víctor Guedes Jr.",
        "contact_representative_email": "willow@macgyver.com",
        "contact_representative_phone": "(34) 92289-1937",
        "email": "lashaun_bogisich@moore.net",
        "name": "Pedro da Veiga",
        "phone_number": "(53) 92053-2427",
        "state_registration_number": "84xae7"
      },
      "document_number": "08459883361"
    },
    "creditor_attributes": {
      "address_attributes": {
        "city": "Santa Rosa de Lima",
        "complement": "Sobrado 18",
        "number": "s/n",
        "neighborhood": "Pine Pointe",
        "state": "MS",
        "street": "Rua João Victor Castanheira",
        "zip_code": "33775-295"
      },
      "asset_part_variant_attributes": {
        "city_registration_number": "a7y3yf7td",
        "company_name": "Camacho e Associados",
        "contact_representative_kind": "contact",
        "contact_representative_name": "Sr. Fabiano Simão",
        "contact_representative_email": "nelda@rice.org",
        "contact_representative_phone": "(64) 93109-5973",
        "email": "jaunita@cummerata.co",
        "name": "Salvador da Bandeira",
        "phone_number": "(53) 95554-0357",
        "state_registration_number": "n8e96u"
      },
      "document_number": "02851562509"
    },
    "guarantor_attributes": {
      "address_attributes": {
        "city": "Mucugê",
        "complement": "Casa 2",
        "number": "696",
        "neighborhood": "Park Oaks",
        "state": "RR",
        "street": "Viela Nathan Ferreira",
        "zip_code": "12566-627"
      },
      "asset_part_variant_attributes": {
        "city_registration_number": "myvcfce39",
        "company_name": "Veles-Melo",
        "contact_representative_kind": "contact",
        "contact_representative_name": "Ana Laura Fernandes",
        "contact_representative_email": "casie@walter.io",
        "contact_representative_phone": "(19) 90416-8347",
        "email": "nickolas@bauch.org",
        "name": "Maria Sophia Araújo",
        "phone_number": "(41) 91309-3038",
        "state_registration_number": "uixb6b"
      },
      "document_number": "07781191900"
    },
    "payer_attributes": {
      "address_attributes": {
        "city": "Areias",
        "complement": "Sobrado 68",
        "number": "4657",
        "neighborhood": "Paradise Pointe",
        "state": "SP",
        "street": "Ponte Valentina",
        "zip_code": "01225-088"
      },
      "asset_part_variant_attributes": {
        "city_registration_number": "hoz2x0s8g",
        "company_name": "Neves, Moreno e Arriaga",
        "contact_representative_kind": "contact",
        "contact_representative_name": "Luiz Gustavo Barros",
        "contact_representative_email": "judy_cummings@lind.com",
        "contact_representative_phone": "(49) 98845-6675",
        "email": "adaline_marks@wiegand.io",
        "name": "Eloah Almeida",
        "phone_number": "(84) 90249-0713",
        "state_registration_number": "wz73gd"
      },
      "document_number": "02670411878"
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
`creditor_attributes` | `object` | não | Dados do credor do ativo. Consulte a seção [guarantor_attributes](#credor_attributes) para a relação completa dos parâmetros. 
`guarantor_attributes` | `object` | não | Dados do avalista do ativo. Consulte a seção [guarantor_attributes](#guarantor_attributes) para a relação completa dos parâmetros. 
`payer_attributes` | `object` | sim | Dados do sacado do ativo. Consulte a seção [payer_attributes](#payer_attributes) para a relação completa dos parâmetros.
`asset_coverage_nfe_attributes` | `object` | sim | Dados da nota fiscal do ativo. Consulte a seção [asset_coverage_nfe_attributes](#asset_coverage_nfe_attributes) para a relação completa dos parâmetros.

### assignor_attributes

Parâmetro | Tipo | Obrigatório? | Descrição
--------- | --------- | --------- | -----------
`document_number` | `string` | sim | Número do documento do cedente, sem pontuação.
`address_attributes` | `object` | sim | Dados do endereço do cedente. Consulte a seção [address_attributes](#address_attributes) para a relação completa dos parâmetros.
`asset_part_variant_attributes` | `object` | sim | Dados do gerais sobre o cedente. Consulte a seção [asset_part_variant_attributes](#asset_part_variant_attributes) para a relação completa dos parâmetros.

### creditor_attributes

Parâmetro | Tipo | Obrigatório? | Descrição
--------- | --------- | --------- | -----------
`document_number` | `string` | sim | Número do documento do credor, sem pontuação.
`address_attributes` | `object` | sim | Dados do endereço do credor. Consulte a seção [address_attributes](#address_attributes) para a relação completa dos parâmetros.
`asset_part_variant_attributes` | `object` | sim | Dados do gerais sobre o credor. Consulte a seção [asset_part_variant_attributes](#asset_part_variant_attributes) para a relação completa dos parâmetros.

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
