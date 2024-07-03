# API's Pearson

# Arquitetura
Todas as API's foram desenvolvidas pensando na AWS Lambda pela [DigitalPath](https://digitalpath.com.br) .

Todas as API's foram desenvolvidas na linguagem [Python](https://www.python.org/) versão 3.12 utilizando o framework [Chalice AWS](https://aws.github.io/chalice/).

## Tempo de execução
O tempo de execução pode variar devido ao captcha das páginas. Nos testes locais, os tempos foram:


| API    | Tempo |
| -------- | ------- |
| Correios  | 110ms - 250ms    |
| Sintegra | 3s - 8s     |
| Receita    | 6s - 12s    |

> Os tempos podem variar quando hospedada na AWS.


