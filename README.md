
<!-- README.md is generated from README.Rmd. Please edit that file -->

# demandacarros

<!-- badges: start -->

[![Lifecycle:
experimental](https://img.shields.io/badge/lifecycle-experimental-orange.svg)](https://lifecycle.r-lib.org/articles/stages.html#experimental)
<!-- badges: end -->

A ideia aqui é desenhar o processo de estimar a demanda por carros novos
no Brasil. A ideia é rodar um BLP bem próximo do artigo original. A
equação principal deve ser algo nesse sentido:

  
![&#10;q\_{ji} = f(p\_j, X\_j,
v\_i)&#10;](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;%0Aq_%7Bji%7D%20%3D%20f%28p_j%2C%20X_j%2C%20v_i%29%0A
"
q_{ji} = f(p_j, X_j, v_i)
")  
A ideia é que a quantidade consumida do carro de modelo
![j](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;j
"j") seja função de:

1.  ![p\_j](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;p_j
    "p_j"): Preço do modelo
    ![j](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;j
    "j");
2.  ![X\_j](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;X_j
    "X_j"): Características observáveis do modelo
    ![j](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;j
    "j");
3.  ![v\_i](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;v_i
    "v_i"): Características observáveis do consumidor
    ![i](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D&space;%5Cbg_white&space;i
    "i").

> Rever essas notações.

Em função disso, vamos precisar 4 dados diferentes e de fontes diversas.

| Informação                     | Fonte                         |
| ------------------------------ | ----------------------------- |
| Quantidade                     | Fenabrave                     |
| Preço                          | Fipe                          |
| Caracteísticas dos modelos     | icarros + fichatecnica.com.br |
| Caracteísticas dos consumidors | PNADc                         |
