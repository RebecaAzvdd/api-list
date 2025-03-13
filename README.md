Endpoint
POST /user

Este endpoint permite o envio de informações sobre a conta bancária e o cartão de crédito, bem como as características e notícias associadas a eles.
Requisição

Método HTTP: POST
URL: /user

Cabeçalhos:

    Content-Type: application/json

Corpo da requisição:

O corpo da requisição deve conter um JSON com a seguinte estrutura:
```
{
  "name": "João Silva",
  "account": {
    "number": "987654321",
    "agency": "1234",
    "balance": 5000,
    "limit": 2000
  },
  "card": {
    "number": "4111222233334444",
    "limit": 3000
  },
  "features": [
    {
      "icon": "credit_card",
      "description": "Cartão de crédito com limite de até R$ 3000"
    },
    {
      "icon": "cash",
      "description": "Saque em caixas eletrônicos sem taxas"
    }
  ],
  "news": [
    {
      "icon": "announcement",
      "description": "Novo aplicativo para gestão de contas e cartões disponível."
    },
    {
      "icon": "alert",
      "description": "Alteração nas taxas de juros para empréstimos a partir do próximo mês."
    }
  ]
}

```
