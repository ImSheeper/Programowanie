# Zadanie 1
```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

void sort(int *tab){

    int swap, przesuniecie = 0;

    srand(time(NULL));

    for(int i = 0; i < 50; i++) {
        tab[i] = rand() % (122 - 97 + 1) + 97;
        printf("%2c ", tab[i]);
    }

    printf("\n\n");

    for(int i = 0; i < 50; i++) {

        for(int j = 0; j < 50; j++) {

            if(tab[j] > tab[j + 1]) {
                swap = tab[j];
                tab[j] = tab[j + 1];
                tab[j + 1] = swap;
                przesuniecie++;
            }
        }
    }

    printf("Liczba przesuniec: %d\n", przesuniecie);
}

int main() {

    int tab[50];

    sort(tab);

    printf("Posortowane elementy:\n");
    for(int i = 0; i < 50; i++) {
        printf("%2c ", tab[i]);
    }

    return 0;
}
```

# Zadanie 2

```c
#include <stdio.h>
#include <stdlib.h>

int sil(int x) {

    int a = 1;

    for(int i = 1; i <= x; i++) {
        a *= i;
    }

    return a;
}

int main(){

    int x, y;

    printf("Podaj x\n");
    scanf("%d", &x);

    y = sil(x);
    printf("%d\n", y);

    return 0;
}
```
# Zadanie 3
```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

void random(int **tab, int n) {

    srand(time(NULL));

    for(int i = 0; i < n; i++) {
        for(int j = 0; j < n; j++) {
            tab[i][j] = rand() % 21 - 10;
            printf("%3d", tab[i][j]);
        }
    }
}

int main() {

    int n, **tab[10][10];

    printf("Podaj n: \n");
    scanf("%d", &n);

    random(**tab, n);

    return 0;
}
```
# Zadanie 4

```c
#include <stdio.h>

int func(int n) {

    int suma = 0;

    for(int i = 0; i < n; i++) {
        suma += i * i * i;
    }

    return suma;

}

int main()
{
    int n, wyw;

    printf("Podaj n \n");
    scanf("%d", &n);

    wyw = func(n);

    printf("%d", wyw);

    return 0;
}
```
