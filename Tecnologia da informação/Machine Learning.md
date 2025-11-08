
Ramo da Inteligência Artificial que lida com ferramentas e técnicas de aprendizado de máquina, em que a IA é treinada com dados de diversos modelos e formas para trabalhar, ter insights e predizer algo baseado nesses dados. Basicamente é treinar uma IA para reconhecer padrões num determinado contexto que é controlado pelo Analista de Dados.

# Como funciona? (passos)

1) Processo de decisão / Função Hipótese:
	É um modelo matemático usado para prever ou classificar os **dados de entrada**. Basicamente a função que mapeia as variáveis de entrada (parâmetros) e transforma numa saída (previsão).
	Essas funções se variam em formas: Linear, polinomial, arvore de decisão, rede neural... A forma é decidida pelo tipo de algoritmo que está sedo utilizado.

2) Função de erro / Função de custo / Função de objetivo:
	Avalia a predição do modelo utilizado no primeiro passo. Trás análises sobre o desempenho do modelo para o analista entender o que pode ser melhorado. Quantifica o quão errado está a predição com relação ao dado de treinamento, mede discrepâncias entre a saída desejada e a saída efetuada pelo primeiro passo. A função dessa fase é minimizar cada vez mais os erros dos resultados a cada vez que ela é executada no processo de ML.

3) Processo de otimização de modelo:
	É o momento de encontrar os melhores parâmetros para utilizar na função hipótese quando for repetir o processo de ML. Aqui o foco é aprimorar os dados de input para reduzir os efeitos na função de erro. São utilizados algoritmos para esse processo de otimização, o mais comum deles é o Gradiente Descendente e suas variantes (Adam, SGD) principalmente no Deep Learning

# Aplicação

<span style="color:rgb(0, 176, 240)">Recomendação de conteúdo nas plataformas de mídia</span> como youtube, tiktok, instagram. A máquina aprende os conteúdos que você mais interage positivamente como se fosse o input e no output ela te dá mais conteúdos relacionados àqueles tópicos mais interagidos.

<span style="color:rgb(0, 176, 240)">Sistemas de combate a fraudes de cartão de crédito</span>: Em qualquer área de segurança bancária podemos treinar sistemas para reconhecer padrões e atitudes maliciosas nas atividades bancárias de uma conta.

Banco de dados autonomo;

# Terminologias

## <span style="color:rgb(0, 176, 240)">Conjunto de dados ou Data Set</span>

Conjunto de registro. Essas unidades contem eventos ou objetos. 

Esse<span style="color:rgb(0, 176, 80)"> registro</span> pode ser <span style="color:rgb(0, 176, 80)">chamado de</span> <span style="color:rgb(0, 176, 80)">instância ou amostra</span>. Então o Data Set tem um conjunto de amostras que <span style="color:rgb(0, 176, 80)">detalham um evento ou objeto</span> através dos seus <span style="color:rgb(255, 255, 0)">atributos</span>.

Colocando como um JSON: 

```
{
  "data set": [
    {
      "descrição": "Evento A",
      "outros_atributos": "valor",
      "mais_atributos": 123
    },
    {
      "descrição": "Evento B",
      "outros_atributos": "outro valor",
      "mais_atributos": 456
    },
    {
      "descrição": "Evento C",
      "outros_atributos": "mais um valor",
      "mais_atributos": 789
    }
  ]
}
```

![[Pasted image 20250522143906.png]]

Dados de treinamento: São dados usado no momento em que estamos treinando a maquina. É feito pois é necessário um ambiente controlado para que seja garantido a maior precisão possível na análise de dados que será feita e posteriormente seus resultados.

# Hipótese

Resultado gerado no algoritmo de aprendizagem. Na maioria das ML supervisionadas o objetivo é descobrir uma possível hipótese a partir do espaço de hipóteses que poderia mapear as entradas para as saídas adequadas.

**Espaço de hipóteses (H):**  Conjunto de todas as hipóteses possíveis. A ideia é o algoritmo escolher a melhor hipótese que descreve a função alvo ou o resultado dentre as que estão no espaço

Também pode ser compreendida como uma fórmula (função G) obtida para aproximar a função alvo (F);

Função G (Fórmula): É a receita(conjunto de dados/input) usada para produzir um resultado (a previsão/output). Função alvo (F) é como se fosse o mundo ideal, um conjunto de inputs mais complexos e quase impossível de se alcançar. A ideia é que nossa Função G ou Fórmula chegue o mais próximo possível da função F;

Bias ou vieses é a diferença entre o quadrado da melhor hipotese (função G) e da função alvo (F);

![[Pasted image 20250522165320.png]]

Linhas vermelhas: hipóteses;
Positivos: Spam;
Negativos: Emails normais;
????: novos emails que ainda não foram classificados;

