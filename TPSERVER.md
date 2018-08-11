# Création d'un mini-serveur en java

Alors la première chose, il créer un Projet ``` File -> New -> Java Project  ```. Nommez le "Server"

Ensuite il faut créer une class nommée "Server"  ``` File -> New -> Class ```  
Cochez la case ``` public static void main(String[] args) ```  

Vous devriez avoir ceci 

````java
public class Server {
	public static void main(String[] args) {	
	    // TODO Auto-generated method stub
	}
}
````

## Création du serveur 
La méthode main est automatiquement appelée quand l'application (ici le server) est lancée.  
````
public static void main(String[] args)
````
C'est donc là que tout va se passer. C'est le point central de notre application. 
C'est dans cette méthode que nous allons utilser notre première objet. 

````java
public static void main(String[] args) {  
	// Creation du socket
	ServerSocket serversocket = new ServerSocket(4900);		
}
````

Mais là on voit que l'ide souligne la ligne qu'on vient d'ajouter. C'est à cause que la méthode renvoie une erreur si jamais quelque chose se passait mal, et qu'en java, on est obligé de gérer les erreurs potentiels. Ici on va donc utiliser un try and catch.
Vous pouvez soit l"écrire soit simplement pointer la souris sur la phrase et cliquez sur "Surrond with try/catch" 

Vous devriez avoir ceci : 

````java 
public static void main(String[] args) {
	// TODO Auto-generated method stub
	try {
		ServerSocket serversocket = new ServerSocket(4900);
	} catch (IOException e) {
		// TODO Auto-generated catch block
		e.printStackTrace();
	}		
} 
````

La méthode ```System.out.println(String string);``` est une méthode de java qui permet d'afficher du texte dans la console. On va donc l'utiliser pour savoir on en est.

````java 
public static void main(String[] args) {
	// TODO Auto-generated method stub
	try {
		ServerSocket serversocket = new ServerSocket(4900);
		// On ajoute un message 
		System.out.println("J'attends la connexion d'un client");		
		
	} catch (IOException e) {
		// TODO Auto-generated catch block
		e.printStackTrace();
	}		
}
````













