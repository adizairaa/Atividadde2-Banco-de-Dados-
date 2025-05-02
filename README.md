
Disciplina:	Manipulação	de	Dados	/	Banco	de	Dados	II
Professor:	Aguinaldo	Neto
Parte 1 – Criação de Tabelas e Inserção de Dados
Tabela: Clientes
Colunas:
- id	(INT,	chave	primária,	autoincremento)
- nome	(VARCHAR(50))
- cidade	(VARCHAR(50))
Registros	a	inserir:
Nome Cidade
Anakin	Skywalker Tatooine
Leia	Organa Alderaan
Yoda Dagobah
Han	Solo Corellia
Tabela: Pedidos
Colunas:
- id	(INT,	chave	primária,	autoincremento)
- id_cliente	(INT,	chave	estrangeira	referenciando	Clientes(id))
- valor_total	(DECIMAL(10,2),	com	CHECK(valor_total	>=	0))
- data_pedido (DATE)
Registros	a	inserir:
Id_cliente Valor_total Data_pedido
1 500.00 '2025-01-15'
1 750.00 '2025-02-20'
2 1200.00 '2025-03-10'
2 300.00 '2025-04-05'
4 1500.00 '2025-05-12'
4 200.00 '2025-06-18'
4 800.00 '2025-07-22'
Parte 2 – Consultas SQL
Nível 1: Consultas Simples
• 1.	Listar	todos	os	clientes:	Mostrar	id_cliente,	nome	e	cidade.
• 2.	Listar	todos	os	pedidos:	Mostrar	id_pedido,	id_cliente,	valor_total	e	data_pedido.
Nível 2: RIGHT JOIN
• 3.	Clientes	e	seus	pedidos:	Utilizar	RIGHT JOIN	para	listar	todos os	clientes,	mesmo	os	
que	não	fizeram	pedidos.
• 			Mostrar:	id_cliente,	nome	(clientes),	id_pedido,	valor_total	(pedidos).	Ordenar	por	
nome	do	cliente.
• 4.	Clientes	sem	pedidos:	Adaptar	a	consulta	anterior	para	mostrar	apenas	clientes	sem	
pedidos	(WHERE	p.id_pedido	IS	NULL).
Nível 3: Agregação
• 5.	Total	gasto	por	cliente:	Calcular	SUM(valor_total)	para	cada	cliente.	Mostrar	
id_cliente,	nome,	total_gasto.	Incluir	clientes	sem	pedidos	(NULL	ou	0).
• 6.	Clientes	que	gastaram	mais	de	R$1000:	Mostrar	apenas	clientes	com	total	gasto	>	
1000	(HAVING	SUM(valor_total)	>	1000).
Nível 4: Validação com CHECK
• 7.	Teste	das	restrições	CHECK:
• 				Inserir	pedido	com	valor_total	=	-100.00.	O	que	acontece?
Nível 5: Desafio Avançado
• 8.	Média	de	gasto	por	cidade:	Calcular	AVG(valor_total)	por	cidade,	mostrando	apenas	
cidades	com	média	>	R$300.
• 			(Use	GROUP	BY	cidade	e	HAVING)
