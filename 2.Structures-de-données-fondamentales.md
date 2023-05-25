## **Structures de données fondamentales :**

Une structure de données est une manière organisée de stocker, gérer et manipuler des données de manière efficace. Elle définit la manière dont les données sont organisées, accessibles et modifiées. Les structures de données permettent de résoudre des problèmes spécifiques de manière optimisée en fournissant des opérations et des algorithmes appropriés.

Une structure de données peut être vue comme un conteneur qui offre différentes opérations pour ajouter, supprimer, rechercher et manipuler les données qu'elle contient. Elle définit également les règles de gestion des données, telles que l'ordre dans lequel elles sont stockées, leur relation et leur accessibilité.

Les structures de données peuvent varier en fonction de la complexité et de l'organisation des données. Elles peuvent être linéaires, comme les tableaux et les listes, ou non linéaires, comme les arbres et les graphes. Chaque structure de données a ses propres caractéristiques, avantages et inconvénients, adaptés à des types de problèmes spécifiques.
Voici les définitions, le pseudo-code et les exemples en JavaScript pour chaque structure de données fondamentale :

1. Tableaux (arrays) :
   - Définition : Un tableau est une structure de données linéaire qui permet de stocker et d'accéder à plusieurs éléments de manière séquentielle en utilisant des indices.
   - Manipulation : Les opérations courantes sur les tableaux incluent l'accès à un élément par son indice, l'insertion d'un nouvel élément, la suppression d'un élément existant et la recherche d'un élément dans le tableau.
   - Exemple de pseudo-code :

     ```plaintext
     tableau <- [valeur1, valeur2, valeur3]  // Initialisation d'un tableau

     // Accès à un élément
     élément <- tableau[indice]

     // Insertion d'un élément
     tableau[indice] <- valeur

     // Suppression d'un élément
     supprimer élément à l'indice

     // Recherche d'un élément
     indice <- trouver indice de l'élément
     ```

   - Exemple en JavaScript :

     ```javascript
     let tableau = [1, 2, 3];  // Initialisation d'un tableau

     // Accès à un élément
     let element = tableau[indice];

     // Insertion d'un élément
     tableau[indice] = valeur;

     // Suppression d'un élément
     tableau.splice(indice, 1);

     // Recherche d'un élément
     let indice = tableau.indexOf(element);
     ```

2. Listes chaînées :
   - Définition : Une liste chaînée est une structure de données linéaire composée de nœuds, où chaque nœud contient une valeur et une référence (ou un lien) vers le nœud suivant.
   - Concepts de base : Les nœuds sont liés les uns aux autres pour former une séquence. La liste chaînée peut être simple (chaque nœud a une seule référence) ou double (chaque nœud a une référence vers le nœud précédent et suivant).
   - Opérations : Les opérations courantes sur les listes chaînées incluent l'insertion d'un nouvel élément, la suppression d'un élément existant, la recherche d'un élément et le parcours de la liste.
   - Avantages : Les listes chaînées permettent une insertion et une suppression efficaces, même au milieu de la liste, contrairement aux tableaux. Elles peuvent être utilisées pour implémenter d'autres structures de données complexes.
   - Inconvénients : L'accès direct à un élément nécessite de parcourir la liste à partir du début, ce qui peut être moins efficace que l'accès indexé dans un tableau.
   - Exemple de pseudo-code :

     ```plaintext
     ListeChainee
       Noeud
         valeur
         referenceVersSuivant

     // Insertion d'un nouvel élément
     inserer(valeur, position)
       nouveauNoeud <- Noeud(valeur)
       si position == debut
         nouveauNoeud.referenceVersSuivant <- debut
         debut <- nouveauNoeud
       sinon si position == fin
         dernierNoeud.referenceVersSuivant <- nouveauNoeud
         dernierNoeud <- nouveauNoeud
       sinon
         noeudPrecedent <- trouverNoeud(position - 1)


         nouveauNoeud.referenceVersSuivant <- noeudPrecedent.referenceVersSuivant
         noeudPrecedent.referenceVersSuivant <- nouveauNoeud
       fin si

     // Suppression d'un élément
     supprimer(position)
       si position == debut
         debut <- debut.referenceVersSuivant
       sinon si position == fin
         noeudPrecedent <- trouverNoeud(position - 1)
         noeudPrecedent.referenceVersSuivant <- null
         dernierNoeud <- noeudPrecedent
       sinon
         noeudPrecedent <- trouverNoeud(position - 1)
         noeudASupprimer <- noeudPrecedent.referenceVersSuivant
         noeudPrecedent.referenceVersSuivant <- noeudASupprimer.referenceVersSuivant
         noeudASupprimer.referenceVersSuivant <- null
       fin si

     // Recherche d'un élément
     trouver(valeur)
       noeudActuel <- debut
       tant que noeudActuel != null
         si noeudActuel.valeur == valeur alors
           retourner vrai
         fin si
         noeudActuel <- noeudActuel.referenceVersSuivant
       fin tant que
       retourner faux
     ```

   - Exemple en JavaScript :

     ```javascript
     class Noeud {
       constructor(valeur) {
         this.valeur = valeur;
         this.referenceVersSuivant = null;
       }
     }

     class ListeChainee {
       constructor() {
         this.debut = null;
         this.dernier = null;
       }

       // Insertion d'un nouvel élément
       inserer(valeur, position) {
         const nouveauNoeud = new Noeud(valeur);
         if (position === 0) {
           nouveauNoeud.referenceVersSuivant = this.debut;
           this.debut = nouveauNoeud;
           if (this.dernier === null) {
             this.dernier = nouveauNoeud;
           }
         } else if (position === this.longueur()) {
           this.dernier.referenceVersSuivant = nouveauNoeud;
           this.dernier = nouveauNoeud;
         } else {
           const noeudPrecedent = this.trouverNoeud(position - 1);
           nouveauNoeud.referenceVersSuivant = noeudPrecedent.referenceVersSuivant;
           noeudPrecedent.referenceVersSuivant = nouveauNoeud;
         }
       }

       // Suppression d'un élément
       supprimer(position) {
         if (position === 0) {
           this.debut = this.debut.referenceVersSuivant;
           if (this.debut === null) {
             this.dernier = null;
           }
         } else if (position === this.longueur() - 1) {
           const noeudPrecedent = this.trouverNoeud(position - 1);
           noeudPrecedent.referenceVersSuivant = null;
           this.dernier = noeudPrecedent;
         } else {
           const noeudPrecedent = this.trouverNoeud(position - 1);
           const noeudASupprimer = noeudPrecedent.referenceVersSuivant;
           noeudPrecedent.referenceVersSuivant = noeudASupprimer.referenceVersSuivant;
           noeudASupprimer.referenceVersSuivant = null;
         }
       }

       // Recherche d'un élément
       trouver(valeur) {
         let noeudActuel = this.debut;
         while (noeudActuel !== null) {
          

 if (noeudActuel.valeur === valeur) {
             return true;
           }
           noeudActuel = noeudActuel.referenceVersSuivant;
         }
         return false;
       }

       // Longueur de la liste
       longueur() {
         let compteur = 0;
         let noeudActuel = this.debut;
         while (noeudActuel !== null) {
           compteur++;
           noeudActuel = noeudActuel.referenceVersSuivant;
         }
         return compteur;
       }

       // Autres méthodes (parcours, etc.)
     }
     ```

