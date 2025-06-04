# 🧮 Calculator / Calculadora

🇺🇸 **English**  
A simple calculator made in C as a university project. It supports addition, subtraction, multiplication, division, and exponentiation. This project was developed during my first semester of Software Engineering at UNIGRAN.

🇧🇷 **Português**  
Uma calculadora simples feita em C como projeto universitário. Ela suporta adição, subtração, multiplicação, divisão e potenciação. O projeto foi desenvolvido durante meu primeiro semestre de Engenharia de Software na UNIGRAN.

---

## ✨ Features / Funcionalidades

- ✅ Menu interativo / Interactive menu
- ➕ Addition / Adição  
- ➖ Subtraction / Subtração  
- ✖️ Multiplication / Multiplicação  
- ➗ Division / Divisão  
- ⬆️ Exponentiation / Potenciação  
- 🌐 Support for accented characters using `locale.h`

---




#include <stdio.h> //Inclusao de biblioteca
#include <locale.h> //Utilizei para permitir usar acentos !
#include <string.h> //Utilizei para poder nomear as strings (vc vai entender dps !! ficou legal eu prometo !)
int main(){ //Tipo da main
  setlocale(LC_ALL, "Portuguese"); //Comando do locale.h para usar acentos

   int N1, N2, op, i=1, r=1, flag; //Declaracao das variaveis, int para poder utilizar switch, senao ate seria melhor utilizar float por conta da divisao !
   char Operacao[20]; //Char para nomear as operacoes
   char Sinal[20]; //Char para os sinais (+, -, x, /, ^)

   do{

   printf("\n========== OPERAÇÔES =========="); //Tabela com as operacoes incluindo a de sair
   printf("\n-> 0\t-Sair\n");
   printf("\n-> 1\t-Adição\n");
   printf("\n-> 2\t-Subtração\n");
   printf("\n-> 3\t-Multiplicação\n");
   printf("\n-> 4\t-Divisão\n");
   printf("\n-> 5\t-Potenciação");
   printf("\n==============================\n");

   printf("\nEscolha uma operação: "); //Pede ao usuario a operacao escolhida
   scanf("%d", &op); //le a operacao

   if (op != 0){ //Caso a operacao escolhida for diferente de 0 (sair) ele continua o codigo, fiz isso para que caso o usuario escolha 0 o programa nao execute todo ele e dps encerre.

   printf("\nInforme um numero: "); //pede o valor de N1
   scanf("%d", &N1); //Le N1

   printf("\nInforme um numero: "); //Pede o valor de n2
   scanf("%d", &N2); //le N2

   switch(op){ //Estrutra de switch para executar a operacao escolhida pelo usuario
      case 1:
         r = N1 + N2; //Adicao
         strcpy(Operacao, "Adição"); //Declara aquele char de antes como "Adicao"
         strcpy(Sinal, "+"); //Declara o char de Sinal como o sinal de adicao
         break;
      case 2:
         r = N1 - N2; //Subtracao
         strcpy(Operacao, "Subtração"); //Declara aquele char de antes como "Subtracao"
         strcpy(Sinal, "-"); //Declara o char de Sinal como o sinal de subtracao
         break;
      case 3:
         r = N1 * N2; //Multiplicacao
         strcpy(Operacao, "Multiplicação"); //Declara aquele char de antes como "Multiplicacao"
         strcpy(Sinal, "x"); //Declara o char de Sinal com o sinal de Multiplicacao
         break;
      case 4:
         if (N2 == 0){ //Caso o N2 for 0 nao executa a divisao
            printf("\nNão existe divisão por 0!\n"); //Mensagem caso o N2 for 0
            flag = 1; //Aqui declarei uma flag para quando o N2 for 0 para o programa nao executar a divisao no fim !!
         }
         else
            r = N1 / N2; //Se o N2 for diferente de 0 executa a conta e tudo mais !
            strcpy(Operacao, "Divisão"); //Declara aquele char de antes como "Divisao"
            strcpy(Sinal, "/"); //Declara o char de Sinal com o sinal de Divisao
         break;
      case 5:
         while(i<=N2){ //Utilizo a estrutura "while" para contar ate o N2 e assim fazer a conta bem sucedida
            r = r * N1; //Conta da potenciacao
            i++; //incrementa o i para ate menor ou igual a N2
         }
         strcpy(Operacao, "Potenciação"); //Declara aquele char de antes como "Potenciacao"
         strcpy(Sinal, "^"); //Declara o char de Sinal com o sinal de Potenciacao !
         break;
      default:
         printf("\nInforme uma operação valída!\n"); //mensagem caso o usuario nao digite uma operacao valida
   }
   if (flag != 1) //Aqui vem a flag da linha 52 que foi usada para impedir a divisao por 0
      printf("\nO resultado da %s de %d %s %d é: %d\n\n", Operacao, N1, Sinal, N2, r); //Aqui e a mensagem do resultado, aqui e o motivo de eu ter usado os char de nome e sinal, pq se a pessoa escolher adicao aparece assim (O resultado da Adicao de x + y e: r ) ai fica bonito !! tmj por ter lido ate aqui Marcos !

  }

   }while (op != 0); //para o Do caso o 0 seja digitado
   printf("\n--> Programa encerrado\n"); //Mensagem para quando o programa for encerrado !

   printf("\n"); //Quebra uma linha no fim para deixar bonitinho
   return 0; //Retorna a main bem sucedida !!
}

//Que exercicio legal TMJ !!








