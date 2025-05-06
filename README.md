💾 Manipulação de Dados – Banco de Dados II
Disciplina: Manipulação de Dados / Banco de Dados II
Professor: Aguinaldo Neto

Este repositório contém a atividade prática da aula 2, que aborda criação de tabelas, inserção de dados e consultas avançadas utilizando SQL.

📌 Parte 1 – Criação de Tabelas e Inserção de Dados
🗂️ Tabela: Clientes
Coluna	Tipo	Observações
id	INT	Chave primária, autoincremento
nome	VARCHAR(50)	
cidade	VARCHAR(50)	

Registros a inserir:

Nome	Cidade
Anakin Skywalker	Tatooine
Leia Organa	Alderaan
Yoda	Dagobah
Han Solo	Corellia

🗂️ Tabela: Pedidos
Coluna	Tipo	Observações
id	INT	Chave primária, autoincremento
id_cliente	INT	Chave estrangeira referenciando Clientes(id)
valor_total	DECIMAL(10,2)	Com CHECK (valor_total >= 0)
data_pedido	DATE	

Registros a inserir:

id_cliente	valor_total	data_pedido
1	500.00	2025-01-15
1	750.00	2025-02-20
2	1200.00	2025-03-10
2	300.00	2025-04-05
4	1500.00	2025-05-12
4	200.00	2025-06-18
4	800.00	2025-07-22

🔍 Parte 2 – Consultas SQL
🔹 Nível 1: Consultas Simples
1️⃣ Listar todos os clientes:
Mostrar id_cliente, nome e cidade.

2️⃣ Listar todos os pedidos:
Mostrar id_pedido, id_cliente, valor_total e data_pedido.

🔸 Nível 2: RIGHT JOIN
3️⃣ Clientes e seus pedidos:
Utilizar RIGHT JOIN para listar todos os clientes, mesmo os que não fizeram pedidos.
Mostrar: id_cliente, nome (clientes), id_pedido, valor_total (pedidos).
Ordenar por nome do cliente.

4️⃣ Clientes sem pedidos:
Adaptar a consulta anterior para mostrar apenas clientes sem pedidos (WHERE p.id_pedido IS NULL).

🔹 Nível 3: Agregação
5️⃣ Total gasto por cliente:
Calcular SUM(valor_total) para cada cliente. Mostrar: id_cliente, nome, total_gasto.
(Incluir clientes sem pedidos – valor NULL ou 0).

6️⃣ Clientes que gastaram mais de R$ 1000:
Mostrar apenas clientes com total_gasto > 1000 (HAVING SUM(valor_total) > 1000).

🔸 Nível 4: Validação com CHECK
7️⃣ Teste da restrição CHECK:
Tentar inserir um pedido com valor_total = -100.00.
Pergunta: O que acontece?

🏅 Nível 5: Desafio Avançado
8️⃣ Média de gasto por cidade:
Calcular AVG(valor_total) por cidade, mostrando apenas as cidades com média superior a R$ 300.
(Utilizar GROUP BY cidade e HAVING).

🚀 Como Executar
1️⃣ Suba o script no seu banco de dados SQL (ex: MySQL ou MariaDB).
2️⃣ Execute os comandos passo a passo, validando as consultas e observando os resultados.
3️⃣ Teste especialmente a parte de validação com CHECK para entender a integridade dos dados.

✍️ Autor
Desenvolvido por Adila para a disciplina Manipulação de Dados / Banco de Dados II.
