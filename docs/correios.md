# API Correios
A API dos Correios permite consultar o endereço de um determinado CEP.

### Documentação

A API é protegida por JWT token que será gerada pela Pearson.

### Infraestrutura
Para gerar o token deve ser definido as seguintes variaveis de ambiente:

- `JWT_SECRET`: Chave de autenticação da API.
- `JWT_ALGORITHM`: Chave de segurança da API.

O algoritmo de segurança usado nos testes é HS256, mas fica a disposição da Pearson para escolher outro algoritmo de segurança.

A API dos correios **não** precisa de quebrar captcha.

#### Método
`POST`


#### Corpo da Requisição
```json
{
    "cep": 20231030
}
```

> É aceito tanto o CEP 20231-030 quanto 20231030.
> 
> Se Passar no formato 20231-030 é obrigatorio que seja enviada como string.
#### Header da Requisição
```json
{
    "Content-Type": "application/json",
    "Authorization": "Bearer {token}"
}
```

#### Corpo da Resposta
Codigo de retorno: 200

**Resposta:**
```json 
{
    "logradouro": "Avenida Henrique Valadares",
    "bairro": "Centro",
    "cep": "20231-030",
    "municipio": "Rio de Janeiro",
    "estado": "RJ"
}
```

Codigo de retorno: 400

**Resposta:**
```json
{
    "message": "Cep inválido"
}
```
Motivo da falha: CEP inválido



### Erros
Quando um CEP não for informado corretamente, será retornado um erro:

### Geração de Token
Para gerar um token de acesso, basta acessar a API de autenticação da Pearson.

