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
