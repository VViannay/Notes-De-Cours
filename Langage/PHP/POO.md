# La POO : Programation Orientée Objet


## Classes :
Une classe est une entité regroupant des variables et des fonctions. Chacune de ces fonctions aura accés au variables de cette entité.Les Classes contiennent la définition des objets que l'on va créer par la suite. Une classe est donc un regroupement logique de variable et fonction que tout objet issu de cette classe possédera.

Conformément à la notation PEAR, on fait commencer le nom d'une classe par une majuscule.

````php
<?php
class Nom_de_classe  
{

}
?>
````

## Instance :

une instance, c'est tout simplement le résultat d'une instanciation. Une instanciation, c'est le fait d'instancier une classe. Instancier une classe afin qu'elle nous créée un objet.
en gros une instance est un objet.

## Attributs et méthodes 

un Attribut (ou propriété) désigne une variable et une méthode désigne une fonction.

## Visibilité 

La visibilité d'un attribut ou d'une d'une méthode indique à partir d'où  on peut y avoir accès. il y a deux trois types de visibilité : Private, Public, Protected.

conformément à la notation PEAR chaque élément private doit etre précédé d'un underscore 

````php
<?php
class Nom_de_classe
{
	private $_attr1;  //attribut 1
	public $attr2; // attribut 2 
	protected $attr3: //attribut 3

	public function nom_de_fonction() // Méthode
	{
		//Code à éxécuter
	}
}
?>
````

## Créer un Objet :

On dit que l'on instancie la classe.
````php
<?php
	$objet = new Nom_de_Classe
?>
````

## Appeler une méthode d'un objet :
On verra plus tard comment accéder à un attribut
````php
<?php                 		
	$objet = new Myclass ;		
	$objet->methode() ;
?>
````

## $this

$this représente l'objet que nous sommes en train d'utiliser, que nous voulons appeler au sein de la classe.

								
	
````php
    <?php							
    	class Personnage					
    	{							
    	  private $_experience = 50;			
    	  public function afficherExperience()	
    	  {							
    	    echo $this->_experience;			
    	  }							
    	}							
    	$perso = new Personnage;			
    	$perso->afficherExperience();	
	?>
   ````	

## Exiger des objets en paramètre

Afin de s'assurer que ce soit bien un objet qui est passé en paramètre de notre méthode (si c'est ce que nous voulons) , il suffit de précéder le paramètre du nom de la classe sur laquelle il est censé s'appliquer.

````php
<?php											
	class Personnage									
	{											
	  // …										
	  public function myFunction(Personnage $parametreObjet)		
	  {											
	    // …										
	  }											
	}			
````	

## Accesseur (ou getters)
ce sont des des méthodes dont le seul rôle sera de nous donner l'attribut qu'on leur demande. Par convention, ces méthodes portent le même nom que l'attribut dont elles renvoient la valeur. 

````php
<?php											
	class Personnage									
	{											
	  private $_attribut;								
												
	  public function attribut()							
	  {											
	    return $this->_attribut;							
 	 }											
	}											
								
````
														

## Mutateurs (ou setters) :

la classe doit impérativement contrôler la valeur afin d’assurer son intégrité car, si elle ne le fait pas, on pourra passer n'importe quelle valeur à la classe et le principe d'encapsulation n'est plus respecté ! Ces méthodes ont aussi un nom spécial : il s'agit des mutateurs (ou setters). Ces méthodes sont de la forme `setNomDeLAttribut()`

````php
<?php											
 class Personnage									
 {												
   private $_attribut;									
   												
   public function setAttribut($attribut) {					
 	if(!is_int($attribut)) // si $attribut n'est pas un entier...	
	{											
		trigger_error('message d\'erreur' , E_USER_WARNING) ;	
		return ;									
	}											
	$this->_attribut = $attribut ;	 
	 // attribue une valeur à l'attribut grace au parametre de la methode											     							    		
	}							
  												
												
   public function attribut()							
   {												
      return $this->_attribut;							
   }												
 }
 ?>
 ````

