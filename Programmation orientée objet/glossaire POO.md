# Glossaire POO
**Poo :** Programmation orienté objet.
**Objet** En informatique, un objet est un conteneur symbolique et autonome qui contient des informations et des mécanismes concernant un sujet, manipulés dans un programme. Le sujet est souvent quelque chose qu'existe, appartenant au monde réel. C'est le concept central de la programmation orientée objet (POO).
**Class :** Programme auto-suffisant. 
**Method :** Une fonction de classe.
**Attribut :** Une variable de classe.
**Instance :** Une réalisation de l'objet.
**Constructeur :** Method appelé lors de l'instanciation.
**Getter :** Method qui récupere un attribut.
**Setter :** Method qui modifie un attribut.
**Héritage :** Mécanisme Parent/Enfant.
**Surcharge :** Redéfinition   d'une method ou d'un attribut dans la classe. "Enfant".
**Static :** Method sans instance.
**Public :** Visible de tous.
**Private :** Non visible de l'extérieur.
**Protected :** Visible de moi + enfant.
**Parent :** Classe Principale.
**Enfant :** Classe qui dérive de **Parent**.
**::** Apelle une method **Static**.
**Abstract :** Qui ne peut pas être instancié.
**$this :** l'objet dans lequel on se trouve.  
**-> :** Attribut ou method de .. . ( à l'intérieur d'une classe)
**implements** :  pour "hériter" d'une interface , signifie qu'une classe implémente une interface, et doit donc proposer une implémentation de toutes ses méthodes.
**Package** : ce sont comme des dossiers permettant de ranger nos classes. Charger un package nous permet d'utiliser les classes qu'il contient.
**const :** (est forcément statique).
Propriété qui ne change pas , lors de la déclaration le $ disparait 
pour utiliser la valeur de la propriété const de la classe on utilise la syntaxe :

   
````php
    class:const`
    // exemple pour une classe chien
    class Animal 
    {
    const nbPattes = 4;
    }
    class Chat extends Animal
    {
    // ici on met les attributs que l'on veut 
    }
    echo Chat::nbPattes;
   ````
  **final :** qui empêche les classes filles de surcharger une méthode, lorsque la définition de cette dernière est préfixée par le mot-clé "final". Si la classe elle-même est définie comme finale, elle ne pourra pas être étendue.

**polymorphism** : Le polymorphisme est la capacité d'un objet à prendre de nombreuses formes. L'utilisation la plus courante du polymorphisme dans la POO se produit lorsqu'une référence de classe parent est utilisée pour faire référence à un objet de classe enfant.   

**build**: Compile le code dans le langages utilisé en langage compréhensible par l'ordinateur , le langage binaire et exécutable.

**super**: c'est pour accèder a des méthodes ou des attribut de la classe mère.

**imports**: permet d'importer des packages dans une class.
    


