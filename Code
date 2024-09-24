#include <stdio.h>
#include <time.h> 
#include <stdlib.h>

//funcao de delay
void delay(int secs)
{
    //trocando segundos para milisegundos
    int mlsecs = 1000 * secs;

    //Colocando uma variavel de tempo para ser t0
    clock_t t0 = clock();

    //Loop ateh o delay desejado
    while (clock() < t0 + mlsecs);
}


//funcao do temporizador
void temporizador(){
    //variaveis
    int h , m, s, vrfy = 0;
    //tempo a ser usado
    while(vrfy != 1){
      do{
        system("clear");
        printf("Digite quantas horas terah o temporizador:\n");
        scanf("%i", &h);
        printf("Digite quantos minutos terah o temporizador:\n");
        scanf("%i", &m);
        printf("Digite quantos segundos terah o temporizador:\n");
        scanf("%i", &s);
        system("clear");
      }while(s > 59 || m > 59);

      //verificacao do tempo
      printf("O tempo estah correto?\n%02i:%02i:%02i\n1 para correto e 0 para errado\n", h, m, s);
      scanf("%i", &vrfy);
    }
  
    //temporizador
    while(vrfy == 1){
      system("clear");
      
      printf("%02i : %02i : %02i\n", h, m, s);
      --s;

      //verificadores de troca de tempo
      if(s < 0){
        --m;
        s = 59;
      }
      if(m < 0 && h > 1){
        --h;
        m = 59;
      }

      else if(m < 0 && h < 1){
        m = 0;
        h = 0;
      }
      
      delay(1000);

      //finalizacao do codigo
      if(h <= 0 && m <= 0 && s <= 0){
        vrfy = 0;
        system("clear");
         printf("%02i : %02i : %02i\n", h, m, s);
        delay(2000);
        system("clear");
      }
    }

}

void horacerta(){
  
  //define t como segundos desde uma data muito atinga ae
  time_t t = time(NULL);
  
  //estrutura que vai dar a data para mim
  struct tm date = *localtime(&t);
  system("clear");
  printf("%02i:%02i:%02i\n", date.tm_hour - 3, date.tm_min, date.tm_sec);
  delay(3000);
  system("clear");
}

void cronometro(){
  int s = 0, m = 0, h = 0;
  while(1){
    system("clear");
    printf("%02i:%02i:%02i\n", h, m, s);
    ++s;
    if(s >= 60){
      s = 0;
      ++m;
    }
    if(m >= 60){
      m = 0;
      ++h;
    }
  
    delay(1000);
  }
}

int main(){
  int func, pingas = 1;

  while(pingas == 1){
    system("clear");
    printf("Escolha um funcao:\n\n1 - Temporizador\n2 - Horario\n3 - Cronometro\n");
    scanf("%i", &func);
    system("clear");
    switch(func){
  
      case 1:
        temporizador();
        break;
  
      case 2:
        horacerta();
        break;
  
      case 3:
       printf("Ao selecionar esta opcao, o sistema soh irah parar se for desligado, tem certeza que deseja continuar?\n1 - Sim\n2 - Nao\n\n");
       scanf("%i", &func);
        if(func == 1){
          cronometro();
         break;
        }
        else{
          system("clear");
          break;
        }
    }
    printf("Deseja realizar alguma outra operacao?\n\n1 - Sim\n2 - Nao\n");
      scanf("%i", &pingas);
  }


  
  return 0;
}
