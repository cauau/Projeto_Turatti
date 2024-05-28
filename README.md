# Projeto_Turatti
elabore um programa em c que sorteie 6 números distintos e os armazene em um vetor. o vetor deve estar ordenado de forma crescente. caso seja sorteada um valor já existente no vetor, esse valor é ignorado e um novo valor é sorteado. Após o preenchimento total do vetor com seis posições que contem valores únicos, mostre esse valor para o usuário

O codigo foi colocado aqui pois não consegui subir o arquivo:

#include <stdio.h>
#include <stdlib.h>
#include <time.h>

void bubbleSort(int vetor[], int tamanho) {
    int i, j, temp;
    for (i = 0; i < tamanho - 1; i++) {
        for (j = 0; j < tamanho - i - 1; j++) {
            if (vetor[j] > vetor[j + 1]) {
                temp = vetor[j];
                vetor[j] = vetor[j + 1];
                vetor[j + 1] = temp;
            }
        }
    }
}

int main(void) {
    int vetor[6], numero_sorteado, n, i, unico;
    srand(time(NULL));

    for ( n = 0; n < 6; n++) {
       
        do {
            unico = 1;
            numero_sorteado = rand() % 6 + 1;

            for ( i = 0; i < n; i++) {
                if (vetor[i] == numero_sorteado) {
                    unico = 0;
                    break;
                }
            }
        } while (!unico);

        vetor[n] = numero_sorteado;
        printf("O numero sorteado foi: %d\n", vetor[n]);
    }

    bubbleSort(vetor, 6);

    printf("Vetor ordenado:\n");
    for ( n = 0; n < 6; n++) {
        printf("%d ", vetor[n]);
    }
    printf("\n");

    return 0;
}
