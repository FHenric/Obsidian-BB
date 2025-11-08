
Variáveis se constroem com "variável = valor"

#### Print

"print()" serve para fazer no console o famoso "Hello World" e demais coisas 

Variações: 

nome = "Filipe"
print(f"hello {nome}") -> // hello Filipe

o f antes da string significa que essa string é uma string formatted e que pode receber expressões python, diferente de uma string normal. Facilita na concatenação e uso prático da linguagem.

## Operadores

![[Pasted image 20250512171249.png]]

![[Pasted image 20250512171516.png]]

## Listas 

Array normal como qualquer outro

##### Métodos

![[Pasted image 20250513112051.png]]

## Repetições

#### For
Serve para iterar sobre um objeto iterável como listas, tuplas, strings e afins.

#### **Sintaxe**: 
for 'item' in 'lista_itens' -> a variável 'item' é setada para receber cada valor do array em sua respectiva volta no loop.
```
	for variável in lista_variaveis:
    # Bloco de código a ser executado para cada item
    ...
else:
    # Bloco de código opcional executado ao final do loop,
    # se o loop não foi interrompido por um 'break'
    ...
```

O 'break' pode ser utilizado dentro de um 'if' nesse bloco de 'for' para condicionar o código a parar a iteração em algum caso específico:

```
numeros = [1, 3, 5]
for num in numeros:
    if num % 2 == 0:
        print("Número par encontrado!")
        break
else:
    print("Nenhum número par encontrado.")
```

###### Range() 
O 'range()' é usado para definir um numero específico de vezes que aquele bloco deve executar seu código. É uma maneira prática de definir limite num loop 'for'.

```
precos = [100, 50, 25, 75, 200]
desconto_percentual = 0.10 # 10% de desconto

# Usando range para iterar sobre os índices da lista
for i in range(len(precos)):
    desconto = precos[i] * desconto_percentual
    precos[i] = precos[i] - desconto

print("Preços com desconto:", precos)
```

No exemplo acima usamos o tamanho da lista de preços para definir o limite e a variável 'i', que está servindo como nosso "guia" para pegar a posição exata da lista de preços e aplicando o desconto no item dessa lista. 
#### While

O loop while serve para rodar infinitamente algum bloco de código enquanto aquela condição for 'true', então aqui definimos uma condição booleana e rodamos um código;

![[Pasted image 20250513124229.png]]

Observe que no fim do loop ele acrescenta o contador para não gerar um loop infinito, pois sem essa linha o bloco de execução rodaria infinitamente, pois o contador não sairia de 1.

## Dicionário

![[Pasted image 20250513124555.png]]

Para acessar esses valores individualmente podemos fazer como fazemos nas listas normais, só que no lugar do index nós colocaremos as chaves:

![[Pasted image 20250513125941.png]]

// "Programador Python"
// 27
// 70.2

## Funções

Blocos reutilizáveis de código

