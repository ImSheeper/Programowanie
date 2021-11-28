# Zadanie 1
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

# Zadanie 2
```c
#include <stdio.h>
#include <time.h>
#include <stdlib.h>

void random(int *tab) {
    for(int i = 0; i < 99; i++) {
        tab[i] = rand() % 50;

        if(tab[i] <= 10) {
            tab[i] = (rand() % 40) + 10;
            if(tab[i] == 10) tab[i] += 1;
            tab[i] *= -1;
        }
        printf("%d\n", tab[i]);
    }
}

int main() {
    char tn;
    do {
        int tab[100];

        srand(time(NULL));
        random(tab);

        printf("Powtorzyc program? t/n \n");
        scanf(" %c", &tn);
    }while(tn != 'n');
    return 0;
}
```

# Zadanie 3
```c
#include <stdio.h>
#include <string.h>

typedef struct {
    int id;
    char imie[20];
    char nazwisko[20];
    int wiek;
} tosoba;

int main() {
    char tn;
    do {
        char wzorzec[20];
        tosoba tab[5];
        tab[5].id = 0;

        for (int i = 0; i < 5; i++) {
            tab[i].id = i + 1;
            printf("Podaj imie:");
            scanf("%s", tab[i].imie);
            printf("Podaj nazwisko:");
            scanf("%s", tab[i].nazwisko);
            printf("Podaj wiek:");
            scanf("%d", &tab[i].wiek);
            printf("\n");
        }

        printf("Podaj wzorzec: \n");
        scanf("%s", wzorzec);

        int compare;

        for (int i = 0; i < 5; i++) {
            compare = strcmp(wzorzec, tab[i].imie);
            if (compare == 0) {
                printf("\nId: %d, Imie: %s, Nazwisko: %s, Wiek: %d\n", tab[i].id, tab[i].imie, tab[i].nazwisko,
                       tab[i].wiek);
                break;
            }
        }

        if (compare != 0) printf("Nie ma takiej wartosci w bazie danych\n");

        printf("Powtorzyc program? t/n\n");
        scanf(" %c", &tn);
    }while(tn != 'n');
    return 0;
}
```

# Zadanie 4
```c
#include <stdio.h>
#include <time.h>
#include <stdlib.h>

void random(int *tab) {
    srand(time(NULL));

    printf("Nieposortowane liczby: \n");
    for(int i = 0; i < 100; i++) {
        tab[i] = rand() % 199;

        if(tab[i] > 100) {
            tab[i] = rand() % 100;
            tab[i] *= -1;
        }
        if (i == 0) printf("%d", tab[i]);
        else printf(", %d", tab[i]);
    }
}

void bubble(int *tab) {
    int swap;
    for(int i = 0; i < 100; i++) {

        for(int j = 0; j < 100; j++) {

            if (tab[j] > tab[j + 1]) {
                swap = tab[j];
                tab[j] = tab[j + 1];
                tab[j + 1] = swap;
            }
        }
    }
}

int main() {
    char tn;
    do {
        int tab[100];

        random(tab);
        bubble(tab);

        printf("\n\nPosortowane liczby: \n");
        for(int i = 0; i < 100; i++) {
            if (i == 0) printf("%d", tab[i]);
            else printf(", %d", tab[i]);
        }

        printf("\n\nPowtorzyc program? t/n \n");
        scanf(" %c", &tn);
    }while(tn != 'n');
    return 0;
}
```
