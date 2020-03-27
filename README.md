Programmation Java @ Et3
<br>
Polytech Paris-Saclay | 2019-20

___

# TP1

Vous allez développer une gestion simple d’autotamponneuses. Celles-ci sont caractérisées par :
- le fait qu’elles soient placées ou non sur une piste d’autotamponneuses, leur position étant alors représentée par une paire de valeurs réelles (coordonnées dans un plan à deux dimensions)
- le fait qu’elles soient occupées ou non, et si oui par quelle personne (il faut qu’elles soient placées pour pouvoir être occupées)
- le fait qu’elle soient allumées ou non (il faut qu’elles soient occupées pour pouvoir être allumées)
- le fait qu’elle soient clignotantes ou non (il faut qu’elles soient allumées pour pouvoir être cignotantes)

1#1. Créez une nouvelle classe Autotamponneuse dans un package com.feteforraine. Ajoutez les données nécessaires à la classe en choisissant les niveaux de visibilité appropriés.

- 1#1.1 classe Autotamponneuse :

> La classe est `public`, ce qui veut dire qu'elle est accessible depuis n'importe quel endroit du projet.
> Les données ne sont visible que depuis la classe, elle sont donc `private`.
> Ici, on travaille avec des [types primitifs](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html) (boolean, double) et une classe des API standard ([String](https://docs.oracle.com/javase/9/docs/api/java/lang/String.html)).
>
> ```Java
> package com.feteforraine;
> 
> public class Autotamponneuse 
> {
> 	private boolean placee = false;
> 	private double[] position = new double[2];
>   
> 	private boolean occupee = false;
> 	private String nomOccupant = "";
> 	
> 	private boolean allumee = false;
> 	
> 	private boolean clignotante = false;
> }
> ```

1#2. Ajoutez deux constructeurs à la classe : l’un sans paramètres, l’autre avec une coordonnée x et une coordonnée y. Faites en sorte de réutiliser ce qui peut l’être dans vos constructeurs.

- 1#2.1 constructeur sans paramètres : 

> ```Java
> public Autotamponneuse()
> {
> 		this.occupee = false;
> 		this.allumee = false;
> 		this.clignotante = false;
> 		this.placee = false;
> 		this.position[0] = 0.0d;
> 		this.position[1] = 0.0d;
> 		this.nomOccupant = "";
> }
> ```
> 
> Le `this` renvoie à l'instance de la classe, donc `this.occupee` renvoie, par exemple, à l'attribut `occupee` de l'autotamponneuse. On peut utiliser le `this` systématiquement mais il est surtout important de l'utiliser lorsqu'un des paramètres d'une méthode a le même nom qu'un attribut de la classe, cela permet de les différencier malgré un nom identique.

- 1#2.2 constructeur avec 2 paramètres :

> ```Java
> public Autotamponneuse(double positionX, double positionY)
> {
> 	this();
> 	this.placee = true;
> 	this.position[0] = positionX;
> 	this.position[1] = positionY;
> }
> ```
> 
> Ici, `this()` renvoie au constructeur sans paramètre

- 1#2.3 Pour quelles raisons aurait-on intérêt à réutiliser (invoquer) d'autres constructeurs lorsqu'on définit des constructeurs ?

> Cela peut être utile si:
> - on veut donner des valeurs par défaut à notre Autotamponeuse (exemple : si l'autotamponeuse est occupée, elle est automatiquement clignotante)
> - on veut définir manuellement d'autres paramètre (exemple : l'utilisateur peut choisir si l'autotamponeuse est clignotante ou non à sa création)

1#3. Ajoutez des méthodes d’instance dans la classe Autotamponneuse pour consulter l’état d’une
autotamponneuse particulière : estOccupee, getNomOccupant, estAllumee, estClignotante.

- 1#3.1 méthodes demandées

> ```Java
> /**
>  * Cette méthode permet de savoir si l'autotamponneuse est occupée ou non.
>  * @return VRAI si l'autotamponneuse est occupée et FAUX sinon
>  */
> public boolean estOccupee()
> {
> 	return this.occupee;
> }
> 
> /**
>  * Cette méthode permet d'obtenir le nom de l'occupant de l'autotamponeuse.
>  * @return Le nom de l'occupant de l'autotamponneuse
>  */
> public String getNomOccupant()
> {
> 	return this.nomOccupant;
> }
> 
> /**
>  * Cette méthode permet de savoir si l'autotamponneuse est allumée ou non.
>  * @return VRAI si l'autotamponneuse est allumée et FAUX sinon
>  */
> public boolean estAllumee()
> {
> 	return this.allumee;
> }
> 
> /**
>  * Cette méthode permet de savoir si l'autotamponneuse est clignotante ou non.
>  * @return VRAI si l'autotamponneuse est clignotante et FAUX sinon
>  */
> public boolean estClignotante()
> {
> 	return this.clignotante;
> }
> ```

- 1#3.2 Pourquoi parle-t-on de "méthodes d'instances" ?

> Une méthode d'instance est appelée sur une instance de la classe. Ce n'est donc pas une méthode `static`.

- 1#3.3 Pourquoi ces méthodes ne contournent-elles pas le principe d'encapsulation des données ?

> Elles ne contournent pas le principe d'encapsulation des données car elles retournent une copie de la donnée et non la donnée elle-même. Cela signifie qu'elles ne donnent pas l'accès à la donnée mais seulement sa valeur.

1#4. Ajoutez une méthode main dans la classe Autotamponneuse afin de pouvoir définir un programme principal de test. Testez-y sur des exemples le code précedemment défini, et utilisez-la pour tester le code des questions suivantes.

- 1#4.1 méthode  main

```Java
public static void main(String[] args)
	{
		Autotamponneuse auto1 = new Autotamponneuse();
		
	}
```

- 1#4.2 affichage produit par l'exécution de votre méthode  main

```Java

```

- 1#4.3 méthode main dans une nouvelle classe TestAutotamponneuse dans le package com.feteforraine

```Java

```

- 1#4.4 Comment faire en sorte d'exécuter la méthode main de la classe com.feteforraine. TestAutotamponneuse ?

```Java

```

- 1#4.5 Pourquoi la méthode main est-elle static ? A quoi correspond son paramètre ?

```Java

```

- 1#4.6 Quelles critiques pourriez-vous faire à l'approche consistant à tester le fonctionnement d'une classe au travers d'un programme de test exécuté par sa méthode main ? Quelles autres approches pourrait-on imaginer pour faire cela ?

```Java

```

1#5. Ajoutez le code nécessaire pour qu’une autotamponneuse ait désormais un identifiant entier unique. Cette valeur ne devra pas être choisie par l’utilisateur, et devra commencer à la valeur 1 pour la première autotamponneuse.

- 1#5.1 code ajouté

> ```Java
> private static int DERNIER_ID_ATTRIBUE = 0;
> private int	id = ++DERNIER_ID_ATTRIBUE; 
> ```
> `++DERNIER_ID_ATTRIBUE` va incrémenter la valeur de `DERNIER_ID_ATTRIBUE` de 1.

- 1#5.2 test du fonctionnement dans la méthode main

> ```Java
> public static void main(String[] args)
> {
> 	Autotamponneuse auto1 = new Autotamponneuse();
> 	Autotamponneuse auto2 = new Autotamponneuse();
>    
> 	// #1.5.2
> 	System.out.println();
> 	System.out.println("Question#1.5.2");
> 	System.out.println();
> 	System.out.println("ID de auto1 : " + auto1.id);
> 	System.out.println("ID de auto2 : " + auto2.id);
> }
> ```
> 
> Voici la sortie que l'on obtient :
> 
> ```
> 
> Question#1.5.2
> 
> ID de auto1 : 1
> ID de auto2 : 2
> ```

1#6. Redéfinissez dans la classe Autotamponneuse la méthode particulière suivante de la classe java.lang.Object : String toString() qui retourne une représentation sous forme de chaı̂ne de caractères de l’état d’un objet. Des exemples de chaı̂nes pourraient être :

[1] (5.0,5.0) libre éteinte non clignotante
[2] (7.0,2.0) occupée (Charles Darwin) éteinte non clignotante
[2] (5.1,5.0) occupée (Charles Darwin) allumée clignotante

- 1#6.1 redéfinition de la méthode toString

> ```Java
> public String toString()
> {
> 	String etatAutotamponeuse = "";
> 	
> 	//On ajoute l'ID de l'autotamponeuse
> 	etatAutotamponeuse += "[" + this.id + "]";
> 	
> 	//On ajoute un espace
> 	etatAutotamponeuse += " ";
> 			
> 	//On ajoute la position de l'autotamponeuse
> 	etatAutotamponeuse += "(" + this.position[0] + ";" + this.position[1] + ")";
> 	
> 	//On ajoute un espace
> 	etatAutotamponeuse += " ";
> 	
> 	//L'autotamponeuse est-elle occupée ?
> 	if(this.occupee)
> 	{
> 		etatAutotamponeuse += "occupée (" + this.nomOccupant + ")";
> 	}
> 	else
> 	{
> 		etatAutotamponeuse += "libre";
> 	}
> 	
> 	//On ajoute un séparateur
> 	etatAutotamponeuse += " / ";
> 	
> 	//L'autotamponeuse est-elle allumée ?
> 	if(this.allumee)
> 	{
> 		etatAutotamponeuse += "allumée";
> 	}
> 	else
> 	{
> 		etatAutotamponeuse += "eteinte";
> 	}
> 	
> 	//On ajoute un séparateur
> 	etatAutotamponeuse += " / ";
> 	
> 	//L'autotamponeuse est-elle clignotante ?
> 	if(this.clignotante)
> 	{
> 		etatAutotamponeuse += "clignotante";
> 	}
> 	else
> 	{
> 		etatAutotamponeuse += "non clignotante";
> 	}
> 			
> 	return etatAutotamponeuse;	
> }
> ```

- 1#6.2 test du fonctionnement dans la méthode main

> ```Java
> public static void main(String[] args)
> {
> 	Autotamponneuse auto1 = new Autotamponneuse();
> 	Autotamponneuse auto2 = new Autotamponneuse();
> 	
> 	// 1#6.2
> 	System.out.println();
> 	System.out.println("Question#1.6.2");
> 	System.out.println();
> 	System.out.println("Etat de auto1 : " + auto1.toString());
> 	System.out.println("Etat de auto2 : " + auto2.toString());
> }
> ```
> 
> Voici la sortie que l'on obtient :
> 
> ```
> 
> Question#1.6.2
> 
> Etat de auto1 : [1] (0.0;0.0) libre / eteinte / non clignotante
> Etat de auto2 : [2] (0.0;0.0) libre / eteinte / non clignotante
> ```

1#7. Ajoutez à présent des méthodes d’instance dans la classe Autotamponneuse pour modifier l’état d’une autotamponneuse particulière, en respectant les règles énoncées ci-dessus : place, ajouteOccupant, enleveOccupant, allume, eteint, demarreClignotement, arreteClignotement. Afin d’informer le programme appelant sur la modification effective ou non de l’objet correspondant, faites retourner à vos méthodes une valeur booléenne. On décide que ces méthodes ne pourront être accessibles qu’aux autres classes du même package (com.feteforraine).

- 1#7.1 définition des méthodes

> ```Java
> /**
>  * Cette méthode permet de placer l'autotamponneuse sur le circuit.
>  * @param positionX La position de l'autotamponneuse sur l'abscisse du circuit
>  * @param positionY La position de l'autotamponneuse sur l'ordonnée du circuit
>  * @return VRAI si l'autotamponneuse a pu être placée et FAUX sinon
>  */
> protected boolean place(double positionX, double positionY)
> {
> 	this.position[0] = positionX;
> 	this.position[1] = positionY;
> 	this.placee = true;
> 	return true;
> }
> 
> /**
>  * Cette méthode permet de définir qui occupe l'autotamponneuse.
>  * @param nomOccupant Le nom de l'occupant de l'autotamponneuse
>  * @return VRAI si l'occupant a pu rentrer dans l'autotamponneuse et FAUX sinon
>  */
> protected boolean ajouteOccupant(String nomOccupant)
> {
> 	if(!this.placee || this.occupee)
> 	{
> 		return false;
> 	}
> 	this.nomOccupant = nomOccupant;
> 	this.occupee = true;
> 	return true;
> }
> 
> /**
>  * Cette méthode permet de retirer l'occupant de l'autotamponeuse.
>  * @return VRAI si un occupant a pu être retiré de l'autotamponneuse et FAUX sinon
>  */
> protected boolean enleveOccupant()
> {
> 	if(!this.occupee)
> 	{
> 		return false;
> 	}
> 	this.nomOccupant = "";
> 	if(this.allumee)
> 	{
> 		this.eteint();
> 	}
> 	this.occupee = false;
> 	return true;
> }
> 
> /**
>  * Cette méthode permet d'allumer l'autotamponneuse.
>  * @return VRAI si l'autotamponneuse a pu être allumée et FAUX sinon
>  */
> protected boolean allume()
> {
> 	if(this.allumee || !this.occupee)
> 	{
> 		return false;
> 	}
> 	this.allumee = true;
> 	return true;
> }
> 
> /**
>  * Cette méthode permet d'éteindre l'autotamponneuse.
>  * @return VRAI si l'autotamponneuse a pu être éteinte et FAUX sinon
>  */
> protected boolean eteint()
> {
> 	if(!this.allumee)
> 	{
> 		return false;
> 	}
> 	this.allumee = false;
> 	if(this.clignotante)
> 	{
> 		this.arreteClignotement();
> 	}
> 	return true;
> }
> 
> /**
>  * Cette méthode permet de démarrer le clignotement de l'autotamponneuse.
>  * @return VRAI si le clignotement a pu être allumé et FAUX sinon
>  */
> protected boolean demarreClignotement()
> {
> 	if(this.clignotante || !this.allumee)
> 	{
> 		return false;
> 	}
> 	this.clignotante = true;
> 	return true;
> }
> 
> /**
>  * Cette méthode permet d'arrêter le clignotement de l'autotamponneuse.
>  * @return VRAI si le clignotement a pu être arrêté et FAUX sinon
>  */
> protected boolean arreteClignotement()
> {
> 	if(!this.clignotante)
> 	{
> 		return false;
> 	}
> 	this.clignotante = false;
> 	return true;
> }
> ```

- 1#7.2 test du fonctionnement dans la méthode main et trace d'exécution

> ```Java
> public static void main(String[] args)
> {
> 	Autotamponneuse auto1 = new Autotamponneuse();
> 	Autotamponneuse auto2 = new Autotamponneuse();
> 	
> 	// 1#7.2
> 	System.out.println();
> 	System.out.println("Question#1.7.2");
> 	System.out.println();
> 	System.out.println("Je place l'auto1 en position (1.0,2.0) : " + auto1.place(1.0,2.0));
> 	System.out.println("Nouvel état de l'auto1 : " + auto1.toString());
> 	System.out.println("Nouvel état de l'auto2 : " + auto2.toString());
> 	System.out.println("J'allume l'auto1 : " + auto1.allume());
> 	System.out.println("J'allume l'auto2 : " + auto2.allume());
> 	System.out.println("état de auto1 : " + auto1.toString());
> 	System.out.println("état de auto2 : " + auto2.toString());
> 	System.out.println("Bob Marley entre dans l'auto1 : " + auto1.ajouteOccupant("Bob Marley"));
> 	System.out.println("John Lennon entre dans l'auto2 : " + auto2.ajouteOccupant("John Lennon"));
> 	System.out.println("état de auto1 : " + auto1.toString());
> 	System.out.println("état de auto2 : " + auto2.toString());
> 	System.out.println("Je démarre le clignotement de l'auto1 : " + auto1.demarreClignotement());
> 	System.out.println("Je démarre le clignotement de l'auto2 : " + auto2.demarreClignotement());
> 	System.out.println("état de auto1 : " + auto1.toString());
> 	System.out.println("état de auto2 : " + auto2.toString());
> 	System.out.println("J'allume l'auto1 : " + auto1.allume());
> 	System.out.println("J'allume l'auto2 : " + auto2.allume());
> 	System.out.println("état de auto1 : " + auto1.toString());
> 	System.out.println("état de auto2 : " + auto2.toString());
> 	System.out.println("Je démarre le clignotement de l'auto1 : " + auto1.demarreClignotement());
> 	System.out.println("Je démarre le clignotement de l'auto2 : " + auto2.demarreClignotement());
> 	System.out.println("état de auto1 : " + auto1.toString());
> 	System.out.println("état de auto2 : " + auto2.toString());
> }
> ```
> 
> Voici la sortie que l'on obtient :
> 
> ```
> 
> Question#1.7.2
> 
> Je place l'auto1 en position (1.0,2.0) : true
> Nouvel état de l'auto1 : [1] (1.0;2.0) libre / eteinte / non clignotante
> Nouvel état de l'auto2 : [2] (0.0;0.0) libre / eteinte / non clignotante
> J'allume l'auto1 : false
> J'allume l'auto2 : false
> état de auto1 : [1] (1.0;2.0) libre / eteinte / non clignotante
> état de auto2 : [2] (0.0;0.0) libre / eteinte / non clignotante
> Bob Marley entre dans l'auto1 : true
> John Lennon entre dans l'auto2 : false
> état de auto1 : [1] (1.0;2.0) occupée (Bob Marley) / eteinte / non clignotante
> état de auto2 : [2] (0.0;0.0) libre / eteinte / non clignotante
> Je démarre le clignotement de l'auto1 : false
> Je démarre le clignotement de l'auto2 : false
> état de auto1 : [1] (1.0;2.0) occupée (Bob Marley) / eteinte / non clignotante
> état de auto2 : [2] (0.0;0.0) libre / eteinte / non clignotante
> J'allume l'auto1 : true
> J'allume l'auto2 : false
> état de auto1 : [1] (1.0;2.0) occupée (Bob Marley) / allumée / non clignotante
> état de auto2 : [2] (0.0;0.0) libre / eteinte / non clignotante
> Je démarre le clignotement de l'auto1 : true
> Je démarre le clignotement de l'auto2 : false
> état de auto1 : [1] (1.0;2.0) occupée (Bob Marley) / allumée / clignotante
> état de auto2 : [2] (0.0;0.0) libre / eteinte / non clignotante
> ```

- 1#7.3 En créant une classe Test dans le package par défaut, invoquez la méthode ajouteOccupant. Que se passe-t-il, pourquoi ?

> On obtient l'erreur suivante :
> Exception in thread "main" java.lang.Error: Unresolved compilation problem:
> The method ajouteOccupant(String) from the type Autotamponneuse is not visible at tp1/test.Test.main(Test.java:10)
> 
> La visibilité de la méthode ajouteOccupant étant `protected`, on ne peut y accéder que depuis le même package ou les classes filles.

1#8. On souhaite détecter des collisions entre autotamponneuses. Pour simplifier, on dira que deux autotamponneuses sont en collision si la distance entre leurs positions (comprise ici comme un point dans le plan) est inférieure à une valeur constante définie au niveau de la classe, DISTANCE_MINIMALE. Ajoutez cette valeur de manière appropriée, puis ajoutez une méthode d’instance pour le calcul de distance entre deux autotamponneuses :

double calculeDistance(Autotamponneuse autreAuto)

ainsi qu’une méthode d’instance indiquant si une collision a lieu entre deux autotamponneuses :

boolean collision(Autotamponneuse autreAuto)

- 1#8.1 déclaration du champ  DISTANCE MINIMALE

> ```Java
> public static final double DISTANCE_MINIMALE = 2.0d;
> ```

- 1#8.2 méthode  calculeDistance

> ```Java
> /**
>  * Cette méthode permet de calculer la distance entre l'autotamponneuse et une autre.
>  * @param autreAuto L'autre autotamponneuse
>  * @return La distance entre les deux autotamponneuses
>  */
> public double calculeDistance(Autotamponneuse autreAuto)
> {
> 	double distance = Math.sqrt((this.position[0] - autreAuto.position[0])
> 			* (this.position[0] - autreAuto.position[0])
> 			+ (this.position[1] - autreAuto.position[1])
> 			* (this.position[1] - autreAuto.position[1]));
> 	return distance;
> }
> ```

- 1#8.3 méthode  collision

```Java

```

- 1#8.4 exemples de tests de collisions dans la classe TestAutotamponneuse

```Java

```

1#9. Afin d’autoriser d’autres types d'utilisation, proposez des équivalents sous forme de méthodes de classes pour les deux méthodes d’instance précédentes :

static double calculeDistance(Autotamponneuse auto1, Autotamponneuse auto2)

et :

static boolean collision(Autotamponneuse auto1, Autotamponneuse auto2)

Bien prendre en compte le fait que les paramètres peuvent tous les deux avoir une valeur null à l’exécution.


- 1#9.1 méthode  de classes calculeDistance

```Java

```

- 1#9.2 méthode de classes collision

```Java

```

- 1#9.3 exemples de tests de collisions dans la classe TestAutotamponneuse

```Java

```

- 1#9.4 La définition des méthodes de classes pourrait-elle réutiliser celle de la méthode d'instances correspondante ? Si oui, pourquoi ?

```Java

```

1#10. Redéfinissez dans la classe Autotamponneuse la méthode de la classe java.lang.Object :

boolean equals(Object autreObjet)

qui indique si deux objets sont égaux (même état complet ici). Attention, la méthode étant déclarée au niveau de la classe java.lang.Object, il faudra vérifier puis transtyper le type du paramètre de la méthode.

- 1#10.1 redéfinition de la méthode  equals

```Java

```

- 1#10.2 tests d'égalité entre objets dans la classe TestAutotamponneuse

```Java

```

1#11. Ajoutez une nouvelle classe PisteAutotamponneuses dans le package com.feteforraine. Une telle classe comporte une collection d’autotamponneuses représentée par un tableau. Ajoutez-y un constructeur prenant pour paramètre la taille de cette collection.

- 1#11.1 définition de la classe PisteAutotamponneuses

```Java

```

1#12. Ajoutez une nouvelle méthode statique main dans la classe PisteAutotamponneuses pour définir un programme de test qui crée le nombre d’autotamponneuses requis et les place de façon aléatoire sur la piste (cf. Math.random()). Faites en sorte qu’aucune autotamponneuse nouvellement placée ne soit en collision avec une autre autotamponneuse.

- 1#12.1 méthode main

```Java

```

- 1#12.2 trace d'exécution de tests de création de piste

```Java

```

1#13. Redéfinissez la méthode String toString() de la classe PisteAutotamponneuses afin qu’elle affiche l’état de la collection complète (l’ordre des autotamponneuses sera par ordre d’ajout). Utilisez pour cela la classe java.lang.StringBuilder.

- 1#13.1 méthode toString

```Java

```

- 1#13.2 test d'utilisation de la méthode toString

```Java

```

1#14. Ajoutez une méthode dereglementAleatoire à la classe PisteAutotamponneuses qui déplace de façon aléatoire et continue chaque autotamponneuse encore pilotée tour à tour, et élimine les autotamponneuses entrées en collision. Cette méthode affichera l’historique des autotamponneuses éliminées, et le vainqueur (autotamponneuse survivante si elle existe).

- 1#14.1 méthode dereglementAleatoire

```Java

```









Vous allez développer une classe utilitaire en Java permettant de réaliser divers traitements sur des tableaux d’entiers.

2#1. Créez une classe au nom approprié dans un package pertinent. Ajoutez une méthode statique à votre classe permettant de créer un tableau d’entiers (int[]) à partir d’un tableau de chaı̂nes de caractères (String[]).

- 2#1.1 code de la classe

> ```Java
> package et3.java;
> 
> public class TableauEntiers
> {
> 	/**
> 	 * Cette méthode permet de transformer un tableau de chaînes de caractères en tableau d'entiers
> 	 * 
> 	 * @param tabString Le tableau de chaînes de caractères à transformer
> 	 * @return Le tableau d'entiers créé à partir du tableau de chaînes de caractères
> 	 */
> 	public static int[] creerTableauEntiers ( String [] tabString )
> 	{
> 		//On crée un tableau d'entiers ayant la même taille que le tableau de chaînes de caractères
> 		int [] tabInt = new int [tabString.length];
> 		
> 		//On parcours le tableau de chaînes de caractères
> 		for(int indice = 0; indice < tabString.length; indice++)
> 		{
> 			//On tente d'éxécuter le code ci-dessous
> 			try
> 			{
> 				//On parse l'élément i du tableau de chaînes de caractère en entier
> 				//On associe cet entier à l'élément i du tableau d'entiers
> 				tabInt[indice] = Integer.parseInt(tabString[indice]);
> 			}
> 			//Si le code du "try" renvoie une erreur "NumberFormatException", on execute le code ci-dessous
> 			catch(NumberFormatException exception)
> 			{
> 				//On informe l'utilisateur que tabString[indice] ne peut pas être transformé en entier
> 				System.out.println("La valeur " + tabString[indice] + " d'indice " 
> 						+ indice + " ne peut pas être transformée en entier");
> 				System.out.println("Cette valeur sera donc remplacée par 0 dans le tableau");
> 				
> 				//On donne la valeur 0 à l'indice i du tableau d'entier
> 				tabInt[indice] = 0;
> 			}
> 		}
> 		
> 		//On retourne le tableau d'entiers
> 		return tabInt;
> 	}
> }
> ```
