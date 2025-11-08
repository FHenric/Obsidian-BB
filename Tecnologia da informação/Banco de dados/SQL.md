# Categorias de agrupamento dos comandos SQL

São definições/ classificações para separar os comandos que lidam com a estrutura do banco de dados (DDL), os que lidam com os dados em si (DML) e os que lidam com o controle/permissões/segurança do banco de dados (DCL)
## DDL (Definition)

Comandos responsáveis por alterar, criar e deletar BASES DE DADOS

#### Comandos mais comuns:

CREATE, ALTER e DELETE: 

CREATE DATABASE nome_do_BD
CREATE TABLE nome_da_tabela

Diferença entre DROP e TRUNCATE

DROP: Apaga A TABELA em si e todos os dados dentro junto. Como se você tivesse demolindo o comodo da casa.

TRUNCATE: Apaga APENAS OS DADOS da tabela, como se tivesse retirando e queimando os móveis da casa. Os dados não são recuperáveis

Alter table geralmente é chamado referenciando a tabela que será alterada e em seguida a regra de modificação como ADD, DROP, MODIFY(muda tipo de dado), CHANGE (muda nome e tipo de dado), RENAME
ALTER TABLE nome_da_tabela ADD (adiciona) nome_coluna  tipo_dado

DECIMAL(10,2) = o campo pode ter 10 dígitos e 2 casas decimais

### Constraints - Regras atreladas a coluna/tabela

Geralmente é no terceiro parametro do dado:

CREATE TABLE pessoa (
	nome  char(50)  NOT NULL <- {constraint}
)

Essa constraint diz que nosso campo não pode ser nulo.

Assim como essa temos outras que aplicam regras diversas para nossa tabela:

UNIQUE - A coluna tem que ter valores únicos e não repetidos, ideal para CPF;

PRIMARY ou FOREINGN KEY - A primary key já aplica o not null e o unique;

CHECK - O valor deve satisfazer uma condição especificada;
	CHECK (idade >= 18): regra para que apenas maiores de idade sejam registrados;
	
DEFAULT - Atribui valor padrão em caso do campo ser registrado sem valor (nulo);

INDEX - Cria ou recupera dados de uma tabela rapidamente;
	CREATE INDEX index_pessoa_nome <span style="color:rgb(217, 46, 229)">ON</span> pessoas (nome);
CONSTRAINT - no estilo out-of-line é usado para nomear a constraint específica que geralmente tem uma lógica mais complexa
	<span style="color:rgb(217, 46, 229)">CONSTRAINT</span> fk_cliente_pedido FOREIGN KEY (id_cliente) <span style="color:rgb(217, 46, 229)">REFERENCES</span> clientes(id)
REFERENCES - palavra obrigatória para se referenciar a uma chave primária quando definimos uma estrangeira
	id_cliente INT FOREIGN KEY REFERENCES clientes(id) {referencia ao id da tabela clientes}

### View - Uma janela para os dados

As views são tabelas virtuais baseadas no resultado de uma consulta como querys pré-salvas para serem utilizadas com mais praticidade. Geralmente uma requisição que envolve diversas tabelas, calculos e é complexa de se construir pode ser feita uma só vez e transformada numa view que será reproduzida várias vezes de forma muito mais prática e com um simples comando de SELECT * FROM MinhaView.

Pode ser usada como forma de restrição de dados, eu posso criar uma query que omite uma coluna de determinada tabela e deixar essa query como uma view para ser acessadas por aqueles que não podem visualizar os dados do campo ocultado na view.

![[Pasted image 20250617212542.png]]

Uma view como essa é construída para salvar o calculo correto, assim o time usa a view e evita de ficar pedindo a query pro coleguinha ou errar um calculo importante para a construção do dado.

CREATE VIEW nome_da_view AS
Aqui tu mete a lógica que tu quiser meu patrão. Depois é só dar um select e mandar ver.


## DML (Manipulation)

Comandos responsáveis por alterar, criar e deletas OS DADOS EM SI.

SELECT DISTINCT -> Distinct informa que não queremos dados repetidos, apenas um dado distinto do outro e isso significa que não vai buscar registros repetidos.

SELECT DISTINCT cidade FROM clientes ->  vai retornar apenas as cidades distintas que estiverem cadastradas.

Podemos juntar o DISTINCT com o COUNT pra retornar a quantidade de cidades diferentes que existe nos registros:
	SELECT COUNT(DISTINCT cidade) FROM clientes;

WHERE nos ajuda a filtrar o dado que vai vir

AND, OR e NOT




## DCL (Control)

Comandos responsáveis por lidar com 

