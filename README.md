#Atividade 34

#include <stdio.h>  
#include <math.h>  
#include <locale.h>
#include <stdlib.h>

int Merge, m1, m2, m3, m4, m5, m6;

int main() {

  setlocale (LC_ALL, "portuguese");
  
  printf ("Digite um número: \n");
  scanf ("%d", &m1);
    printf ("Digite o segundo número: \n");
    scanf ("%d", &m2);
    printf ("Digite o terceiro número: \n");
    scanf ("%d", &m3);
    printf ("Digite o quarto número: \n");
    scanf ("%d", &m4);
    printf ("Digite o quinto número: \n");
    scanf ("%d", &m5);
    printf ("Digite o sexto número: \n");
    scanf ("%d", &m6);
    
    system("cls");

    // Ordenação dos números
    printf ("Então os números são: \n");
    printf ("%d, %d, %d, %d, %d, %d\n", m1, m2, m3, m4, m5, m6);
    printf ("Ordenaremos esses números em Merge Sort: \n");
    printf ("Dividimos em 2 pilhas \n");
    printf ("%d, %d, %d\n", m1, m2, m3);
    printf ("%d, %d, %d\n", m4, m5, m6);
    printf ("Agora dividimos em 3 pilhas de apenas 1 número a primeira sequência \n");
    printf ("%d\n", m1);
    printf ("%d\n", m2);
    printf ("%d\n", m3);
    printf ("Agora dividimos em 3 pilhas de apenas 1 número a segunda sequência \n");
    printf ("%d\n", m4);
    printf ("%d\n", m5);
    printf ("%d\n", m6);
    printf ("Agora comparamos os 6 números separadamente: \n");
    printf ("E juntamos em ordem crescente \n");

    // Reversão dos números em Ordem Crescente
    if (m1 > m2) {
        int temp = m1;
        m1 = m2;
        m2 = temp;
    }
    if (m1 > m3) {
        int temp = m1;
        m1 = m3;
        m3 = temp;
    }
    if (m2 > m3) {
        int temp = m2;
        m2 = m3;
        m3 = temp;
    }
   
    if (m4 > m5) {
        int temp = m4;
        m4 = m5;
        m5 = temp;
    }
    if (m4 > m6) {
        int temp = m4;
        m4 = m6;
        m6 = temp;
    }
    if (m5 > m6) {
        int temp = m5;
        m5 = m6;
        m6 = temp;
    }
    
    int sorted[6]; 
    int i = 0, j = 0, k = 0;
    while (i < 3 && j < 3) {
        if (m1 < m4) {
            sorted[k++] = m1;
            m1 = m2;
            m2 = m3;
            i++; 
        } else {
            sorted[k++] = m4;
            m4 = m5;
            m5 = m6;
            j++; 
        }
    }
    
    while (i < 3) {
        sorted[k++] = m1;
        m1 = m2;
        m2 = m3;
        i++;
    }
   
    while (j < 3) {
        sorted[k++] = m4;
        m4 = m5;
        m5 = m6;
        j++;
    }
    printf ("Então após utilizarmos o Merge Sort, os números recebidos estarão dessa forma:")
    printf ("%d, %d, %d, %d, %d, %d\n", sorted[0], sorted[1], sorted[2], sorted[3], sorted[4], sorted[5]);
  return 0;
}
