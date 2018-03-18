# Les Variables

 Une variable est un espace de stockage sur votre ordinateur permettant d'enregistrer tout type de données, que ce soit une chaîne de caractères, une valeur numérique ou bien des structures un peu plus particulières.
 
 ## Déclarer une variable
 
 Déclarer une variable ? Il s'agit tout simplement de lui réserver un espace de stockage en mémoire. Une fois la variable déclarée, vous pouvez commencer à y stocker des données.
 
 Pour déclarer une variable, il vous faut d'abord lui trouver un nom. Il est important de préciser que le nom d'une variable, il ne peut contenir que des caractères alphanumériques, autrement dit les lettres de A à Z et les chiffres de 0 à 9 ; 
 
 l'underscore (_) et le dollar ($) sont aussi acceptés. Autre chose : le nom de la variable ne peut pas commencer par un chiffre et ne peut pas être constitué uniquement de mots-clés utilisés par le JavaScript. 
 
 Pour déclarer une variable, il vous suffit d'écrire la ligne suivante :
 ````js
 let myVariable;
 // Ici on déclare une variable nommée myVariable
 `````
 Le mot-clé **let** est présent pour indiquer que vous déclarez une variable. Une fois celle-ci déclarée, il ne vous est plus nécessaire d'utiliser ce mot-clé pour cette variable et vous pouvez y stocker ce que vous souhaitez :

````js
let myVariable;
myVariable = 2;
//je déclare une variable nommée myVariable
// j'attribue la valeur de type entier (integer) 2 à ma variable myVariable
````

Le signe = sert à attribuer une valeur à la variable ; ici nous lui avons attribué le nombre 2. Quand on donne une valeur à une variable, on dit que l'on fait une affectation, car on affecte une valeur à la variable.
 
 Il est possible de simplifier ce code en une seule ligne :
 ````js
let myVariable = 5.5; // Comme on peut constater les nombres à virgule s'écrivent avec un " . "
`````
 De même, vous pouvez déclarer et assigner des variables sur une seule et même ligne :
 
 ````js
let myVariable1, myVariable2;
myVariable1 = myVariable2 = 2;
`````
Et enfin une dernière chose utile occasionnellement :
 
````js
let myVariable1, myVariable2;
myVariable1 = myVariable2 = 2;
`````
 Les deux variables contiennent maintenant le nombre 2 ! Vous pouvez faire la même chose avec autant de variables que vous le souhaitez.
 
 ## Les Types de Variables
 Le JavaScript est un langage typé dynamiquement. Cela veut dire, généralement, que toute déclaration de variable se fait avec le mot-clévarsans distinction du contenu, tandis qu'avec certains autres langages, comme le C, il est nécessaire de préciser quel type de contenu la variable va devoir contenir.
 
 En JavaScript, nos variables sont typées dynamiquement, ce qui veut dire que l'on peut y mettre du texte en premier lieu puis l'effacer et y mettre un nombre quel qu'il soit, et ce, sans contraintes.
 
 Commençons tout d'abord par voir quels sont les trois types principaux en JavaScript :

- **Le type numérique** (alias number) : il représente tout nombre, que ce soit un entier, un nombre négatif, scientifique, etc. Bref, c'est le type pour les nombres.
- 
Pour assigner un type numérique à une variable, il vous suffit juste d'écrire le nombre seul :

``var number = 5;``

Tout comme de nombreux langages, le JavaScript reconnaît plusieurs écritures pour les nombres, comme l'écriture décimale ``let  number = 5.5;``
ou l'écriture scientifique ``let number = 3.65e+5;`` 
ou encore l'écriture hexadécimale ``let number = 0x391;``

Bref, il existe pas mal de façons d'écrire les valeurs numériques !

- **Les chaînes de caractères** (alias string) : ce type représente n'importe quel texte. On peut l'assigner de deux façons différentes :
````js
let text1 = 'mon premier texte';
let text2 = "mon deuxieme texte";
`````
l est important de préciser que si vous écrivez  ``let myVariable = '2';``alors le type de cette variable est une chaîne de caractères et non pas un type numérique.

Une autre précision importante, si vous utilisez les apostrophes pour « encadrer » votre texte et que vous souhaitez utiliser des apostrophes dans ce même texte, il vous faudra alors « échapper » vos apostrophes de cette façon :
````js
let text = 'Ça c\'est quelque chose !';
````

Pourquoi ? Car si vous n'échappez pas votre apostrophe, le JavaScript croira que votre texte s'arrête à l'apostrophe contenue dans le mot « c'est ». À noter que ce problème est identique pour les guillemets.
En ce qui nous concerne, nous utilisons généralement les apostrophes mais quand le texte en contient trop alors les guillemets peuvent être bien utiles. C'est à vous de voir comment vous souhaitez présenter vos codes, libre à vous de faire comme vous le souhaitez !

- Les **booléens** (alias boolean) : les booléens sont un type bien particulier que vous n'étudierez réellement qu'au chapitre suivant. Dans l'immédiat, pour faire simple, un booléen est un type à deux états qui sont les suivants : vrai ou faux. Ces deux états s'écrivent de la façon suivante :
````js
let isTrue = true;
let isFalse = false;
````

Voilà pour les trois principaux types. Il en existe d'autres, mais nous les étudierons lorsque ce sera nécessaire.

### Tester l'existence de variables avec ``typeOf``
Il se peut que vous ayez un jour ou l'autre besoin de tester l'existence d'une variable ou d'en vérifier son type. Dans ce genre de situations, l'instruction ``typeof``est très utile, voici comment l'utiliser :

````js
let number = 2;
alert(typeof number); // Affiche : « number »

let text = 'Mon texte';
alert(typeof text); // Affiche : « string »

let aBoolean = false;
alert(typeof aBoolean); // Affiche : « boolean »
````
voici comment tester l'existence d'une variable :
````js
alert(typeof nothing); // Affiche : « undefined »
````

Voilà un type de variable très important ! Si l'instruction``typeof``vous renvoie``undefined``, c'est soit que votre variable est inexistante, soit qu'elle est déclarée mais ne contient rien.

