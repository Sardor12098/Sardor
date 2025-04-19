#include <stdio.h>
#include <string.h>

#define MAX 100

struct mamlakat {
    char nomi[30];
    int odamlar_soni;
    char turi[30];
};
int main()
{
system("clear");
    int n, x, y;
    struct mamlakat davlat[MAX];

sardor:
    printf("Nechta mamlakat kiritasiz, brat? ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++) {
	printf("%d - mamlakat malumotini kiriting brat ",i+1);
        printf("\nMamlakat nomini kiriting: ");
        scanf("%s", davlat[i].nomi);

        printf("Davlatdagi odamlar sonini kiriting: ");
        scanf("%d", &davlat[i].odamlar_soni);

        printf("Davlat turi qanday: ");
        scanf("%s", davlat[i].turi);
    }

    printf("\nSiz kiritgan davlatlar:\n");
    printf("--------------------------------------------------\n");
    for (int i = 0; i < n; i++) {
        printf("Davlat nomi         --->> %s\n", davlat[i].nomi);
        printf("Davlat odamlar soni --->> %d\n", davlat[i].odamlar_soni);
        printf("Davlat turi         --->> %s\n", davlat[i].turi);
        printf("--------------------------------------------------\n");
    }

bekki:
    printf("\nNechta odamdan ko'p aholiga ega davlatlarni chiqaray? ");
    scanf("%d", &x);

    for (int i = 0; i < n; i++) {
        if (davlat[i].odamlar_soni > x) {
            printf("Davlat nomi         --->> %s\n", davlat[i].nomi);
            printf("Davlat odamlar soni --->> %d\n", davlat[i].odamlar_soni);
            printf("Davlat turi         --->> %s\n", davlat[i].turi);
            printf("--------------------------------------------------\n");
        }
    }

    printf("\nYana nima qilmoqchisiz?\n");
    printf("1. Qayta davlat kiritaman\n2. Yana qidiraman\n3. Dasturdan chiqaman\n");
    scanf("%d", &y);

    if (y == 1)
        goto sardor;
    else if (y == 2)
        goto bekki;
    else if (y == 3)
        return 0;
    else
        printf("Brat, noto‘g‘ri raqam tanladingiz\n");

    return 0;
}

