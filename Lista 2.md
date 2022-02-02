# Zadanie 1 (Tu się coś wyjebało! Poszukajcie na necie jak się tego używa, albo zróbcie to za pomocą ASCII)
```c
#include <stdio.h>
#include <conio.h>

int main ()
{
    char litera[20];

    printf("Podaj litere od a-z: \n");
    scanf("%c", &litera);
    printf("Duza litera: %c \n", toupper(litera));
    printf("Mala litera: %c \n", tolower(litera));

    return 0;
}
```
# Zadanie 2
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int a,b,c;

    printf("Podaj a: \n");
    scanf("%d", &a);

    printf("Podaj b: \n");
    scanf("%d", &b);

    printf("Podaj c: \n");
    scanf("%d", &c);

    if(a%2 == 0 || b%2 == 0 || c%2 == 0)
    {
        printf("Przynajmniej jedna z liczb jest parzysta \n");
    }

    else
    {
        printf("Zadna z liczb nie jest parzysta \n");
    }

    return 0;
}
```
# Zadanie 3 (To da się zrobić prościej, jeżeli będziecie używać zmiennej min, przypisywać jej wartość i porównywać)
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int a,b,c;

    printf("Podaj a: \n");
    scanf("%d", &a);
    printf("Podaj b: \n");
    scanf("%d", &b);
    printf("Podaj c: \n");
    scanf("%d", &c);

    int A = pow(a,2);
    int B = pow(b,2);
    int C = pow(c,2);

    if(A < B && A < C)
    {
        printf("%d jest najmniejszym kwadratem. ", a);
    }

    else if(B < A && B < C)
    {
        printf("%d jest najmniejszym kwadratem. ", b);
    }

    else if(C < A && C < B)
    {
        printf("%d jest najmniejszym kwadratem. ", c);
    }

    else
    {
        printf("Wszystkie potegi sa najmniejsze. ");
    }

    return 0;
}
```
# Zadanie 4
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int a,b,c,d,e;
    int min;

    printf("Wprowadz a: \n");
    scanf("%d", &a);
    printf("Wprowadz b: \n");
    scanf("%d", &b);
    printf("Wprowadz c: \n");
    scanf("%d", &c);
    printf("Wprowadz d: \n");
    scanf("%d", &d);
    printf("Wprowadz e: \n");
    scanf("%d", &e);

    min = a;

    if(b < min){
        min = b;
    }

    if(c < min){
        min = c;
    }

    if(d < min){
        min = d;
    }

    if(e < min){
        min = e;
    }

    printf("Najmniejsza wartosc to %d", min);

    return 0;
}
```
# Zadanie 5
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int liczba;

    printf("Podaj liczbe: \n");
    scanf("%d", &liczba);

    if(liczba > 99){
        int jednosci = liczba % 10;
        int dziesiatki = (liczba / 10) % 10;
        int setki = (liczba / 100) % 10;
        printf("Jednosci: %d, dziesiatki: %d, setki: %d", jednosci, dziesiatki, setki);
    }
}
```

# Zadanie 6
```c
#include <stdio.h>
#include <stdlib.h>
#include <math.h>

int main()
{
    int a;

    printf("Podaj liczbe calkowita: \n");
    scanf("%d", &a);

    int square = sqrt(a);

    if(square * square == a){
        printf("Liczba %d jest liczba kwadratowa \n", a);
    }

    else{
        printf("Liczba %d nie jest liczba kwadratowa \n", a);
    }

    return 0;
}
```
