# Zadanie 1
```c
#include <stdio.h>
#include <string.h>

int main()
{
    int n;
    char tab[10][10];
    char tab2[10][10];
    printf("Podaj N: \n");
    scanf("%d", &n);
    printf("Podaj %d imion\n", n);

    for(int i = 0; i < n; i++) {
        scanf("%s", tab[i]);
        strrev(tab[i]);

        if(tab[i][0] == 'a') {
            strrev(tab[i]);
            strcpy(tab2[i], tab[i]);
        }
    }

    printf("Imiona konczace sie na litere a: ");
    for(int i = 0; i < n; i++) {
        printf("%s\n", tab2[i]);
    }

    return 0;
}
```

# Zadanie 2
```c
#include <stdio.h>
#include <string.h>

int main()
{
    char tn;
    do {
        int n;
        char tab[10][10];
        printf("Podaj N: \n");
        scanf("%d", &n);
        printf("Podaj %d imion\n", n);

        for (int i = 0; i < n; i++) {
            scanf("%s", tab[i]);
            strrev(tab[i]);
        }

        printf("Imiona konczace sie na litere a:\n");
        for (int i = 0; i < n; i++) {
            if (tab[i][0] == 'a') {
                strrev(tab[i]);
                printf("%s\n", tab[i]);
            }
        }
        printf("Powtorzyc program? t/n\n");
        scanf(" %c", &tn);
    }while(tn != 'n');
    return 0;
}
```

# Zadanie 4 (Robocze)
```c
#include <stdio.h>
#include <time.h>
#include <stdlib.h>

int swap(int a, int b) {
    int temp;
    temp = a;
    a = b;
    b = temp;
}

int main() {
    char tn;
    do {
        int tab[100];
        int swap, temp;
        srand(time(NULL));

        for(int i = 0; i < 100; i++) {
            tab[i] = rand() % 200;

            if(tab[i] > 100) {
                tab[i] = rand() % 100;
                tab[i] *= -1;
            }
            for(int j = 0; j < 100; j++) {
                if(tab[i] > tab[i + 1]) {
                    swap = tab[i];
                    tab[i] = tab[i + 1];
                    tab[i + 1] = temp;
                }
            }
        }
        printf("Posortowane liczby: \n");
        for(int i = 0; i < 100; i++) printf("%d\n", tab[i]);

        printf("Powtorzyc program? t/n \n");
        scanf(" %c", &tn);
    }while(tn != 'n');
    return 0;
}
```
