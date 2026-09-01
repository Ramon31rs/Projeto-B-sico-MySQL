# Projeto-B-sico-MySQL

# 🏦 Sistema de Gerenciamento de Contas Bancárias

Este projeto consiste em um modelo de banco de dados relacional MySQL simplificado para gerenciamento e armazenamento de informações de contas bancárias de usuários.

---

## 📌 Estrutura do Banco de Dados

O banco de dados possui uma tabela principal chamada **`contas`**, projetada para registrar os dados cadastrais e financeiros de cada titular.

### 🛠️ Tabela `contas`

| Campo | Tipo | Descrição | Restrições |
| :--- | :--- | :--- | :--- |
| `id` | `INT` | Identificador único da conta | Primary Key, Auto Increment |
| `nome` | `VARCHAR(100)` | Primeiros nomes do titular | - |
| `sobrenome` | `VARCHAR(100)` | Sobrenome do titular | - |
| `saldo` | `INT` | Saldo atual disponível na conta | Indexado (`index_saldo`) |
| `data_nascimento` | `DATE` | Data de nascimento do titular | - |

> ⚡ **Otimização:** A coluna `saldo` possui um índice dedicado (`index_saldo`) para otimizar a velocidade de consultas avançadas, ordenações e filtragens por faixa de valores.

---

## 🚀 Como Importar e Executar o Projeto

Você pode importar esta base de dados utilizando o **MySQL Workbench** ou via **linha de comando**.

### 1. Usando o MySQL Workbench (Interface Gráfica)
1. Abra o MySQL Workbench e conecte-se ao seu servidor local.
2. No menu superior, acesse **Server** > **Data Import**.
3. Selecione a opção **Import from Self-Contained File** e escolha o arquivo `.sql` deste repositório.
4. Em **Default Target Schema**, escolha o banco de dados de destino (ou crie um novo chamado `banco`).
5. Clique em **Start Import**.

### 2. Usando o Terminal / Linha de Comando
Crie o banco de dados no MySQL e execute o comando de importação:

```bash
# 1. Acesse o MySQL e crie o banco de dados
mysql -u seu_usuario -p -e "CREATE DATABASE IF NOT EXISTS banco;"

# 2. Importe o arquivo dump.sql para a base recém-criada
mysql -u seu_usuario -p banco < seu_arquivo.sql
