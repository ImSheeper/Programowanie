# Zadanie 1
```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
    int tab[10][10];
    int tab2[10][10];

    srand(time(NULL));

    printf("Pierwsza tablica: \n");
    for(int i = 0; i < 10; i++) {
        for(int j = 0; j < 10; j++) {
            tab[i][j] = rand() % (9 + 9 + 1) - 9;
            printf("%4d", tab[i][j]);
        }
        printf("\n");
    }

    printf("Tablica po transpozycji: \n");
    for(int i = 0; i < 10; i++) {
        for(int j = 0; j < 10; j++) {
            tab2[i][j] = tab[j][i];
            printf("%4d", tab2[i][j]);
        }
        printf("\n");
    }
    return 0;
}
```

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
# Zadanie 3
```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
    srand(time(NULL));
    int rozmiar;

    printf("Podaj rozmiar tablicy:\n");
    scanf("%d", &rozmiar);

    while(rozmiar > 10 || rozmiar <= 0) {
        printf("Zly rozmiar! Podaj jeszcze raz: \n");
        scanf("%d", &rozmiar);
    }

    int tab[rozmiar][rozmiar];

    for(int i = 0; i < rozmiar; i++) {
        for(int j = 0; j < rozmiar; j++) {
            tab[i][j] = rand() % 21 - 10;
            printf("%4d", tab[i][j]);
        }
        printf("\n");
    }

    int suma = 0, suma2 = 0;

    for(int i = 0; i < rozmiar; i++) {
        for(int j = 0; j < rozmiar; j += rozmiar) {
            suma += tab[i][j + i];
        }
    }

    printf("\nSuma pierwszej przekatnej: %d\n", suma);

    for(int i = 0; i < rozmiar; i++) {
        for(int j = rozmiar - 1; j > 0; j -= rozmiar) {
            suma2 += tab[i][j - i];
        }
    }

    printf("Suma drugiej przekatnej: %d\n\n", suma2);
    printf("Suma obu przekatnych: %d", suma + suma2);

    return 0;
}
```
