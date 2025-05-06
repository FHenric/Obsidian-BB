# MMC

Mínimo múltiplo comum é quando queremos encontrar o valor mínimo que é o múltiplo de um conjunto determinado de números.

Múltiplos de 2: {2,4,<span style="color:rgb(255, 0, 0)">6</span>,8,10,<span style="color:rgb(255, 0, 0)">12</span>...}

Múltiplos de 3: {3,<span style="color:rgb(255, 0, 0)">6</span>,<span style="color:rgb(255, 0, 0)">12</span>,15,21...}

Múltiplos comum entre 2 e 3: {6, 12,  n...}

Mínimo múltiplo comum entre 2 e 3 = 6;

Para encontrar isso precisamos decompor simultaneamente em fatores primos:

![[Pasted image 20250329173844.png]]

Apesar de simultânea, a decomposição não precisa ser sempre junta, quando tiver 2 e 3 nós dividimos o 2 por 2 e o 3 por 3, a situação que não pode decompor separadamente é a do MDC. Lembrando que os números que não podem ser dividido pelo fator primo se repete e é feito a divisão apenas dos que podem ser divididos.

## Propriedades do MMC:

1) O MMC de 2 ou mais N primos será sempre igual ao produto entre eles
	![[Pasted image 20250329174334.png]]

2) Quando o maior número é múltiplo dos demais (simultaneamente), o MMC deles é o próprio número maior:
	![[Pasted image 20250329174648.png]]

3) 
	 ![[Pasted image 20250329174852.png]]


 
# MDC - Máximo Divisor Comum

Quando queremos encontrar o maior número inteiro que divide os números parametrizados.

Divisores do 18 = {<span style="color:rgb(255, 0, 0)">1,2,3</span>,<span style="color:rgb(0, 176, 80)">6</span>,9,18};

Divisores do 30 = {<span style="color:rgb(255, 0, 0)">1,2,3</span>,5,<span style="color:rgb(0, 176, 80)">6</span>};

Divisores comuns ao 18 e 30 = {1,2,3,6}

Maior Divisor Comum entre 18 e 30 = {6};

### Algoritmo de Euclides

1) Pega os números que quer fazer o MDC (160, 64) e joga o maior deles para a esquerda do esquema:
   ![[Pasted image 20250329181949.png]]
2) Descubra quantas vezes o 64 cabe dentro do 160: 2 vezes que é o mesmo que 128;
3) O que sobrar para completar 160 joga embaixo dele:
   ![[Pasted image 20250329182214.png]]
4) Pega esse 32 que restou e joga para o lado do 64:
   ![[Pasted image 20250329182341.png]]
5)  Repete o processo com o 64 no lugar do 160 e 32 no lugar do 64:
    ![[Pasted image 20250329182427.png]]

6) Quando o resto atingir 0 o algoritmo termina e o MDC é o ultimo número da linha do meio;


## Decomposição Simultânea em fatores primos:

MDC de 90 e 54: 

![[Pasted image 20250329183146.png]]

Faz a decomposição padrão como no MMC, mas <span style="color:rgb(217, 46, 229)">só multiplicamos os fatores que puderam dividir os valores parametrizados simultaneamente</span>.

Mesmo em situações onde não é sequencialmente dividido, a regra é dividir o máximo possível pelo menor primo e só partir para o outro quando não houver divisão por nenhum valor. <span style="color:rgb(217, 46, 229)">No final só juntar os que puderam dividir os valores simultaneamente e multiplicar</span>:

![[Pasted image 20250329183620.png]]

## Propriedades do MDC:

1) O MDC entre números primos é 1, pois eles são divididos apenas por 1 e por eles mesmos;
2) Se A é divisor de B, então o MDC é o A:
   ![[Pasted image 20250329184346.png]]
3) 
   ![[Pasted image 20250329184904.png]]

4) Relação entre MMC e MDC:
	A multiplicação do MMC e MDC dos mesmos valores é o mesmo que a multiplicação dos valores entre si:
![[Pasted image 20250329185134.png]]

