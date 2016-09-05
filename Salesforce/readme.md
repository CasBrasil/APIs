#Documento Salesforce

##Intro

Essa documentação visa auxiliar na configuração válida dos arquivos para envio para CasBrasil utilizando a API v0.0.1

##Parametros

###token
####Tipo: Varchar
####Tamanho: 256

Exemplo:
`ewogICJ0b2tlbiIgOiAicXV3aWhlaW91c2Rob2lhdXNncnl1d3FnZXJ1b3lxd2dleXVxd2dydXlxd2dydXlxd2dyZG9uc2E7b3F3ZW8iLAogICJjbnBqIiA6ICIxMjM0NTY3ODkwMTIzNCIsCiAgInllYXIiIDogIjIwMTYiLAogICJkYXRhIiA6IFsgewogICAgIm1vbnRoIiA6IDEsCiAgICAiZmllbGRzIiA6IFsgewogICAgICAiaWQiIDogMSwKICAgICAgInZhbHVlIiA6IDEwMDAwLjAKICAgIH0sIHsKICAgICAgImlkIiA6IDIsCiAgICAgICJ2YWx1ZSIgOiAyMDAwMC4wMQogICAgfSBdCiAgfSwgewogICAgIm1vbnRoIiA6IDIsCiAgICAiZmllbGRzIiA6IFsgewogICAgICAiaWQiIDogMSwKICAgICAgInZhbHVlIiA6IDEwMDAwLjAKICAgIH0sIHsKICAgICAgImlkIiA6IDIsCiAgICAgICJ2YWx1ZSIgOiAyMDAwMC4wMQogICAgfSBdCiAgfSBdCn0`,
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