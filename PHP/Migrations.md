# Les Migrations 
les migrations sont un moyen de contrôle de version de database Elles permettent à l'équipe de modifier le schéma de la database et de rester à jour sur l’état actuel du schéma. Les migrations sont généralement associées au générateur de schéma pour gérer facilement le schéma de votre application.

## Créer migrations
Pour créer une migration , on doit utiliser la commande `migrate:make` de artisan.

    php artisan migrate make: create_users_table

la migration va etre placer dans le dossier `app/database/migrations` et va contenir un timestamp ce qui permet au framework de déterminer l'ordre des migrations.

Vous pouvez également spécifier une option --path lors de la création de la migration. Le chemin doit être relatif au répertoire racine de votre installation:

    php artisan migrate:make foo --path=app/migrations

Les options --table et --create peuvent également être utilisées pour indiquer le nom de la table et si la migration va créer une nouvelle table:

    php artisan migrate:make add_votes_to_user_table --table=users
    
    php artisan migrate:make create_users_table --create=users


## Démarrer les migrations

### Exécuter toutes les migration :

    php artisan migrate

### Exécution de toutes les migrations exceptionnelles pour un chemin

    php artisan migrate --path=app/foo/migrations

### Exécution de toutes les migrations exceptionnelles pour un package

    php artisan migrate --package=vendor/package

 

**Remarque: Si vous recevez une erreur "class not found" lors de l'exécution de migrations, essayez d'exécuter la commande `composer dump-autoload`.**

## Forcer les migrations

Certaines opérations de migration sont destructrices, ce qui signifie qu'elles peuvent vous faire perdre des données. Afin de vous protéger de l'exécution de ces commandes sur votre base de données de production, vous serez invité à confirmer avant d'exécuter ces commandes. Pour forcer l'exécution des commandes sans invite, utilisez l'indicateur --force:

    php artisan migrate --force
    
## Rolling back Migration 


### Annuler la dernière opération de migration

    php artisan migrate:rollback
### Annuler toutes les migrations

    php artisan migrate:reset

### Annulez toutes les migrations et réexécutez-les

    php artisan migrate:refresh
    php artisan migrate:refresh --seed
    

## database Seeding 

Laravel inclus aussi un moyen simple d'alimenter votre database avec des données de test ou d'initialisation qui utilise les classes `seed`. Les Classes seed sont stocker dans le répertoire `app/database/seeds`. 
Les classes seed peuvent avoir n'importe quel nom , mais doivent suivre une convention raisonnable, telle que `UserTableSeeder`.

### Exemple de database seed Class:
````php
class DatabaseSeeder extends Seeder {

    public function run()
    {
        $this->call('UserTableSeeder');

        $this->command->info('User table seeded!');
    }

}

class UserTableSeeder extends Seeder {

    public function run()
    {
        DB::table('users')->delete();

        User::create(array('email' => 'foo@bar.com'));
    }

}
````


Pour alimenter votre base de données, vous pouvez utiliser la commande `db: seed` sur l'interface de ligne de commande Artisan:

    php artisan db:seed


Par défaut, la commande db: seed exécute la classe DatabaseSeeder, qui peut être utilisée pour appeler d'autres classes de seed. Toutefois, vous pouvez utiliser l'option --class pour spécifier une classe de semeur spécifique à exécuter individuellement:


    php artisan db:seed --class=UserTableSeeder

Vous pouvez également alimenter  votre base de données à l'aide de la commande migrate: refresh, qui annulera et réexécutera toutes vos migrations:

    php artisan migrate:refresh --seed
    	

