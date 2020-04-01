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
