# API Pearson

## Arquitetura

As APIs Pearson foram desenvolvidas pela [DigitalPath](https://digitalpath.com.br) com foco na execução em ambientes AWS Lambda. A implementação é feita em [Python](https://www.python.org/) versão 3.10, utilizando o framework [Chalice AWS](https://aws.github.io/chalice/), o que permite uma integração eficiente com os serviços da AWS e uma estrutura escalável.


## Autenticação

Para garantir a segurança e a integridade dos dados, todas as APIs utilizam autenticação via [JWT](https://jwt.io/). Inicialmente, os tokens de autenticação serão gerados pela DigitalPath até que o sistema de gerenciamento de senhas da Pearson esteja em operação para automatizar a geração dos tokens.

Todas as requisições às APIs devem incluir um token de autenticação no cabeçalho, conforme o exemplo abaixo:

```json
{
    "Authorization": "Bearer {token}"
}
```

> O token é passado no formato Bearer {token}



## Tempo de execução
O tempo de execução pode variar devido ao captcha das páginas. Nos testes locais, os tempos foram:


| API    | Tempo |
| -------- | -------       |
| Correios | 110ms - 250ms |
| Sintegra | 3s - 8s       |
| Receita  | 6s - 20s      |

>  Observação: Os tempos de execução podem variar quando as APIs estiverem hospedadas na AWS,
devido a fatores como latência de rede, carga do servidor e disponibilidade dos servidores que resolvem o captcha.


Considerações Finais

- As APIs foram desenvolvidas para serem altamente escaláveis e seguras.
- A autenticação via JWT é essencial para garantir que apenas usuários autorizados acessem os dados.
- O desempenho pode variar, e otimizações adicionais podem ser necessárias dependendo do uso e carga esperada.

Para mais detalhes consulte a [DigitalPath](https://digitalpath.com.br).


