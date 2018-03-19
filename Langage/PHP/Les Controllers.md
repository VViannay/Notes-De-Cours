# Les Controllers 

Les controllers peuvent regrouper la logique de routage connexe dans une classe et tirer parti des fonctionnalités de cadres avancées telles que l'injections automatique de dépendances 

les controlleurs sont rangé dans le dossier `app/controllers` et ce repertoire est enregistrer dans la `classmap` une option de `composer.json` le fichier par default.
Cependant les controllers peuvent techniquement se trouver dans n'importe quel dossier ou sous dossier. les déclaration des routes ne dépendent pas de l'endroit ou se trouve le fichier de classe controller sur le disque. Donc, tant que Composer sait comment charger automatiquement la classe de contrôleur, il peut être placé n'importe où.

**Exemple de controller :** 

````
class UserController extends BaseController {

    /**
     * Show the profile for the given user.
     */
    public function showProfile($id)
    {
        $user = User::find($id);

        return View::make('user.profile', array('user' => $user));
    }

}
````

tout les controleurs doivent etendre la classe `BaseController`qui est également stocké dans le repertoire.
maintenant nous pouvons router vers cette action du controller 

    Route::get('/user/{id}', 'UserController@index');