## Constructeur :

Le constructeur est une méthode écrite dans la classe. il sert a initialiser les attribut d'un objet dès sa création, sans connaitre les valeurs à l'avance. Le constructeur se nomme toujours avec 2 underscore au début : 
````php
<?php
__construct
?>
````
comme son nom l'indique il sert à construire l'objet (initialisation des attributs ou connexion à la BDD (base de données). il est exécuté dés la création de l'objet et par conséquent; aucune valeur ne doit être retournée même si ça ne générera aucune erreur. Une classe fonctionne trés bien sans constructeur, il n'est en rien obligatoire.S'il n'est pas spécifié, cela revient au même que d'en écrire un vide (sans instruction à l'intérieur).

````php
<?php											
 class Personnage									
 {												
   private $_attr1;									
   private $_attr2;									
   private $_attr3;									
   												
   public function __construct($attr1,$attr2) {				
	$this->setAttr1($attr1) ;							
	$this->setAttr2($attr2) ;							
	$this->_attr3 = 1 ;								
   }												
												
   public function setAttr1($attr1) {						
 	if(!is_int($attr1)) // si $attribut n'est pas un entier...	
	{											
		trigger_error('message d\'erreur' , E_USER_WARNING) ;	
		return ;									
	}											
	$this->_attr1 = $attr1 ;
	 // attribue une valeur à l'attribut grâce au paramètre de la méthode					
   }						
  												
												
   public function attribut()							
   {												
      return $this->_attribut;							
   }												
   // ...											
 }												
?>												

Il suffit ensuite de créer l'instance en passant les valeurs adéquates en paramètre, e.g. : 

									
	<?php                 					
	$objet1 = new Personnage(60 , 30) ;		
	$objet2 = new Personnage(100 , 10) ;		
									

## Auto-chargement de classes

Pour une question d organisation, il vaut mieux créer un fichier par classe. 
Une bonne pratique est de toujours appeler les fichiers  « MaClasse.php ».
Ainsi, pour pouvoir utiliser la classe MaClasse, il suffit d inclure ce fichier : 

												
 <?php											
   require 'MaClasse.php'; // J'inclus la classe.				
												
   $objet = new MaClasse; // Puis, seulement après, je me sers de ma classe.			
 ?>			
												

Si l'on a beaucoup de classes il peut être laborieux d'inclure
 tous les fichiers dans notre fichier principal, d'autant
 qu'on n'est pas sûr de toutes les utiliser. 
 On peut alors faire appel à la fonction autoload de php. 

													
 <?php											
												
   function chargerClasse($classe){						
	require $classe.'.php' ;// On inclut la classe correspondante	
	au paramètre passé.								
   }												
												
   spl_autoload_register('chargerClasse') ; // On enregistre la 	
   fonction en autoload pour qu'elle soit appelée dès qu'on 		
   instanciera une classe non déclarée.						
												
   require 'MaClasse.php'; // J'inclus la classe.				
												
   $objet = new MaClasse; 
   // Puis, seulement après, je me sers de  ma classe.	
   ?>														
````

