---
title: Instalando R e RStudio no Linux Mint
subtitle: Fácil.
author: 'Ricardo Theodoro'
date: '2021-09-26'
slug: []
categories: []
tags: []
---


![Formspree Logo](linuxmint-logo.png)


O objetivo desta postagem é ensinar a instalar o R e o RStudio no Linux Mint.



# Instalando o R

O primeiro passo é instalar o R Base. Podemos fazer a instalação via terminal com os seguintes comandos (`ctrl+alt+t` para abrir o terminal):


```bash
sudo apt update -qq

sudo apt install --no-install-recommends software-properties-common dirmngr

# To verify key, run gpg --show-keys /etc/apt/trusted.gpg.d/cran_ubuntu_key.asc 

sudo wget -qO- https://cloud.r-project.org/bin/linux/ubuntu/marutter_pubkey.asc | sudo tee -a /etc/apt/trusted.gpg.d/cran_ubuntu_key.asc

sudo add-apt-repository "deb https://cloud.r-project.org/bin/linux/ubuntu $(lsb_release -cs)-cran40/"

sudo apt install --no-install-recommends r-base r-base-dev
```

O R também possui um repositório no Ubuntu, você pode tentar baixá-lo manualmente através da loja de aplicativos do Mint. Ou através do comando `sudo apt install r-base r-base-dev`.

Você pode ter mais detalhes consultando o README completo da instalação em <https://cloud.r-project.org/bin/linux/ubuntu/fullREADME.html>

# Instalando o RStudio

O RStudio não possui um repositório para ser adicionado ao sistema, temos que fazer a instalação manual pelo site:

<https://www.rstudio.com/products/rstudio/download/#download>

É só clickar em *rstudio-1.4.1717-amd64.deb*, ou na versão mais recente .deb, então será feito o download de um arquivo de instalação. Então é só clickar duas vezes para iniciar a instalação e clickar em avançar até o fim.

Ainda vou melhorar este post, foi só um teste.
