# **SomatiVEP_v01-2022** 
Pipeline para Anotação de Arquivo VCF utilizando o  Ensembl Variant Effect Predictor(VEP) version 105.0 via Google Colab

  ***SomatiVEP_v01** é de código aberto e está disponível no GitHub* 
  
  SomatiVEP_v01 precisa ter as seguintes coisas: 

    - Linguagens utilizadas: Bash e Python (version 3.11.10); 
    - Biblioteca Python: pandas; 
    - Boa conexão com internet; 
    - Conta no Google Colab; 
    - Espaço de armazenamento no Google Colab. 
  
* Introdução
* Preparação do Ambiente 
  * Criar diretórios 
  * Instalar Programas 
  * Adicionar Arquivos 
* Como utilizar?
  * Argumentos
  * Exemplo
* Contato    

> # **Introdução**

  Sejam bem-vindos bioinformatas! \
  SomatiVEP-v01 é uma script utilizado para você analisar os arquivos no formato VCF e filtrar as variantes de interesse de uma amostra de herança somática. Código foi criado de maneira que possa utilizar via Google Colab sem grandes dificuldades. 

> # **Preparação do Ambiente**

> ## *Criar diretórios*

  >> Crie uma conta no Google e acesse Google Colab 
  >> (disponível em: https://colab.research.google.com/#create=true)
  
  É necessário criar um espaço de diretórios para pode organizar seus arquivos input e output dentro do Google Colab. \
  Crie uma linha do código - Para linkar com ambiente nuvem:
  ```
  from google.colab import drive
  drive.mount('/content/drive')
  ```
  
> ## *Instalar Programas*

**A. Instalando VEP ensembl-vep-105.0 - via GitHub**

Link: https://github.com/Ensembl/ensembl-vep/tags \
Neste link vai ter o repositório não apenas da versão 105.0 do VEP, mas todas versões que desejar.

Use a linha de código para instalação:

```
%%bash
sudo apt install unzip curl git libmodule-build-perl libdbi-perl libdbd-mysql-perl build-essential zlib1g-dev
wget -c https://github.com/Ensembl/ensembl-vep/archive/refs/tags/105.0.tar.gz
tar -zxvf 105.0.tar.gz
cd ensembl-vep-105.0
./INSTALL.pl --NO_UPDATE
```

1. Instalar as dependências;
2. Download da release ensembl-vep 105.0 no GitHub;
3. Descompactar o arquivo .tar.gz;
4. Entrar dentro do diretório;
5. Rodar o Script INSTALL.PL com a opção -NO_UPDATE (para não perguntar se quero a versão mais nova).

Obs.: --NO_UPDATE é a função para não atualizar para versões mais novas.

*Tempo de Instalação: ~1 minuto*

**Verifivcação do VEP - executando o script `./vep`**

1. Entrei dentro do diretório ensembl-vep-105.0
2. Executei o script `./vep`

**B. Instalando biblioteca Pandas**

```
!pip install pandas
```
*Tempo de Instalação: ~30 segundos*

> ## *Adicionar Arquivos*
