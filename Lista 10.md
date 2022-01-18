# Zadanie 1
```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

void plik(int *tab) {

    FILE *fp;
    fp = fopen("text.txt", "w");

    for(int i = 0; i < 10; i++) {
        tab[i] = rand() % 10;
        fprintf(fp, "%d\n", tab[i]);
    }

    fclose(fp);

    fp = fopen("bin.bin", "wb");

    fwrite(tab, sizeof(int), 10, fp);

    fclose(fp);

}

int main() {

    srand(time(NULL));

    int tab[10];

    plik(tab);

    return 0;
}
```
