# 📁 Gerenciador de Arquivos em Python

Gerenciador de arquivos desenvolvido em **Python** para a disciplina de **Organização de Computadores**.

O projeto permite realizar operações básicas de manipulação do sistema de arquivos por meio de uma interface interativa no terminal, utilizando recursos nativos do Python para criação, leitura, cópia, renomeação e exclusão de arquivos e diretórios.

## 🎯 Objetivo

O objetivo do projeto é aplicar, na prática, conceitos relacionados à **manipulação do sistema de arquivos**, utilizando Python para interagir com arquivos e diretórios do sistema operacional.

A aplicação foi estruturada de forma modular, separando a interface do terminal das funções responsáveis pelas operações sobre o sistema de arquivos.

## ⚙️ Funcionalidades

O sistema disponibiliza as seguintes operações:

| Opção | Funcionalidade                     |
| ----- | ---------------------------------- |
| 1     | 📖 Ler arquivo                     |
| 2     | 📂 Listar arquivos de um diretório |
| 3     | ✏️ Renomear arquivo ou diretório   |
| 4     | 📄 Copiar arquivo                  |
| 5     | 📁 Copiar diretório                |
| 6     | ➕ Criar novo diretório             |
| 7     | 📝 Criar novo arquivo              |
| 8     | 🗑️ Excluir diretório              |
| 9     | 🗑️ Excluir arquivo                |
| 0     | 🚪 Encerrar o programa             |

As operações são realizadas diretamente sobre o sistema de arquivos da máquina em que o programa está sendo executado.

## 🛠️ Tecnologias utilizadas

* **Python 3**
* `pathlib`
* `os`
* `shutil`
* Terminal / CLI

O projeto utiliza principalmente bibliotecas nativas do Python, não sendo necessário instalar pacotes externos para sua execução.

## 📂 Estrutura do projeto

```text
Trabalho_OC_gerenciadorArquivos/
│
├── main.py
├── modulo_edilson.py
├── modulo_rafael_martins.py
├── modulo_rafael_naves.py
├── modulo_telas.py
├── README.md
└── .gitignore
```

### `main.py`

Responsável pelo **menu principal da aplicação** e pelo direcionamento das opções escolhidas pelo usuário.

O menu disponibiliza as operações de gerenciamento de arquivos e diretórios e encaminha cada opção para a tela correspondente.

### `modulo_edilson.py`

Contém funcionalidades relacionadas à:

* Listagem de arquivos;
* Criação de diretórios;
* Criação de arquivos.

O módulo utiliza `pathlib.Path` para manipulação dos caminhos e realização das operações no sistema de arquivos.

### `modulo_rafael_martins.py`

Responsável pelas operações de:

* Exclusão de arquivos;
* Leitura de arquivos;
* Renomeação de arquivos e diretórios.

Também possui tratamento de situações como arquivo inexistente, caminho inválido e tentativa de utilizar um nome que já existe.

### `modulo_rafael_naves.py`

Responsável pelas operações de:

* Exclusão de diretórios;
* Cópia de arquivos;
* Cópia de diretórios.

Para essas operações são utilizadas ferramentas da biblioteca `shutil`, como `copy2()` e `copytree()`.

### `modulo_telas.py`

Responsável pela **interface do usuário no terminal**.

O módulo apresenta os menus, recebe as entradas do usuário, chama as funções dos demais módulos e apresenta mensagens de sucesso ou erro.

Também possui uma interface com cores e cabeçalhos para tornar a utilização do programa mais organizada.

## 🚀 Como executar

### 1. Pré-requisitos

É necessário possuir o **Python 3** instalado na máquina.

Para verificar a instalação:

```bash
python --version
```

ou:

```bash
python3 --version
```

### 2. Clonar o repositório

```bash
git clone https://github.com/rafaelmartins0216-del/Trabalho_OC_gerenciadorArquivos.git
```

### 3. Acessar a pasta do projeto

```bash
cd Trabalho_OC_gerenciadorArquivos
```

### 4. Executar o programa

No Windows:

```bash
python main.py
```

No Linux/macOS:

```bash
python3 main.py
```

## 🖥️ Utilização

Após executar o programa, será apresentado um menu semelhante a:

```text
==================================================
######## SISTEMA DE ARQUIVOS - GRUPO V1.0 ########
==================================================

[ Operações em Arquivos ]
 [1] Ler Arquivo
 [2] Listar Arquivos
 [3] Renomear Arquivo/Diretório
 [4] Copiar Arquivo
 [5] Copiar Diretório

[ Criar ]
 [6] Criar Novo Diretório
 [7] Criar Novo Arquivo

[ Operações de Exclusão ]
 [8] Excluir Diretório
 [9] Excluir Arquivo

==================================================
 [0] Sair do Programa
==================================================
```

Basta informar o número correspondente à operação desejada.

Durante as operações, a opção **`V`** pode ser utilizada para retornar ao menu anterior em diversas telas.

## 🧩 Organização do código

O projeto foi dividido em módulos para separar as diferentes responsabilidades:

```text
                    ┌─────────────┐
                    │   main.py   │
                    │ Menu inicial│
                    └──────┬──────┘
                           │
                           ▼
                  ┌─────────────────┐
                  │ modulo_telas.py │
                  │ Interface CLI   │
                  └───────┬─────────┘
                          │
          ┌───────────────┼────────────────┐
          ▼               ▼                ▼
 ┌────────────────┐ ┌───────────────┐ ┌────────────────┐
 │modulo_edilson  │ │modulo_rafael_ │ │modulo_rafael_  │
 │                │ │   martins      │ │     naves      │
 ├────────────────┤ ├───────────────┤ ├────────────────┤
 │ Criar arquivo  │ │ Ler arquivo   │ │ Copiar arquivo │
 │ Criar diretório│ │ Excluir       │ │ Copiar diretório│
 │ Listar arquivos│ │ Renomear      │ │ Excluir diretório│
 └────────────────┘ └───────────────┘ └────────────────┘
```

Essa divisão permite que a interface e a lógica responsável pelas operações de arquivos permaneçam separadas.

## ⚠️ Observações

As operações de criação, cópia, renomeação e exclusão são realizadas **diretamente no sistema de arquivos**.

Por isso, recomenda-se utilizar o programa inicialmente em uma pasta de testes para evitar alterações ou exclusões acidentais de arquivos importantes.

Em especial, a opção de exclusão de diretórios utiliza uma operação recursiva, removendo também os arquivos e subdiretórios presentes dentro da pasta selecionada.

## 🎓 Contexto acadêmico

Este projeto foi desenvolvido como atividade prática da disciplina de **Organização de Computadores**, com o objetivo de aplicar conceitos de programação e manipulação de arquivos e diretórios utilizando Python.

Além da implementação das funcionalidades, o projeto possibilita compreender como uma aplicação pode interagir com recursos do sistema operacional por meio de bibliotecas de manipulação do sistema de arquivos.

## 👥 Equipe

* **Rafael Martins**
* **Edilson**
* **Rafael Naves**

## 📌 Status do projeto

**Concluído — projeto acadêmico.**

-
