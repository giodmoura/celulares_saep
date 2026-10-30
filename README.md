# 📱 Sistema de Assistência Técnica

<p align="center">
  <strong>Gerenciamento de clientes, aparelhos e agendamentos de reparos.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.13.1-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Flask-3.0.3-000000?style=for-the-badge&logo=flask&logoColor=white" />
  <img src="https://img.shields.io/badge/MySQL-8.0-4479A1?style=for-the-badge&logo=mysql&logoColor=white" />
  <img src="https://img.shields.io/badge/JavaScript-Vanilla-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" />
</p>

---

## Sobre o projeto

O **Sistema de Assistência Técnica** é uma aplicação web desenvolvida para facilitar a organização e o gerenciamento de uma assistência técnica de celulares.

A plataforma centraliza o cadastro de clientes e aparelhos, permitindo controlar os serviços de reparo e acompanhar os agendamentos realizados.

O sistema conta com autenticação de usuários, validação de informações e integração com um banco de dados MySQL, proporcionando uma administração mais organizada dos atendimentos.

## Funcionalidades

**01. Autenticação**
- Login com usuário e senha.
- Proteção das páginas por sessão.
- Expiração automática da sessão após 30 minutos.
- Encerramento seguro do acesso.

**02. Clientes**
- Cadastro de clientes.
- Consulta e pesquisa de registros.
- Edição e exclusão de informações.
- Validação de CPF e e-mail.
- Armazenamento do CPF utilizando hash bcrypt.

**03. Aparelhos**
- Cadastro de celulares vinculados aos clientes.
- Registro de marca, modelo, IMEI, cor e defeito.
- Validação de IMEI com 15 dígitos.
- Edição e exclusão de aparelhos.
- Verificação de IMEI duplicado.

**04. Agendamentos**
- Cadastro de reparos.
- Seleção de aparelhos e serviços.
- Definição de data e horário.
- Listagem organizada por data.
- Reagendamento de serviços.
- Controle de status dos atendimentos.

## Tecnologias

| Tecnologia | Utilização |
|---|---|
| Python | Lógica e processamento do sistema |
| Flask | Framework para aplicação web |
| MySQL | Banco de dados relacional |
| HTML5 | Estrutura das páginas |
| CSS3 | Estilização da interface |
| JavaScript | Interatividade e integração com a API |
| bcrypt | Geração e verificação de hashes |
| MySQL Connector | Comunicação com o banco de dados |

## Arquitetura do projeto

A aplicação foi organizada em módulos para separar as responsabilidades e facilitar a manutenção do código.

```text
Sistema_Assistencia_Celulares/
│
├── sistema/
│   ├── app.py
│   ├── rotas.py
│   ├── db.py
│   ├── autenticacao.py
│   ├── clientes.py
│   ├── aparelhos.py
│   ├── agendamento.py
│   ├── testar_conexao.py
│   ├── requirements.txt
│   │
│   ├── static/
│   │   ├── app.js
│   │   └── style.css
│   │
│   └── templates/
│       ├── login.html
│       ├── principal.html
│       ├── clientes.html
│       ├── aparelhos.html
│       └── agendamentos.html
│
├── assistencia_db.sql
├── der.pdf
├── GUIA.pdf
└── Saep.pdf
```

## Banco de dados

O projeto utiliza o MySQL para armazenar os dados da aplicação.

O banco de dados `assistencia_db` possui cinco tabelas principais:

- `usuarios` — informações de acesso ao sistema.
- `clientes` — dados dos clientes cadastrados.
- `aparelhos` — informações dos celulares recebidos.
- `servicos` — serviços e valores disponíveis.
- `agendamentos` — registros dos reparos programados.

Os relacionamentos entre as tabelas permitem manter os dados associados corretamente, evitando inconsistências nos cadastros.

## Segurança e validações

Alguns mecanismos implementados no sistema:

- Hash bcrypt para armazenamento de senhas e CPFs.
- Consultas SQL parametrizadas.
- Validação de CPF com 11 dígitos.
- Verificação de IMEI com 15 dígitos.
- Identificação de registros duplicados.
- Controle de acesso por sessão.
- Restrições de exclusão para registros relacionados.

## Como executar

### Pré-requisitos

- Python 3.10 ou superior.
- MySQL Server 8.0 ou superior.
- MySQL Workbench (opcional).

### 1. Clone o repositório

```bash
git clone URL_DO_REPOSITORIO
```

### 2. Acesse a pasta do projeto

```bash
cd Sistema_Assistencia_Celulares
```

### 3. Crie o banco de dados

Execute o arquivo `assistencia_db.sql` pelo MySQL Workbench ou, no terminal, a partir da pasta principal:

```bash
mysql -u root -p < assistencia_db.sql
```

**Atenção:** o script recria o banco de dados, removendo uma versão anterior de `assistencia_db`.

### 4. Acesse a pasta do sistema

```bash
cd sistema
```

### 5. Crie um ambiente virtual

```bash
python -m venv venv
```

Ative o ambiente virtual:

**Windows:**
```bash
venv\Scripts\activate
```

**Linux / macOS:**
```bash
source venv/bin/activate
```

### 6. Instale as dependências

```bash
pip install -r requirements.txt
```

### 7. Configure as variáveis de ambiente

**Windows (PowerShell):**

```powershell
$env:DB_USER="root"
$env:DB_PASSWORD="SUA_SENHA"
$env:SECRET_KEY="SUA_CHAVE_SECRETA"
```

**Linux / macOS:**

```bash
export DB_USER=root
export DB_PASSWORD="SUA_SENHA"
export SECRET_KEY="SUA_CHAVE_SECRETA"
```

### 8. Inicie a aplicação

```bash
python app.py
```

Acesse pelo navegador:

`http://localhost:5000`

## Acesso para testes

O banco de dados disponibiliza os seguintes usuários de demonstração:

| Usuário | Senha |
|---|---|
| admin | admin123 |
| carlos | carlos123 |
| ana | ana12345 |

## Objetivo acadêmico

Este projeto foi desenvolvido com o propósito de aplicar conhecimentos de desenvolvimento web, programação em Python, integração com banco de dados, manipulação de informações e segurança de aplicações.

Durante sua construção, foram trabalhados conceitos de organização de código, operações CRUD, relacionamento entre tabelas, autenticação e desenvolvimento de APIs.

---

<p align="center">
  Desenvolvido como projeto acadêmico de Desenvolvimento de Sistemas.
</p>

<p align="center">
  <strong>Sistema de Assistência Técnica de Celulares</strong>
</p>
