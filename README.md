# Lista 4

Zadanie C
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    char tn;
    do{
        int n;

        printf("Podaj n: \n");
        scanf("%d", &n);

        if(n >= 1 && n <= 15) {
            for(int i = 1; i <= n; i++) {
                printf("\n");

                for(int j = n; j >= i; j--) {
                    printf(" ");

                    if(j == i) {
                        for (int g = 1; g <= i + j - 1; g++) {
                            printf("*");
                        }
                    }
                }
            }
        }
        else{
            printf("Zla wartosc \n");
        }

        printf("\nPowtorzyc program? t/n \n");
        scanf(" %c", &tn);

    }while(tn!='n');

    return 0;
}

Zadanie D
