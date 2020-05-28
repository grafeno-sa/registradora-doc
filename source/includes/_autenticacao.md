# Autenticação

A API possui uma camada dupla de autenticação para garantir a segurança dos dados e evitar que acessos indevidos possam comprometer a privacidade da informações.

A primeira camada de autenticação é a [autenticação de aplicações cliente](#autenticacao-de-aplicacoes-cliente), através da qual, apenas aplicações previamente autorizadas poderão originar qualquer tipo de requisição à API.

A segunda camada de autenticação é a [autenticação de usuários](#autenticacao-de-usuarios), através da qual, apenas pessoas que possuem um cadastro de usuário válido e ativo, poderão acessar à API. 

Com exceção das requisições de autenticação, todas as demais requisições à API deverão ser realizadas por um usuário autenticado e através de uma aplicação autorizada, simultaneamente.  

## Autenticação de aplicações cliente

> Este é um exemplo do cabeçalho de uma requisição contendo o token de autenticação da aplicação:

```json
{
  "Authorization": "27cc4835-53e9-4dcc-a064-d6609549f9ea.QHrAqIvp4M8dxWmmQZ1h3P85Vww"
}
```

> Não se esqueça de substituir o valor do exemplo pelo token de autenticação da sua aplicação.

Esta camada de segurança permite que a API identifique qual aplicação cliente está originando uma requisição. Caso a aplicação esteja autorizada para acessar à API, a requisição é processada, caso contrário, a requisição é bloqueada e uma mensagem de erro é devolvida em resposta (consulte a seção [erros](#erros) para obter mais referências). 

Para autenticar a aplicação cliente, é necessário incluir o token de autenticação da aplicação no cabeçalho de **todas** as requisições feitas à API.

<aside class="warning">Este token é secreto e não deve ser compartilhado publicamente. Mantenha ele salvo em um lugar seguro e caso desconfie de um possível vazamento, solicite que um novo token seja gerado.</aside>
        
## Autenticação de usuários

Esta camada protege os dados da API contra o acesso de pessoas não autorizadas e garante a privacidade dos dados dos usuários. A autenticação de usuários é feita através de tokens de autenticação JWT e ocorre em duas etapas.

> Este é um exemplo do corpo da requisição que deve ser enviada no endpoint de login:

```json
{
  "email": "user@company.com",
  "password": "secret"
}
```

> Este é um exemplo do cabeçalho retornado na resposta da API, contendo as informações do token de acesso do usuário autenticado:

```json
{
  "access-token": "ZGLvgsf1dDs59sIybcIitg",
  "client": "bohV15kuQUVrriur8F911Q",
  "uid": "user@company.com"
}
```

Na primeira etapa, é necessário enviar uma requisição para o endpoint de login da API com as credenciais de acesso do usuário que está solicitando acesso, no caso, e-mail e senha. Caso as credenciais enviadas estejam corretas, a API irá retornar uma resposta de sucesso, e junto, no cabeçalho da resposta, irá retornar um token de acesso exclusivo para o usuário, composto de 3 partes: `access-token`, `client` e `uid`.

### Endpoint

`GET /api/v1/auth/sign_in`

### Parâmetros da requisição

Estas são as definições dos parâmetros aceitos por este endpoint.

Parâmetro | Tipo | Obrigatório? | Descrição
--------- | ---- | ------------ | ---------
`email` | `string` | sim | E-mail cadastrado do usuário.
`password` | `string` | sim | Senha de acesso do usuário.

> Este é um exemplo do cabeçalho de uma requisição com os tokens de autenticação da aplicação e do usuário:

```json
{
  "Authorization": "27cc4835-53e9-4dcc-a064-d6609549f9ea.QHrAqIvp4M8dxWmmQZ1h3P85Vww",
  "access-token": "ZGLvgsf1dDs59sIybcIitg",
  "client": "bohV15kuQUVrriur8F911Q",
  "uid": "user@company.com"
}
```

Na segunda etapa, já em posse do token de acesso do usuário, basta realizar as requisições desejadas à API, adicionando ao cabeçalho da requisição, todas as partes do token do usuário e também o token da aplicação. Desta forma, a API será capaz de validar a identidade do usuário que realizou uma requisição e também garantir que esta mesma requisição foi originada a partir de uma aplicação autorizada. 


