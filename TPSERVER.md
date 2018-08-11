# Création d'un mini-chat en java

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
Il faut qu'on fasse un héritage de la class Thread. En étendant cette class, nous allons devoir redifinir une méthode appellée run(){
}
````java
public class Server extends Thread {
	public static void main(String[] args) {	
	    // TODO Auto-generated method stub
	}
	
	@Override
	public void run() {  // On redifinit la méthode
				
	}
}
````

Dans la méthode ``main`` nous allons utilser notre première objet. On instacie la class server qui va appeller la méthode run ici plus haut.

````java
public static void main(String[] args) {  
	// Creation du socket
	new Server().start();	// 
}
````


A chaque fois que quelqu'un se connecte au serveur, il faut créer un nouveau thread. 
Ici On ceer un server sur le port 1800. Ici le seul moyen de dire au serveur que les clients peuvent se connecter n'importe quand c'est en faisant en boucle infinie. Si non le script va s'éxécuter qu'une seul fois lors de la  premiere connexion d'un client et les autres clients n'auront plus acces au server.

````java 
@Override
public void run() {  // On redifinit la méthode
	try {
		ServerSocket ss = new ServerSocket(1800);
		while(true) {				
			Socket socket = ss.accept();
		}

	} catch (IOException e) {
		e.printStackTrace();
	} 

}
````
En java, on est obligé de gérer les erreurs potentiels. Ici on va donc utiliser un try and catch.

Maintenant que nous avons une connexion au serveur nous allons faire des actions.
Tout d'abord nous allons créer une variable int pour donner des id's aux client
````java 
	int idClient;
````
Il faut la mettre en **golbal** donc en début de script. ensuite dans la boucle while, on incrémente cet id. 

````
while(true) {				
	Socket socket = ss.accept();			
	++idClient;				
}
````























