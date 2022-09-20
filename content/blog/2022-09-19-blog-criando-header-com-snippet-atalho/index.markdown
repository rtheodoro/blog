---
title: Criando um snippet (atalho) para header (cabeçalho)
subtitle: 2 min. de leitura.
author: 'rtheodoro'
date: '2022-09-19'
slug: []
categories: ["r", "snippet", "atalhos", "rstudio"]
tags: ["r", "rstudio", "snippet"]
---

Hoje vou ensinar vocês a criarem um atalho em seu `RStudio` para já definir um `header` (cabeçalho) para o seu script, assim você evita ter que digitar várias vezes os mesmos textos sempre que criar um novo script.

O exemplo de `header` a ser criado, vai ser esse:

```r
	#--------------------------------------------------------------------------#
	#
	# Nome do Script: 
	#
	# Objetivo:
	#
	# Autor: Ricardo Theodoro
	# Email: rtheodoro@usp.br
	# Data da criação: 20/09/2022
	# 
	#--------------------------------------------------------------------------#
	#
	# Notas:
	#   
	#--------------------------------------------------------------------------#
	options(scipen = 6, digits = 4)
	#--------------------------------------------------------------------------#
```

Assim, com um único comando eu evito digitar todo esse texto.

Para isso, o primeiro passo é abrir seu `RStudio`, ir em `Tools (Ferramentas)` -> `Global Options (Opções Globais)` -> `Code (Código)` -> `Edit Snippets (Editar Snippets)`.


Irá abrir uma tela como a de baixo:
![](snippet_original.png)
Então, você irá rolar a tela até o final e adicionar o seguinte código:


```r
snippet header
	#--------------------------------------------------------------------------#
	#
	# Nome do Script: 
	#
	# Objetivo:
	#
	# Autor: Seu Nome
	# Email: Seu Email
	# Data da criação: `r paste(Sys.Date())`
	# 
	#--------------------------------------------------------------------------#
	#
	# Notas:
	#   
	#--------------------------------------------------------------------------#
	options(scipen = 6, digits = 4)
	#--------------------------------------------------------------------------#
```

E clicar em Save (Salvar).

Ficará parecido com a imagem abaixo:

![](snippet_editado.png)

Feito isso, sempre que você digitar `header` e apertar `TAB`, o `RStudio` irá preencher estas linhas automaticamente!

Você pode usar o `snippet` para vários atalhos, como para criar separações de um  rascunho, por exemplo, com:


```r
snippet rascunho
  # Pacotes usados ----------------------------------------------------------
  library(dplyr)
  library(magrittr)
  library(ggplot2)

  # Importar dados ----------------------------------------------------------


  # Tratar dados ------------------------------------------------------------


  # Estatisticas Descritivas ------------------------------------------------


  # Visualizacao dos dados --------------------------------------------------
```

Para isso, basta adicionar o código acima, embaixo do snippet que você adicionou anteriormente. Então, não irá precisar digitar  todoaquele texto novamente.

**DETALHE:** Não se esqueça do `TAB` nas linhas embaixo do `snippet nome_atalho`.

Outro atalho legal de se adicionar, é seguinte:


```r
snippet dset
	${1:dataset} <- ${1:dataset} |> 
	  ${0}
```

Assim, quando você digitar `dset` e apertar `TAB`, já irá aparecer essa estrutura de pipes. Os dois nomes de dataset irão se alterar sozinhos, e o cursor irá pular para a função após o pipe.


```r
dataset <- dataset |> 
```

Sobre o `dset`, veja o segundo link abaixo.

Esse post foi inspirado nas postagens: [My easy R script header template](https://timfarewell.co.uk/my-r-script-header-template/) e [The Best Rstudio Snippet Ever!](https://rtask.thinkr.fr/the-best-rstudio-snippet-ever/)

