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
