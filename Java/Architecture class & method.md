### Architecture d'une classe et d'une methode Java :

````java
public class WhiteSpace {
	public static void main(String[] args) {
  /* Î          Î       Î       Î         Î           Î
    (1)       (2)     (3)   (4)      (5)       (6)
*/
		boolean isFormatted = false;
        System.out.println(isFormatted);

	}
}
/*
    1* Type de Visibilité.
    2* Précise que la method main() n'est pas liée à une instance de classe.
    3* Method qui annonce qu'on ne return rien.
    4* main désigne le point d'entrée de mon application.
    5* Le type String permet de gérer les chaînes de caractères, c'est-à-dire le stockage de texte.
    6* Nom de mon type String[]
*/
````