# Instruções

- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 6 questões objetivas assinalando a alternativa correta
- Resolva as 4 questões dissertativas escrevendo no próprio arquivo .md
  - lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com ChatGPT e afins: entregar algo só para ganhar nota não faz você aprender e ficar mais inteligente. Não seja dependente da máquina! (E não se envolva em plágio!)
- ao final, publique seu arquivo lista_02.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas

**1)** Considere o seguinte código JavaScript:

```javascript
//EX01
let x = 17
let y = 5
let z = 8

resultadoBooleano =  (x < y) && (z > x) || (x - y > z)
console.log(resultadoBooleano)

const listaDeNumeros = [1, 2, 3, 4, 5];
let soma = 0;

for (let i = 0; i < listaDeNumeros.length; i++) {
  soma += listaDeNumeros[i];
}

console.log("A soma dos números é:", soma);

```
Qual das seguintes alternativas melhor descreve o que o código faz?

A) O código avalia a expressão booleana, imprime o resultado `false`, calcula a soma dos números de 1 a 5 e imprime o resultado no console.

**B) O código avalia a expressão booleana, imprime o resultado `true`, calcula a soma dos números de 1 a 5 e imprime o resultado no console.**

C) O código avalia a expressão booleana, imprime o resultado `true` e verifica se o número 5 está presente na lista de números.

D) O código avalia a expressão booleana, imprime o resultado `false` e ordena a lista de números em ordem crescente.

Resposta: b
______

**2)** Analise as funções calcularOrcamento() e calcularOrcamento2(). Num cenário em que a lista gastos fosse incializada como var gastos = [3600, 950, 620, 38] em ambas funções.

```javascript
//Versão 1 da função que calcula orçamento
function calculaOrcamento(){

    var gastos = [1800, 950, 620, 38];
    var totalGastos = gastos[0];
    var salario = 3500;
    var saldo = 0; 
    var statusSaldo =  'positivo';
    var i = 1;

    do{
        totalGastos += gastos[i];
        i++;
    } while(salario >= totalGastos && i<gastos.length)
    
    saldo = salario - totalGastos;

    if (saldo < 0 ){
        statusSaldo = 'negativo';
    } 
    console.log (`Seu saldo é ${statusSaldo} de ${saldo}. `);
}
```

```javascript
//Versão 2 da função que calcula orçamento
function calculaOrcamento2(){

    var gastos = [1800, 950, 620, 38];
    var totalGastos = gastos[0];
    var salario = 3500;
    var statusSaldo =  'positivo';
    var saldo = 0;
    var i = 1;

    while(salario >= totalGastos && i<gastos.length){
        totalGastos += gastos[i];
        i++;
    }

    saldo = salario - totalGastos;
    if (saldo < 0 ){
        statusSaldo = 'negativo';
    } 
    console.log (`Seu saldo é ${statusSaldo} de ${saldo}. `);
}
```

Escolha a opção que responde corretamente qual seria a saída após a execução de cada função:

A) As funções calcularOrcamento() e calcularOrcamento2() teriam a mesma saída: 'Seu saldo é negativo de -1050.'

**B) A saída de calcularOrcamento() seria: 'Seu saldo é negativo de -1050.' e a de calcularOrcamento2() seria: 'Seu saldo é negativo de -100.'**

C) A saída de calcularOrcamento() seria: 'Seu saldo é negativo de -100.' e a de calcularOrcamento2() seria: 'Seu saldo é negativo de -1050.'

D) As funções calcularOrcamento() e calcularOrcamento2() teriam a mesma saída: 'Seu saldo é negativo de -100.'

Resposta: b
______

**3)** Considere o seguinte trecho de código em JavaScript:
```javascript
//EX03
const numero = 10;

if (numero % 2 === 0) {
  console.log("O número é par!");
} else if (numero % 3 === 0) {
  console.log("O número é divisível por 3!");
} else {
  console.log("O número é ímpar e não é divisível por 3!");
}
```

 Qual das seguintes alternativas é a descrição mais precisa do que o código faz?


A) O código verifica se o número é divisível por 3 e, se for, exibe a mensagem "O número é divisível por 3!".

B) O código verifica se o número é par ou ímpar. Se for par, exibe a mensagem "O número é par!". Se for ímpar, exibe a mensagem "O número é ímpar!".

C) O código verifica se o número é par, ímpar ou divisível por 3. Se for par, exibe a mensagem "O número é par!". Se for divisível por 3, exibe a mensagem "O número é divisível por 3!". Se for ímpar, exibe a mensagem "O número é ímpar e não é divisível por 3!".