On crée dans notre fichier principal (celui on l'on crée des instances de classe) une ou plusieurs fonctions(s) qui tenteront de charger le fichier déclarant la classe. Dans la plupart des cas, une fonction suffit. Ces fonctions doivent accepter un paramètre, c'est le nom de la classe qu'on doit tenter de charger (e.g. ci-dessus la fonction chargerClasse). Ensuite on utilise la fonction spl_autoload_register en spécifiant en premier paramètre le nom de la fonction à charger. 

En PHP, il y a ce qu'on appelle une « pile d'autoloads ». Cette pile contient une liste de fonctions. Chacune d'entre elles sera appelée automatiquement par PHP lorsque l'on essaye d'instancier une classe non déclarée. Nous avons donc ici ajouté notre fonction à la pile d'autoloads afin qu'elle soit appelée à chaque fois qu'on essaye d'instancier une classe non déclarée. 

## Opérateur de résolution de portée (`::`) :

Appelé « double deux points » (« Scope Resolution Operator » en anglais), il est utilisé pour appeler des éléments appartenant à telle classe et non à tel objet.  

Les constantes de classe :

Une constante est une sorte d'attribut appartenant à la classe dont la valeur ne change jamais. Les constantes de classe permettent d'éviter le 'code muet'. Comme par exemple quand on passe un entier en paramètre d'une création d'objet mais qu'on ne sait pas à quel attribut il correspond. Si par ex. on crée un objet Personnage avec une force qu'on déclare en attribut et qu'il n'y a que 3 niveaux de force possible, on peut les déclarer en constante. 
Pour déclarer une constante, vous devez faire précéder son nom du mot-clé const. Attention, une constante ne prend pas de « $ » devant son nom.

````php											
<?php											
 class Personnage									
 {												
   private $_force;									
   private $_experience;								
   private $_degats;									
   												
   // Déclaration des constantes en rapport avec la force		
   const FORCE_PETITE = 20 ;								
   const FORCE_MOYENNE = 50 ;							
   const FORCE_GRANDE = 80 ;																				
   public function __construct($forceInitiale)				
   {												
	$this->setForce($forceInitiale) ;						
   // Il faut assigner la valeur d'un attribut uniquement depuis 	
   son setter										
   }												
   // ...											
   public function setForce($force)						
   {												
   // On vérifie qu'on nous donne bien soit une « FORCE_PETITE »,	
   soit une « FORCE_MOYENNE », soit une « FORCE_GRANDE ».		
	if (in_array($force, [self::FORCE_PETITE, self::FORCE_MOYENNE,	self::FORCE_GRANDE]))								
    	{											
         $this->_force = $force;							
    	}											
   }												
   }							
````

Lors de la création de l'objet, la syntaxe est la suivante :

````php
 <?php											
   // On envoie une « FORCE_MOYENNE » en guise de force initiale.	
   $perso = new Personnage(Personnage::FORCE_MOYENNE);	
````

## Les méthodes statiques :

Les méthodes statiques sont des méthodes qui sont faites pour agir sur une classe et non sur un objet. Par conséquent, aucun $this dans la méthode, c'est un paramètre implicite qui n'est vrai que pour les méthodes appelées sur les objets.
Même si la méthode est dite « statique », il est possible de l'appeler depuis un objet 
````php
($obj->methodeStatique())
````

 mais, même dans ce contexte, la variable `$this` ne sera toujours pas passée. 
 Pour déclarer une méthode statique, faire précéder le mot-clé function du mot- clé static après      le type de visibilité. 

````php
<?php											
   class Personnage									
   {												
   // …											
	public static function saySomething() {						
	   echo 'Something' ;									
	}			
``````

Et dans le code :

````php											
 <?php											
   Personnage::saySomething();
   
````

résultat final.Préférer appeler la méthode avec l'opérateur de résolution de portée.

Les attributs statiques :

Le principe est le même, c'est-à-dire qu'un attribut statique appartient à la classe et non à un objet. Ainsi, tous les objets auront accès à cet attribut et cet attribut aura la même valeur pour tous les objets. 

La déclaration d'un attribut statique se fait en faisant précéder son nom du mot-clé `static` :

````php
<?php											
   class Personnage									
   {												
   // …											
	private static $_staticAttr = 'something' ;																		
	public static function saySomething() {						
	   echo self::$_staticAttr ;								
	}				
````

L'intérêt de l'attribut statique est que, si on le change, toutes les instances bénéficieront du changement. Si un attribut statique est modifié, il n'est pas modifié uniquement dans l'objet créé mais dans la structure complète de la classe. 
Le mot-clé self veut « moi-même » c'est-à-dire la classe dans lequel il est utilisé. A ne pas confondre avec $this qui se réfère à l'instance/l'objet créé.
   





