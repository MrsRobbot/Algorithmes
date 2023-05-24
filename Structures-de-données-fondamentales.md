## **Structures de données fondamentales :**

Une structure de données est une manière organisée de stocker, gérer et manipuler des données de manière efficace. Elle définit la manière dont les données sont organisées, accessibles et modifiées. Les structures de données permettent de résoudre des problèmes spécifiques de manière optimisée en fournissant des opérations et des algorithmes appropriés.

Une structure de données peut être vue comme un conteneur qui offre différentes opérations pour ajouter, supprimer, rechercher et manipuler les données qu'elle contient. Elle définit également les règles de gestion des données, telles que l'ordre dans lequel elles sont stockées, leur relation et leur accessibilité.

Les structures de données peuvent varier en fonction de la complexité et de l'organisation des données. Elles peuvent être linéaires, comme les tableaux et les listes, ou non linéaires, comme les arbres et les graphes. Chaque structure de données a ses propres caractéristiques, avantages et inconvénients, adaptés à des types de problèmes spécifiques.

**-Tableaux (arrays) : manipulation, recherche, insertion, suppression.**

Les tableaux, également connus sous le nom d'arrays, sont des structures de données linéaires qui permettent de stocker une collection d'éléments de même type. Voici comment effectuer différentes opérations sur les tableaux :

1. Manipulation :
   - Accès à un élément : Vous pouvez accéder à un élément spécifique dans un tableau en utilisant son index. Par exemple, `tableau[2]` retournera l'élément à l'indice 2 du tableau.
   - Modification d'un élément : Vous pouvez modifier la valeur d'un élément en lui assignant une nouvelle valeur. Par exemple, `tableau[1] = 10` modifiera la valeur de l'élément à l'indice 1 pour être égale à 10.

2. Recherche :
   - Recherche séquentielle : Pour rechercher un élément spécifique dans un tableau, vous pouvez parcourir les éléments un par un jusqu'à ce que vous trouviez une correspondance. Cela implique de comparer chaque élément avec la valeur recherchée.
   - Recherche binaire (uniquement pour les tableaux triés) : Si le tableau est trié, vous pouvez utiliser la recherche binaire, qui divise le tableau en deux à chaque itération pour rechercher plus efficacement l'élément cible. Cette méthode est plus rapide que la recherche séquentielle pour les tableaux de grande taille.

3. Insertion :
   - Ajout en fin de tableau : Vous pouvez ajouter un nouvel élément à la fin du tableau en utilisant l'indice suivant la dernière position occupée. Par exemple, `tableau[longueur] = nouvelElement` ajoute `nouvelElement` à la fin du tableau.
   - Insertion à une position donnée : Si vous souhaitez insérer un élément à une position spécifique, vous devrez décaler les éléments existants vers la droite pour faire de la place, puis assigner la nouvelle valeur à l'indice souhaité.

4. Suppression :
   - Suppression par indice : Pour supprimer un élément à un indice donné, vous devrez décaler les éléments suivants vers la gauche pour combler l'espace vacant.
   - Suppression par valeur : Si vous souhaitez supprimer une occurrence spécifique d'une valeur dans le tableau, vous devrez rechercher l'indice de cette valeur, puis supprimer l'élément à cet indice en décalant les éléments suivants vers la gauche.

Il est important de noter que les opérations d'insertion et de suppression peuvent entraîner des décalages importants dans le tableau, ce qui peut être coûteux en termes de performances pour les tableaux de grande taille.

**-Listes chaînées : concepts de base, opérations, avantages et inconvénients.**

**-Piles (stacks) : principes, opérations (push, pop), applications.**

**-Files d'attente (queues) : principes, opérations (enqueue, dequeue), applications.**