**D) O código verifica se o número é par, se é divisível por 3 ou se é ímpar. Se for par, exibe a mensagem "O número é par!". Se for divisível por 3 (e não for par), exibe a mensagem "O número é divisível por 3!". Se for ímpar (e não for divisível por 3), exibe a mensagem "O número é ímpar e não é divisível por 3!".**


Resposta: d
______

**4)** Qual será o resultado impresso no console após a execução desse código?
```javascript
//EX04
var saldo = 1000;
var limiteCredito = 500;
var valorCompras = [200, 800, 300, 400, 600];

for (var i = 0; i < valorCompras.length; i++) {
    var valorCompra = valorCompras[i];

    if (valorCompra <= saldo) {
        console.log("Compra " + (i+1) + " aprovada. Saldo restante: " + (saldo - valorCompra));
        saldo -= valorCompra;
    } else if (valorCompra <= saldo + limiteCredito) {
        console.log("Compra " + (i+1) + " aprovada com limite de crédito. Saldo restante: " + ((saldo + limiteCredito) - valorCompra));
        saldo = 0;
        limiteCredito -= (valorCompra - saldo);
    } else {
        console.log("Compra " + (i+1) + " negada. Saldo insuficiente e limite de crédito excedido.");
    }
}
```

Escolha a opção que responde corretamente:

A)
Compra 1 aprovada. Saldo restante: 800

Compra 2 aprovada com limite de crédito. Saldo restante: 700

Compra 3 aprovada. Saldo restante: 400

Compra 4 aprovada com limite de crédito. Saldo restante: 0

Compra 5 aprovada. Saldo restante: -200


B)
Compra 1 aprovada. Saldo restante: 800

Compra 2 aprovada com limite de crédito. Saldo restante: 700

Compra 3 aprovada. Saldo restante: 200

Compra 4 negada. Saldo insuficiente e limite de crédito excedido.

Compra 5 negada. Saldo insuficiente e limite de crédito excedido.


C)
Compra 1 aprovada. Saldo restante: 800

Compra 2 aprovada com limite de crédito. Saldo restante: 700

Compra 3 aprovada. Saldo restante: 400

Compra 4 negada. Saldo insuficiente e limite de crédito excedido.


**D)**

Compra 1 aprovada. Saldo restante: 800

Compra 2 aprovada. Saldo restante: 0

Compra 3 aprovada com limite de crédito. Saldo restante: 200

Compra 4 negada. Saldo insuficiente e limite de crédito excedido.

Compra 5 negada. Saldo insuficiente e limite de crédito excedido.


Resposta: d
______

**5)** Qual é o principal ciclo de vida de um jogo em Phaser.js?

Escolha a opção que responde corretamente:

A) Setup -> Update -> Draw

**B) Preload -> Create -> Update**

C) Load -> Initialize -> Render

D) Begin -> Play -> End


Resposta: b
______

**6)** Qual é o objetivo principal do módulo Arcade Physics em Phaser.js?

Escolha a opção que responde corretamente:

A) Renderizar gráficos 3D para jogos em HTML5.

**B) Simular interações físicas realistas, como colisões e movimentos, em jogos 2D.**

C) Criar efeitos de áudio para melhorar a experiência do usuário em jogos.

D) Gerenciar a lógica do jogo e a sincronização de eventos em jogos multiplayer.


Resposta: b
______

# Questões dissertativas

**7)** Implemente o pseudocódigo para o algoritmo representado no fluxograma da imagem.
![Uma imagem](assets/image.png)

Resposta:
``` 
algoritmo "votação"

var inteiro idade

# Leitura da idade do usuário
escreva("Insira sua idade: ")
idade <- leia(idade)

# Verifica se a pessoa pode votar
Se idade for menor que 16 então:
    escreva("Você não pode votar")

Se não então:
    # Verifica se o voto é opcional ou não
    Se idade for maior ou igual 16 e menor do que 18 então:
        escreva("Voto opcional")
    Se não então:
        escreva("Voto obrigatório")
```
______

**8)** Considere a implementação da classe base FormaGeometrica em um sistema de modelagem de formas geométricas. Sua tarefa é implementar, utilizando pseudocódigo, as classes derivadas Retangulo e Circulo, que herdam da classe FormaGeometrica, adicionando atributos específicos e métodos para calcular a área de um retângulo e de um círculo, respectivamente.

