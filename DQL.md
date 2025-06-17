#DQL

```sql
SELECT nome_cliente FROM cliente 
WHERE id_cliente='2';

SELECT * FROM cliente

SELECT nome_cliente, data_nascimento 
FROM cliente 
ORDER BY nome_cliente

SELECT nome_produto, qtd_produto 
FROM produto 
LIMIT 3

SELECT * FROM colaboradores
WHERE cargo = 'Atendente' AND
EXTRACT(YEAR FROM data_nascimento) = 1995;

SELECT * FROM colaboradores
WHERE cargo = 'Atendente' OR
EXTRACT(YEAR FROM data_nascimento) = 1997;

SELECT * FROM colaboradores
WHERE NOT cargo = 'Atendente' 

SELECT id_endereco 
FROM endereco
WHERE cidade IN ('São Paulo')

SELECT nome_cliente, data_nascimento
FROM cliente 
WHERE data_nascimento BETWEEN '1980-01-01' AND '2000-01-01'

SELECT nome_cliente
FROM cliente
WHERE nome_cliente LIKE'Fe%';

```