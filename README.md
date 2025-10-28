
<!-- README.md is generated from README.Rmd. Please edit that file -->

# demandacarros

<!-- badges: start -->

[![Lifecycle:
experimental](https://img.shields.io/badge/lifecycle-experimental-orange.svg)](https://lifecycle.r-lib.org/articles/stages.html#experimental)
<!-- badges: end -->

A ideia aqui é desenhar o processo de estimar a demanda por carros novos
no Brasil. A ideia é rodar um BLP bem próximo do artigo original. A
equação principal deve ser algo nesse sentido:

q\_{ji} = f(p\_j, X\_j, v\_i)

A ideia é que a quantidade consumida do carro de modelo *j* seja função
de:

1.  p\_j: Preço do modelo *j*;
2.  X\_j: Características observáveis do modelo *j*;
3.  v\_i: Características observáveis do consumidor *i*.

> Rever essas notações.

Em função disso, vamos precisar 4 dados diferentes e de fontes diversas.

| Informação                     | Fonte                         |
| ------------------------------ | ----------------------------- |
| Quantidade                     | Fenabrave                     |
| Preço                          | Fipe                          |
| Caracteísticas dos modelos     | icarros + fichatecnica.com.br |
| Caracteísticas dos consumidors | PNADc                         |

![](plano.png)

``` r
library(carrosbr)
#> Loading required package: fenabrave
#> Loading required package: fipe
# p_j
precos <- precos_fipe
head(precos)
#>   montadora modelo  ano  preco
#> 1      audi     a3 2003  49239
#> 2      audi     a3 2004  52329
#> 3      audi     a3 2005  61664
#> 4      audi     a3 2006  64991
#> 5       bmw     x1 2022 284474
#> 6       bmw     x1 2023 301838

# q_j
quantidades <- emplacamento_anual
head(quantidades)
#>         tipo montadora  modelo quantidade  ano
#> 1    veiculo        VW     GOL     180073 2003
#> 2 utilitario      FIAT  STRADA      27921 2003
#> 3    veiculo      FIAT   PALIO     118756 2003
#> 4 utilitario        VW SAVEIRO      16097 2003
#> 5    veiculo        GM   CELTA     114690 2003
#> 6 utilitario        GM     S10      14111 2003
```