```
Classe FormaGeometrica:
    Atributos:
        - cor

    Método Construtor(cor):
        Define o valor do atributo cor com o valor passado como parâmetro.

    Método CalcularArea():
        # Implementação genérica para cálculo de área, a ser sobrescrita pelas subclasses.

```
Resposta:
```
algoritmo "criando classes retângulo e circulo"

Classe Retangulo herda de FormaGeometrica
    Atributos:
        - base
        - altura
    
    Método Construtor(base, altura):
        # Define os valores da base e altura para aqueles passados como parâmetro

    Método CalcularArea():
        # Implementação do retorno da área
        # Devolve a base multiplicada pela altura
        devolve(base x altura)

Classe Circulo herda de FormaGeometrica
    Atributos:
        - raio
    
    Método Construtor(raio):
        # Define o valor raio para aquele passado como parâmetro

    Método CalcularArea():
        # Implementação do retorno da área
        # Devolve a multiplicação de pi (arredondado para 3,14) com o quadrado do raio
        devolve(3,14 * raio^2)
```
______

**9)** Você foi contratado(a) como estagiário(a) da Tesla e está participando do desenvolvimento de um programa para simular o desempenho de um carro elétrico em uma corrida. Seu objetivo é determinar em quantos minutos o carro levará para completar uma determinada distância, levando em consideração uma velocidade inicial e uma taxa de aceleração constante. No entanto, você deseja garantir que o carro não exceda uma velocidade máxima nem que a corrida demore mais do que um tempo máximo. Implemente a lógica dessa simulação em pseudocódigo.

Resposta:
```
algoritmo "simulação corrida"

var inteiro distancia, velocidadeInicial, aceleracao, tempoLimite, velocidadeMaximo, tempoEncontrado, delta

# Inputs dos dados necessários
escreva("Insira a distância desejada: ")
distancia <- leia(distancia)

escreva("Insira a velocidade inicial desejada: ")
velocidadeInicial <- leia(velocidadeInicial)

escreva("Insira a acelaração desejada: ")
aceleracao <- leia(aceleracao)

escreva("Insira o tempo limite desejada: ")
tempoLimite <- leia(tempoLimite)

escreva("Insira a velocidade máxima permitida: ")
velocidadeMaximo <- leia(velocidadeMaximo)

# Para calcular o tempo para terminar a corrida, é preciso aplicar a fórmula de Bhaskara usando os valores recebidos
# Para isso, calcularemos primeiro o delta (b^2 -4ac) e depois o restante
# ^2 indica que um número está ao quadrado
# raiz() se refere a raiz quadrada de um número

delta <-  velocidadeInicial^2 -4*(aceleracao/2)*(-S) # Cálculo do delta representado como possível em pseudo código

tempoEncontrado <- (-velocidadeInicial + raiz(delta))/2a # Cálculo da primeira raiz representado como possível em pseudo código

Se tempoEncontrado for maior do que 0 então: # Verifica se o resultado é possitivo

    # Uso da fórmula da velocidade variada (v = v0 + at) em pseudo código para verificar se passamos a velocidade máxima
    Se velocidadeMaximo for menor que (velocidadeInicial + aceleracao * tempoEncontrado) então: 
        escreva("Velocidade máxima superada. Tente outros valores de entrada") # Retorno de invalidação

    # Verifica-se se o tempo limite não foi ultrapassado
    Ou se tempoLimite for menor que tempoEncontrado então:
        escreva("Tempo limite violado. Tente outros valores de entrada") # Retorno de invalidação

    Se não então: # Caso nenhum caso inválido tenha aparecido
        escreva("Experimento bem sucedido! Tempo final: " + tempoEncontrado) # Devolve o resultado da velocidade do trajeto

Se não então: # Se o resultado for negativo, refazemos o cálculo com a segunda raíz da equação

    tempoEncontrado <- (-velocidadeInicial - raiz(delta))/2a # Cálculo da segunda raiz representado como possível em pseudo código

    # Uso da fórmula da velocidade variada (v = v0 + at) em pseudo código para verificar se passamos a velocidade máxima
    Se velocidadeMaximo for menor que (velocidadeInicial + aceleracao * tempoEncontrado) então: 
        escreva("Velocidade máxima superada. Tente outros valores de entrada") # Retorno de invalidação

    # Verifica-se se o tempo limite não foi ultrapassado
    Ou se tempoLimite for menor que tempoEncontrado então:
        escreva("Tempo limite violado. Tente outros valores de entrada") # Retorno de invalidação

    Se não então: # Caso nenhum caso inválido tenha aparecido
        escreva("Experimento bem sucedido! Tempo final: " + tempoEncontrado) # Devolve o resultado da velocidade do trajeto

```
______

