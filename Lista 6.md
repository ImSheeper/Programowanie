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
