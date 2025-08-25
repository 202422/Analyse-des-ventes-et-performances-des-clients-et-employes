# Description du projet


Dans le cadre de ce projet, j’ai travaillé sur l’analyse des données commerciales issues de la base de données **classicmodels**, une base représentant les activités d’un détaillant de maquettes de voitures classiques. Cette base contient des informations complètes sur les **clients**, leurs **commandes**, leurs **paiements**, ainsi que sur les **produits**, leur **classification**, les **employés** et les **bureaux**.

L’objectif principal du projet est **d’extraire des informations pertinentes** afin de mieux comprendre les ventes, la performance des employés et la répartition du chiffre d’affaires. Pour cela :

* **Power Query** a été utilisé pour **transformer et nettoyer** les données provenant de la base **MySQL**.
* **Power BI** a servi à modéliser les **relations entre les tables**, créer des **visualisations interactives** et des **tableaux de bord**.
* **Python** a été mobilisé pour effectuer des **analyses statistiques** avancées.
* **SQL** pour des jointures complexes sur les tables



![](/Ressources/Visuel.png)


# Architecture du répertoire


```plaintext

│   Objectifs_du_projet_Data_Analyse.pdf
│   README.md
│
├───Analyse statistique
│       Hypothesis_Testing.ipynb
│
├───Base de données MySQL
│       classicmodels.zip
│       Création_de_la_base_de_données.pdf
│       Description_Classic_model_Database.pdf
│
├───PowerBI
│       Analyse de vente et performances des employés et des clients.pbix
│
└───Ressources
        Visuel.png

```

# Rapport

### SQL

* Nombre d’enregistrements dans chaque table :

    * 23 employés
    * 7 bureaux
    * 122 clients
    * 326 commandes
    * 273 paiements
    * 2 996 détails de commande
    * 110 produits
    * 7 lignes de produits

* On recense **7 intitulés de poste différents** (President, VP Sales, VP Marketing, Sales Manager (APAC), Sales Manager (EMEA), Sales Manager (NA), Sales Rep). Le poste de **Sales Rep** est le plus représenté avec **17 occurrences**.

* Les **bureaux** sont situés dans **5 pays différents** (États-Unis, France, Royaume-Uni, Japon, Australie). Il y a **3 bureaux aux États-Unis**, tandis qu’on en trouve **un seul dans chacun des autres pays**.

* Les **clients** sont répartis dans **28 pays différents**. **50 % des clients** sont situés aux **États-Unis, en Allemagne et en France**.

* Les **commandes** présentent **6 statuts différents** (Shipped, Resolved, Cancelled, On Hold, Disputed, In Process). Parmi les **326 commandes**, **303 ont été expédiées (Shipped)**.


### Power Query

* Suppression des colonnes (autres que les clés étrangères) qui font référence à une autre table
* Modification des noms de colonnes
* Vérification et modification des types de colonnes
* Suppression des colonnes non pertinentes comme **"image"** et **"htmlDescription"** dans **productlines**
* Suppression des lignes vides et des doublons


### Power BI

* Le produit "**1992 Ferrari 360 Spider red**" domine largement avec environ 50 unités vendues, bien au-dessus des autres produits qui oscillent entre 20 et 30 unités.
* Deux pics majeurs sont observés pour le chiffre d'affaires: autour de **Novembre 2003** (proche de 1M) et **Novembre 2004** (légèrement inférieur à 1M). Ces périodes indiquent des augmentations marquées du chiffre d'affaires.
* Les clients "**Euro+ Shopping Channel**" et "**Mini Gifts Distributors Ltd.**" réalise le plus d'achat de prouduits
* Les clients sont éparpignés un peu partout dans le monde, cependant, la plupart (36) sont basés aux **USA**, suivi de **l'Allemagne** (13) et de la **France** (12)
* **Leslie** et **Gérard** sont les employés qui réalisent le plus de chiffre de d'Affaire
* Le bureau situé à **Paris** est celui qui génèrent le plus de chiffre d'affaires

### Analyse Statistique (Tests d'Hypothèses)

* **On ne peut pas rejetter** l'hypothèse selon laquelle, la moyenne du chiffre d’affaires entre les bureaux en Europe et ceux en Amériques soient différents
* **On peut rejetter** l'hypothèse selon laquelle les ventes diffèrent significativement entre plusieurs lignes de produits