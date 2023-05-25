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

    pour i de 0 à n - m
        j <- 0
        tant que j < m et texte[i + j] == motif[j]
            j <- j + 1
        fin tant que
        si j == m alors
            retourner i
        fin si
    fin pour

    retourner -1

```
```
function rechercheMotif(texte, motif) {
    const n = texte.length;
    const m = motif.length;

    for (let i = 0; i <= n - m; i++) {
        let j = 0;
        while (j < m && texte[i + j] === motif[j]) {
            j++;
        }
        if (j === m) {
            return i;
        }
    }

    return -1;
}

// Exemple d'utilisation
const texte = "Bonjour, comment ça va ?";
const motif = "comment";
console.log(rechercheMotif(texte, motif)); // Sortie : 9
console.log(rechercheMotif(texte, "salut")); // Sortie : -1
```

Ces exemples représentent les algorithmes de recherche séquentielle, binaire et de motifs (substring) en pseudo-code et en JavaScript. Vous pouvez les utiliser comme point de départ et les adapter en fonction de vos besoins spécifiques.

