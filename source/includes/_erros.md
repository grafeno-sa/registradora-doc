# Erros

Esta é a lista dos erros que eventualmente podem ocorrer ao enviar uma requisição para a API e também uma breve descrição das possíveis causas de cada problema:

Código | Erro | Descrição
---------- | ---------- | ----------
400 | Bad Request | A requisição não foi montada corretamente. Pode ser que o corpo da requisição possua algum erro de formatação ou que algum parâmetro do cabeçalho esteja mal preenchido. 
401 | Unauthorized | Não foi possível autenticar o acesso. Pode ser que o token de autenticação da aplicação ou do usuário não tenham sido adicionados ao cabeçalho da requisição ou que eles não tenham sido preenchidos corretamente. 
404 | Not Found | O recurso solicitado não foi encontrado. Pode ser que o ID passado na requisição esteja errado, que não exista um dado cadastrado com o ID fornecido ou que o endereço tenha sido digitado errado.  
500 | Internal Server Error | Ocorreu algum problema interno na API ao tentar processar a requisição. Se o problema persistir, nos mande uma mensagem através [desse email](mailto:meajuda@grafeno.digital) com mais detalhes sobre a requisição que deu problema.
