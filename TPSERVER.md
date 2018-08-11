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


Ici On ceer un server sur le port 1800. Le seul moyen de dire au serveur que les clients peuvent se connecter n'importe quand c'est en faisant en boucle infinie. Si non le script va s'éxécuter qu'une seul fois lors de la  premiere connexion d'un client et les autres clients n'auront plus acces au server.

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
Il faut la mettre en **golbal** donc en début de script. Ensuite dans la boucle while, on incrémente cet id à chaque fois que quelqu'un se connecte. 

````
while(true) {				
	Socket socket = ss.accept();			
	++idClient;				
}
````

vous devriez voir quelque chose comme ça :

````java 
public class Test {	
	int idClient;
	
	@Override
	public void run() {  // On redifinit la méthode
		try {
			ServerSocket ss = new ServerSocket(1800);
			while(true) {				
				Socket socket = ss.accept();			
				++idClient;			
			}			
		} catch (IOException e) {
			e.printStackTrace();
		} 		
	}
	
	public static void main(String[] args) {
		new ServerMT().start();
	}		
}
````

On va devoir créer une nouvelle class nommée "Converstaion" qui étendra également de thread. On peut soit la créer dans un autre fichier, soit faire en créer une dans la class Server. Et c'est ce que nous allons faire. ET puis que c'est une class étendu, on redifint à noiuveau la méthode run().

````java
class Conversation extends Thread { 
	@Override
		public void run() {
			// TODO Auto-generated method stub
			
		}
}
	
````
Ce qui devrait donner ceci
````java 

public class Serevr {

	int idClient;
	
	@Override
	public void run() {  // On redifinit la méthode
		try {
			ServerSocket ss = new ServerSocket(1800);
			while(true) {				
				Socket socket = ss.accept();			
				++idClient;				
			}
			
		} catch (IOException e) {
			e.printStackTrace();
		} 
		
	}
	
	class Conversation extends Thread { 		
		@Override
		public void run() {
			
		}		
	}
	
	public static void main(String[] args) {
		new ServerMT().start();
	}
	
		
}
````
Nous allons continuer à construire cette class. Pour poursuivre nous aurons besoin de 2 informations Le socket (donc le connecteur reseaux) et l'id du client. On va donc créer 2 variables


````java
class Conversation extends Thread {
	private Socket socket;
	private int idClient;
	
	@Override
	public void run() {

	}
}
````

Ensuite on va le récuperer les valeurs avec le constructeur

````java
public Conversation(Socket socket, int idClient) {
	this.socket = socket;
	this.idClient = idClient;
}
````
Ce qui devrait donner  

````java 
class Conversation extends Thread { 

	private Socket socket;
	private int idClient;

	public Conversation(Socket socket, int idClient) {
		this.socket = socket;
		this.idClient = idClient;
	}

	@Override
	public void run() {
		// TODO Auto-generated method stub

	}

}
````

## Ecoute le flux












Maintenant allons dans la boucle se trouvant dans la méthode run() de la class **Server** et on instancie notre nouvelle class

````java 

public void run() {  // On redifinit la méthode
	try {
		ServerSocket ss = new ServerSocket(1800);
		while(true) {				
			Socket socket = ss.accept();
			++idClient;
			new Conversation(socket, idClient).start();
		}

	} catch (IOException e) {
		e.printStackTrace();
	} 
	
````
		
































