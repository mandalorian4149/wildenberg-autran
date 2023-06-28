# Aprendendo Programação em C
#### Um jeito diferente de aprender programação.

## Revisando estrutura básica

##### Aqui você irá ver de novo e praticar a estrutura básica.

> Usando o compilador C online repassado para a turma {https://www.onlinegdb.com/online_c_compiler} reescreva o código abaixo:
```C
#include<stdio.h>
int main(){
	int a;
	a = 20;
	printf("o valor de a é: %d",a);
}
```
Na estrutura básica temos:
>	#include<stdio.h>
>	int main()
> 	{} //chaves para o escopo do código.
### Atividade QT01 (0,1 pontos) - Reescreva o código criando mais duas variáveis inteiras e mostre-as na saída padrão.

## Revisando estrutura condicional.

##### Aqui você irá ver de novo e praticar as condicionais de C.

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
>  Tarefa 01 - Altere o código e execute-o no falcon++ para que ele imprime todos os números entre 20 e 40. Após conseguir, basta copiar as linhas de código e colar aqui e realize o commit. #include<stdio.h>
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
