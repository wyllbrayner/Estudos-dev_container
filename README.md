# Criar novo projeto usando devcontainer com VS Code
__OBS:__ _este guia desmonstrará a criação de um ambiente de desenvolvimento python que servirá de base para a criação de qualquer outro projeto_

## Prerequisitos:
* VS Code instalado
    [veja procedimentos no endereço:]
    (https://code.visualstudio.com/download)
* Possuir a extenssão Dev Containers (desenvolvida pela Microsoft) instalada no VS Code.
* WSL2 instalado na máquina (se estiver usando Sistema Operacional diferente do Linux).
* Docker sendo executado na máquina e habilitado para usar o WSL2 (se estiver usando Sistema Operacional diferente do Linux).

## Criar devcontainer com VS Code
* Abra o VS Code.
* Aperte as teclas Ctrl + Shift + 'P' simultaneamente para abrir a Paleta de Comandos do VS Code.
* Na lista suspensa que aparecerá, selecione 'Dev Containers: Add Dev Containers Configuration Files...'.
* Na lista suspensa, escolha a inagem base para a criação do continer. Para nosso exemplo, digite Python e selecione a versão do python a ser utilizada na imagem (escolhi a versão 3.12-bullseye para este exemplo).
* Pode adicionar à imagem recursos adicionais, necessários para a aplicação ou ESC para avançar.

Ao final deste procedimento, será criada nova pasta .devcontainer na raiz do repositório e esta pasta possuirá um arquivo de configuração devcontainer.json 

## Abrir o devcontainer com VS Code
* Navegue, com o comando cd, até a pasta raiz do projeto (a pasta onde se encontra a subpasta .devcontainer).
* Aperte as telcas Ctrl + Shift + 'P' simultameamente para abrir a Paleta de Comandos do VS Code.
* Na lista suspensa aberta, selecione 'Dev Containers: Open Folder in Containers..' caso seja a primeira vez que suba o container ou seleciona 'Dev Containers: Rebuild Container', caso deseje acessar o ambiente já montado anteriormente.

__OBS-00:__ _É normal demorar um pouco mais a primeira vez que subir o ambiente, pois a imagem escolhida será baixada para a máquina do usuário._

__OBS-01:__ _Toda alteração realizada no arquivo devcontainer.json e/ou Dockerfile implicará em alteração no ambiente de desenvolvimento. Sendo assim. se o ambiente ja estiver em execução, será necessário atualizar o ambiente com as novas diretrizes com os seguintes passos:_
* _Aperte as telcas Ctrl + Shift + 'P' simultameamente para abrir a Paleta de Comandos do VS Code._
* _Na lista suspensa aberta, selecione 'Dev Containers: Rebuild Container'._

## Testar o ambiente devcontainer
* Abra o terminal do VS Code e notará que estará que o caminho do seu terminal estará diferente. Algo como, 'vscode ->/worksparces/nome_da_pasta (master) $'

## Sair do ambiente devcontainer
* Aperte as telcas Ctrl + Shift + 'P' simultameamente para abrir a Paleta de Comandos do VS Code.
* Na lista suspensa aberta, selecione 'Dev Containers: Reopen Folder Locally'. Este comando encerrará o ambiente de desenvolvimento criado pelo devcontainer e retornará para o ambiente local original.

Como o Dev Container cria um container para o desenvolvedor com todo o ambiente necessário para seu trabalho. Este container pode ser acessado como qualquer outro container docker em execução na máquina host.
Fora do Dev Container, execute:
* docker container ls -a (para listar os containers em execução);
* docker container exec -ti quatro_primeiros_digitos_do_id_do_container bash;
* navegue pelas pastas até identificar a pasta do projeto.

<f0oter>
    <p> As dicas deste documentos foram baseadas no post <a href='https://medium.com/marvelous-mlops/how-to-start-with-dev-containers-1e92bf0e0f78'>How To Start With Dev Containers</a>.
    </p>
</f0oter>