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
