# Les Routes 
## les Routes basiques : 

Les routes sont constitué du mots clé `Route` d'une méthode statique `get:: || post:: || put:: || delete::` d'une URI `('/index',` d'une action du controller `'MyController@index');`
### Exemple de Routes : 

    Route::get('/index', 'MyController@index');

Exemple de CRUD (Create, Read, Update, Delete)
cet exemple provient du projet happyCofee-ilot3
````php
        Route::get('/drinks', 'DrinkController@index');
        Route::get('/drinks/create', 'DrinkController@create'); 
        Route::post('/drink/store','DrinkController@store');
        Route::get('/drinks/{id}', 'DrinkController@show');
        Route::get('/drinks/{id}/edit','DrinkController@edit');
        Route::put('/drinks/{id}', 'DrinkController@update');
        Route::delete('/drinks/{id}', 'DrinkController@destroy');
````

# Route Nommées
Les routes nommées permette la generation pratique d'URL ou de redirection pour des Routes spécifiques. On peut spécifier un nom pour une Route en chainant la methode `name` sur la definition de la route.

    Route::get(/'index', myController@index') ->name('Display');

		
On peut par exemple rediriger vers une vue dans le fichier `MyController`
 

     public function index()
        {
          return redirect(route('Display');
        }

# Paramêtre dans les Routes :
On peut passer des paramètres dans les routes si on veut passer un `id` dans la route par exemple : 

    Route::get('/drinks/{id}', 'DrinkController@show');
	
traduction du code ci dessous : 

    Route::get(uri:'/drinks/{paramètre}', action:'myController@show'

