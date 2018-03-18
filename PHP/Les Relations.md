
# les Relations 
Intéragir avec une table c'est bien, mais dans une application complexe on est souvent amené à lier plusieurs table à travers des relations plus ou moins avancées.

### Relation 1..n
On va commencer par la relation la plus courante, la relation  hasMany/belongsTo . Par exemple, dans le cas d'une machine à café , une boisson peut avoir plusieurs vente et une vente peut être associé à une seule boisson.

Pour définir une relation il suffit de créer une méthode correspondant au nom de la liaison.
````php
class Drink extends model 
{
	public function log()
	{
		return $this->hasMany('app\Price');
	}
}
``````
 
 et sa relation inverse : 
 ````php
class Price extends model 
{
	public function log()
	{
		return $this->belongsTo('app\Drink');
	}
}
``````



