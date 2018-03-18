# Installation d'un framework 
1) **définition de composer** 

	Composer est un gestionnaire de dépendances libre écrit en PHP. Il permet à ses utilisateurs de déclarer et d'installer les bibliothèques dont le projet principal a besoin.

2) **installation de composer**
Aprés avoir télécharger au préalable l'éxécutable sur le site de composer et avoir installer via le `composer.exe`

## installation de laravel
Pour telecharger l'installer de laravel via le gestionnaire de dépendance composer une utilise la commande :

    composer global require "laravel/installer"

Dans le Bash (ouvert dans mon dossier de travail) entrer la ligne suivante :

    laravel new myProjectDirectory


## Lancer Artisan
Artisan est un CLI (Command line Utility) associée à Laravel. Il fournit toue une série de commandes intéressantes :

    php artisan --help

On peut ensuite démarrer un serveur de développement local grâce à Artisan :

    php artisan serve

Laravel nous renvoie le message suivant :

    Laravel development server started: <http://127.0.0.1:8000>

La racine de notre projet est maintenant visible à l'adresse ci-dessus.



