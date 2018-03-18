# Les Opérateur et La Conversion de types
---
## Les Opérateurs Arithmétiques

Nous Allons nous interesser aux opérateurs arithmétiques. Ces derniers sont à la base de tout calcul et sont au nombre de cinq.

 | Opérateurs                          |Signes                        
-|-------------------------------|
|Addition|+|
|Soustraction   |-|
|Multiplication |*|
|Division          | / |
|Modulo        |%|

Concernant le dernier opérateur, le modulo est tout simplement le reste d'une division. Par exemple, si vous divisez 5 par 2 alors il vous reste 1, c'est le modulo.

### Quelques calculs simples

````js
let result = 3 + 2;
alert(result); // Affiche : « 5 »
`````
Alors vous savez faire des calculs avec deux nombres c'est bien, mais avec deux variables contenant elles-mêmes des nombres c'est mieux 

````js
let number1 = 3, number2 = 2, result;
result = number1 * number2;
alert(result); // Affiche : « 6 »
````

On peut aller encore plus loin comme ça en écrivant des calculs impliquant plusieurs opérateurs ainsi que des variables :

````js
let divisor = 3, result1, result2, result3;

result1 = (16 + 8) / 2 - 2 ; // 10
result2 = result1 / divisor;
result3 = result1 % divisor;

alert(result2); // Résultat de la division : 3,33
alert(result3); // Reste de la division : 1
````
Vous remarquerez que nous avons utilisé des parenthèses pour le calcul de la variable result1. Elles s'utilisent comme en mathématiques : grâce à elles le navigateur calcule d'abord 16 + 8 puis divise le résultat par 2.

Simplifier encore plus vos calculs
Par moment vous aurez besoin d'écrire ce genre de choses : 

````js
let  number = 3;
number = number + 5;
alert(number); // Affiche : « 8 »
````
À noter que ceci ne s'applique pas uniquement aux additions mais fonctionne avec tous les autres opérateurs arithmétiques :

* +=

* -=

* *=

* /=

* %=

### Initiation à la concaténation et à la conversion des types

Certains opérateurs ont des particularités cachées. Prenons l'opérateur + ; en plus de faire des additions, il permet de faire ce que l'on appelle des concaténations entre des chaînes de caractères.

La concaténation
Une concaténation consiste à ajouter une chaîne de caractères à la fin d'une autre, comme dans cet exemple :

````js
let hi = 'Bonjour', name = 'toi', result;
result = hi + name;
alert(result); // Affiche : « Bonjourtoi »
````

Cet exemple va afficher la phrase « Bonjourtoi ». Vous remarquerez qu'il n'y a pas d'espace entre les deux mots, en effet, la concaténation respecte ce que vous avez écrit dans les variables à la lettre près. Si vous voulez un espace, il vous faut en ajouter un à l'une des variables, comme ceci :var hi = 'Bonjour ';

Autre chose, vous souvenez-vous toujours de l'addition suivante ?

````js
let number = 3;
number += 5;
````
Eh bien vous pouvez faire la même chose avec les chaînes de caractères :

````js
let text = 'Bonjour ';
text += 'toi';
alert(text); // Affiche « Bonjour toi ».
````

### Interagir avec l'utilisateur
La concaténation est le bon moment pour introduire votre toute première interaction avec l'utilisateur grâce à la fonction ``prompt()``. Voici comment l'utiliser :
````js
let  text = prompt('Tapez quelque chose :');
````
Ainsi, le texte tapé par l'utilisateur se retrouvera directement stocké dans la variabletext.

### Convertir une chaîne de caractères en nombre

Essayons maintenant de faire une addition avec des nombres fournis par l'utilisateur :

````js
let first, second, result;

first  = prompt('Entrez le premier chiffre :');
second = prompt('Entrez le second chiffre :');
result = first + second;

alert(result);
````

Si vous avez essayé ce code, vous avez sûrement remarqué qu'il y a un problème. Admettons que vous ayez tapé deux fois le chiffre 1, le résultat sera 11… Pourquoi ? Eh bien la raison a déjà été écrite quelques lignes plus haut :

Citation

Elle renvoie ce que l'utilisateur a écrit sous forme d'une chaîne de caractères […]

Voilà le problème, tout ce qui est écrit dans le champ de texte deprompt()est récupéré sous forme d'une chaîne de caractères, que ce soit un chiffre ou non. Du coup, si vous utilisez l'opérateur +, vous ne ferez pas une addition mais une concaténation !

C'est là que la conversion des types intervient. Le concept est simple : il suffit de convertir la chaîne de caractères en nombre. Pour cela, vous allez avoir besoin de la fonction ``parseInt()``qui s'utilise de cette manière :

````js
let text = '1337', number;

number = parseInt(text);
alert(typeof number); // Affiche : « number »
alert(number); // Affiche : « 1337 »
````
Maintenant que vous savez comment vous en servir, on va pouvoir l'adapter à notre code :

````js
let first, second, result;

first = prompt('Entrez le premier chiffre :');
second = prompt('Entrez le second chiffre :');
result = parseInt(first) + parseInt(second);

alert(result);
````

Maintenant, si vous écrivez deux fois le chiffre 1, vous obtiendrez bien 2 comme résultat.

### Convertir un nombre en chaîne de caractères
nous allons voir comment convertir un nombre en chaîne de caractères. Il est déjà possible de concaténer un nombre et une chaîne sans conversion, mais pas deux nombres, car ceux-ci s'ajouteraient à cause de l'emploi du +. D'où le besoin de convertir un nombre en chaîne. Voici comment faire :

````js
let text, number1 = 4, number2 = 2;
text = number1 + '' + number2;
alert(text); // Affiche : « 42 »
````
Qu'avons-nous fait ? Nous avons juste ajouté une chaîne de caractères vide entre les deux nombres, ce qui aura eu pour effet de les convertir en chaînes de caractères.

Il existe une solution un peu moins archaïque que de rajouter une chaîne vide mais vous la découvrirez plus tard.

#### En résumé
* Une variable est un moyen pour stocker une valeur.

* On utilise le mot clévarpour déclarer une variable, et on utilise=pour affecter une valeur à la variable.

* Les variables sont typées dynamiquement, ce qui veut dire que l'on n'a pas besoin de spécifier le type de contenu que la variable va contenir.

* Grâce à différents opérateurs, on peut faire des opérations entre les variables.

* L'opérateur + permet de concaténer des chaînes de caractères, c'est-à-dire de les mettre bout à bout.

* La fonctionprompt()permet d'interagir avec l'utilisateur.