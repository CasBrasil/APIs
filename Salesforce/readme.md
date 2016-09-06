# Documento Salesforce

## Intro

Essa documentação visa auxiliar na configuração válida dos arquivos para envio para CasBrasil utilizando a API v0.0.1

# RCB

Parametro de envio dos dados de vendas

JSON:
```
{
  "token" : "ewogICJ0b2tlbiIgOiAicXV3aWhlaW91c2Rob2lhdXNncnl1d3FnZXJ1b3lxd2dleXVxd2dydXlxd2dydXlxd2dyZG9uc2E7b3F3ZW8iLAogICJjbnBqIiA6ICIxMjM0NTY3ODkwMTIzNCIsCiAgInllYXIiIDogIjIwMTYiLAogICJkYXRhIiA6IFsgewogICAgIm1vbnRoIiA6IDEsCiAgICAiZmllbGRzIiA6IFsgewogICAgICAiaWQiIDogMSwKICAgICAgInZhbHVlIiA6IDEwMDAwLjAKICAgIH0sIHsKICAgICAgImlkIiA6IDIsCiAgICAgICJ2YWx1ZSIgOiAyMDAwMC4wMQogICAgfSBdCiAgfSwgewogICAgIm1vbnRoIiA6IDIsCiAgICAiZmllbGRzIiA6IFsgewogICAgICAiaWQiIDogMSwKICAgICAgInZhbHVlIiA6IDEwMDAwLjAKICAgIH0sIHsKICAgICAgImlkIiA6IDIsCiAgICAgICJ2YWx1ZSIgOiAyMDAwMC4wMQogICAgfSBdCiAgfSBdCn0",
  "app_id" : 000014,
  "cnpj" : "27505087000105",
  "year" : "2016",
  "months" : [ {
    "month" : 1,
    "data" : [ {
      "day" : 1,
      "values" : [ {
        "products" : [ {
          "barcode" : "123456789",
          "employers" : [ {
            "cpf" : "1223242342",
            "quantity" : 30.0,
            "gross_value" : 12132.0,
            "net_value" : 12121.0
          } ],
          "tickects" : [ {
            "cpf" : "1223242342",
            "quantity" : 30.0,
            "gross_value" : 12132.0,
            "net_value" : 12121.0
          } ]
        } ]
      } ]
    } ]
  } ]
}
```


## RCB - Parametros
### 1 token
> Chave individual do CNPJ para conexão com as ferramentas da CasBrasil

- Tipo: Varchar
- Tamanho: 256
- Obrigatorio


Exemplo:
```
ewogICJ0b2tlbiIgOiAicXV3aWhlaW91c2Rob2lhdXNncnl1d3FnZXJ1b3lxd2dleXVxd2dydXlxd2dydXlxd2dyZG9uc2E7b3F3ZW8iLAogICJjbnBqIiA6ICIxMjM0NTY3ODkwMTIzNCIsCiAgInllYXIiIDogIjIwMTYiLAogICJkYXRhIiA6IFsgewogICAgIm1vbnRoIiA6IDEsCiAgICAiZmllbGRzIiA6IFsgewogICAgICAiaWQiIDogMSwKICAgICAgInZhbHVlIiA6IDEwMDAwLjAKICAgIH0sIHsKICAgICAgImlkIiA6IDIsCiAgICAgICJ2YWx1ZSIgOiAyMDAwMC4wMQogICAgfSBdCiAgfSwgewogICAgIm1vbnRoIiA6IDIsCiAgICAiZmllbGRzIiA6IFsgewogICAgICAiaWQiIDogMSwKICAgICAgInZhbHVlIiA6IDEwMDAwLjAKICAgIH0sIHsKICAgICAgImlkIiA6IDIsCiAgICAgICJ2YWx1ZSIgOiAyMDAwMC4wMQogICAgfSBdCiAgfSBdCn0
```

### 2 app_id
> Chave de identificação do arquivo

- Tipo: Varchar
- Tamanho: fixo 6
- Obrigatorio
##### valor fixo para esse arquivo: 000014,

### 3 cnpj
> Chave de identificação da loja

- Tipo: Varchar
- Tamanho: fixo 14
- Obrigatorio

Exemplo:
```
"27505087000105"
```
### 4 year
> Ano do conteudo

- Tipo: inteiro
- Tamanho: fixo 4
- Obrigatorio

