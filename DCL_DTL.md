```sql

-- Criando usuários
CREATE USER administrador WITH PASSWORD 'admin123';
CREATE USER farmaceutico WITH PASSWORD 'farm123';

-- DCL
GRANT ALL PRIVILEGES ON SCHEMA public TO administrador;
GRANT ALL PRIVILEGES ON ALL TABLES IN SCHEMA public TO administrador;
GRANT ALL PRIVILEGES ON ALL SEQUENCES IN SCHEMA public TO administrador;

GRANT USAGE ON SCHEMA public TO farmaceutico;
GRANT SELECT ON ALL TABLES IN SCHEMA public TO farmaceutico;

ALTER DEFAULT PRIVILEGES IN SCHEMA public
    GRANT SELECT ON TABLES TO administrador;

ALTER DEFAULT PRIVILEGES IN SCHEMA public
    GRANT SELECT ON TABLES TO farmaceutico;


-- DTL
BEGIN;

SAVEPOINT ponto1;

INSERT INTO produto (nome_produto, qtd_produto, valor_produto) VALUES
('Condicionador Pantene', 60, 10.90);

ROLLBACK TO SAVEPOINT ponto1;

COMMIT;