É um sistema de centralização de dados de um grupo, usado especialmente para **análise e tomada de decisão**

## Características:

- **Não volatilidade**: 
	  Os dados não são alterados dentro desse repositório. Todas as cargas de chamadas para esse banco de dados são apenas de INSERT e SELECT;
- **Organizado/orientado por assuntos**: 
	  Armazena as informações dividindo-as em temas específicos.
- I**integrado**: 
	  Ele integra diversas fontes de dados de sistemas 
- **Variações de dados por tempo**: 
	  Ao longo do tempo haverá cargas de dados que obedecem padrões específicos e característicos àquele momento, isso dá a possibilidade de fazer pesquisas e análises de dados por períodos para observar essas mudanças de padrões entre os dados decorrente da sua época de inserção.
- **Suporte para tomada de decisão**: 
	  É a principal utilidade dessa merda

## Objetivos

Melhorar a tomada de decisão através da análise de dados contidos no DW. Como esse banco funciona como um grande armazém de logs e informações variadas, é justamente o lugar para encontrar material de estudo para os diversos modelos de análise de dados.

Fazer análises históricas com reconhecimento de padrões considerando momentos específicos como: "dados de vendas de produtos como empréstimos no período de recessão econômica de tal ano"

Centralizar os dados num só lugar para facilitar o seu principal uso que é análise de dados para tomada de decisão.

Ter um desempenho otimizado, pois considerando suas características de não volatilidade/integridade junto com o fato de que é um grande apanhado de muitos dados num só canto.

Todos esses fatores são decisivos para seu objetivo principal: Análise de dados em larga escala e com o maior desempenho possível, pois sua finalidade é justamente para tomar decisões de forma mais clara e analisando os cenários possíveis.

## Diferença dele para bancos transacionais

Os BD Transacionais são mais conhecidos pelo seu uso para operações diárias e para lógicas mais dinâmicas e que recebem atualização frequente. Um DW não recebe atualizações nos seus dados e geralmente não é utilizado com frequência, ele junta um bolo de informações pra jogar tudo pro DW de uma vez. Além disso a sua função principal é um ponto importante, visto que seu foco é processar rapidamente as transações de dados (inserção, deleção e modificação de dados).

### Data Mart

É um conceito de DW mais direcionado a um departamento específico que coleciona um conjunto de assuntos relacionados a esse departamento. Exemplo: Dp de RH possui um Data Mart pra lançar dados relacionados aos assuntos desse departamento. Basicamente cumpre a função do DW mas para um escopo mais reduzido.

### Data Lake/Lakehouse

Armazena dados não filtrados, não formatados e não estruturados de várias fontes.

É como se fosse um lugar pra armazenar dados brutos que são organizados apenas no momento da análise. Os dados não passam por processos de ETL antes de ser carregado para dentro do DL.

## Modelagem conceitual de DW

Essa é a forma como organizamos os dados dentro de uma DW pra a análise ser a melhor e mais eficiente possível.

#### Abordagem multidimensional

Principal característica da modelagem pra DW. É uma forma de visualização de dados de negócio através de diferentes perspectivas ou dimensões. 

Imagina que queremos saber sobre as vendas dos produtos bancários do BB. A pergunta não é feita simplesmente "quanto foi vendido no total?", pois na abordagem multidimensional aborda mais dimensões como o "quais produtos", "para quais clientes", "em qual região", "em qual período de tempo". Unindo essas **dimensões** com a **métrica** de "quanto foi vendido" temos uma abordagem feita de forma multidimensional pois seus parâmetros estão mais detalhados e o resultado final vai ser mais certeiro quanto ao objetivo da análise que é saber qual situação trás o melhor lucro.

Além das **Dimensões** temos os **fatos** como componente central da modelagem multidimensional e no exemplo acima está sendo representado pela métrica e é o valor numérico central da nossa análise pois observaremos como os outros fatores (dimensões) interagem e influenciam esse fato.

#### Tabelas Fato

Coração do DW. Ela tem as chaves estrangeiras das tabelas de dimensões de forma que conecte os fatos aos seus determinados contextos (dimensões) e as medidas numéricas que representam esses fatos.

###### Aditividade da medida

As medidas podem ser aditivas, não-aditivas e semi-aditivas:

Aditivas: quando uma medida pode ser somada livremente por qualquer dimensão
	ex: Valor total de vendas (medida) por produto (dimensão). Aqui podemos mudar a dimensão livremente pois tbm conseguimos observar o valor total de vendas por mês (tempo), estado (região), classificação de cliente e por ai vai.

Semi aditivas: Aquele fato só pode ser somado considerando algumas dimensões específicas.
	ex: Faz sentido somar o saldo de várias contas em um dado momento mas não faz sentido somar o saldo da mesma conta ao longo do mês. 

Não aditivas: Não podem ser somadas de forma alguma. Ex: `Taxa de Juros` ou `Porcentagem de Desconto`. Para analisar essas medidas, você geralmente precisa de outras operações (média, contagem, etc.) ou usá-las como parte de um cálculo maior.
