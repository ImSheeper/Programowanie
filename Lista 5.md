# Zadanie 1
```c
#include <stdio.h>

int main() {
    int a,b;

    printf("Podaj a: \n");
    scanf("%d", &a);
    printf("Podaj b: \n");
    scanf("%d", &b);

    while(a != b) {
        if(a > b) a = a-b;
        else b = b-a;
    }

    printf("%d", a);

    return 0;
}
```
# Zadanie 2
```c
#include <stdio.h>

int main() {
    int n,i=1;
    int t[20];

    printf("Podaj liczbe w systemie dziesietnym\n");
    scanf("%d",&n);

    if(n <= 65535) {
        while (n > 0) {
            t[i] = n % 2;
            n /= 2;
            i++;
        }
        printf("\n");
        for(int j = i - 1; j >= 1; j--) printf("%d", t[j]);
    }
    else printf("Zla wartosc");

    return 0;
}
```
# Zadanie 3
```c
#include <stdio.h>

int main() {
    int n,i=1;
    int t[20];
    int ascii[20];

    printf("Podaj liczbe w systemie dziesietnym\n");
    scanf("%d",&n);

    if(n <= 65535) {
        while (n > 0) {
            t[i] = n % 16;
            ascii[i] = 55 + n % 16;
            n /= 16;
            i++;
        }
        printf("Ta liczba w systemie szesnastkowym to: ");
        for(int j = i - 1; j >= 1; j--) {
            if(ascii[j] >= 65) printf("%c", ascii[j]);
            else printf("%d", t[j]);
        }
    }
    else printf("Zla wartosc");

    return 0;
}
```
# Zadanie 4 (generuje powtórzenia, może tablica, porównanie i potem break)
```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

void random() {
    srand(time(NULL));
    for(int i = 1; i <= 5; i++) printf("%d\n", rand() % (999 - 100 + 1) + 100);
}

int main() {
    random();
    return 0;
}
```
# Zadanie 5 (nie jestem pewny odnośnie imienia i nazwiska
```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

typedef struct {
    int id;
    char imie[20];
    char nazwisko[20];
    int rok_u,mies_u,dzien_u;
}tosoba;


int main() {
    srand(time(NULL));

    tosoba a;

    sprintf(a.imie, "imie%d", rand() % 100);
    sprintf(a.nazwisko, "naz%d", rand() % 100);
    a.rok_u = rand() % (1999 - 1900 + 1) + 1900;
    a.mies_u = rand() % (12 - 1 + 1) + 1;
    a.dzien_u = rand() % (31 - 1 + 1) + 1;
    a.id = rand() % (99 - 1 + 1) + 1;

    printf("Imie: %s\n", a.imie);
    printf("Nazwisko: %s \n", a.nazwisko);
    printf("Rok urodzenia: %d \n", a.rok_u);
    printf("Miesiac urodzenia: %d \n", a.mies_u);
    printf("Dzien urodzenia: %d \n", a.dzien_u);
    printf("ID: %d \n", a.id);

    return 0;
}
```
