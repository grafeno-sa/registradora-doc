# Erros

A seguir listamos os erros que eventualmente podem ocorrer ao enviar uma requisição para nossa API e também uma breve descrição das possíveis causas de cada problema:

Código | Erro | Descrição
---------- | ---------- | ----------
400 | Bad Request | A requisição não foi montada corretamente. Pode ser que o corpo da requisição possua algum erro de formatação ou que algum parâmetro do cabeçalho esteja mal preenchido. 
401 | Unauthorized | Não foi possível autenticar seu acesso. Pode ser que o token de autenticação não tenha sido adicionado ao cabeçalho da requisição ou que ele não tenha sido preenchido corretamente. 
404 | Not Found | O recurso solicitado não foi encontrado. Pode ser que o ID passado na requisição esteja errado, que não exista um registro cadastrado com o ID fornecido ou que o endereço tenha sido digitado errado.  
500 | Internal Server Error | Ocorreu algum problema interno na API ao tentar processar a requisição. Se o problema persistir, nos mande uma mensagem através [desse link](http://example.com/developers) com mais detalhes sobre a requisição que deu problema. 
503 | Service Unavailable | Estamos realizando a manutenção da nossa plataforma e estamos fora do ar por alguns momentos. Tente enviar a requisição novamente dentro de alguns instantes.
