---
title: Introdução ao uso do VS Code com o WSL
date: 2023-06-19 22:11:00 -0300
categories: [Tutoriais, Visual Studio Code]
tags: [vscode, wsl, tutorial, developer]
pin: false
---

## Pré-requisitos

As instruções pressupõe que você já sabe utilizar o WSL, e que esteja conectado com privilégios.

## Introdução

Visual Studio Code, juntamente com a extensão WSL, permite que você use o WSL como seu ambiente de desenvolvimento em tempo integral diretamente do VS Code. Você pode:

- desenvolver em um ambiente baseado em Linux
- usar ferramentas e utilitários específicos do Linux
- executar e depurar seus aplicativos baseados em Linux a partir do conforto do Windows, mantendo o acesso a ferramentas de produtividade como o Outlook e o Office
- usar o terminal interno do VS Code para executar sua distribuição de opções do Linux


## Instalar o Visual Studio Code e a extensão WSL

- Visite a [página de instalação do VS Code](https://code.visualstudio.com/download) e selecione o instalador de 32 ou 64 bits. Instale Visual Studio Code no Windows (não no sistema de arquivos WSL).

- Quando solicitado a selecionar tarefas adicionais durante a instalação, verifique a opção Adicionar ao PATH para que você possa abrir facilmente uma pasta no WSL usando o comando de código.

- Instale o [pacote de extensão de Desenvolvimento Remoto](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack). Esse pacote de extensão inclui a extensão WSL, além das extensões Remote - SSH e Dev Containers, permitindo que você abra qualquer pasta em um contêiner, em um computador remoto ou no WSL.

## Atualizar sua distribuição do Linux

Algumas distribuições do WSL Linux não têm bibliotecas necessárias para iniciar o servidor VS Code. Você pode adicionar bibliotecas adicionais à distribuição do Linux usando o gerenciador de pacotes.

Por exemplo, para atualizar o Debian ou o Ubuntu, use:
```bash
sudo apt-get update
```

Para adicionar wget (para recuperar conteúdo de servidores Web) e certificados ca (para permitir que aplicativos baseados em SSL verifiquem a autenticidade das conexões SSL), insira:
```bash
sudo apt-get install wget ca-certificates
```

## Abrindo um projeto WSL no Visual Studio Code

### Na linha de comando

Para abrir um projeto da distribuição WSL, abra a linha de comando da distribuição e insira: `code .`

![cmd-vscode](https://learn.microsoft.com/pt-br/windows/wsl/media/wsl-open-vs-code.gif)

### No Visual Studio Code

Você também pode acessar mais opções de WSL do VS Code usando o atalho: `CTRL+SHIFT+P` no VS Code para criar a paleta de comandos. Se você digitar WSL, verá uma lista das opções disponíveis, permitindo que você reabra a pasta em uma sessão WSL, especifique em qual distribuição deseja abrir e muito mais.

![vscode-vscode](https://learn.microsoft.com/pt-br/windows/wsl/media/vscode-remote-command-palette.png)

Pronto, agora você usufluir do melhor dos dois mundos.

> Em maquina windows com o wsl ao invocar o comando `code .` na pasta do projeto ele vai abrir em modo remoto. 🤞


