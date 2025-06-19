 #Data Definition Language
## ddl

```sql

CREATE TABLE colaborador (
    id_colaborador SERIAL PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    cargo VARCHAR(50) NOT NULL,
    rg VARCHAR(14) UNIQUE NOT NULL,
    data_nascimento DATE NOT NULL, 
    id_farmacia INTEGER NOT NULL REFERENCES farmacia(id_farmacia)
);

CREATE TABLE cliente (
    id_cliente SERIAL PRIMARY KEY,
    nome_cliente VARCHAR(50) NOT NULL,
    rg VARCHAR(14) UNIQUE NOT NULL,
    data_nascimento DATE NOT NULL,
    id_endereco INTEGER REFERENCES endereco(id_endereco)
);

CREATE TABLE produto (
    id_produto SERIAL PRIMARY KEY,
    nome_produto VARCHAR(50) NOT NULL,
    qtd_produto INT NOT NULL,
    valor_produto DECIMAL(6, 2) NOT NULL
);

CREATE TABLE farmacia(
    id_farmacia SERIAL PRIMARY KEY,
    cnpj VARCHAR(14) UNIQUE NOT NULL,
    nome_fantasia VARCHAR(50) NOT NULL,
    razao_social VARCHAR(50) NOT NULL,
    telefone VARCHAR(14) UNIQUE NOT NULL,
);

CREATE TABLE endereco (
    id_endereco SERIAL PRIMARY KEY,
    logradouro VARCHAR(50) NOT NULL,
    numero VARCHAR(10) NOT NULL,
    complemento VARCHAR(100),
    bairro VARCHAR(50),
    cidade VARCHAR(50) NOT NULL,
    estado VARCHAR(2) NOT NULL,
    cep VARCHAR(9) NOT NULL,
    -- caso nenhum for inserido o campo será preenchido com residecial
    tipo VARCHAR(20) NOT NULL DEFAULT 'Residencial' 
    -- aceita apenas dois tipos "Comercial" e "Residencial" 
        CHECK (tipo IN ('Comercial','Residencial')),  
    id_farmacia INTEGER REFERENCES farmacia(id_farmacia),
    CHECK (
        (id_cliente IS NOT NULL AND id_farmacia IS NULL) OR
        (id_cliente IS NULL AND id_farmacia IS NOT NULL))
);

CREATE TABLE farmacia_produto (
    id_farmacia INTEGER NOT NULL REFERENCES farmacia(id_farmacia),
    id_produto INTEGER NOT NULL REFERENCES produto(id_produto),
    PRIMARY KEY (id_farmacia, id_produto)
);

CREATE TABLE farmacia_cliente (
    id_farmacia INTEGER NOT NULL REFERENCES farmacia(id_farmacia),
    id_cliente INTEGER NOT NULL REFERENCES cliente(id_cliente)
    PRIMARY KEY (id_farmacia, id_cliente)
);

```





