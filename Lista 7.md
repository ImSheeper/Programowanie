# Zadanie 2
```c
#include <stdio.h>

int main() {
    int tab[5][5];
    int a;

    again:printf("Podaj 25 liczb: \n");
    for(int i = 0; i < 5; i++) {
        for(int j = 0; j < 5; j++) {
            scanf("%d", &a);
            if(a == 0 || a < -5 || a >= 10) {
                goto again;
            }
            tab[i][j] = a;
        }
    }

    for(int i = 0; i < 5; i++) {
        for(int j = 0; j < 5; j++) {
            if(tab[i][j] > 0) printf(" %d ", tab[i][j]);
            else printf("%d ", tab[i][j]);
        }
        printf("\n");
    }

    int kolumna, suma = 0;

    printf("Ktora kolumne zliczyc? (1-5)\n");
    scanf("%d", &kolumna);

    for(int i = 0; i < 5; i++) {
        for(int j = kolumna - 1; j < 5; j += 5) {
            suma += tab[i][j];
        }
    }

    printf("Suma %d kolumny: %d", kolumna, suma);
    return 0;
}
```
