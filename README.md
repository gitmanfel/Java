![JAVA](./java.png)

# Java

## C'est quoi le java ?
On va regarder sur Wikipédia 

> Le langage Java a débuté dans les années 1990 avec James Gosling qui souhaitait développer un langage de programmation indépendant de  la plate-forme hardware. Oak (traduction : « Chêne ») fut un échec.

> Par la suite, Bill Joy (cofondateur de la firme Sun Microsystems) proposa une nouvelle version de Oak appelée « Java ». Son but était > de pallier une déficience des langages de programmation en produisant un langage conçu pour des machines et des logiciels hétérogènes.

> On trouve gratuitement sur le marché une machine virtuelle (Java Virtual Machine), qui inclut un compilateur, ainsi que de nombreux 
> outils visant à faciliter l'investissement du Web par Java. Cette machine virtuelle exécute un bytecode Java (similaire à de 
> l'assembleur) qui ajoute des étapes supplémentaires (décodage et interpretation) lors du runtime ce qui a pour conséquence de ralentir > fortement le fonctionnement d'une application par rapport à sa version compilée nativement (obtenue par exemple avec des langages tels  > que C ou C++).

> Après de très nombreuses modifications visant à améliorer le système, Java est devenu plus qu’une simple solution Internet, c’est 
> dorénavant un langage utilisé pour toutes sortes de développements, distribués, client lourd ou léger, etc


### Les avantages de Java

* Relativement plus simple que le c++
* Moins de bugs à gerer que le c++ (Surchage des opérateurs...)
* Temps de production réduit par rapport au c++ de 30%
* Java utilise le typage "fort" (Donc moins de possibilités d'erreurs).
* Java est robuste...
* Gestion de la mémoire n'est pas à charge du dev, contrairement au c++
* On peut faire du web, des applis desktop ou encore android.
* TRES demandé sur le marché de l'emploi

### Les incovénients de java

* Syntaxe longue même très longue.
* Plus complexe que la programmation web et donc c'est plus long à apprendre

### Petit rappel 

|Nom |Correspondance  | 
|:---|:---------------| 
|Bit | C'est la plus petite valeur informatique : soit 0 soit 1 |
|Octet (ou byte) | Regroupement de 8 bits, par exemple : 01011101 |
|Kilo octet | Regroupement de 1024 octets |
|Méga octet | Regroupement de 1024 Ko |
|Giga octet | Regroupement de 1024 Mo |
|Tera octet | Regroupement de 1024 Go |

Un bit = 2 possibilités.

Un octet =  2 exposant 8, ça fait 256 possibilités.

Deux Octets = 256 * 256 = 65536 possibilités.  

Quatre Octets = 256 exposant 4  = 4294967296 possibilités.

Huit Octets = 256 exposant 8 = 1.9631688e+19 possibilités.
...

### Les différents types de variables
**Déclaration et typage des variables**

Les noms des variables doivent toujours commencer par une minuscule et être écrite en [camelCase](https://fr.wikipedia.org/wiki/Camel_case). 

Lorsqu'on veut déclarer une variable, on doit la typer.
```java
TypeDeVariable  nomDeVariable;
```

Par exemple si on veut écrire une chaîne de caractère, nous devrons l'écrire comme ceci :
```java
String message = "Vous avez un message";  
```

Autre exemple, si on souhaite déclarer un integer.

```java
int nbMessage = 4;  
```

Pour concatener, on utilise le caractère ``+``

```java
int nbMessage = 4;  
String message = "Vous avez " + nbMessage + " message(s)";  
```

Si on veut typer plusieurs varaibles en une fois on peut faire :

````java
int nbMessages = 4, idUser =25655, nbObjets; 
String hello = "Bonjour ", name, phrase =" passe une bonne journée";

// cela revient à écrire

int nbMessages = 4;
int idUser = 25655;
int nbObjets;

String hello = "Bonjour";
String name;
String prhase = "passe une bonne journée";

````

#### Les variables  *primitives*

| Raccourcis | Type |
|:-----------|:-----|
| byte       | Peut contenir les entiers entre -128 et +127 (1 Octet) |
| short      | Peut contenir les entiers entre -32768 et +32767 (2 Octets)| 
| int        | Peut contenir les entiers entre -2147483648 et +2147483647 (4 Octets)|
| long       | Peut contenir les entiers entre  -9.8158441e+18 et +9.8158441e+18  (8 Octets)|
| float      | Peut contenir les décimaux (Virgule flottante)  de 4 Octets |
| double    | Peut contenir des décimaux  de  8 Octets | 
| char | Peut contenir une seule et unique lettre. |
| boolean | Peut contenir uniquement ``true`` ou ``false`` |


**Attention pour les float et les doubles** 

On ne mets pas de virgule pour exprimer un chiffre décimal, on utilise un point. 
En java on écrit les float de cette manière. 

````java
float decimal = 0.637f;

````
On rappelle toujours à Java qu'il s'agit d'un float à la fin avec le ``f``

Et de même pour les doubles

````java
double decimal = 0.63755555488787d;

````

Si on veut écrire un chiffre rond avec les ```float```et  ``double`` on doit tout de même écrire avec le point comme ceci 
````java 
float round = 2.0f;
double number = 2.0d;
````

On peut convertir les variables. Exemple : 
```java 
int i = 256;
float j = (float)i; // Le résultat sera 256.0f

```
De même que 
```java
float a = 25.90;
int b = (int)a; // Le résultat sera 26

float c = 25.30;
int d = (int)c; // Le résultat sera 25
```
On appelle cela "caster" une variable. 

#### Les variables *objets*

À l'inverse des variables primitives, les variabales objects sont des class héritées de la class Object.
Elles contiennent un constructeur, des méthodes et propriétés. 

| Raccourcis | Type |
|:-----------|:-----|
| String      | Peut contenir une chaîne de caractère |



## héritage 

### Différence entre une méthode surchargée et une méthode polymorphe.
Une méthode surchargée diffère de la méthode originale par le nombre ou le type des paramètres qu'elle prend en entrée.

Une méthode polymorphe a un squelette identique à la méthode de base, mais traite les choses différemment. Cette méthode se trouve dans une autre classe et donc, par extension, dans une autre instance de cette autre classe.








