#include <stdio.h>
#include <math.h>

int main(void) {
  int Impedancia;
  float Espessura;
  float Permissividade;
  float ComprimentoOnda;
  float Atenuacao;
  float A, B, W;
  float auxiliar1 = W/Espessura;
  float auxiliar2 = W/Espessura;
  
  //Impedância - Informações.
  printf("Informe o valor da impedância característica:\n");
  scanf("%d", &Impedancia);
  
  //Espessura - Informações.
  printf("Digite o valor da espessura do susbtrato em centímetros:\n");
  scanf("%f", &Espessura);

  //Permissividade relativa - Informações.
  printf("Determine o valor da permissividade relativa:\n");
  scanf("%f", &Permissividade);
  printf("\n");
  
  printf("A partir dos dados fornecidos, será calculado a espessura 'W' da linha e o comprimento de onda guiado.\n");
  printf("\n");
  
  printf("Recapitulando, dados coletados:\n");
  printf("Permissividade: %f\n", Permissividade);
  printf("Espessura: %f\n", Espessura);
  printf("Impedância: %d\n", Impedancia);
  printf("\n");

  //Definição dos parâmetros.
  A = (Impedancia/60.0)*sqrt((Permissividade+1)/2.0)+(Permissividade-1)/(Permissividade+1)*(0.23+0.11/Permissividade);
  B = (377*3.14159265)/(2*Impedancia*sqrt(Permissividade));
  
  printf("Cálculo do parâmetro A: %f", A);
  printf("\n");
  printf("Cálculo do parâmetro B: %f", B);
  printf("\n");

  //Cálculo 1:
  auxiliar1 = (8*pow(2.7182818, A))/(pow(2.7182818, 2*A)-2);
  printf("\n");
  printf("Através da equação 1, isto é, W/D <= 2: %f", auxiliar1);
  printf("\n");

  //Cálculo 2:
  float a = (2/3.14159265); /*2 dividido por pi*/
  float b = B-1-log(2*B-1); /*B-1-ln(2B-1)*/
  float c = log(B-1); /* ln(B-1)*/
  
  auxiliar2 = (a*(b+((Permissividade-1)/(2*Permissividade))*(c+0.39-(0.61/Permissividade))));
  printf("\n");
  printf("Utilizando-se a equação 2, ou seja, W/D >= 2: %f", auxiliar2);
  printf("\n");

  printf("\n");
  printf("Nesse viés, nota-se que a expressão 1 é a correta para o problema vigente.\n");
  printf("Assim o valor de W é obtido por meio de 'espessura vezes equação 1'.\n");
  printf("\n");
  printf("Portanto, W é igual a %f centímetros.", auxiliar1*Espessura);
  printf("\n");
  printf("\n");
  
  //Cálculo 3:
  float Ko = 9*pow(10,9);
  float Beta = Ko*sqrt(1.7584319);
  float Velocidade = 3*pow(10,8)/sqrt(1.7584319);
  float Frequencia = (Beta*Velocidade)/(2*3.14159265);
  ComprimentoOnda = Velocidade/Frequencia;
  printf("Velocidade = %f", Velocidade);
  printf("\n");
  
  printf("Beta = %f", Beta);
  printf("\n");
  
  printf("Frequencia = %f", Frequencia);
  printf("\n");

  printf("\n");
  printf("Já o valor do comprimento de onda guiado é: %E", ComprimentoOnda);
  printf("\n");

  //Cálculo 4:
  Atenuacao = (Ko*Permissividade*(1.7584319-1)*0.001)/(2*sqrt(1.7584319)*(Permissividade-1));
  printf("Em síntese, o valor da atenuação é: %E Np/m.", Atenuacao);
  printf("\n");
  return 0;
  }
