Construindo seu Primeiro Projeto Lógico de Banco de Dados (E-COMMERCE
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


Projeto Lógico de Banco de Dados do Zero(OFICINA)
 Projeto de Banco de Dados - Oficina Mecânica
📘 Descrição do Projeto
Este projeto tem como objetivo criar o esquema lógico e físico de um banco de dados relacional para gerenciar o funcionamento de uma oficina mecânica. A base deste trabalho parte do modelo conceitual (ER) desenvolvido no desafio anterior, agora refinado e mapeado para o modelo lógico com base nas boas práticas de modelagem relacional.

A solução contempla o controle de clientes, veículos, ordens de serviço, serviços prestados, peças utilizadas, bem como os mecânicos responsáveis por cada atendimento. O projeto também inclui scripts SQL para criação das tabelas, inserção de dados e execução de consultas complexas.

🎯 Objetivos
Realizar o mapeamento do modelo ER para modelo relacional;

Criar o esquema lógico e físico no SGBD;

Garantir integridade com o uso adequado de chaves primárias, estrangeiras e constraints;

Popular o banco com dados reais/simulados;

Realizar consultas SQL com:

SELECT

WHERE

expressões derivadas

ORDER BY

GROUP BY + HAVING

JOINs entre tabelas

🗃️ Estrutura do Banco de Dados
Principais Entidades:
Cliente

Veículo

Ordem de Serviço

Serviço

Peça

Mecânico

Relacionamentos:
Um cliente pode ter vários veículos;

Um veículo pode ter várias ordens de serviço;

Cada ordem de serviço pode conter múltiplos serviços e utilizar várias peças;

Um mecânico pode realizar muitos serviços.

💻 Tecnologias Utilizadas
MySQL

SQL padrão

DBeaver / MySQL Workbench

Git e GitHub

📂 Estrutura do Projeto
bash
Copiar
Editar
📦 oficina-bd
 ┣ 📁 sql
 ┃ ┣ 📄 script_criacao.sql
 ┃ ┣ 📄 script_inserts.sql
 ┃ ┗ 📄 queries_complexas.sql
 ┣ 📄 README.md
✅ Funcionalidades Implementadas
Criação do schema completo do banco de dados com CREATE TABLE;

Inserção de dados de exemplo (INSERT INTO);

Execução de consultas SQL complexas para extração e análise dos dados.

🔍 Exemplos de Consultas Criadas
1. Recuperação simples:
sql
Copiar
Editar
SELECT nome, telefone FROM Cliente;
2. Filtros com WHERE:
sql
Copiar
Editar
SELECT * FROM Veiculo
WHERE modelo = 'Gol' AND ano >= 2015;
3. Atributo derivado (ex: custo total por ordem):
sql
Copiar
Editar
SELECT os.id_ordem, SUM(s.preco) + SUM(p.preco_unitario * p.quantidade) AS total
FROM OrdemServico os
JOIN Servico s ON os.id_ordem = s.id_ordem
JOIN PecaUsada p ON os.id_ordem = p.id_ordem
GROUP BY os.id_ordem;
4. Ordenação:
sql
Copiar
Editar
SELECT * FROM OrdemServico
ORDER BY data_abertura DESC;
5. Filtro por grupo (HAVING):
sql
Copiar
Editar
SELECT id_cliente, COUNT(*) AS total_servicos
FROM OrdemServico
GROUP BY id_cliente
HAVING COUNT(*) > 3;
6. Junções entre tabelas:
sql
Copiar
Editar
SELECT c.nome AS cliente, v.modelo AS veiculo, os.data_abertura, m.nome AS mecanico
FROM OrdemServico os
JOIN Cliente c ON os.id_cliente = c.id_cliente
JOIN Veiculo v ON os.id_veiculo = v.id_veiculo
JOIN Mecanico m ON os.id_mecanico = m.id_mecanico;
📌 Instruções de Execução
Clone este repositório:

bash
Copiar
Editar
git clone https://github.com/seu-usuario/nome-do-repositorio.git
Importe os scripts .sql no seu gerenciador de banco (MySQL, DBeaver, Workbench, etc).

Execute o arquivo script_criacao.sql para criar o schema do banco.

Execute script_inserts.sql para popular o banco com dados.

Execute as consultas em queries_complexas.sql para visualizar os resultados.

📈 Possíveis Melhorias Futuras
Adição de controle de status da ordem de serviço (em aberto, finalizada, aguardando peça);

Cadastro de fornecedores de peças;

Controle de estoque de peças na oficina;

Relatórios mensais de serviços e faturamento.

🧠 Aprendizados
Neste projeto, foi possível aplicar conceitos fundamentais de modelagem de dados e praticar a implementação de um banco relacional do início ao fim. Além disso, foram desenvolvidas habilidades na construção de consultas SQL mais avançadas para análise e tomada de decisão baseada em dados.


projeto final (DASHBOARD)
# 📊 Projeto de Dashboard de Vendas no Excel

## 🎯 Objetivo do Projeto

Este projeto foi desenvolvido com o intuito de **transformar uma base de dados bruta em um dashboard de vendas interativo no Excel**, facilitando a visualização dos principais indicadores de desempenho. O objetivo é permitir uma **análise rápida, clara e eficiente** dos dados de vendas por meio de gráficos, tabelas e segmentações.

A proposta atende ao desafio de criar uma solução visual dentro do Excel que apoie a **tomada de decisões baseadas em dados**.

---

## 🧾 Explicação dos Dados Utilizados

Os dados utilizados estão presentes no arquivo `base.xlsx`. Essa base contém informações reais ou simuladas relacionadas ao processo de vendas, incluindo:

- **Data da venda**  
- **Produto**  
- **Categoria**  
- **Região de venda**  
- **Quantidade vendida**  
- **Preço unitário**  
- **Receita total**

Essas informações foram organizadas, tratadas e utilizadas para criar tabelas dinâmicas, gráficos e filtros que compõem o dashboard.

---

## 📌 Funcionalidades do Dashboard

O dashboard final foi desenvolvido no arquivo `dashboard_xbox_finalizado.xlsx` e inclui:

- Indicadores de **total de vendas**, **quantidade total vendida** e **ticket médio**
- **Gráficos dinâmicos** para análise de vendas por categoria, por região e ao longo do tempo
- **Segmentações (filtros visuais)** que permitem interagir com os dados e personalizar as análises por:
  - Produto
  - Região
  - Período (data)

---

## 🔄 Instruções para Reprodução

Caso deseje visualizar ou testar o dashboard, siga os passos abaixo:

1. **Baixe os arquivos do repositório**:
   - `base.xlsx` (contém os dados brutos)
   - `dashboard_xbox_finalizado.xlsx` (contém o dashboard já montado)

2. **Abra o arquivo `dashboard_xbox_finalizado.xlsx`** no **Microsoft Excel 365** (ou uma versão que suporte Tabelas Dinâmicas e Segmentações).

3. Para testar a atualização do dashboard:
   - Modifique alguns valores na base de dados (por exemplo, quantidade ou receita).
   - Clique com o botão direito em uma Tabela Dinâmica ou gráfico e selecione **"Atualizar"**.

4. Use os filtros (segmentações) para explorar diferentes cenários, como:
   - Vendas por produto
   - Comparação de regiões
   - Evolução de vendas ao longo do tempo

---

## 📁 Estrutura do Repositório

- `README.md`: explicação do projeto (este arquivo)
- `base.xlsx`: arquivo com os dados brutos utilizados
- `dashboard_xbox_finalizado.xlsx`: dashboard finalizado e pronto para uso

---

## 📌 Considerações Finais

Este projeto foi criado como parte de um desafio prático com foco em **organização visual, análise de dados e usabilidade** no Excel. A proposta é mostrar como é possível gerar **insights valiosos** com ferramentas simples e acessíveis.