O conjunto dessas linhas formam o espaço de hipóteses (H) e no contexto de uma máquina que separa spam de emails normais nós conseguimos entender melhor esse conceito. 
A máquina forma uma hipótese ao traçar essa linha entre os dados e separá-los em Spam (positivos) e emails normais. Observe que uma das hipóteses separou um falso positivo no local onde devem ficar os negativos, mas a tendência é que a melhor hipótese seja a que tiver menos valores errados ou erros de distinção entre email e spam.

# Aprendizado supervisionado

Faz uso de dados **rotulados** para treinar os algoritmos para classificar ou prever algo. Durante a entrada de dados, o modelo pode ter seus pesos ajustados. Geralmente os sistemas de classificação de spam ou antivirus são treinados com aprendizado supervisionado.

Nesse tipo de algoritmo as features (entradas) são treinadas com suas labels (saídas) esperadas para poder extrapolar para os demais dados sem saída que forem colocados. A rotulação se dá justamente nessa prática de ajustar as expectativas.

<span style="color:rgb(255, 0, 0)">O fato dos dados serem rotulados que caracterizam como supervisionado</span> 

### Métodos mais comum de ML Supervisionado

Redes neurais
Naive Bayes
Regressão linear
Regressão logistica
Regressão Polinomial
Floresta aleatória/Árvore de decisão
Support vector machine (SVM)

# Aprendizado Não-supervisionado

Sem rotulação de dados, a máquina terá que distinguir e analisar sem uma explicação prévia. 

Descobre padrões "escondidos" e conjunto de dados diferentes sem precisar da ajuda de humanos. Geralmente esse fator é o que faz escolherem o método não supervisionado, principalmente quando se está buscando um novo ponto de vista ou perspectiva que os analista não conseguiram detectar, geralmente pelo grande volume de dados.

Por isso é um método ideal para estratégias de vendas, identificação de perfis diferentes de clientes ou reconhecer padrões e imagens.

### Principais métodos:

Principal Component Analysis (PCA);
Singular Value Decomposition (SVD);
Redes neurais;
Clusterização K-means;
Métodos de Clusterização Probabilístico;

# Aprendizado por reforço

É um modelo de machine learning que pode ser descrito como "aprender fazendo" com uma série de experimentos de tentativa e erro. Um “agente” aprende a realizar uma tarefa definida por meio de um ciclo de feedback até que o desempenho esteja dentro de um intervalo desejável. O agente recebe reforço positivo quando executa a tarefa bem e reforço negativo quando tem um desempenho ruim. Um exemplo de aprendizado por reforço é quando os pesquisadores do Google ensinaram um algoritmo desse tipo a jogar Go. O modelo, que não tinha conhecimento prévio das regras de Go, simplesmente moveu as peças aleatoriamente e “aprendeu” os melhores movimentos a fazer. O algoritmo foi treinado com reforço positivo e negativo até que o modelo de machine learning pudesse vencer um jogador humano no jogo.

# Redes neurais

Tentativa de representar como as conexões neurais funcionam. Possui um grande número de nós de processamento ligados. Usados em reconhecimento de padrões e tradução de linguagens naturais, reconhecimento e criação de imagem.

# Regressão linear

Se baseia no relacionamento linear entre dois ou mais valores diferentes. Um exemplo de uso é quando queremos predizer o valor de uma casa baseando-se nos valores de casas da região. Comumente usado para predizer valores numéricos.

A ideia é criar uma linha reta ou hiperplano que traga uma definição específica da relação entre os valores de entrada (tamanho da casa) e os valores de saída (preço da casa) tentando criar a linha reta mais real possível de relação entre tamanho e preço.

<span style="color:rgb(255, 0, 0)">Sensível a Outliers.</span>

**Exemplo:** Prever o preço de uma casa com base em tamanho, localização e número de quartos.

**Rotulação:**

- Features -> **X** = **[ tamanho, localização, quartos ]**
    
- Label/target -> **y** = preço da casa (valor contínuo)  
    **Ponto supervisionado:** O modelo ajusta os coeficientes para minimizar o erro entre **y_predito** e **y_real**.
# Regressão logística

Classificação binária.

Sua diferença da regressão linear é que as saídas são binárias ou booleanas (para os devs hehe). Utilizando o exemplo dos emails spams ou normais, aqui seguimos a rotulação com as entradas sendo algumas palavras-chave e as saídas seriam algo como "é spam" e "não é spam" 
# Clusterização

Não supervisionado que é usado para identificar padrão em dados possibilitando o agrupamento dos dados que podem passar despercebidos pelos humans beans. O proprio nome cluster que significa "agrupar" nos ajuda a entender o que ele faz.

![[Pasted image 20250522183601.png]]

Nesse caso é um algoritmo K-means de Clusterização que está sendo utilizado. Podemos notar isso por conta dos centroides. Esses centroides são médias daqueles dados agrupados. Existe o algoritmo de Clusterização K-medoids que é mais robusto e evita outliers.

# Árvores de decisões

Prevê valores numéricos e classifica dados em categorias. Utiliza uma sequencia de ramificações de decisões relacionadas. são fáceis de validar e auditar.

