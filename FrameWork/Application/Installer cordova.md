


# Installer Cordova 
Aprés avoir installer Node.js  (et donc NPM ):

Pour installer cordova les ligne de commande marche avec Node.js et sont disponible su NPM.
Ouvrir un terminal et taper 

    npm install -g cordova

# Créer un projet Cordova 
pour créer un projet qui utilise les lignes de commandes , se positionner dans le repertoire dans lequel on veut créer le projet et taper :

    cordova create <Nom de mon Application>

# Ajouter une plateforme

près avoir créé un projet Cordova, accédez au répertoire du projet. Dans le répertoire du projet, vous devez ajouter une plate-forme pour laquelle vous souhaitez créer votre application.

 

    cd MyApp
	

    cordova platform add browser

## Supprimer une plateforme 

	cordova platform rm android
   
    cordova platform remove blackberry10

# Lancer une plateforme 

    cordova run android 
 
 # Build son Application
 

    cordova build <platform>


