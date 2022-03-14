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

# Zadanie 2
```c
#include <stdio.h>
#include <stdlib.h>

int main() {

    FILE *fp;
    char a[100];
    int liczba = 0;

    fp = fopen("znaki.txt", "rt");

    fscanf(fp, "%s", a);

    fclose(fp);

    for(int i = 0; i < 100; i++) {
     if(a[i] >= 48 && a[i] <= 57) liczba++;
    }

    printf("%s\n", a);
    printf("Ilosc liczb w tekscie: %d", liczba);

    return 0;
}
```
```c
#include <stdio.h>
#include <stdlib.h>

typedef struct {
    char imie[30];
    char nazwisko[50];
    short wiek;
    char PESEL[12];
    char email[50];
} tperson;

FILE* fp;
tperson* baza;
int n;


int dodanie();
int usuniecie();
void wyswietlenie();
int zapis();

void menu() {
    printf("Menu:\n");
    printf("1 - Dodawanie\n");
    printf("2 - Usuwanie\n");
    printf("3 - Wyswietlanie\n");
    printf("4 - Zapisywanie\n");
    printf("5 - Koniec\n");
}

int main() {

    fp = fopen("baza.bin", "rb");

    if(fp == 0) {
        fp = fopen("baza.bin", "wb");

        if(fp == 0){
            printf("Plik niedostepny.");
            return 1;
        }

        printf("Utworzono nowy plik 'baza.bin'\n");
        fclose(fp);
    }

    fp = fopen("baza.bin", "rb");

    if(fp == 0){
        printf("Plik niedostepny.");
        return 2;
    }

    printf("Otworzono plik 'baza.bin'\n");
    printf("Liczenie rekordow zapisanych: ");

    fseek(fp, 0, SEEK_END);
    n = ftell(fp);

    if(n % sizeof(tperson) != 0) {
        printf("Problem z plikiem 'baza.bin': rozmiar sie nie zgadza.");
        return 3;
    }

    n /= sizeof(tperson);
    printf("%d\n", n);
    fseek(fp, 0, SEEK_SET);

    baza = calloc(n, sizeof(tperson));

    if(baza == 0) {
        printf("Problem z zarezerwowaniem miejsca w pamieci.");
        return 4;
    }

    int numread = fread(baza, sizeof(tperson), n, fp);

    if(numread != n) {
        printf("Ciekawa sytuacja...");
        return 5;
    }

    fclose(fp);
    printf("Wczytywanie poprawne.\n");


    char wejscie;
    int exit=0;

    while(exit==0) {
        menu();
        do {
            scanf("%c", &wejscie);
        } while(wejscie < '1' || wejscie > '5');
        switch(wejscie){
            case '1' : if(dodanie() != 0) return 6; break;
            case '2' : if(usuniecie() != 0) return 7; break;
            case '3' : if(n == 0) printf("Nie ma nic do wyswietlenia"); else wyswietlenie(); break;
            case '4' : if(zapis() != 0) return 8; break;
            case '5' : exit = 1; break;
        }
    }
    return 0;
}


int dodanie() {

    tperson* nowy = (tperson*) realloc(baza, (n+1)*sizeof(tperson));

    if(nowy == 0){
        free(baza);
        printf("Blad z pamiecia...");
        return -1;
    }

    else {
        baza = nowy;
        printf("     Imie: "); scanf("%s", baza[n].imie);
        printf(" Nazwisko: "); scanf("%s", baza[n].nazwisko);
        printf("     Wiek: "); scanf("%d", &(baza[n].wiek));
        printf("    PESEL: "); scanf("%s", baza[n].PESEL);
        printf("   E-mail: "); scanf("%s", baza[n].email);
        n++;
        return 0;
    }
}

int usuniecie() {

    int x;

    do{
        printf("Index rekordu do usuniecia (-1 do cofniecia): ");
        scanf("%d", &x);
    } while(x < -1 || x >= n);

    if(x == -1) return 0;

    while(x<n-1){
        memcpy(&baza[x], &baza[x+1], sizeof(tperson));
        x++;
    }

    tperson* nowy = (tperson*) realloc(baza, (n-1)*sizeof(tperson));

    if(nowy == 0) {
        free(baza);
        printf("Blad z pamiecia...");
        return -1;
    }

    else {
        baza = nowy;
        n--;
        return 0;
    }
}

void print_rekord(int n) {

    printf("Rekord nr. %d:\n", n);
    printf("     Imie: %s\n", baza[n].imie);
    printf(" Nazwisko: %s\n", baza[n].nazwisko);
    printf("     Wiek: %d\n", baza[n].wiek);
    printf("    PESEL: %s\n", baza[n].PESEL);
    printf("   E-mail: %s\n", baza[n].email);
}

void wyswietlenie() {

    int x;

    if(n == 1) {
        x = 0;
    }

    else {
        do {
            printf("Index rekordu do wyswietlenia [0..%d]: ", n-1);
            scanf("%d", &x);

        } while(x < 0 || x >= n);
    }
    print_rekord(x);
}

int zapis() {

    fp = fopen("baza.bin", "wb");

    if(fp == 0) {
        printf("Plik niedostepny.");
        return -1;
    }

    fwrite(baza, sizeof(tperson), n, fp);
    fclose(fp);
    printf("Zapisano poprawnie.");
    return 0;
}
```
