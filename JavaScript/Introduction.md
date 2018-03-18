# Vues JS 

 ## 1. Rendu Déclaratif 
 
 Au cœur de Vue.js, il y a un système qui va nous permettre de faire le rendu des données déclarativement dans le DOM en utilisant simplement cette syntaxe de template :

 ````html
 <div id="app">  //element = el
 {{ message }}  //template
</div>
 ````
 ````js
 var app = new Vue({  
	 el: '#app', //nom de l'id  
	 data: {  
		 message: 'Hello Vue !' // nom du template 
	 }  
})
 ````

Vue effectue un réel travail. Les données et le DOM sont maintenant couplés et tout est a présent réactif.
Comment s'en rendre compte ?
ouvrez la console JavaScript de votre  navigateur et attribuez a app.message differente valeurs comme ceci : 

    app.message = 'Vins';

on obtient le rendu de l'exemple ci dessus se mettre à jour en concordance

## 2. Lier les attribut d'un éléments

pour lier un attribut il faut faire comme ceci : 
````html
<div id="app-2">  
 <span v-bind:title="message">  
 Passez votre souris sur moi pendant quelques secondes  
 pour voir mon titre lié dynamiquement !  
 </span>  
</div>
````
````js
	var app2 = new Vue({  
		 el: '#app-2',  
		 data: {  
		message: 'Vous avez affiché cette page le '+ newDate().toLocaleString()  
		 }  
})
````
Ici nous venons de rencontrer quelque chose de nouveau. L’attribut  `v-bind`  que vous voyez est appelé une  **directive**. Les directives sont préfixées par  `v-`  pour indiquer que ce sont des attributs spéciaux fournis par Vue, et comme vous l’avez peut-être deviné, elles appliquent un comportement réactif spécifique au DOM après rendu. Ici cela veut basiquement dire : « garde l’attribut  `title`  de cet élément à jour avec la propriété  `message`  de l’instance de Vue ».

Si vous ouvrez votre console JavaScript une nouvelle fois et entrez  `app2.message = 'un nouveau message'`, de nouveau vous verrez le HTML lié — dans notre cas l’attribut  `title`  — se mettre à jour.
 
## 3.Condition et Boucles
````html
<div id="app-3">  
 <p v-if="seen">Maintenant vous me voyez</p>  
</div>
````
````js
var app3 = new Vue({  
 el: '#app-3',  
 data: {  
 seen: true  
 }  
})
````
Côté console entrez  `app3.seen = false`. Vous devriez voir le message disparaitre.

Cet exemple démontre que nous pouvons lier des données non seulement aux textes et attributs, mais également à la  **structure**  du DOM. De plus, Vue fournit un puissant système d’effets de transition qui peut automatiquement appliquer des  effets de transition quand des éléments sont insérés/mis à jour/enlevés par Vue.

l existe quelques autres directives, chacune avec leur propre fonction spécifique. Par exemple, la directive `v-for` peut être utilisée pour afficher une liste d’éléments en provenance d’un tableau de données.
````html
<div id="app-4">  
	<ol>  
		 <li v-for="todo in todos">  
			 {{ todo.text }}  
		 </li>  
	 </ol>  
</div>
````
````js
var app4 = new Vue({  
	 el: '#app-4',  
	 data: {  
		 todos: [  
			 { text: 'Apprendre JavaScript' },  
			 { text: 'Apprendre Vue' },  
			 { text: 'Créer quelque chose de génial' }  
		]	  
	 }  
})
````

Dans la console, entrez `app4.todos.push({ text: 'Nouvel élément' })`. Vous devriez le voir ajouté à la liste.

## 4.Gestion des entrées utilisateurs

Afin de permettre aux utilisateurs d’interagir avec votre application, nous pouvons utiliser la directive `v-on` pour attacher des écouteurs Evènements qui invoquent des méthodes sur nos instances de Vue :

````html
<div id="app-5">  
 <p>{{ message }}</p>  
 <button v-on:click="reverseMessage">Message retourné</button>  
</div>
````
````js
var app5 = new Vue({  
 el: '#app-5',  
 data: {  
 message: 'Hello Vue.js !'  
 },  
 methods: {  
 reverseMessage: function () {  
 this.message = this.message.split('').reverse().join('')  
 }  
 }  
})
````
Notez que dans la méthode, nous avons seulement mis à jour l’état de l’application sans toucher au DOM. Toutes les manipulations de DOM sont prises en charge par Vue, ainsi le code que vous écrivez se concentre sur la logique sous-jacente.

Vue fournit aussi la directive `v-model` qui fait de la liaison de données bidirectionnelle entre les champs d’un formulaire et l’état de l’application. Une simple formalité :
````html
<div id="app-6">  
 <p>{{ message }}</p>  
 <input v-model="message">  
</div>
````
````js
var app6 = new Vue({  
 el: '#app-6',  
 data: {  
 message: 'Hello Vue !'  
 }  
})
````