3. Piles (stacks) :
   - Principes : Une pile est une structure de données linéaire de type LIFO (Last-In-First-Out), ce qui signifie que le dernier élément ajouté est le premier élément à être retiré.
   - Opérations : Les principales opérations sur les piles sont "push" pour ajouter un élément au sommet de la pile et "pop" pour retirer l'élément supérieur de la pile.
   - Applications : Les piles sont couramment utilisées dans les langages de programmation pour gérer l'appel de fonctions (pile d'appels), les opérations de désallocation de mémoire (pile d'exécution), la vérification des parenthèses équilibrées, etc.

   Exemple de pseudo-code :

     ```plaintext
     Pile
       elements
       taille

     // Opération Push (Ajouter un élément)
     push(element)
       elements[taille] <- element
       taille <- taille + 1

     // Opération Pop (Retirer l'élément supérieur)
     pop()
       si taille > 0
         taille <- taille - 1
         retourner elements[taille]
       fin si
     ```

   - Exemple en JavaScript :

     ```javascript
     class Pile {
       constructor() {
         this.elements = [];
         this.taille = 0;
       }

       // Opération Push (Ajouter un élément)
       push(element) {
         this.elements[this.taille] = element;
         this.taille++;
       }

       // Opération Pop (Retirer l'élément supérieur)
       pop() {
         if (this.taille > 0) {
           this.taille--;
           return this.elements[this.taille];
         }
       }
     }

     // Exemple d'utilisation
     const pile = new Pile();
     pile.push(1);
     pile.push(2);
     pile.push(3);
     console.log(pile.pop());  // Affiche 3
     ```

4. Files d'attente (queues) :
   - Principes : Une file d'attente est une structure de données linéaire de type FIFO (First-In-First-Out), ce qui signifie que le premier élément ajouté est le premier élément à être retiré.
   - Opérations : Les principales opérations sur les files d'attente sont "enqueue" pour ajouter un élément à la fin de la file et "dequeue" pour retirer l'élément en tête de file.
   - Applications : Les files d'attente sont couramment utilisées dans les systèmes de gestion des processus, la planification des tâches, la gestion des requêtes, etc.

   Exemple de pseudo-code :

     ```plaintext
     FileAttente
       elements
       taille
       debut

     // Opération Enqueue (Ajouter un élément à la fin)
     enqueue(element)


       elements[debut + taille] <- element
       taille <- taille + 1

     // Opération Dequeue (Retirer l'élément en tête)
     dequeue()
       si taille > 0
         debut <- debut + 1
         taille <- taille - 1
         retourner elements[debut - 1]
       fin si
     ```

   - Exemple en JavaScript :

     ```javascript
     class FileAttente {
       constructor() {
         this.elements = [];
         this.taille = 0;
         this.debut = 0;
       }

       // Opération Enqueue (Ajouter un élément à la fin)
       enqueue(element) {
         this.elements[this.debut + this.taille] = element;
         this.taille++;
       }

       // Opération Dequeue (Retirer l'élément en tête)
       dequeue() {
         if (this.taille > 0) {
           this.debut++;
           this.taille--;
           return this.elements[this.debut - 1];
         }
       }
     }

     // Exemple d'utilisation
     const file = new FileAttente();
     file.enqueue(1);
     file.enqueue(2);
     file.enqueue(3);
     console.log(file.dequeue());  // Affiche 1
     ```

Ces structures de données fondamentales sont largement utilisées en programmation et jouent un rôle crucial dans la résolution de problèmes complexes.