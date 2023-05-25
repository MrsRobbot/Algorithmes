## **Algorithmes de graphes:**

Les algorithmes de graphes sont des techniques et des procédures utilisées pour résoudre des problèmes liés aux graphes, qui sont des structures de données constituées de sommets (ou nœuds) reliés par des arêtes. Les graphes peuvent être utilisés pour représenter diverses situations, telles que les réseaux sociaux, les itinéraires, les relations entre objets, etc. Les algorithmes de graphes permettent d'effectuer des opérations telles que la recherche, le parcours, la recherche de chemins, la recherche d'arbres couvrants, la détection de cycles, etc.

Voici quelques algorithmes de graphes couramment utilisés :

Représentation des graphes :
- Définition : La représentation des graphes fait référence à la façon dont les sommets et les arêtes d'un graphe sont stockés en mémoire.
- Pseudo-code : Il n'y a pas de pseudo-code spécifique pour la représentation des graphes car cela dépend de la méthode choisie (matrice d'adjacence, liste d'adjacence, etc.).
- Exemple JavaScript :

```javascript
// Représentation des graphes en utilisant une liste d'adjacence

class Graphe {
  constructor() {
    this.listeAdjacence = new Map();
  }

  ajouterSommet(sommet) {
    this.listeAdjacence.set(sommet, []);
  }

  ajouterArete(sommetSource, sommetDestination) {
    this.listeAdjacence.get(sommetSource).push(sommetDestination);
    this.listeAdjacence.get(sommetDestination).push(sommetSource);
  }

  obtenirVoisins(sommet) {
    return this.listeAdjacence.get(sommet);
  }
}

// Exemple d'utilisation
const graphe = new Graphe();

graphe.ajouterSommet('A');
graphe.ajouterSommet('B');
graphe.ajouterSommet('C');
graphe.ajouterSommet('D');

graphe.ajouterArete('A', 'B');
graphe.ajouterArete('B', 'C');
graphe.ajouterArete('C', 'D');

console.log(graphe.obtenirVoisins('B')); // Sortie : ['A', 'C']
```

Parcours en profondeur (DFS) :
- Définition : Le parcours en profondeur est un algorithme de recherche qui explore les sommets d'un graphe en suivant les arêtes aussi loin que possible avant de revenir en arrière.
- Pseudo-code :

```plaintext
DFS(graphe, sommet):
    marquer sommet comme visité
    pour chaque voisin dans graphe.obtenirVoisins(sommet) :
        si voisin n'est pas visité :
            DFS(graphe, voisin)
```

- Exemple JavaScript :

```javascript
function DFS(graphe, sommet, visite) {
  visite.add(sommet);
  console.log(sommet);

  const voisins = graphe.obtenirVoisins(sommet);
  for (const voisin of voisins) {
    if (!visite.has(voisin)) {
      DFS(graphe, voisin, visite);
    }
  }
}

// Exemple d'utilisation avec le graphe précédent
const visite = new Set();
DFS(graphe, 'A', visite);
```

Parcours en largeur (BFS) :
- Définition : Le parcours en largeur est un algorithme de recherche qui explore les sommets d'un graphe en commençant par un sommet source, puis en visitant tous les voisins avant de passer aux voisins des voisins.
- Pseudo-code :

```plaintext
BFS(graphe, sommet):
    créer une file d'attente Q
    marquer sommet comme visité
    ajouter sommet à Q

   

 tant que Q n'est pas vide :
        extraire le premier élément de Q dans sommetActuel
        pour chaque voisin dans graphe.obtenirVoisins(sommetActuel) :
            si voisin n'est pas visité :
                marquer voisin comme visité
                ajouter voisin à Q
```

- Exemple JavaScript :

```javascript
function BFS(graphe, sommet) {
  const visite = new Set();
  const file = [sommet];
  visite.add(sommet);

  while (file.length > 0) {
    const sommetActuel = file.shift();
    console.log(sommetActuel);

    const voisins = graphe.obtenirVoisins(sommetActuel);
    for (const voisin of voisins) {
      if (!visite.has(voisin)) {
        visite.add(voisin);
        file.push(voisin);
      }
    }
  }
}

// Exemple d'utilisation avec le graphe précédent
BFS(graphe, 'A');
```

Plus courts chemins (Dijkstra, Bellman-Ford) :
- Définition : Dijkstra et Bellman-Ford sont des algorithmes utilisés pour trouver les plus courts chemins entre un sommet source et tous les autres sommets d'un graphe pondéré.
- Pseudo-code et exemples en JavaScript pour les algorithmes de plus courts chemins peuvent être un peu plus complexes. Si vous souhaitez obtenir ces informations, veuillez le spécifier.

Arbres couvrants de poids minimum (Kruskal, Prim) :
- Définition : Kruskal et Prim sont des algorithmes utilisés pour trouver un arbre couvrant de poids minimum dans un graphe pondéré.
- Pseudo-code et exemples en JavaScript pour les algorithmes d'arbres couvrants de poids minimum peuvent être un peu plus complexes. Si vous souhaitez obtenir ces informations, veuillez le spécifier.