**10)** Uma matriz é uma coleção bidimensional de elementos, organizados em linhas e colunas. A seguir, é fornecida a implementação da função SomaDeMatrizes(matrizA, matrizB), que calcula a soma de duas matrizes. Sua tarefa é implementar uma função semelhante, porém que realize a multiplicação de duas matrizes.

```
Função SomaDeMatrizes(matrizA, matrizB):
    # Verifica se as duas matrizes têm o mesmo número de linhas e colunas
    Se tamanho(matrizA) ≠ tamanho(matrizB) então:
        Retornar "As matrizes não podem ser somadas. Elas têm dimensões diferentes."
    
    /* Nesse contexto, o correto é "se não", pois a presença de "se" logo acima exige o par "se" e "se não",
    mesmo que "senão" possa ter o mesmo valor em alguns contextos */
    **Senão**: 
        linhas <- tamanho(matrizA)
        colunas <- tamanho(matrizA[0]) # Considerando que todas as linhas têm o mesmo número de colunas
        matrizResultado <- novaMatriz(linhas, colunas)

        # Loop para percorrer cada elemento das matrizes e calcular a soma
        Para i de 0 até linhas-1 faça:
            Para j de 0 até colunas-1 faça:
                matrizResultado[i][j] <- matrizA[i][j] + matrizB[i][j]

        Retornar matrizResultado

# Exemplo de uso da função
matrizA <- [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
matrizB <- [[9, 8, 7], [6, 5, 4], [3, 2, 1]]

matrizSoma <- SomaDeMatrizes(matrizA, matrizB)
Escrever("Soma das matrizes:")
ImprimirMatriz(matrizSoma)
```
Resposta:

```
algoritmo "multiplicação de matrizes"

Função MultiplicaMatrizes(matriz1, matriz2):
    # Verifica se as duas matrizes têm o tamanho de linhas e colunas compatíveis entre sí
    Se tamanho(matriz1) != tamanho(matriz2) então:
        Retornar "Multiplicação inválida! Dimenções diferentes encontradas."
    
    Se não: 
        linhas <- tamanho(matriz1)
        colunas <- tamanho(matriz1[0]) # Assume-se que a matriz é simétrica
        matrizResultado <- novaMatriz(linhas, colunas)

        /* ***Explicações:***
        A multiplicação de matrizes é mais complicada em relação as somas, optando-se pelo uso de uma 
        terceira variável para resolver a situação.

        O método parte de algumas observações em cima de multiplicações matriciais:
        1) A linha da posição resoltado sempre é a mesma linha da matriz 1
        2) A coluna da matriz resultado sempre é a mesma coluna da matriz 2
        3) A coluna da matriz 1 é sempre igual a linha da matriz dois

        A partitir disso foram criadas 3 variáveis i, j e k que funcionam, respectivamente, como as regras apresentadas.

        A escolha de que j se basearia nas colunas e não nas linhas, é irrelevante neste caso, por se tratar de um algoritmo 
        específico para matrizes quadradas, mas teria que se basear nas colunas da segunda matriz em casos de matrizes não quadradas.

        Optou-se pelo desenvolvimento da calculadora apenas para matrizes quadradas por dois motivos:

        1) O autor ter desenvolvido este código com febre e com dores no corpo;
        2) Devido a indicação do enunciado para se basear na função de somas apresentada, sem explicitar a necessidade de alterar
        essa propriedade.

        Entendo que essa não é a função ideal para a solução do problema, mas caso fossemos ajustar essa questão, seria preciso que 
        o número de linhas e colunas da matrix resultados fossem iguais ao da matriz 2, necessitando de mudança na estruturação das 
        variáveis para desvincular as linhas da matriz resultado das da matriz 1.
        Ainda precisaríamos fazer mais ajustes e testes, mas esse seria o maior problema a ser resolvido. 
        /*


        # Loop para percorrer cada elemento das matrizes e calcular a multiplicação de forma correta
        Para i de 0 até ser igual a linhas-1 faça:
            Para j de 0 até ser igual a colunas-1 faça:
                matrizResultado[i][j] <- 0
                Para k de 0 até ser igual a colunas-1 faça:
                    matrizResultado[i][j] <- matrizResultado + matriz1[i][k] * matriz2[k][j]

        Devolve matrizResultado

        ----Fim do Algoritmo--


# Demonstração de uso
matriz1 <- [[a, b, c], [d, e, f], [g, h, i]]
matriz2 <- [[j, k, l], [m, n, o], [p, q, r]]

matrizMultiplicada <- MultiplicaMatrizes(matriz1, matriz2)
Escrever("A mutiplicação matrícial é: ")
MostraMatriz(matrizMultiplicada)

```
