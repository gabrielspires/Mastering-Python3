# Mastering-Python3 <!-- omit in toc -->
Um guia pelas várias funcionalidades do Python3.5, com exemplos de códigos e tutoriais.

## Table of Contents <!-- omit in toc -->
- [Parte 1 - Um ambiente por projeto](#parte-1---um-ambiente-por-projeto)
  - [Criando seu primeiro venv](#criando-seu-primeiro-venv)
    - [Resumo](#resumo)
  - [Argumentos do venv](#argumentos-do-venv)

## Parte 1 - Um ambiente por projeto

Muitas vezes um projeto precisa de uma versão específica de um pacote ou então de muitos pacotes. Para evitar que projetos entrem em conflito ou então que sua máquina fique cheia
de coisas instaladas desnecessáriamente, podemos usar ambientes virtuais que isolam os
projetos e possibilitam que pacotes sejam instalado localmente, de forma que apenas aquele
projeto enxergue o que foi instalado.

Por padrão os pacotes globais são escondidos do ambiente virtual, ou seja, seu projeto não irá enxergar os pacotes instalados na sua máquina fora do ambiente virtual. Um benefício disso é que é mais fácil listar todos os pacotes instalados no ambiente, basta usar `pip freeze`. Um ponto negativo é que alguns pacotes mais pesados como `numpy` precisarão ser instalados toda vez para cada projeto que utilizá-los. Essa opção pode ser alterada para que o projeto enxergue os pacotes globais, o que pode ser útil ao se utilizar extensões de C/C++ por exemplo, mas isso varia de projeto para projeto.

### Criando seu primeiro venv

O comando para criar o ambiente é `pyvenv DIRETORIO_DO_NOVO_AMBIENTE_VIRTUAL`, caso esse comando não funcione, pode ser que o script do pyvenv esteja localizado em `Tools/Scripts` ao invés de `Scripts` no diretório de instalação do python, nesse caso o comando pode ser rodado com `python3 -m venv DIRETORIO_DO_NOVO_AMBIENTE_VIRTUAL`, ou então é possível copiar o script para a pasta certa. Caso o script nem esteja lá é possível que seja necessário instalá-lo, faça isso com o comando `sudo apt-get install python3-venv` ou o equivalente de sua distro.

Para ativar o ambiente use o comando `. ./DIRETORIO_DO_NOVO_AMBIENTE_VIRTUAL/bin/activate`, note que existe um espaço entre o primeiro e o segundo ponto.


#### Resumo
Instalar o venv: `sudo apt-get install python3-venv`
Criar o ambiente virtual: `python3 -m venv DIRETORIO_DO_NOVO_AMBIENTE_VIRTUAL`
Ativar o ambiente virtual: `. ./DIRETORIO_DO_NOVO_AMBIENTE_VIRTUAL/bin/activate`


### Argumentos do venv

Com os comandos acima conseguimos criar um ambiente virtual padrão, mas existem argumentos que podem ser úteis.

| Parâmetro | Descrição |
|---|---|
| --system-site-packages | Dá ao ambiente virtual acesso ai diretório `system-site-packages` |
| --symlinks | Tenta usar `symlinks` ao invés de cópias quando `symlinks` não são o padrão da plataforma |
| --copies | O contrário do comando acima |
| --clear | Exclui o conteúdo do diretório do ambiente, se existir, antes de criar o ambiente |
| --upgrade | Atualiza o diretório do ambiente para usar essa versão do Python, assumindo que o Python tenha sido atualizado in-place |
| --without-pip | Pula a instalação ou atualização do `pip` no ambiente virtual, que é carregado por padrão |