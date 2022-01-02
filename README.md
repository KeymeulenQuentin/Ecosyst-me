# Ecosysteme
Simulation d'un écosystème

Diagramme de classe:
![image](https://user-images.githubusercontent.com/78801832/147873853-c4f48b21-d534-4d72-b3f3-61e78115381b.png)

Digramme de séquence:
![image](https://user-images.githubusercontent.com/78801832/147873920-0034b917-a857-45b3-9721-bb154034000f.png)

Explication des principes SOLID utilisés:

  1) S : Single Responsibility Principle (SRP)
  
Ce principe consiste à attribuer une seule et unique responsabilité à chaque classe. 
En effet, dans notre projet, nous avons veillé à ce que chaque classe s'occupe d'une entité différente afin d'éviter que le code ne soit embrouillant. Notamment, la classe Carnivore gère uniquement les fonctions de cet espèce telles que sa reproduction, son déplacement, la gestion de son énergie et sa sant, etc.
Ainsi, nous nous retrouvons avec un code beaucoup plus clair que si l'on avait mis les classes de toutes les entités dans un même fichier(ledit fichier serait très lourd avec un code énorme). 
De plus, chaque fichier possède un rôle intrinsèque.
Enfin, le code est facile de maintenance.
    
  2) L : Liskov Substitution Principle (LSP)
  
Ce principe est respecté, lorsque nous avons une classe mère reliée à une classe enfant (autrement dit une relations d’héritage) et que nous pouvons remplacer l’instance de la classe mère par une instance de la classe enfant, sans impacter le comportement de l’instance de classe mère. 

En effet, nous avons bien respecté ce principe du fait que nous avons créé une classe mère Animal ayant des méthodes telles que Nivenergy() et Movement() et deux classes enfants qui héritent de ces méthodes. Nous pouvons modifier les objets de la classe enfant sans pour autant affecter ceux de la classe mère.

   3) D : Dependency Inversion Principle (DIP)
   
Ce  principe consiste à ce que la classe de haut niveau ne dépende pas de la classe de bas niveau. De plus, ces deux classes doivent dépendre des abstractions. Les abstractions étant des classes dont on ne peut pas créer des instances contrairement aux classes concrètes.

Effectivement, dans notre code nous avons eu recours à une classe de haut niveau Animal, par exemple, qui ne dépend point de la classe de bas niveau Carnivore. Or, ces deux classes (haut et bas niveau) dépendent d'une classe abstraite Specie dont on ne crée pas d'objet.

