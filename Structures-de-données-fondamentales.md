## **Structures de données fondamentales :**

Une structure de données est une manière organisée de stocker, gérer et manipuler des données de manière efficace. Elle définit la manière dont les données sont organisées, accessibles et modifiées. Les structures de données permettent de résoudre des problèmes spécifiques de manière optimisée en fournissant des opérations et des algorithmes appropriés.

Une structure de données peut être vue comme un conteneur qui offre différentes opérations pour ajouter, supprimer, rechercher et manipuler les données qu'elle contient. Elle définit également les règles de gestion des données, telles que l'ordre dans lequel elles sont stockées, leur relation et leur accessibilité.

Les structures de données peuvent varier en fonction de la complexité et de l'organisation des données. Elles peuvent être linéaires, comme les tableaux et les listes, ou non linéaires, comme les arbres et les graphes. Chaque structure de données a ses propres caractéristiques, avantages et inconvénients, adaptés à des types de problèmes spécifiques.

**-Tableaux (arrays) : manipulation, recherche, insertion, suppression.**

Les tableaux, également connus sous le nom d'arrays, sont des structures de données linéaires qui permettent de stocker une collection d'éléments de même type. Voici comment effectuer différentes opérations sur les tableaux :

1. Manipulation : La manipulation d'un tableau fait référence aux opérations permettant d'accéder aux éléments du tableau, de les modifier ou de les traiter d'une manière spécifique. Cela inclut l'accès à un élément par son index, la modification de la valeur d'un élément existant, l'ajout d'éléments supplémentaires ou la suppression d'éléments.

   <img src="Manipulation-Pseudo-code.png" alt="Manipulation-Pseudo-code">
   <img src="Manipulation - Javascript.png" alt="Manipulation-Javascript">


2. Recherche : La recherche dans un tableau consiste à trouver un élément spécifique à l'aide d'une valeur donnée. Cela peut être réalisé en parcourant le tableau et en comparant chaque élément avec la valeur recherchée. Si une correspondance est trouvée, l'indice de l'élément peut être retourné ou une indication peut être donnée sur sa présence dans le tableau.
<img src="Recherche-Pseudo-code.png" alt="Recherche-Pseudo-code">
<img src="Recherche-Javascript.png" alt="Recherche-Javascript">

3. Insertion : L'insertion dans un tableau se réfère à l'ajout d'un nouvel élément à une position spécifique du tableau. Cela peut être effectué en décalant les éléments existants vers la droite (pour faire de la place) et en insérant le nouvel élément à l'indice souhaité. L'insertion peut également se faire à la fin du tableau en ajoutant simplement l'élément à la dernière position.
<img src="Insertion-Pseudo-code.png" alt="Insertion-Pseudo-code">
<img src="Insertion-Javascript.png" alt="Insertion-Javascript">

4. Suppression : La suppression d'éléments dans un tableau consiste à enlever un élément spécifique du tableau. Cela peut être réalisé en décalant les éléments suivants vers la gauche (pour remplir l'espace vide) après la suppression de l'élément ciblé. La suppression peut être basée sur l'indice de l'élément ou sa valeur, selon le cas.



<img src="Suppression-Pseudo-code.png" alt="Suppression-Pseudo-code">
<img src="Suppression-Javascript.png" alt="Suppression-Javascript">

Ces opérations de manipulation, recherche, insertion et suppression sont fondamentales pour travailler avec des tableaux et permettent de gérer et de traiter les données stockées de manière efficace.

**-Listes chaînées : concepts de base, opérations, avantages et inconvénients.**

Les listes chaînées sont des structures de données linéaires qui permettent de stocker et d'organiser des éléments de manière dynamique. Voici les concepts de base, les opérations, ainsi que les avantages et les inconvénients des listes chaînées :

Concepts de base :
- Une liste chaînée est composée de nœuds, où chaque nœud contient une valeur et un pointeur (référence) vers le nœud suivant dans la liste.

- Le premier nœud de la liste est appelé "tête" (head), et le dernier nœud est généralement un nœud spécial appelé "sentinelle" ou "sentinelle de fin" (tail).
- Les nœuds d'une liste chaînée sont généralement créés dynamiquement, ce qui permet une allocation flexible de la mémoire en fonction des besoins.

Opérations courantes :
- Insertion : Permet d'ajouter un nouvel élément à la liste chaînée, que ce soit en tête, en fin ou à une position spécifique.

<img src="Insertion-dans-une-liste-chaînée-Pseudo-code.png" alt="Insertion-dans-une-liste-chaînée-Pseudo-code">
<img src="Insertion-dans-une-liste-chaînée-Javascript.png" alt="Insertion-dans-une-liste-chaînée-Javascript">

- Suppression : Permet de retirer un élément de la liste chaînée en mettant à jour les pointeurs appropriés.

<img src="Suppression-liste-chaînée-Pseudo-code.png" alt="Suppression-liste-chaînée-Pseudo-code">
<img src="Suppression-liste-chaînée-Javascript.png" alt="Suppression-liste-chaînée-Javascript">

- Recherche : Permet de trouver un élément spécifique dans la liste chaînée en parcourant les nœuds de manière séquentielle.

<img src="Recherche-liste-chaînée-Pseudo-code.png" alt="Recherche-liste-chaînée-Pseudo-code">
<img src="Recherche-liste-chaînée-Javascript.png" alt="Recherche-liste-chaînée-Javascript">

- Parcours : Permet de parcourir tous les éléments de la liste chaînée pour les afficher ou les traiter.

<img src="Parcours-liste-chaînée-Pseudo-code.png" alt="Parcours-liste-chaînée-Pseudo-code">
<img src="Parcours-liste-chaînée-Javascript.png" alt="Parcours-liste-chaînée-Javascript">

- Accès : Bien que les listes chaînées ne supportent pas un accès direct par indice comme les tableaux, il est possible d'accéder à un élément en suivant les pointeurs à partir de la tête de liste.

<img src="Accès-liste-chaînée-Pseudo-code.png" alt="Accès-liste-chaînée-Pseudo-code">
<img src="Accès-liste-chaînée-Javascript.png" alt="Accès-liste-chaînée-Javascript">

Avantages des listes chaînées :
- Allocation dynamique : Les nœuds des listes chaînées peuvent être alloués et libérés dynamiquement, permettant une gestion flexible de la mémoire.
- Insertion et suppression efficaces : Comparées aux tableaux, les listes chaînées peuvent insérer et supprimer des éléments plus efficacement, car elles n'impliquent pas le décalage d'autres éléments.
- Taille variable : Les listes chaînées peuvent être facilement étendues ou réduites en fonction des besoins, sans nécessiter une allocation continue de mémoire.

Inconvénients des listes chaînées :
- Accès séquentiel : Contrairement aux tableaux, l'accès aux éléments d'une liste chaînée nécessite un parcours séquentiel à partir de la tête, ce qui peut être moins efficace pour des opérations de recherche aléatoire.
- Utilisation de mémoire supplémentaire : Les listes chaînées nécessitent de la mémoire supplémentaire pour stocker les pointeurs de chaque nœud, ce qui peut augmenter l'utilisation de mémoire par rapport aux tableaux.

Les listes chaînées sont couramment utilisées lorsque la taille des données est inconnue à l'avance ou lorsqu'il est nécessaire d'effectuer des opérations d'insertion et de suppression fréquentes. Elles offrent une structure de données flexible et efficiente pour de nombreux problèmes informatiques.

**-Piles (stacks) : principes, opérations (push, pop), applications.**

**-Files d'attente (queues) : principes, opérations (enqueue, dequeue), applications.**