Exemplo:
```
"2016"
```
### 5 months
- Tipo: JSON
- Obrigatorio

#### 5.1 months -> month
> Esse elemento faz parte do elemento "months"
> Mes de referencia do conteudo contido no elemento 5.2

- Tipo: inteiro
- Tamanho: 2
- Obrigatorio

#### 5.2 months -> data  
> Esse elemento faz parte do elemento "months"
> Contem as vendas do mes

- Tipo: JSON
- Obrigatorio

#### 5.2.1 months -> data -> day
> Esse elemento faz parte do elemento "data"
> Dia de referencia do conteudo contido no elemento 5.2.2

- Tipo: inteiro
- Tamanho: 2
- Obrigatorio

####   5.2.2 months -> data -> values
> Esse elemento faz parte do elemento "data"
> Contem as vendas do dia totalizadas por produto e vendedor

- Tipo: JSON
- Obrigatorio

####  5.2.2.1 months -> data -> values -> products
> Esse elemento faz parte do elemento "values"
> Contem os produtos vendidos no dia*

- Tipo: JSON
- Obrigatorio

####     5.2.2.1.1 months -> data -> values -> products -> barcode
> Esse elemento faz parte do elemento "products"
> Contem os produtos vendidos no dia

- Tipo: inteiro
- Tamanho: 13
- Obrigatorio

####     5.2.2.1.1 months -> data -> values -> products -> employers
> Esse elemento faz parte do elemento "products"
> Contem os vendedores que fizeram venda desse produto no dia

- Tipo: JSON
- Obrigatorio

####       5.2.2.1.1.1 months -> data -> values -> products -> employers -> cpf
> Esse elemento faz parte do elemento "employers"
> CPF do vendedor

- Tipo: inteiro
- Tamanho: 11
- Obrigatorio

####       5.2.2.1.1.2 months -> data -> values -> products -> employers -> quantity
> Esse elemento faz parte do elemento "employers"
> Quantidade vendida no dia pelo vendedor

- Tipo: inteiro
- Obrigatorio

####       5.2.2.1.1.3 months -> data -> values -> products -> employers -> gross_value
> Esse elemento faz parte do elemento "employers"
> Total de venda bruta do vendedor no dia

- Tipo: decimal
- Obrigatorio

####       5.2.2.1.1.4 months -> data -> values -> products -> employers -> net_value
> Esse elemento faz parte do elemento "employers"
> Total de venda liquida do vendedor no dia

- Tipo: decimal
- Obrigatorio

####      5.2.2.1.2 months -> data -> values -> products -> tickets
> Esse elemento faz parte do elemento "tickets"
> Contem dados de vendas por mes do vendedor

- Tipo: JSON
- Obrigatorio

####      5.2.2.1.2.1 months -> data -> values -> products -> tickets -> cpf
> Esse elemento faz parte do elemento "tickets"
> CPF do vendedor

- Tipo: inteiro
- Tamanho: 11
- Obrigatorio

####      5.2.2.1.2.2 months -> data -> values -> products -> tickets -> quantity
> Esse elemento faz parte do elemento "tickets"
> Quantidade de vendas(tickets) do vendedor no mes

- Tipo: inteiro
- Obrigatorio

####      5.2.2.1.2.3 months -> data -> values -> products -> tickets -> gross_value
> Esse elemento faz parte do elemento "tickets"
> Total de venda bruta do vendedor no mes

- Tipo: decimal
- Obrigatorio

####      5.2.2.1.2.4 months -> data -> values -> products -> tickets -> net_value
> Esse elemento faz parte do elemento "tickets"
> Total de venda liquida do vendedor no mes

- Tipo: decimal
- Obrigatorio


Exemplo:
```
"months" : [ {
  "month" : 1,
  "data" : [ {
    "day" : 1,
    "values" : [ {
      "products" : [ {
        "barcode" : "123456789",
        "employers" : [ {
          "cpf" : "1223242342",
          "quantity" : 30.0,
          "gross_value" : 12132.0,
          "net_value" : 12121.0
        } ],
        "tickets" : [ {
          "cpf" : "1223242342",
          "quantity" : 30.0,
          "gross_value" : 12132.0,
          "net_value" : 12121.0
          } ]
        } ]
      } ]
    } ]
  } ]
  ```