O algoritmo utiliza perguntas (OS RÓTULOS DESSE ALGORÍTMO) para dividir os dados e classifica-los de acordo com a regra de negócio. Sua auditabilidade e validação se dão pelo fato de que podemos estruturar adequadamente essas perguntas para obtermos o melhor resultado.

Sua principal diferença da rede neural é o fato de ser auditada e validada internamente. As redes neurais são conhecidas como caixas pretas, pois não possuem uma forma clara de mexer no interior dela, apenas nas entradas e saídas.

A sua organização é como se fosse uma estrutura de dados ou processos de decisões. 

![[Pasted image 20250522190446.png]]

vemos como ele utiliza de alguns parâmetros internos para direcionar os caminhos de acordo com a lógica necessária ao contexto. 

# Random florest

Quando usamos diversas arvores de decisão para chegar ao nosso resultado, geralmente é usado quando uma só arvore não dá conta do recado. Mais robusto que uma unica arvore e reduz o overffiting

![[Pasted image 20250522190850.png]]

Nesse outro exemplo vemos uma floresta em que cada arvore utiliza da mesma instância (entrada de dado) para verificar sua classificação. No fim é feito a votação e o maior resultado é a classificação oficial.

# Support Vector Machine

Encontra a melhor fronteira para separar classes. Bom para classificar imagens quando colocado os pixels de entrada e treinado com resultados de saída como os números que esses pixels representam.



# Hierarquia de Dados, Informação e Conhecimento na Aprendizagem de Máquina

A hierarquia entre **dados, informação e conhecimento** é um conceito fundamental na **Ciência da Informação** e é amplamente aplicado na **Tecnologia da Informação**, incluindo **Aprendizado de Máquina** (Machine Learning). Esse modelo hierárquico ajuda a entender como a informação é estruturada e utilizada para gerar conhecimento e decisões.


**1. Definições: Dado, Informação e Conhecimento**

A hierarquia segue três níveis principais:

**1.1. Dado (Base da Pirâmide)**

Os **dados** são elementos brutos e isolados, sem contexto ou significado direto. Eles podem ser números, textos, imagens ou qualquer outra representação de fatos sem interpretação.

📌 **Exemplos:**

- Um conjunto de números: 24, 31, 18, 45
- Temperatura registrada em diferentes momentos: 22°C, 24°C, 26°C
- Palavras ou frases sem contexto: "carro", "vermelho", "rápido"

📌 **No Aprendizado de Máquina:**

Os dados são **coletados** de diversas fontes, como sensores, bancos de dados, redes sociais, e precisam ser processados antes de se tornarem úteis.

  
**1.2. Informação (Nível Intermediário)**

A **informação** surge quando os dados são organizados e interpretados dentro de um contexto. Aqui, os dados começam a ter significado.

📌 **Exemplos:**

- A lista de números pode representar **idades** de um grupo de pessoas.
- A sequência de temperaturas pode indicar **a variação do clima ao longo do dia**.
- As palavras podem formar uma **descrição**: "O carro vermelho é muito rápido."

📌 **No Aprendizado de Máquina:**

Os dados brutos são transformados em informações por meio de **limpeza, normalização e organização**, tornando-os utilizáveis para treinar modelos.

  
**1.3. Conhecimento (Topo da Pirâmide)**

O **conhecimento** é gerado quando múltiplas informações são relacionadas, contextualizadas e aplicadas para tomar decisões ou resolver problemas.

📌 **Exemplos:**

- **Previsão do tempo:** Ao analisar padrões históricos de temperatura, um sistema pode prever **o clima do dia seguinte**.
- **Diagnóstico médico:** Um médico pode usar informações de sintomas e exames para diagnosticar uma doença.
- **Recomendações de filmes:** O Netflix analisa seu histórico de visualizações para recomendar **filmes que você provavelmente gostará**.

📌 **No Aprendizado de Máquina:**

O conhecimento é extraído quando um **modelo** aprende padrões e pode fazer previsões, classificações ou tomar decisões de forma autônoma.

  
**2. Aplicação na Aprendizagem de Máquina**

A hierarquia de **dado → informação → conhecimento** é crucial para a construção de sistemas inteligentes. O processo segue estas etapas:

**🔹 Passo 1: Coleta de Dados**

Os sistemas de Machine Learning começam coletando **grandes volumes de dados** de diversas fontes, como sensores, câmeras, bancos de dados, redes sociais e logs de sistemas.

  
**🔹 Passo 2: Transformação em Informação**

Os dados brutos são processados, organizados e limpos. Técnicas como **normalização, remoção de ruídos e estruturação** são aplicadas para extrair significado dos dados.

  
**🔹 Passo 3: Geração de Conhecimento**

Com base na informação organizada, **algoritmos de aprendizado de máquina** identificam padrões, fazem previsões e auxiliam na tomada de decisões.

📌 **Exemplo prático:**

- Dados brutos: Clientes e seus históricos de compra
- Informação: Padrões de comportamento de compra
- Conhecimento: Sistema de recomendação que sugere produtos personalizados para cada cliente
# Processamento de linguagem natural



