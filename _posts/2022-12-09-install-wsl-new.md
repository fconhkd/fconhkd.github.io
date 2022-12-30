---
title: Instalar o Linux no Windows com o WSL (Build 19041 ou superior)
date: 2022-12-09 19:55:00 -0300
categories: [Procedimento, WSL]
tags: [wsl, linux, virtual-machine]
pin: false
---

## Pré-requisitos
Você deve estar executando o Windows 10 versão 2004 ou superior (Build 19041 ou superior) ou o Windows 11 para usar os comandos abaixo. Se você estiver em versões anteriores, consulte a página de instalação manual.


## Instalar o WSL no Windows
### Instalar o WSL por linha de comando
Abra o PowerShell ou o Prompt de Comando do Windows no modo de administrador clicando com o botão direito do mouse e selecionando "Executar como administrador"; insira o comando wsl --install e reinicie o computador.
```powershell
wsl --install
```
Esse comando habilitará os recursos necessários para executar o WSL e instalar a distribuição Ubuntu do Linux.


### Instalar o WSL pela Windows Store
Abra o aplicativo do [Windows Store](https://apps.microsoft.com/store/apps), pesquise por Ubuntu e clique em `Obter o aplicativo da Store`


### Verificar a versão do WSL que você está executando
Você pode listar suas distribuições do Linux instaladas e verificar a versão do WSL para a qual cada uma está definida inserindo o comando: `wsl -l -v` no PowerShell ou Prompt de Comando do Windows.
```powershell
wsl -l -v
```


## Atualizar a versão do WSL 1 para o WSL 2
As novas instalações do Linux, instaladas usando o comando `wsl --install`, serão definidas como WSL 2 por padrão.

O comando `wsl --set-version` pode ser usado para fazer downgrade do WSL 2 para o WSL 1 ou atualizar as distribuições do Linux instaladas anteriormente do WSL 1 para o WSL 2.

Para mudar de versão, use o comando: `wsl --set-version <distro name> 2` substituindo `<distro name>` pelo nome da distribuição do Linux que você quer atualizar. Por exemplo, `wsl --set-version Ubuntu-20.04 2` definirá sua distribuição do Ubuntu 20.04 para usar o WSL 2.


## Remover uma distribuição Linux WSL
Aqui está o que você precisa fazer.

1. Abra o PowerShell.
2. Para obter o nome exato da distribuição desejada, digite `wsl -l -v`
3. Entre no terminal `wsl --unregister <nome da distribuição>`.
```powershell
wsl --unregister <nome da distribuição>
```

## Fazer backup e importar para o WSL
O backup é um processo bastante simples que envolve a exportação para um arquivo .tar, os principais comandos necessários são os seguintes:
```powershell
# exportar uma distro
wsl --export <distro> <filename.tar>

# importar uma distro
wsl --import <distro> <install location=""> <filename> </filename></install></distro></filename.tar></distro>
```

## Acessar os arquivos da distro Linux instalada no WSL pelo Windows Explorer
O acesso aos arquivos das distribuições Linux instaladas através do WSL já era possível desde a versão 1903 do Windows 10, só que agora está muito mais facil.
1. Abrir o executar
2. Digite o comando: `\\wsl.localhost`
3. Uma janela do Windows Explorer vai abrir e vocÊ pode escolher qual distro quer acessar.


Espero que o resumo acima seja util.

`“Passarinho que acompanha morcego, acorda de cabeça para baixo e perde o canto”`{: .right }
