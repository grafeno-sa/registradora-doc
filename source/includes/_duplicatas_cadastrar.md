## Cadastrar duplicata

> Este é um exemplo do objeto que deve ser passado no corpo da requisição:

```json
{
  "asset_trade_bill": {
    "emitted_at": "2020-05-24T18:43:45.000-03:00",
    "kind": "goods",
    "operation_attributes": {
      "acquired_at": "2020-05-21T16:52:20.000-03:00",
      "installments_attributes": [
        {
          "acquisition_value": 56903.54,
          "due_date": "2020-05-22T19:33:34.000-03:00",
          "original_due_date": "2020-05-22T12:24:36.000-03:00",
          "original_value": 69628.45,
          "value": 76712.54,
          "payments_attributes": [
            {
              "performed_at": "2020-05-24T01:58:04.000-03:00",
              "value": 68397.21
            },
            {
              "performed_at": "2020-05-25T00:14:15.000-03:00",
              "value": 20569.46
            },
            {
              "performed_at": "2020-05-24T04:50:30.000-03:00",
              "value": 69376.56
            }
          ]
        },
        {
          "acquisition_value": 93630.54,
          "due_date": "2020-05-25T02:31:05.000-03:00",
          "original_due_date": "2020-05-23T22:38:47.000-03:00",
          "original_value": 98205.86,
          "value": 33916.25,
          "payments_attributes": [
            {
              "performed_at": "2020-05-23T04:50:36.000-03:00",
              "value": 90527.48
            },
            {
              "performed_at": "2020-05-23T10:23:55.000-03:00",
              "value": 94030.36
            },
            {
              "performed_at": "2020-05-26T17:24:00.000-03:00",
              "value": 90111.18
            }
          ]
        },
        {
          "acquisition_value": 70367.69,
          "due_date": "2020-05-26T00:30:52.000-03:00",
          "original_due_date": "2020-05-24T16:57:23.000-03:00",
          "original_value": 28355.28,
          "value": 63912.31,
          "payments_attributes": [
            {
              "performed_at": "2020-05-23T13:13:00.000-03:00",
              "value": 65163.91
            },
            {
              "performed_at": "2020-05-22T19:10:35.000-03:00",
              "value": 25503.78
            },
            {
              "performed_at": "2020-05-22T20:13:21.000-03:00",
              "value": 14381.48
            }
          ]
        }
      ]
    },
    "assignor_attributes": {
      "city_registration_number": "sbshrzps8",
      "company_name": "Amoreira-Datena",
      "contact_representative_kind": "contact",
      "contact_representative_name": "Sra. Enzo Miguel Arantes",
      "contact_representative_email": "loree_watsica@farrellmedhurst.com",
      "contact_representative_phone": "(49) 90145-7420",
      "document_number": "52749223000400",
      "email": "teie@turner.info",
      "name": "Paula Gabeira",
      "phone_number": "(92) 96830-5355",
      "state_registration_number": "7k702q",
      "address_attributes": {
        "city": "Igaci",
        "complement": "Apto. 892",
        "number": "632",
        "neighborhood": "Eagle Oaks",
        "state": "RN",
        "street": "Avenida João Lucas",
        "zip_code": "65822-129"
      }
    },
    "creditor_attributes": {
      "city_registration_number": "6o1g730i1",
      "company_name": "Ferraço, Chaves e Hermingues",
      "contact_representative_kind": "contact",
      "contact_representative_name": "Milena da Bandeira",
      "contact_representative_email": "bruno@little.io",
      "contact_representative_phone": "(96) 93437-7194",
      "document_number": "11489737000217",
      "email": "garry@franecki.biz",
      "name": "Beatriz Pinheira",
      "phone_number": "(24) 99039-5994",
      "state_registration_number": "ugmu6z",
      "address_attributes": {
        "city": "Engenho Velho",
        "complement": "Apto. 929",
        "number": "73160",
        "neighborhood": "Summer Place",
        "state": "BA",
        "street": "Ponte Gustavo",
        "zip_code": "43010-929"
      }
    },
    "guarantor_attributes": {
      "city_registration_number": "rbdtl9211",
      "company_name": "Garcez e Associados",
      "contact_representative_kind": "contact",
      "contact_representative_name": "Srta. Francisca Laranjeira",
      "contact_representative_email": "young.considine@mantemcglynn.co",
      "contact_representative_phone": "(84) 99529-3386",
      "document_number": "05977230000714",
      "email": "meredith@heidenreich.io",
      "name": "Matheus Silva",
      "phone_number": "(45) 98505-7840",
      "state_registration_number": "d8dqzc",
      "address_attributes": {
        "city": "Piau",
        "complement": "Casa 4",
        "number": "4243",
        "neighborhood": "Willow Gardens",
        "state": "PE",
        "street": "Avenida César",
        "zip_code": "14044-876"
      }
    },
    "payer_attributes": {
      "city_registration_number": "ty5zlkcf8",
      "company_name": "Ribas Comércio",
      "contact_representative_kind": "contact",
      "contact_representative_name": "Maria Chaves",
      "contact_representative_email": "cletus.braun@kiehn.net",
      "contact_representative_phone": "(98) 91467-8897",
      "document_number": "68109436000319",
      "email": "garland@borerrogahn.net",
      "name": "Davi Ludmer Carvalheira",
      "phone_number": "(61) 95562-6444",
      "state_registration_number": "wb90ls",
      "address_attributes": {
        "city": "Itapitanga",
        "complement": "Casa 5",
        "number": "281",
        "neighborhood": "Pine Court",
        "state": "TO",
        "street": "Ponte Natália Aroeira",
        "zip_code": "28449-337"
      }
    },
    "nfe_attributes": {
      "nfe_access_key": "35200248477780000191550010000033561442834725"
    }
  }
}
```

