````sql
INSERT INTO farmacia (CNPJ, nome_fantasia, razao_social, telefone) VALUES
('17.514.572/0001-91', 'Farma+', 'Farma Mais Comércio de Produtos Farmacêuticos Ltda', '(11)98765-4321'),

INSERT INTO colaboradores (nome, cargo, rg, data_nascimento) VALUES
('Ana Paula Souza', 'Atendente', '12.345.678-9', '1995-08-15'),
('Carlos Eduardo Lima', 'Farmacêutico', '98.765.432-1', '1988-03-22');

INSERT INTO cliente (nome, rg, data_nascimento) VALUES
('Fernanda Oliveira', '11.223.344-5', '2000-12-05'),
('João Pedro Ramos', '55.667.788-9', '1992-06-10');

INSERT INTO endereco (logradouro, numero, complemento, bairro, cidade, estado, cep, tipo) VALUES
('Rua das Flores', '123', 'Apto 101', 'Centro', 'São Paulo', 'SP', '01001-000', 'Residencial'),
('Av. Brasil', '456', NULL, 'Jardins', 'Rio de Janeiro', 'RJ', '20040-002', 'Comercial');

INSERT INTO produtos (nome_produto, qtd_produto, valor_produto) VALUES
('Paracetamol 500mg', 200, 4.50),
('Dipirona 1g', 150, 3.80);

```