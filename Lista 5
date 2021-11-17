
#Zadanie 2
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
