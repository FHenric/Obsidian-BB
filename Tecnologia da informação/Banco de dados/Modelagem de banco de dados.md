
## Existem 3 camadas ou níveis de modelagem: 

**Modelagem Conceitual**: Representa "o que é" aquele banco e foi feito pra compreensão conceitual do banco de dados. É considerado de alto nível pois foi feito para ser compreendido de forma prática e próxima da nossa linguagem. Seu foco é na regra de negócio como demonstrar a relação entre a tabela 'cliente' e a tabela 'pedido'. As vezes não é nem mencionado como tabela, mas sim como o cliente em si e sua relação conceitual com o pedido, por exemplo: O cliente está ligado a tabela pedido e um cliente pode ter vários pedidos, mas um pedido só pode pertencer a um cliente.

![[Pasted image 20250806213642.png]]

**Modelo lógico**: Transforma a representação conceitual em algo mais técnico com o nome oficial, formato de tabela com definição de chaves primárias e estrangeiras. Esse modelo se parece com uma transição de algo mais conceitual para algo completamente técnico.

![[Pasted image 20250806213655.png]]
**Modelo físico**: Representação puramente técnica que considera o SGBD e demais dados técnicos relevantes para a persistência dos dados como chaves primárias/estrangeiras, tipagem de dados, relacionamento entre tabelas e indices ou restrições. Esse modelo reúne tudo que os outros tem de forma mais técnica.

![[Pasted image 20250806213712.png]]


![[Pasted image 20250806213538.png]]

# Entidade, Atributos e Identificadores

Podemos pensar na entidade como um substantivo. É qualquer coisa que pode possuir um conjunto. Dentro de um sistema as entidades são os protagonistas da regra de negócio do cliente e tudo gira em torno de correlaciona-las ou arquitetar a interação entre elas. Por exemplo, Professor e Aula são entidades que possuem atributos e ao menos um identificador. Um colégio pode ter diversos professores e cada professor pode ter várias aulas ligadas a ele, com isso observamos que a entidade Professor é um conceito/representação que é replicado e num banco de dados essa entidade representa a tabela PROFESSOR que vai comportar o registro de cada objeto. 

Atributos são as informações que compõem a entidade, podemos dizer que ela é o adjetivo que acompanha o substantivo. No exemplo do professor, os seus atributos vão representar informações importantes para sua identificação, que é o que o torna único, e para compor sua regra negocial. Os atributos do professor seriam CPF (chave primária), nome, id_graduação (chave estrangeira) e na entidade Aula seriam id_aula (chave primaria), cpf_prof (chave estrangeira de ligação com professor), id_turma (FK da turma), carga_horaria, timestamp.

Observe que alguns dos atributos são identificadores, que relacionam as tabelas e fazem parte da lógica do sistema. Além disso, os atributos como carga_horaria e timestamp são atributos utilizados para regras de negócio como verificações de limite de carga_horaria ou registro de horário em que a aula foi ministrada. Todos os atributos são relevantes e em algum momento serão usados dentro do sistema para validar, modificar ou relacionar algo. 

Outra característica especial dos identificadores é que são únicos, por isso nem todo atributo pode ser um identificador. A ideia é que eles sejam usado para correlacionar dados entre tabelas e dados repetíveis entre objetos da entidade poderia confundir o sistema e quebra-lo. Um professor tem seu CPF associado às aulas e isso é o que diz ao banco de dados que aquela aula pertence ao professor, assim como a aula tem o id da turma que identifica que aquela aula pertence a uma turma. 


O identificador surge na tabela de acordo com sua regra de relacionamento

### Entidade fraca e forte

Entidade forte é aquela que possui sua própria chave primária, as fracas são aquelas que sua chave primária é na verdade uma chave estrangeira que serve como linha de frente para relacionar essa entidade fraca a uma forte. Ou seja, a entidade fraca depende da chave primaria de uma entidade forte para existir e só existe por causa dela e para ela. 

Exemplo: A entidade "Curso" pode ser uma entidade forte, com atributos como código do curso e nome do curso. A entidade "Seção" (ou turma) pode ser uma entidade fraca. Uma seção só existe dentro de um curso específico. Para identificar uma seção, você precisa tanto do código do curso (atributo da entidade forte) quanto do número da seção (atributo da própria entidade fraca).

Pegadinha: a banca pode criar uma ideia de que uma entidade é fraca só por que sua "chave primária" recebe um nome que geralmente está associada a outra entidade, mas se não houver essa entidade representada como uma tabela na questão, então não existe a tabela. SÓ CONSIDERE INFORMAÇÕES QUE ESTÃO NA QUESTÃO POR MAIS QUE ELA NÃO SEJA A MAIS ADEQUADA PARA A LÓGICA.

Exemplo:

A questão dá essas tabelas:

ALUNO (==MATRICULA==, NOME)

CURSO (==CODIGO==, NOME, DATA_INICIO)

TURMA (==COD_DISCIPLINA==, NUMERO)

PROFESSOR (==DEPARTAMENTO==, NUMERO, NOME)

DISCIPLINA (==COD_DISCIPLINA==, NOME, CARGA_HORARIA)

Pede para você identificar as entidades fracas. O olhar de um dev astuto é ver que não faz sentido que o PK de um professor seja o departamento e você logo considera uma tabela DEPARTAMENTO que faz a conexão com o professor, logo esse prof não tem chave primária própria e é uma entidade fraca.

O gabarito da questão só considera TURMA como entidade fraca pois é a ÚNICA TABELA COM A MESMA PK e isso sugere que a turma é uma entidade fraca ligada à disciplina. Ou seja, só é considerada a informação que está na questão, sem deduções.