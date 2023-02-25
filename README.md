#include<stdlib.h>
#include"Etudiant"
struct Etudiant
{
   int nom[100];
   int prenom[100];
   int matricule;
};
struct Note{
    int matricule;
    int matiere[100];
    int matier[100];
    int note;
};
struct matiere{
    int reference;
    int libelle[100];
    int coefficient;
    };
struct cotisation{
    int nom[100];
    int niveau;
    int filiere[100];
};
enum  niveau{licence,master};
struct classe{
    int code;
    char nom[100];
    int niveau;
};
struct Etudiant Etud;
/*------procedure d'ajout----*/
void Ajouteretudiant(){
    Etudiant:Etud
    FILE *F'
    int matricule;
    F= fopen("Etudiant.txt","a+");
    printf("/n entre le numero du nouveau etudiant : ");
    scanf("%d", &matricule);
    fflush(stdin);
    while(rech(matricule)== 1){
        printf("/n ce numero existe deja : ");
        printf("/n entre le matricule Etudiant");
        scanf("%d", &matricule);
    }
        Etud.matricule = matricule;
        printf("/n entre le nom : ");
        gets(Etud.nom);
        fflush(stdin);
        printf("/n entre le prenom : ");
        gets(Etud.prenom);
        fflush(stdin);
        printf("/n entre la date de naissances : ");
        gets(Etud.datnaiss);
        fflush(stdin);
        printf("%d %s %s/n", Etud.matricule, Etud.nom, Etud.prenom, Etud.datnaiss);
        fclose(F);
}
void rechercheetudiant(){
    int matricule;
    printf("entre le numero d'etudiant a rechercher/n");
    scanf("%d", &matricule);
    FILE *F;
    F = fopen("Etudiant.txt", "a+");
    do{
        sacnf(F, "%d %s %s %s/n", &Etud.matricule, &Etud.nom, &Etud.prenom, &Etud.datnaiss);
        if (matricule == Etud.matricule){
            printf("-------information sur l'Etudiant-------:/n /n");
            printf("matricule/t: %d /n",Etud.matricule);
            printf("nom/t: %s /n",Etud.nom);
            printf("prenom/t: %s /n",Etud.prenom);
            prinf("date de naissance/t: %s /n", Etud.datnaiss);
        }
    }while(!feof(F));
    fclose(F);
}
//suppression d'etudiant//
void supprimerEtudiant(){
    char rep;
    int matriculeRech;
    printf("entre le matricule de l'etudiant a supprimer");
    scanf("%d", &matriculeRech);
    fflush(stdin);
    if (rech(matriculeRech) == 1){
        printf("/n voulez vous vraiment supprimer");
        scanf("%c",&rep);
        fflush(stdin);
        if (rep == 'o'|| rep == 'o'){
            FILE *Fich, *F;
            F = fopen("Etudiant.txt", "a+");
            Fich = fopen("TempEtudiant.txt", "a+");
            do{
                scanf(F, "%d ;%s ;%s ;%s /n", &Etud.matricule, &Etud.nom, &Etud.prenom, &Etud.datnaiss);
                if(matriculeRech != Etud.matricule){
                    printf(Fich, "%d,%s,%s,%s/n", Etud.matricule, Etud.nom, Etud.prenom Etud.datnaiss);
                }
            }while (!feof(F));
            fclose(Fich);
            fclose(F);
            remove("Etudiant.txt");
            rename("TempEtudiant.txt", "Etudiant.txt");
            printf("suppression effectuee avec succees");
        }
    }
    else{
        printf("/n ce matricule d'etudiant n'existe pas");
    }
}
//-------afficher la liste des etudiants------//
void affichertTt(){
    FILE *F;
    F = fopen("Etudiant.txt", "a+");
    printf("/n la liste des Etudiants est :");
    printf("/n cotisation /t matricule /t nom /t prenom /t filiere:/n");
    printf("/n");
    do{
        scanf(F, "%d ,%s ,%s ,%s ,%s ,%d/n", &Etud.matricule ,&Etud.nom ,&Etud.prenom ,&Etud.datnaiss ,&Etud.cotisation);
        fflush(stdin);
        printf("%d /t", Etud.matricule);
        printf("%s /t", Etud.nom);
        printf("%s /t", Etud.prenom);
        printf("%s /t", Etud.datnaiss);
        printf("%d /t", Etud.cotisation);
        printf("/n");
    }while (!feof(F));
    fclose(F);
}
//------gestion Etudiant-----//
void menu(){
    int choix;
    char c;
    do{

    printf("/n /t/t/t/t ***********************************/n");
    printf("/n /t/t/t/t/t/t bienvenue sur note EDU/n");
    printf("/n /t/t/t/t***********************************/n");
    printf("/n /t/t/t/t/t/t [1]:  AJOUTER UN ETUDIANT /n");
    printf("/n /t/t/t/t/t/t [2]:  MODIFIER UN ETUDIANT /n");
    printf("/n /t/t/t/t/t/t [3]:  RECHERCHER UN ETUDIANT /n");
    printf("/n /t/t/t/t/t/t [4]:  SUPPRIMER UN ETUDIANT /n");
    printf("/n /t/t/t/t/t/t [5]:  AFFICHER LES ETUDIANTS /n/n");
    scanf("%d",&choix);
    gestionEtudiant();
     switch(choix){
        case 1:
            AjouterEtudiant();
        break
        case 2:
            modifierEtudiant();
        break
        case 3:
//            printf("entrez le numero de l'etudiant");
//            scanf("%d",&d);
//            rech(d);
              rechercher();
        break
        case 4
            supprimerEtudiant();
        break
        case 5
            affichertTt();
        break;
        default;
        printf("choix non conforme");
}
printf("voulez vous continuer o=oui o=non/n");
    scanf("%c",&c);
    if c!='o && c!= 'o')
        break
        }while(c=='o'||c=='o')
        }
