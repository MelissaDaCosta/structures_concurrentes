 Lab2
 =====================================================================
 1. 
 Le problème de publication c'est quand une thread peut voir un objet
 avec des champs non initialisé
 car la premier thread a été deschedulé avant
  
2.
IL peut y avoir une thread qui crée objet Foo
et une autre qui voit objet Foo non initialisé

3.
Il y a un problème de publication 
Le corriger en mettant les 2 champs à final :
garantie que le champ sera bien initialié avant la sortie du constructeur


4.
Pas de problème de publication car une écritures volatile garantit que toutes
les écritures avant ont été faites.
Donc toutes les écritures faites avant la sortie du constructeur.
Un champ volatile coute plus cher qu'un champ final

5.
Problème de publication
car on publie this dans un constructeur
et il y a un thread démarré dans le constructeur

Pour le corriger :
On met le thread dans une autre méthode et ne pas l'appeler dans le constructeur.

6.
Ne pas démarrer un thread dans un constructeur.
Sinon pas de problème de publication car les variables affichées sont données en paramètres.
Ce ne sont pas les champs de la classe.