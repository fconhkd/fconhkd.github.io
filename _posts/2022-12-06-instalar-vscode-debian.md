---
title: Como instalar o Visual Studio Code no Debian 10
date: 2022-12-06 20:55:00 -0300
categories: [Tutoriais, Visual Studio Code]
tags: [vscode, debian, tutorial, developer]
pin: false
---

## Pré-requisitos

As instruções pressupõe que você esteja conectado como um usuário com privilégios.


## Instalando o Visual Studio Code no Debian

Eu tentei instalar o arquivo `.deb` que baixei, mas não deu muito certo, então tive de habilitar o repósitório e instalar o pacote através da linha de comando:

1. Atualizar o indice de pacotes e instalar as dependências:
```shell
sudo apt update
sudo apt install gnupg2 software-properties-common apt-transport-https curl
```
2. Importe a chave GPG da Microsoft:
```shell
curl -sSL https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
```
3. Adicione o repositório do Visual Studio no sistema:
```shell
sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"
```
4. Instale o pacote:
```shell
sudo apt update
sudo apt install code
```

Pronto, o VSCode está instalado no Debian 10, você pode usá-lo.

> Em maquina windows com o wsl ao invocar o comando `code .` na pasta do projeto ele vai abrir em modo remoto. 🤞


