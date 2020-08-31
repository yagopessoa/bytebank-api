# Bytebank web API

Web API feita com [json-server](https://github.com/typicode/json-server) para consumo do [App em Flutter do Bytebank](https://github.com/yagopessoa/bytebank)

## Funcionalidades

A Web API oferece as seguintes funcionalidades:

- Listagem e cadastro de transações.

## Como executar

Abra o terminal ou prompt e acesse o diretório do projeto, então execute o seguinte comando:

```
json-server --watch db.json --host=<your_host_ip>
```

Obs: para saber seu IP, no linux, rode o seguinte comando:

```
hostname -I | cut -d' ' -f1
```

## Mapeamento de end-points

Para acessar as funcionalidades foram disponibilizados os seguintes end-points:

- `/transactions`:
  - **GET**: Listagem:

  ```
  // response example
  [
    {
      "id": 1,
      "value": 200.00,
      "contact": {
          "name": "Yago",
          "accountNumber": 1000
      },
      "dateTime": "2020-08-30 12:57:23"
    },
    {
      "id": 2,
      "value": 200.00,
      "contact": {
          "name": "Yago",
          "accountNumber": 1500
      },
      "dateTime": "2020-08-30 12:57:37"
    }
  ]
  ```

  - **POST**: Inserção:

  ```
  // request body example
  {
    "value": 200.0,
    "contact": {
      "name": "Yago",
      "accountNumber": 1000
    },
    "dateTime": "2020-08-30 12:57:37"
  }

  // response example
  {
    "id": 3,
    "value": 200.00,
    "contact": {
        "name": "Yago",
        "accountNumber": 1000
    },
    "dateTime": "2020-08-30 12:57:37"
  }
  ```
