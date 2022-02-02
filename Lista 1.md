# Zadanie 1
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    printf("Imie: Patryk \n");
    printf("Nazwisko: Gawolek \n");
    printf("Adres: ul. Rynek, Biala \n");
    printf("Numer telefonu: 666333222 \n");

    return 0;
}
```

# Zadanie 2
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    unsigned long int r = 0;
    printf("Wprowadz promien: \n");
    scanf("%d", &r);

    float pole = 0;
    float objetosc = 0;

    pole = 4*3.14*(r*r);
    objetosc = (4/3.0)*3.14*(r*r*r);

    printf("Pole kuli wynosi %f \n", pole);
    printf("Objetosc kuli wynosi %f \n", objetosc);
    return 0;
}
```

# Zadanie 3
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int a,b,c;
    a = 0;
    b = 0;
    c = 0;


    do{
    printf("Podaj a: \n");
    scanf("%d", &a);
    }while(a==0);

    printf("Podaj b: \n");
    scanf("%d", &b);

    printf("Podaj c: \n");
    scanf("%d", &c);

    int D = (b*b)-4*a*c;

    printf("Wynik %d", D);

    return 0;
}
```

# Zadanie 4
```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int C = 0;

    printf("Wprowadz C: ");
    scanf("%d", &C);

    printf("Wynik: %d", (C*2-C+5)*(C*C) );
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
    a = 0;
    b = 0;

    printf("Wprowadz a: \n");
    scanf("%d", &a);

    printf("Wprowadz b: \n");
    scanf("%d", &b);

    printf("Dodawanie: %d \n", a+b);
    printf("Odejmowanie: %d \n", a-b);
    printf("Mnozenie: %d \n", a*b);

    if(b>0)
    {
        printf("Dzielenie: %d \n", a/b);
    }

    else if(b==0)
    {
        printf("Nie wolno dzielic przez zero. \n");
    }

    int potega = 1;

    if(b>0)
    {
        for(int i=0; i<b; i++)
        {
            potega*=a;
        }
            printf("Potega: %d \n", potega);
    }

    else if(b==0)
    {
        potega = 1;
        printf("Potega: %d \n", potega);
    }

    else if(b<0)
    {
        for(int i=0; i>=b; i--)
        {
            potega*=a;
        }
        printf("Potega: %d/1 \n");
    }

    return 0;
}
```
