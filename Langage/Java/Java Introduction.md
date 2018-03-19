

# Java ?
Java est un langage de programmation moderne développé par **Sun Microsystems**(aujourd'hui racheté par **Oracle**). Il ne faut surtout pas le confondre avec JavaScript (langage de scripts utilisé principalement sur les sites web), car Java n'a rien à voir.  
Une de ses plus grandes forces est son excellente portabilité : une fois votre programme créé, il fonctionnera automatiquement sous Windows, Mac, Linux, etc

# Les Variables 
rappel :  Une variable est un élément qui stocke des informations de toute sorte en mémoire : des chiffres, des résultats de calcul, des tableaux, des renseignements fournis par l'utilisateur…
déclaration de variables en java : 

    <type de la variable> <nom de la variable>;

En java nous avons deux types de variables :
 1.des variables de types simple ou "primitif"
 2.des variables de types complexe ou des "objets"

**Ce que l'on appelle des type simple ou primitifs en java sont tout simplement des nombres entiers, des nombres réels, des booléens ou encore des caractère.**

1.Les Variable de type Numérique :

le type **byte** (1 octet) peut contenir les entier enter -128 et +127 
````java
byte temperature;
temperature = 64;
````
le type **short** (2 octet) contient les entiers compris entre -32768 et+32767
````java
short vitesseMax;
vitesseMax = 32000;
````
 
 le type **int** (4 octet) va de -2*109 à 2*109
````java
int temperatureSoleil = 15600000;
````

le type **long** (8 octet) peut aller de   −9×1018−9×1018 à 9×1018
````java
long anneeLumiere;
anneeLumiere = long anneeLumiere;
anneeLumiere = 9460700000000000L;
````
