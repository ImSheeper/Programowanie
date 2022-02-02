# Zadanie 1 (Zróbcie to za pomocą strcmp, strcpy, strrev, będzie o wiele łatwiej)
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
char tn;
do{
    char znak[100];
    int c = 0;
    int i;
    int n;
    printf("Wpisz lancuch znakow \n");
    scanf("%s", znak);

    n = strlen(znak);

    for(i=0, c=0; i<n/2; i++)
    {
        if(znak[i] == znak[n-i-1])
        {
            c++;
        }
    }

    if(c==i)
    {
        printf("To slowo jest palindromem \n");
    }
    else
    {
        printf("To slowo nie jest palindromem \n");
    }

    printf("\nPowtorzyc program? t/n \n");
    scanf(" %c", &tn);
}while(tn != 'n');

    return 0;
}
```

# Zadanie 2
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
char tn;
do{
    int a;
    int silnia = 1;

    printf("Podaj a \n");
    scanf("%d", &a);

    if(a <= 10){
        for(int i=1; i<=a; i++){
            silnia = i * silnia;
        }
    printf("silnia: %d \n", silnia);
    }

    printf("Powtorzyc program? t/n \n");
    scanf(" %c", &tn);

    }while(tn != 'n');

    return 0;
}
```

# Zadanie 3
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    char tn;

    do{

    int l[9], min=0, max=0;

    printf("Podaj 10 liczb: \n");

    for(int i=0; i<=9; i++){
        scanf("%d", &l[i]);

        if(min > l[i] || i == 0){
            min = l[i];
        }

        if(max < l[i]){
            max = l[i];
        }
    }


    printf("Wartosc maksymalna to: %d \nWartosc minimalna to: %d \n", max, min);

    printf("Czy chcesz powtorzyc program? t/n \n");
    scanf(" %c", &tn);
    }while(tn != 'n');

    return 0;
}
```

# Zadanie 4
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{

char tn;
do{
    int n;
    float suma;

    printf("Podaj n: \n");
    scanf("%d", &n);

    printf("Elementy: \n");
    for(int i=1; i<=n; i++){
        printf("1/%d ", i);
        suma += (float)1/i;
    }
    printf("Suma wynosi: %f", suma);

    printf("\nPowtorzyc program? t/n \n");
    scanf(" %c", &tn);
}while(tn != 'n');

    return 0;
}
```
# Zadanie 5
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int a,b;

    printf("Podaj a: \n");
    scanf("%d", &a);
    printf("Podaj b: \n");
    scanf("%d", &b);

    printf("Liczby: ");
    if(a < b){
        for(int i=a; i<=b; i++){
            if(i % 2 == 0 && i >= 0){
                printf("%d ", i);
            }
        }
    }

    else if(a > b){
        for(int i=a; i>=b; i--){
            if(i % 2 == 0 && i >= 0){
                printf("%d ", i);
            }
        }
    }

    return 0;
}
```
