 #Data Definition Language
## ddl

```sql

CREATE TABLE farmacia(
    CNPJ SERIAL PRIMARY KEY,
    nome_fantasia VARCHAR(100) NOT NULL,
    razao_social VARCHAR(100) NOT NULL,
    telefone VARCHAR(14) UNIQUE NOT NULL,
    
);
CREATE TABLE colaboradores (
    id_colaborador SERIAL PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    cargo VARCHAR(50) NOT NULL,
    rg VARCHAR(14) UNIQUE NOT NULL,
    data_nascimento DATE NOT NULL

);

CREATE TABLE cliente (
    id_cliente SERIAL PRIMARY KEY,
    nome cliente VARCHAR(100) NOT NULL,
    rg VARCHAR(100) NOT NULL,
    data_nascimento DATE NOT NULL

);

CREATE TABLE endereco (
   
    id_endereco SERIAL PRIMARY KEY,
    logradouro VARCHAR(100) NOT NULL,
    numero VARCHAR(10) NOT NULL,
    complemento VARCHAR(100),
    bairro VARCHAR(100),
    cidade VARCHAR(100) NOT NULL,
    estado VARCHAR(2) NOT NULL,
    cep VARCHAR(9) NOT NULL,
    tipo VARCHAR(20) NOT NULL CHECK (tipo IN ('Comercial','Residencial')) DEFAULT 'Residencial'
    
);

CREATE TABLE produtos (
    id_produto SERIAL PRIMARY KEY,
    nome_produto VARCHAR(100) NOT NULL,
    qtd_produto INT (100) NOT NULL,
    valor_produto DECIMAL(6, 2) NOT NULL,


);

```





