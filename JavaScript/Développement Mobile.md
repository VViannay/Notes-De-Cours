# Développement d'une application mobile native 

Une application mobile native c'est une application qui à été conçue spécifiquement pour un System d'exploitation (OS) avec un langage et une/des technologie appropriées.
Tableau des langages et IDE  le plus courant pour chaque System d'exploitation 



Definition de IDE : Integrated Development environment (en francais "Environnement de Developpement"), est un logiciel qui rassemble un certain nombre d'outils permettant de developper d'autre logiciels.

[![natif_generique_blanc.png](https://s13.postimg.org/kcipbun47/natif_generique_blanc.png)

# Trois étapes de conception 

 

## 1 -  Rédaction du Code Source 
 
	Dans un premier temps, un développeur rédige le code source de la future application dans un langage approprié.
	
**a. Développement mobile, une compétence particulière**
Attention, maîtriser un langage de programmation tel que Objective C, Java ou C# est une véritable compétence qui nécessite une longue formation ; certains développeurs sont d’ailleurs spécialisés dans un seul langage et il faut souvent faire appel à plusieurs professionnels ayant des spécialisations différentes pour développer une application mobile native pour plusieurs systèmes d’exploitation.

**b. « Communiquer avec le SDK natif »**

Dans un deuxième temps, pour développer une application mobile qui exploite les fonctionnalités natives du terminal (géolocalisation, contact, médias, appareil photo…) il faut “communiquer avec le SDK natif” via le code source. C’est-à-dire programmer des « ponts » qui vont aller chercher des morceaux de codes du SDK du système d’exploitation visé. Ces derniers vont permettre d’“appeler” des fonctionnalités natives pour les intégrer dans l’application mobile.

## 2 - Compilation du code source

La compilation a un rôle primordial car les logiciels fonctionnent avec du code binaire qui est trop complexe pour être conçu tel quel. Il faut donc rédiger un code plus simple “human readable” (le code source) qui va passer dans un compilateur et être transformé en code binaire “machine readable”. Les IDE contiennent un compilateur.
