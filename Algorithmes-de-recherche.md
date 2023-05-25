## **Algorithmes de recherche :**

Les algorithmes de recherche sont des techniques utilisées pour trouver un élément spécifique dans une collection de données. Voici quelques exemples d'algorithmes de recherche couramment utilisés :



1. Recherche séquentielle :
La recherche séquentielle est un algorithme simple où les éléments d'une liste sont parcourus séquentiellement jusqu'à ce que l'élément recherché soit trouvé ou que la fin de la liste soit atteinte. Voici un exemple de pseudo-code et de code JavaScript pour la recherche séquentielle :

Pseudo-code :
```
RechercheSequentielle(liste, valeur)
    pour chaque élément dans liste
        si élément == valeur alors
            retourner vrai
        fin si
    fin pour

    retourner faux
```

JavaScript :
```javascript
function rechercheSequentielle(liste, valeur) {
    for (let i = 0; i < liste.length; i++) {
        if (liste[i] === valeur) {
            return true;
        }
    }
    return false;
}

// Exemple d'utilisation
const liste = [1, 3, 5, 7, 9];
console.log(rechercheSequentielle(liste, 5)); // Sortie : true
console.log(rechercheSequentielle(liste, 2)); // Sortie : false
```

2. Recherche binaire :
La recherche binaire est un algorithme de recherche efficace qui suppose que la liste est triée par ordre croissant. Il divise la liste en deux à chaque itération, en comparant l'élément du milieu avec la valeur recherchée. Voici un exemple de pseudo-code et de code JavaScript pour la recherche binaire :

Pseudo-code :
```
RechercheBinaire(liste, valeur)
    début <- 0
    fin <- longueur(liste) - 1

    tant que début <= fin
        milieu <- (début + fin) div 2
        si liste[milieu] == valeur alors
            retourner vrai
        sinon si liste[milieu] < valeur alors
            début <- milieu + 1
        sinon
            fin <- milieu - 1
        fin si
    fin tant que

    retourner faux
```

JavaScript :
```javascript
function rechercheBinaire(liste, valeur) {
    let debut = 0;
    let fin = liste.length - 1;

    while (debut <= fin) {
        let milieu = Math.floor((debut + fin) / 2);
        if (liste[milieu] === valeur) {
            return true;
        } else if (liste[milieu] < valeur) {
            debut = milieu + 1;
        } else {
            fin = milieu - 1;
        }
    }

    return false;
}

// Exemple d'utilisation
const liste = [1, 3, 5, 7, 9];
console.log(rechercheBinaire(liste, 5)); // Sortie : true
console.log(rechercheBinaire(liste, 2)); // Sortie : false
```

3. Recherche de motifs (substring) :
La recherche de motifs consiste à rechercher un motif spécifique (sous-chaîne) à l'intérieur d'une chaîne de caractères. Cela peut être réalisé à l'aide d'algorithmes tels que l'algorithme de recherche de Knuth-Morris-Pratt (KMP) ou l'algorithme de Boyer-Moore. Voici un exemple de pseudo-code pour la recherche de motifs :

Pseudo-code (Algorithme de Boyer-Moore) :
```
RechercheMotif(texte, motif)
    n <- longueur(texte)
   

 m <- longueur(motif)
    i <- m - 1
    j <- m - 1

    tant que i < n
        si texte[i] == motif[j] alors
            si j == 0 alors
                retourner i
            fin si
            i <- i - 1
            j <- j - 1
        sinon
            i <- i + m - min(j, 1 + dernierIndexDu(texte[i], motif))
            j <- m - 1
        fin si
    fin tant que

    retourner -1
```

Ce pseudo-code représente l'algorithme de Boyer-Moore, qui est un algorithme efficace pour la recherche de motifs. Sa mise en œuvre complète nécessiterait plus de code, mais cela vous donne une idée générale de son fonctionnement. En JavaScript, vous pouvez utiliser des bibliothèques ou des fonctions intégrées telles que `indexOf` pour effectuer la recherche de motifs dans une chaîne.

