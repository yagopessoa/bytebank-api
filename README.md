# Bytebank web API

Web API feita com [json-server](https://github.com/typicode/json-server) para consumo do [App em Flutter do Bytebank](https://github.com/yagopessoa/bytebank)

## Funcionalidades

A Web API oferece as seguintes funcionalidades:

- Listagem e cadastro de transações.

## Como executar

Abra o terminal ou prompt e acesse o diretório do projeto, então execute o seguinte comando:

```
json-server --watch db.json --delay=500 --host=<your_host_ip>
```

Obs: para saber seu IP, no linux, rode o seguinte comando:

```
hostname -I | cut -d' ' -f1
```

Ou você pode juntar em um único comando:

```
json-server --watch db.json --delay=500 --host=$(hostname -I | cut -d' ' -f1)
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
      "value": 200.0,
      "contact": {
        "name": "Yago",
        "accountNumber": 1000
      }
    },
    {
      "id": 2,
      "value": 200.0,
      "contact": {
        "name": "Yago",
        "accountNumber": 1500
      }
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
    }
  }

  // response example
  {
    "id": 3,
    "value": 200.0,
    "contact": {
      "name": "Yago",
      "accountNumber": 1000
    }
  }
  ```
