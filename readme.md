# Teste Técnico - BackEnd #VemSerAcesso

Olá 😊
Parabéns por chegar aqui.
Seu perfil e valores deram match com a nossa cultura e por isso você está evoluindo em nosso processo :grinning:

O próximo passo é um teste técnico com foco em Back-End.
Crie um repositório em sua conta do GitHub, com a solução do problema abaixo: 

## Problema

Criação de uma API para realização de transferencia de valores entre duas contas, essa transferencia não precisará ser online.

Para consultar contas, fazer movimentação financeira e consulta de saldo deve-se usar a [API de conta](#api-conta) que está documentada abaixo.

Deve haver um endpoint para consulta de status da transferencia, que podem ser:

- In Queue
- Processing
- Confirmed
- Error
  - Nestes casos é necessário retornar o motivo do erro

Temos que ter logs de todas as operações efetuadas pela API, sejam elas consultas ou transferencias.

O tempo de resposta da API tem que ser baixo e temos que ter a menor quantidade de erros possivel.

Os payloads de request e response estão descritos abaixo.


## Payloads

##### Request Transferencia
```
{
    "accountOrigin": "123",
    "accountDestination": "123",
    "value": 123
}
```

##### Response Transferencia
```
{
    "transactionId": "d4a5bc48-3e01-4ee4-aed4-7007325e738e"
}
```

##### Request Status
```
{
    "transactionId": "d4a5bc48-3e01-4ee4-aed4-7007325e738e"
}
```

##### Response Status
```
{
    "Status": "Confirmed"
}
```
ou
```
{
    "Status": "Error",
    "Message": "Invalid account number"
}
```

## Nossa Stack

Você poderá utilizar a linguagem que quiser 😊 
Porém, se liga nas tecnologias que utilizamos no dia-a-dia da Acesso, caso queira aplica-las no desenvolvimento do seu teste:

- Docker
- .NET Core
- RabbitMq
- MySql/SqlServer
- RavenDb/DynamoDb/MongoDb
- ELK Stack (ElasticSearch,Logstash,Kibana)
  
---

## API Conta

Você precisará desta API para desenvolver o nosso teste. Boa sorte 😉

### Uso

Essa API pode ser encontrada no [Docker Hub](https://hub.docker.com/repository/docker/baldini/testacesso) ou no [Heroku](https://acessoaccount.herokuapp.com/swagger/index.html)

Acessando a url /swagger você consegue acesso a documentação.

Essa API tem intermitências como tempo de reposta alto e em alguns momentos do dia ela fica indisponivel :dizzy_face:

---

## Dúvidas

Abra uma issue que responderemos o mais rápido possivel :smile: