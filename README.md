# Aprendendo Programação em C
#### Um jeito diferente de aprender programação.

# Registros em C - Uma forma legal de criar uma "ficha" sobre alguma coisa.
### Nos exemplos a seguir vamos ver códigos com Structs em C que representa um registro, ou seja, tipos diferentes de dados em uma mesma estrutura.
#### Observe o código abaixo auto-explicativo e faça as questões seguintes.

```C
#include <stdio.h>
#include <conio.h>
int main(void)
{
  /*Criando a struct */
  struct ficha_de_aluno
  {
    char nome[100];
    char disciplina[100];
    float nota_prova1;
    float nota_prova2;
  };
  
  /*Criando a variável aluno que será do
  tipo struct ficha_de_aluno */
  struct ficha_de_aluno aluno; //perceba que ficha_de_aluno é como se fosse um tipo. A vairável aluno está sendo criada com esse tipo.
  
  printf("\n---------- Cadastro de aluno -----------\n\n\n");
  
  printf("Nome do aluno ......: ");
  fflush(stdin);
  
  /*usaremos o comando fgets() para ler strings, no caso o nome
  do aluno e a disciplina.
  fgets(variavel, tamanho da string, entrada)
  como estamos lendo do teclado a entrada é stdin (entrada padrão),
  porém em outro caso, a entrada tambem poderia ser um arquivo */
  
  fgets(aluno.nome, 40, stdin);
  
  printf("Disciplina ......: ");
  fflush(stdin);
  fgets(aluno.disciplina, 40, stdin);
  
  printf("Informe a 1a. nota ..: ");
  
  scanf("%f", &aluno.nota_prova1);
  
  printf("Informe a 2a. nota ..: ");
  scanf("%f", &aluno.nota_prova2);
  
  printf("\n\n --------- Mostrando os dados da struct ---------\n\n");
  printf("Nome ...........: %s", aluno.nome);
  printf("Disciplina .....: %s", aluno.disciplina);
  printf("Nota da Prova 1 ...: %.2f\n" , aluno.nota_prova1);
  printf("Nota da Prova 2 ...: %.2f\n" , aluno.nota_prova2);
  
  getch();
  return(0);
}
```
>	QT11(0,25) - Crie estruturas novas e correlacione com sua realidade. Use estruturas de repetição e estruturas switch. Ao final, as fichas com os cadastros deverão ser apresentadas.
```
#include <stdio.h>
#include <stdlib.h>

struct ficha_de_aluno
{
  char nome[100];
  char disciplina[100];
  float nota_prova1;
  float nota_prova2;
};

int main(void)
{
  int num_alunos;
  
  printf("Quantidade de alunos: ");
  scanf("%d", &num_alunos);
  
  struct ficha_de_aluno alunos[num_alunos];
  
  for (int i = 0; i < num_alunos; i++)
  {
    printf("\n---------- Cadastro de aluno %d -----------\n\n", i+1);
  
    printf("\n\nNome do aluno:Autran ");
    fflush(stdin);
    fgets(alunos[i].nome, 100, stdin);
  
    printf("Disciplina: introdução a metodologia cientifica ");
    fflush(stdin);
    fgets(alunos[i].disciplina, 100, stdin);
  
    printf("Informe a 1a. nota: 10 ");
    scanf("%f", &alunos[i].nota_prova1);
  
    printf("Informe a 2a. nota: 10");
    scanf("%f", &alunos[i].nota_prova2);
  }
  
  printf("\n\n --------- Mostrando os dados dos alunos ---------\n\n");
  
  for (int i = 0; i < num_alunos; i++)
  {
    printf("\n---------- Aluno %d -----------\n\n", i+1);
    printf("Nome: %s", alunos[i].nome);
    printf("Disciplina: %s", alunos[i].disciplina);
    printf("Nota da Prova 1: %.2f\n", alunos[i].nota_prova1);
    printf("Nota da Prova 2: %.2f\n", alunos[i].nota_prova2);
  }

  return 0;
}
````
QT12(0,25) - Crie estruturas em C para organizar alguma necessidade sua e realize o cadastro dos registros. Utilize estruturas de loop para realizar mais de um registro. Ao final, apresente todos os cadastros realizados. Justifique todo o seu código.
```
#include <stdio.h>
#include <stdlib.h>

struct horario_estudo
{
  char disciplina[100];
  int dia_semana;
  int hora_inicio;
  int hora_fim;
};

int main(void)
{
  int num_registros;
  
  printf("Quantidade de registros:02");
  scanf("%d", &num_registros);
  
  struct horario_estudo registros[num_registros];
  
  for (int i = 0; i < num_registros; i++)
  {
    printf("\n---------- Cadastro de horário de estudo %d -----------\n\n", i+1);
  
    printf("Disciplina: reações isostaticas");
    fflush(stdin);
    fgets(registros[i].disciplina, 01, stdin);
  
    printf("\n\nDia da semana (1-6): ");
    scanf("%d", &registros[i].dia_semana);
  
    printf("Hora de início:08:00 ");
    scanf("%d", &registros[i].hora_inicio);
  
    printf("Hora de fim: 10:00 ");
    scanf("%d", &registros[i].hora_fim);
    
    printf("disciplina: equações diferenciais");
    fflush(stdin);
    fgets(registros[i]. disciplina, 02,stdin);
    
    printf("\n\ndia da semana(2-6:");
    scanf("%d", &registros[i].hora_inicio);
    
    printf("hora de início:10:30");
    scanf("%d",&registros[i].hora_fim);
    
    
    
  }
  
  printf("\n\n --------- Mostrando os registros de horário de estudo ---------\n\n");
  
  for (int i = 0; i < num_registros; i++)
  {
    printf("\n---------- Registro %d -----------\n\n", i+1);
    printf("Disciplina: %s", registros[i].disciplina);
    printf("Dia da semana: %d\n", registros[i].dia_semana);
    printf("Hora de início: %d\n", registros[i].hora_inicio);
    printf("Hora de fim: %d\n", registros[i].hora_fim);
  }

  return 0;
}



# Funções em C
````
Declare funções. Uma com opção de menu para o R.U, Biblioteca Central, Teatro ou H.U e mostre-os na tela. Outra que mostre apenas uma saudação do dia após leitura do nome da pessoa. (QT9 - 0,25)

````
#include <stdio.h>

void exibirMenu() {
    printf("Menu:\n");
    printf("1. R.U\n");
    printf("2. Biblioteca Central\n");
    printf("3. Teatro\n");
    printf("4. H.U\n");
}

void exibirSaudacao(char nome[]) {
    printf("Bom dia, %s!\n", nome);
}

int main() {
    int opcao;
    char nome[100];
    
    exibirMenu();
    
    printf("Escolha uma opção: ");
    scanf("%d", &opcao);
    
    switch (opcao) {
        case 1:
            printf("Você escolheu R.U\n");
            break;
        case 2:
            printf("Você escolheu Biblioteca Central\n");
            break;
        case 3:
            printf("Você escolheu Teatro\n");
            break;
        case 4:
            printf("Você escolheu H.U\n");
            break;
        default:
            printf("Opção inválida\n");
            break;
    }
    
    printf("Digite seu nome: ");
    scanf("%s", nome);
    
    exibirSaudacao(nome);
    
    return 0;
}
````
Declare funções para: Totalizar a quantidade de árvores em cada setor(CCHL, CCE, CT, CCN, DIE, CCS) da ufpi através de entrada de dados pelo teclado. Ao final mostrar o total de árvores na UFPI. (Q10 - 25).

````
#include <stdio.h>
int totalArvoresSetor(const char* setor) {
    int totalArvores;
    printf("Digite a quantidade de árvores no setor %s: ", setor);
    scanf("%d", &totalArvores);
    return totalArvores;
}

int main() {
    int cchl, cce, ct, ccn, die, ccs;
    int totalArvores;

    cchl = totalArvoresSetor("CCHL");
    cce = totalArvoresSetor("CCE");
    ct = totalArvoresSetor("CT");
    ccn = totalArvoresSetor("CCN");
    die = totalArvoresSetor("DIE");
    ccs = totalArvoresSetor("CCS");

    totalArvores = cchl + cce + ct + ccn + die + ccs;

    printf("\nTotal de árvores na UFPI:\n");
    printf("CCHL: %d\n", cchl);
    printf("CCE: %d\n", cce);
    printf("CT: %d\n", ct);
    printf("CCN: %d\n", ccn);
    printf("DIE: %d\n", die);
    printf("CCS: %d\n", ccs);
    printf("Total geral: %d\n", totalArvores);

    return 0;
}


# Vetores em C
````
Declarar e preencher um vetor em C nos possibilita muitas utilizações. Observe a estrutura básica de um vetor em C.
Observe o código abaixo.



```
#include <stdio.h>

int main()
{
    int meuVetor[3];
    
    meuVetor[0] = 32;
    meuVetor[1] = 10;
    meuVetor[2] = 5;
    
    printf("O valor dos vetores é: %d\n",meuVetor[0]);
    printf("O valor dos vetores é: %d\n",meuVetor[1]);
    printf("O valor dos vetores é: %d\n",meuVetor[2]);
    
    return 0;
}
```
>	QT04 (0,25 pontos) - Altere o código acima para 10 posições de vetor atribuindo 10 valores inteiros manuais e imprimindo todos eles na tela.

Para cada valor a partir da posição zero do vetor, temos um elemento. Cada posição é representada pelo símbolo de colchetes. Sempre iniciará da posição zero. Dessa forma, se o vetor de elementos tem 3 posições corresponderá às posições 0,1,2 (três elementos). A mesma ideia se aplica a qualquer quantidade de elementos.
Quando essa quantidade é bem grande, usamos laços de repetição. Observe o código abaixo.
```
#include <stdio.h>

int main()
{
    int meuVetor[10];
    
    printf("Digite 10 valores inteiros:\n");
    
    for (int i = 0; i < 10; i++) {
        printf("Valor %d: ", i + 1);
        scanf("%d", &meuVetor[i]);
    }
    
    printf("\nValores do vetor:\n");
    for (int i = 0; i < 10; i++) {
        printf("Valor na posição %d: %d\n", i, meuVetor[i]);
    }
    
    return 0;
}
```C
#include <stdio.h>
// Cada posição i do vetor é um valor multiplicado por 2. Usamos um for para preencher e outro for para mostrar.
int main()
{
    int meuVetor[10];
    
    for (int i=0; i<10; i++){
        meuVetor[i] = i*2;
    }
    for (int i=0; i<10; i++){
        printf("Posição %d e valor => %d \n",i,meuVetor[i]);
    }
    return 0;
}

```
>	QT05 (0,25 pontos) - Altere o código acima para que seja lido diretamente do teclado um valor inteiro, ao invés de atribuído. Mostre todos os valores lidos ao final.
```
>#include <stdio.h>

int main()
{
    int meuVetor[10];
    
    printf("Digite 10 valores inteiros:\n");
    
    for (int i = 0; i < 10; i++) {
        printf("Valor %d: ", i + 1);
        scanf("%d", &meuVetor[i]);
    }
    
    printf("\nValores lidos:\n");
    for (int i = 0; i < 10; i++) {
        printf("Posição %d e valor => %d\n", i, meuVetor[i]);
    }
    
    return 0;
}

Em algumas situações temos que impor condições para obter dados de tudo o que foi lido e armazenado em uma lista de vetores. Vejamos um exemplo no código abaixo:
```C
#include <stdio.h>

int main()
{
    int meuVetor[10]; 	//vetor de 10 elementos
    int numero;		//variável inteira
    int pos = 0;	//variável inteira e inicializada com zero
    int neg = 0;	// outra inteira e inicializada com zero	

//Essa estrtura for preenche o vetor
    for (int i=0; i<10; i++){
        printf("Digite um valor para o vetor: ");
        scanf("%d",&numero);
        meuVetor[i] = numero;
    }
//Essa verifica uma condição e totaliza os valores.
    for (int i=0; i<10; i++){
        if(meuVetor[i] > 0){
            pos = pos + 1;
        }else neg = neg + 1;
    }
//Ao final do código, mostra os valores totalizados.
    printf("Quantidade de numeros positivos: %d \n",pos);
    printf("Quantidade de numeros negativos: %d \n",neg);
    return 0;
}
```
>	QT06 (0,5 - pontos) - Crie um código onde sejam lidos 20 votos. Os votos serão armazenados em um vetor inteiro de elementos. Cada número do voto corresponde a um time de futebol que será mostrado em um menu com 4 opções sendo elas: Flamengo, Vasco, São Paulo, Corinthians. Totalize os votos ao final e mostre na tela.
```
#include <stdio.h>

int main()
{
    int votos[20];
    int totalFlamengo = 0, totalVasco = 0, totalSaoPaulo = 0, totalCorinthians = 0;
    int i;

    printf("Digite os votos:\n");
    for (i = 0; i < 20; i++) {
        printf("Voto %d: ", i + 1);
        scanf("%d", &votos[i]);

        switch (votos[i]) {
            case 1:
                totalFlamengo++;
                break;
            case 2:
                totalVasco++;
                break;
            case 3:
                totalSaoPaulo++;
                break;
            case 4:
                totalCorinthians++;
                break;
            default:
                printf("Opção inválida!\n");
                i--; // Repetir a leitura para o mesmo índice
                break;
        }
    }

    printf("\nResultado dos votos:\n");
    printf("Flamengo: %d votos\n", totalFlamengo);
    printf("Vasco: %d votos\n", totalVasco);
    printf("São Paulo: %d votos\n", totalSaoPaulo);
    printf("Corinthians: %d votos\n", totalCorinthians);

    return 0;
}

    
````
QT07 (0,5 - pontos) - Refaça a mesma questão anterior utilizando o While e acrescentando uma condição de parada chamada "Totalizar" representada pelo número 99 no menu.
````
#include <stdio.h>

int main()
{
    int meuVetor[10];
    int numero;
    int pos = 0;
    int neg = 0;
    int totalizar = 0; // Condição de parada
    
    printf("Digite os valores do vetor (digite 99 para parar):\n");
    
    int i = 0;
    while (i < 10 && totalizar != 99) {
        printf("Valor %d: ", i + 1);
        scanf("%d", &numero);
        
        if (numero == 99) {
            totalizar = 99; // Definindo a condição de parada
        } else {
            meuVetor[i] = numero;
            
            if (meuVetor[i] > 0) {
                pos++;
            } else {
                neg++;
            }
            
            i++;
        }
    }
    
    printf("\nValores do vetor:\n");
    for (int j = 0; j < i; j++) {
        printf("Valor na posição %d: %d\n", j, meuVetor[j]);
    }
    
    printf("\nTotal de valores positivos: %d\n", pos);
    printf("Total de valores negativos: %d\n", neg);
    
    return 0;
}
````
QT08 (0,5 - pontos) - Crie um vetor de 20 posições para ler números correspondente ao estilo musical da turma (1 - Sertanejo, 2 - Internacional, 3 - Pop, 4 - Coreano, 5 - Forró, 6 - Funk, 7 - Gospel, 8 - Rock, 9 - Eletrônica, 10 - Classica). Totalize os votos por estilo e mostre ao final. Utilize o Do..while.
#include <stdio.h>
```
int main()
{
    int estiloMusical[20];
    int voto;
    int totalEstilo[10] = {0}; // Vetor para armazenar a contagem de votos por estilo
    int i = 0;
    
    printf("Digite os votos dos estilos musicais (1 a 10) [99 para parar]:\n");
    
    do {
        printf("Voto %d: ", i + 1);
        scanf("%d", &voto);
        
        if (voto >= 1 && voto <= 10) {
            estiloMusical[i] = voto;
            totalEstilo[voto - 1]++; // Incrementa a contagem de votos para o estilo correspondente
            i++;
        } else if (voto != 99) {
            printf("Voto inválido! Digite novamente.\n");
        }
    } while (voto != 99 && i < 20);
    
    printf("\nTotal de votos por estilo musical:\n");
    for (int j = 0; j < 10; j++) {
        printf("Estilo %d: %d voto(s)\n", j + 1, totalEstilo[j]);
    }
    
    return 0;
}

## Revisando estrutura básica

##### Aqui você irá ver de novo e praticar a estrutura básica.
````
> Usando o compilador C online repassado para a turma {https://www.onlinegdb.com/online_c_compiler} reescreva o código abaixo:
```C
#include<stdio.h>
int main(){
	int a;
	a = 20;
	printf("o valor de a é: %d",a);
}

Na estrutura básica temos:
>	#include<stdio.h>
>	int main()
> 	{} //chaves para o escopo do código.
### Atividade QT01 (0,1 pontos) - Reescreva o código criando mais duas variáveis inteiras e mostre-as na saída padrão.

## Revisando estrutura condicional.

##### Aqui você irá ver de novo e praticar as condicionais de C.
````
> Usando o compilador C online repassado para a turma {https://www.onlinegdb.com/online_c_compiler} reescreva o código abaixo:
```C
#include <stdio.h>
int main(){
	int a;
	a = 20;
	if (a < 20){
		printf("O valor é menor que 20");
	}
}
```
Na estrutura acima temos:
>	O uso de uma estrutura condicional com o if
>	Seu escopo também inicia com chaves e termina com chaves.
### Atividade QT02 (0,1 pontos) - Reescreva o código criando mais uma estrutura if para uma frase se valores de a forem maiores que 20.

## Revisando estrutura condicional com if - else.

##### Aqui você irá ver de novo e praticar as condicionais de C com if - else.

> Usando o compilador C online repassado para a turma {https://www.onlinegdb.com/online_c_compiler} reescreva o código abaixo:
```C
#include <stdio.h>
int main(){
	int a;
	a = 20;
	if (a < 20){
		printf("O valor é menor que 20");
	}else{
		printf("esse é maior");
	}
}
```
Na estrutura acima temos:
>	O uso de uma estrutura condicional com o if e outra para o else
>	Seu escopo também inicia com chaves e termina com chaves também.
### Atividade QT03 (0,1 pontos) - Reescreva o código com estrutura if-else para uma frase se valores forem negativos ou positivos.

## Revisando Laços de Repetição: for.
##### Nessa atividade iremos revisar através de código escrito em C, como podemos trabalhar com esse tipo de variável que pode armazenar dados de um único tipo.

>  Usando novamente o "for" em C.
```C
int main(){
  
  //Vamos criar um laço de repetição ou loop usando o for logo abaixo.
  //Esse laço apenas escreverá 10 números começando do zero.
  //Observe que foi criado e inicializado uma variável "i" no próprio for.
  
  for(int i=0; i<10;i++){
    print("Esse é o valor de i: %d",i);
  }
}
```
>  Tarefa 01 - Altere o código e execute-o no falcon++ para que ele imprime todos os números entre 20 e 40. Após conseguir, basta copiar as linhas de código e colar aqui e realize o commit.
```
> #include<stdio.h>
int main(){
	for(int i=20; i<41;i++){
    printf("\nEsse é o valor de i: %d",i);
  }
}

## Revisando Laços de Repetição: While.
#### Aqui iremos agora focar no laço de repetição While.

>  Usando o While temos uma particularidade. Diferente do for, ele não é finalizado com um valor específico. Ele é finalizado com uma condição. Observe:

```C
int main(){
  // Foi criado uma variável inteira chamada "parada" e inicializada com 0 (zero).
  int parada = 0;
  //Agora vamos impor a condição de que essa variável não pode ser maior que 20. Iremos incrementar ela de 1 a cada interação.
  while (parada <=20){    
    printf("\n O valor da parada agora: %d",parada);
    //na linha abaixo incrementamos de 1 para a próxima interação.
    parada++;
  }  
}
```
>  Tarefa 2 - Altere o código anterior para mostrar a frase "esse é o valor escolhido" quando a variável "parada" for igual a 9. Copie e cole o código aqui e realize o commit.
 ```
 #include<stdio.h>
int main(){
  int parada = 0;
  while (parada <=20){    
    printf("\n O valor da parada agora: %d",parada);
    parada++;
     if (parada==9){  
	     printf("\n esse e o valor escolhido:%d",parada);  
	            }
  }
   return 0 ;
}
   

## Revisando Laços de Repetição: Do
#### Agora iremos finalizar nosso último laço de repetição. Iremos usar o do.
>  Usando o do..while temos algo bem legal: iremos colocar a condição de parada apenas no final do código. Observe:
```C
int main(){
  //Criamos a variável inteira incremento aqui para ser lida do teclado. O usuário irá digitar um valor inteiro.
  int incremento = 0;
  // Nas linhas abaixo iremos escrever todo o nosso cardápio vitual.
  do{
    printf("\n############# CARDAPIO VIRTUAL ##############");
    printf("\n[1]-Cafe");
    printf("\n[2]-Almoco");
    printf("\n[3]-Janta");
    printf("\n[99]-Sair do Menu");
    printf("\n#############################################");
    //Aqui mostramos uma frase para o usuário escolher um dos números do cardápio.
    printf("\nEscolha a um numero do cardapio: ");
    //Nesse scanf fazemos a leitura do valor que ele vai digitar.
    scanf("%d",&incremento);
  }while(incremento != 99);// com essa condição, o laço do..while só irá parar quando ele digitar 99.
}
```
>  Tarefa 3 - Altera o código para que quando seja escolhido 1, seja escrito "você escolheu cafe da manhã". Quando 2, seja escrito "você escolheu almoço". Quando 3, seja escrito "você escolheu agora jantar". Copie o código aqui e realize o commit.

 ```
int main(){
  int incremento = 0;
  do{
    printf("\n############# CARDAPIO VIRTUAL ##############");
    printf("\n[1]-Cafe da manha");
    printf("\n[2]-Almoco");
    printf("\n[3]-Janta");
    printf("\n[99]-Sair do Menu");
    printf("\n#############################################");
    printf("\nEscolha a um numero do cardapio: ");
    scanf("%d",&incremento);
    if(incremento==1)
    	printf( "\n voce escolheu o cafe da manha");
    if(incremento==2)
        printf("\n voce escoheu o almoco");
    if(incremento==3)
        printf("\n voce escolheu o jantar");
    if(incremento==99)
    	printf("MEUS PONTOS VEACO");
  }while(incremento !=99);
}
