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
#include <time.h>
#include <stdlib.h>

int main() {
    char tn;
    do {
        int tab[100];
        int a = 0;
        srand(time(NULL));
        for (int i = 0; i < 99; i++) {
            tab[i] = rand() % 50;
            if (tab[i] <= 10) {
                tab[i] = (rand() % 40) + 10;
                tab[i] *= -1;
            }
            if (tab[i] % 2 == 0) a += tab[i];
            printf("%d\n", tab[i]);
        }
        printf("Suma liczb parzystych: %d\n", a);
        printf("Wykonac program jeszcze raz? t/n\n");
        scanf(" %c", &tn);
    }while(tn != 'n');
    return 0;
}

```
