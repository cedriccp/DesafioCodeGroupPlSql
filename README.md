# DesafioCodeGroupPlSql
Teste PLSQL para a análise de processo de admissão a Code Group

Oportunidade: Desenvolvedor PL/SQL.
Desafio Técnico 
-------------------------------------------------------------------------------------------------------------------------
Requisitos: 
•	Criar uma function PL/SQL que calcule o total de um pedido (informando o ID do pedido).
•	Com base nas tabelas disponibilizado neste teste, criar uma Function, uma Procedure e uma Trigger, conforme requisitos abaixo:
•	Criar uma trigger PL/SQL que calcula automaticamente o total do pedido sempre que um novo item do pedido é inserido. A trigger será acionada após a inserção de um novo item na tabela itens_pedido.
•	Criar uma procedure PL/SQL para compra com tratamento de exceções, (informando o id do cliente, id do produto e quantidade), em caso de erro fazer rollback da transação.

Entrega: 
•	O teste deverá ser enviado em um e-mail contendo o link para o repositório deste teste em sua conta pessoal no GitHub.


Script do banco de dados: 

-- ----------------------------------------------------- 
-- Table Produtos
-- ----------------------------------------------------- 
CREATE TABLE produtos (
    produto_id NUMBER PRIMARY KEY,
    nome VARCHAR2(50),
    preco NUMBER
);
-- ----------------------------------------------------- 
-- Table Clientes 
-- ----------------------------------------------------- 
CREATE TABLE clientes (
    cliente_id NUMBER PRIMARY KEY,
    nome VARCHAR2(50),
    email VARCHAR2(50)
);
-- ----------------------------------------------------- 
-- Table Pedidos 
-- ----------------------------------------------------- 
CREATE TABLE pedidos (
    pedido_id NUMBER PRIMARY KEY,
    cliente_id NUMBER,
    data_pedido DATE,
    total_pedido NUMBER,
    FOREIGN KEY (cliente_id) REFERENCES clientes(cliente_id)
);
-- ----------------------------------------------------- 
-- Table Itens Pedido
-- ----------------------------------------------------- 

CREATE TABLE itens_pedido (
    item_id NUMBER PRIMARY KEY,
    pedido_id NUMBER,
    produto_id NUMBER,
    quantidade NUMBER,
    FOREIGN KEY (pedido_id) REFERENCES pedidos(pedido_id),
    FOREIGN KEY (produto_id) REFERENCES pro
dutos(produto_id)
);




