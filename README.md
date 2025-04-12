Construindo seu Primeiro Projeto Lógico de Banco de Dados
📝 Descrição do Projeto
Este projeto tem como objetivo modelar e implementar um banco de dados relacional para um sistema de e-commerce, utilizando boas práticas de modelagem lógica e física. A proposta faz parte de um desafio prático de projeto, onde é necessário considerar regras de negócio reais e refinar o modelo conceitual com base em um diagrama EER (Modelo Entidade-Relacionamento Estendido).

A modelagem contempla o cadastro de clientes Pessoa Física (PF) e Pessoa Jurídica (PJ), registros de pedidos com múltiplas formas de pagamento, e controle de entregas com status e código de rastreio, além de relacionamentos com produtos, fornecedores, vendedores e estoque.

🎯 Objetivo
Reproduzir e refinar o modelo lógico do banco de dados de um sistema de e-commerce, considerando:

Clientes do tipo PF ou PJ (um cliente pode ser apenas um dos dois);

Registro de múltiplos pagamentos por pedido;

Controle de entrega com status e código de rastreio;

Relacionamentos entre produtos, fornecedores, vendedores e estoque;

Criação de queries SQL mais avançadas, usando JOIN, GROUP BY, HAVING, ORDER BY e expressões derivadas.

🧩 Estrutura de Tabelas
Principais Entidades:
Cliente (com especialização em ClientePF e ClientePJ);

Pedido;

Pagamento;

Produto;

Fornecedor;

Vendedor;

Estoque;

Entrega.

Relacionamentos importantes:
Um cliente pode fazer muitos pedidos;

Um pedido pode ter vários pagamentos;

Cada produto é fornecido por um fornecedor;

Produtos estão relacionados a um estoque;

Um pedido está associado a uma entrega com status e rastreamento.

💾 Tecnologias Utilizadas
MySQL

SQL padrão

Git e GitHub

🚀 Funcionalidades Implementadas
Criação do schema do banco com CREATE TABLE, chaves primárias, estrangeiras e constraints;

Inserção de dados para testes;

Execução de queries complexas, como:

Exemplos de Perguntas Respondidas com SQL:
Quantos pedidos foram feitos por cada cliente?

Algum vendedor também é fornecedor?

Quais produtos estão em estoque e quem os fornece?

Relação de nomes dos fornecedores e produtos;

Qual o valor total de pagamentos por pedido?

Entregas realizadas com seus respectivos status e códigos de rastreio.

📌 Instruções de Uso
Clone o repositório:

bash
Copiar
Editar
git clone https://github.com/seu-usuario/nome-do-repositorio.git
Importe o arquivo SQL no seu gerenciador de banco (MySQL, DBeaver, etc).

Execute as queries disponíveis no diretório /sql.

✅ Status do Projeto
✔️ Modelagem lógica finalizada
✔️ Script SQL criado com chaves e constraints
✔️ Inserção de dados de teste
✔️ Queries com JOIN, WHERE, HAVING, ORDER BY, expressões derivadas
✔️ Pronto para avaliação

🧠 Aprendizados
Esse projeto permitiu o aprofundamento em modelagem de dados, uso de tipos especiais de entidade (subtipos PF e PJ), e construção de consultas complexas que representam situações reais de sistemas de e-commerce.

