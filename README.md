# DESAFIO QA POSTMAN

# Sobre o desafio

O desafio é composto por duas etapas:

A primeira etapa tem como objetivo avaliar a forma como é realizado o planejamento de casos de testes, estratégias de testes, análise e modelagem dos  cenários de teste. O fluxo a ser considerado nesta etapa são fluxos de Extrato, Saldo e Transferência Interna através da nossa API Pública.

A segunda etapa tem como finalidade avaliar os testes nos fluxos de Extrato, Saldo e Transferência Interna através do Postman.


### Instruções iniciais

Para você desenvolver o desafio, utilize a seguinte conta que foi criada no nosso ambiente de Sandbox com dados fictícios.

- username - desafioqastone@gmail.com
- password - desafioqa

Você consegue acessar sua conta por esse link: https://sandbox.conta.stone.com.br/login.

Pronto! Você já está pronto para começar seu desafio.

Para se logar pela linha de comando, basta usar o seguinte comando:

```
curl https://login.sandbox.stone.com.br/auth/realms/stone_account/protocol/openid-connect/token \
	  -d 'client_id=admin-cli' \
	  -d 'username=YYYYYYYYY' \
	  -d 'password=ZZZZZZZZZ' \
          -d 'grant_type=password'
```

Isso te devolverá um `access_token`. Use-o para se autenticar nas chamadas para a API.

Você pode fazer transferências internas para essa conta:  
- Stone: 197  
- Agência: 0001  
- Conta: 475384

### Como operar na API de sandbox da Stone OpenBanking?

Todos os endpoints possuem autenticação. Utilizamos OAuth2 e OpenID Connect como especificações de autenticação e autorização. Para o desafio de QA, criamos uma "client application" e um usuário para os testes:

- client_id: XXXXXXXXXX
- username: YYYYYYYY
- password: ZZZZZZZZ

Para conseguir o token de acesso, basta fazer um POST para o nosso IAM:

```
curl https://login.sandbox.stone.com.br/auth/realms/stone_account/protocol/openid-connect/token \
	  -d 'client_id=XXXXXXXXXX' \
	  -d 'username=YYYYYYYYY' \
	  -d 'password=ZZZZZZZZZ' \
          -d 'grant_type=password'
```

### Contexto

A Stone possui uma API de [OpenBanking](https://en.wikipedia.org/wiki/Open_banking) que estamos testando e evoluindo continuamente. O link para a documentação de referência é https://docs.openbank.stone.com.br/. 

Queremos que você use esta API para nos mostrar como iria planejar e levantar os cenários de testes aplicando as principais técnicas de testes.


## 1. Planejamento de Casos de Testes

Seu desafio nessa etapa é criar um planejamento dos casos de testes que você julgar necessário para 3 endpoints da nossa API:

- Saldo: `GET api/v1/accounts/:id/balance`
- Extrato: `GET api/v1/accounts/:id/statement`
- Simulação de transferência interna: `POST api/v1/dry_run/internal_transfers`

### Informações sobre a etapa

   - Utilizar o formato Gherkin para a descrever os casos de teste das APIs;
   - Os casos de testes devem ser commitados em formato .pdf;
   - As informações sobre o documento e sua localização devem estar no README na pasta raiz do repositório.

### Critérios de Avaliação

 Levaremos em conta os seguintes fatores:

   - Qualidade dos cenários de testes;
   - Cobertura do fluxo;
   - Detalhamento e Organização.


## 2. Testes de API via Postman

Nessa etapa sua missão é automatizar os testes que foram planejados na etapa anterior, nos fluxos de Extrato, Saldo e Transferência Interna, através do Postman.

### Informações sobre a etapa

  - Os casos de testes devem ser construídos através do Postman;
  - O desafio deve conter, no mínimo uma Collection do Postman que instrumente o uso da API seguindo um conjunto de cenários que você mesmo irá criar para os 3 endpoints citados acima;
  - A execução deve retornar um status;
  - Ao término da execução deve ser gerado um relatório sobre as APIs testadas (cenários com sucesso/falha, timing, security e etc);

### Critérios de Avaliação

 Levaremos em conta os seguintes fatores:
 
  - Detalhamento e Organização;
  - Conhecimento de APIs;
  - Uso dos Testes no Postman;
  - Escrita de cenários sobre os endpoints; 
  - Coleta de evidências da execução;


## Envio do desafio

Você deve disponibilizar seu projeto no Github e manter o repositório como privado. Quando finalizar, favor entrar em contato com a sua recrutadora, para disponibilizarmos os usuários que deverão possuir acesso para realizar a avaliação.

O repositório deve ser facilmente executável! E lembre-se, a organização e o nível de detalhamento da entrega serão cruciais nesta avaliação!

Bom desafio!


