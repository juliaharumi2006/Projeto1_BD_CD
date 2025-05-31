```sql

INSERT INTO colaborador (nome, cargo, rg, data_nascimento) VALUES
('Ana Paula Souza', 'Atendente', '123456789', '1995-08-15'),
('Carlos Eduardo Lima', 'Farmacêutico', '987654321', '1988-03-22'),
('Elenn Queiroz da Silva', 'Administrador', '456789123', '1989-12-09');

INSERT INTO cliente (nome_cliente, rg, data_nascimento) VALUES
('Fernanda Oliveira', '112233445', '2000-12-05'),
('João Pedro Ramos', '556677889', '1992-06-10'),
('Bruno Silva', '445567789', '1995-01-30'),
('Juliana Rocha', '667788990', '2001-07-12');

INSERT INTO produto (nome_produto, qtd_produto, valor_produto) VALUES
('Paracetamol 500mg', 200, 4.50),
('Dipirona 1g', 150, 3.80),
('Creme hidratante corporal Nivea', 50, 29.90),
('Shampoo Pantene', 60, 25.60);

INSERT INTO farmacia (cnpj, id_colaborador, nome_fantasia, razao_social, telefone) VALUES
('17514572000191', 1, 'Farma+', 'Farma Mais Comércio de Produtos Farmacêuticos Ltda', '(11)98765-4321'),
('12345678000100', 2, 'Saúde Já', 'Saúde Já Distribuidora de Medicamentos Ltda', '(21)99876-5432');

INSERT INTO endereco (id_cliente, id_farmacia, logradouro, numero, complemento, bairro, cidade, estado, cep, tipo) VALUES
(1, NULL, 'Rua das Flores', '123', 'Apto 101', 'Centro', 'São Paulo', 'SP', '01001-000', 'Residencial'),
(2, NULL, 'Rua do Sol', '789', NULL, 'Boa Vista', 'Recife', 'PE', '50050-000', 'Residencial'),
(3, NULL, 'Av. Independência', '321', 'Casa', 'São Cristóvão', 'Salvador', 'BA', '40020-000', 'Residencial'),
(4, NULL, 'Rua da Paz', '88', NULL, 'Jardim América', 'Goiânia', 'GO', '74043-010', 'Residencial'),
(NULL, 1, 'Av. Brasil', '456', NULL, 'Jardins', 'Rio de Janeiro', 'RJ', '20040-002', 'Comercial'), 
(NULL, 2, 'Av. das Nações', '1001', NULL, 'Setor Oeste', 'Brasília', 'DF', '70070-300', 'Comercial');


INSERT INTO farmacia_produto (id_farmacia, id_produto) VALUES 
(1, 1),
(1, 2),
(2, 3),
(2, 4);


INSERT INTO farmacia_cliente (id_farmacia, id_cliente) VALUES
(1, 1),
(1, 2),
(2, 3),
(2, 4);


```