Este endpoint realiza o cadastro de um novo ativo do tipo duplicata na plataforma.

### Endpoint

`POST /api/v1/assets/trade_bills`

### Parâmetros da requisição

Estas são as definições dos parâmetros aceitos por este endpoint. O objeto JSON enviado na requisição deve possuir uma chave raiz chamada `asset_trade_bill` e todos os outros parâmetros devem estar contidos dentro desta chave.

### Ativo

Parâmetro | Tipo | Obrigatório? | Descrição
--------- | ---- | ------------ | ---------
`emitted_at` | `datetime` | sim | Data e hora de emissão do ativo.
`kind` | `string` | sim | Tipo do ativo. Use `goods` para bens e `services` para serviços.
`assignor_attributes` | `object` | sim | Dados do cedente do ativo. Consulte a seção [Parte da operação](#parte_da_operacao) para a relação completa dos parâmetros.
`creditor_attributes` | `object` | não | Dados do credor do ativo. Consulte a seção [Parte da operação](#parte_da_operacao) para a relação completa dos parâmetros. 
`guarantor_attributes` | `object` | não | Dados do avalista do ativo. Consulte a seção [Parte da operação](#parte_da_operacao) para a relação completa dos parâmetros. 
`operation_attributes` | `object` | sim | Dados da operação de aquisição do ativo. Consulte a seção [Operação](#operacao) para a relação completa dos parâmetros.
`payer_attributes` | `object` | sim | Dados do sacado do ativo. Consulte a seção [Parte da operação](#parte_da_operacao) para a relação completa dos parâmetros.
`nfe_attributes` | `object` | sim | Dados da nota fiscal que dá lastro ao ativo. Consulte a seção [Nota fiscal](#nfe_attributes) para a relação completa dos parâmetros.

### Operação

Parâmetro | Tipo | Obrigatório? | Descrição
--------- | ---- | ------------ | ---------
`acquired_at` | `datetime` | sim | Data e hora de aquisição do ativo.
`installments_attributes` | `array` | não | Dados das parcelas do ativo. Consulte a seção [Parcela](#parcela) para a relação completa dos parâmetros. 

### Parcela

Parâmetro | Tipo | Obrigatório? | Descrição
--------- | ---- | ------------ | ---------
`acquisition_value` | `number` | sim | Valor de aquisição da parela.
`due_date` | `datetime` | sim | Data atual de vencimento da parcela.
`original_due_date` | `datetime` | sim | Data original de vencimento da parcela.
`original_value` | `number` | sim | Valor nominal original da parcela.
`value` | `number` | sim | Valor nominal atual do parcela.
`payments_attributes` | `array` | não | Dados das baixas da parcela. Consulte a seção [Baixa](#baixa) para a relação completa dos parâmetros.

### Baixa

Parâmetro | Tipo | Obrigatório? | Descrição
--------- | ---- | ------------ | ---------
`performed_at` | `datetime` | sim | Data do pagamento.
`value` | `number` | sim | Valor pago.

### Parte da operação

Parâmetro | Tipo | Obrigatório? | Descrição
--------- | ---- | ------------ | ---------
`city_registration_number` | `string` | não | Número de inscrição municipal.
`company_name` | `string` | não | Nome da empresa.
`contact_representative_kind` | `string` | não | Tipo do representante da empresa. User `contact` para contato e `representative` para representante legal. 
`contact_representative_name` | `string` | não | Nome completo do representante da empresa.
`contact_representative_email` | `string` | não | E-mail do representante da empresa.
`contact_representative_phone` | `string` | não | Telefone do representante da empresa.
`document_number` | `string` | sim | Número do cpf ou cnpj (somente números).
`email` | `string` | não | E-mail de contato.
`name` | `string` | sim | Nome completo.
`phone_number` | `string` | não | Telefone de contato.
`state_registration_number` | `string` | não | Número de inscrição estadual.

### Endereço

Parâmetro | Tipo | Obrigatório? | Descrição
--------- | ---- | ------------ | ---------
`city` | `string` | sim | Nome da cidade.
`complement` | `string` | não | Complemento ou ponto de referência do endereço.
`number` | `string` | sim | Número do endereço.
`neighborhood` | `string` | sim | Nome do bairro.
`state` | `string` | sim | Nome do estado abreviado.
`street` | `string` | sim | Logradouro do endereço.
`zip_code` | `string` | sim | Número do CEP do endereço.

### Nota fiscal

Parâmetro | Tipo | Obrigatório? | Descrição
--------- | ---- | ------------ | ---------
`nfe_access_key` | `string` | sim | Chave de acesso da nota fiscal.
