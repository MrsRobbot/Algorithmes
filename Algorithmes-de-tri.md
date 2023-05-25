## **Algorithme de tri  :**

Un algorithme de tri est un ensemble d'instructions qui permet de réorganiser les éléments d'une liste dans un certain ordre. L'objectif est de placer les éléments dans un ordre croissant ou décroissant, facilitant ainsi les opérations de recherche, d'accès ou de manipulation ultérieures.

Il existe plusieurs algorithmes de tri, chacun ayant ses propres caractéristiques, performances et conditions d'utilisation. Voici quelques-uns des algorithmes de tri couramment utilisés :



1. Tri par sélection :
Le tri par sélection est un algorithme de tri qui parcourt la liste à plusieurs reprises, à chaque itération en sélectionnant l'élément le plus petit et en le plaçant à sa position correcte. Il continue jusqu'à ce que toute la liste soit triée.

Pseudo-code :
```
TriParSelection(liste)
    pour i de 0 à longueur(liste) - 1
        indexMin <- i
        pour j de i+1 à longueur(liste) - 1
            si liste[j] < liste[indexMin] alors
                indexMin <- j
            fin si
        fin pour
        échanger(liste[i], liste[indexMin])
    fin pour
```

JavaScript :
```javascript
function triParSelection(liste) {
    const n = liste.length;
    for (let i = 0; i < n - 1; i++) {
        let indexMin = i;
        for (let j = i + 1; j < n; j++) {
            if (liste[j] < liste[indexMin]) {
                indexMin = j;
            }
        }
        [liste[i], liste[indexMin]] = [liste[indexMin], liste[i]];
    }
}

// Exemple d'utilisation
const liste = [5, 3, 8, 1, 2];
triParSelection(liste);
console.log(liste); // Sortie : [1, 2, 3, 5, 8]
```

2. Tri par insertion :
Le tri par insertion est un algorithme de tri qui construit une liste triée en insérant chaque élément à sa place correcte dans la partie déjà triée de la liste.

Pseudo-code :
```
TriParInsertion(liste)
    pour i de 1 à longueur(liste) - 1
        valeurCourante <- liste[i]
        j <- i - 1
        tant que j >= 0 et liste[j] > valeurCourante
            liste[j + 1] <- liste[j]
            j <- j - 1
        fin tant que
        liste[j + 1] <- valeurCourante
    fin pour
```

JavaScript :
```javascript
function triParInsertion(liste) {
    const n = liste.length;
    for (let i = 1; i < n; i++) {
        let valeurCourante = liste[i];
        let j = i - 1;
        while (j >= 0 && liste[j] > valeurCourante) {
            liste[j + 1] = liste[j];
            j--;
        }
        liste[j + 1] = valeurCourante;
    }
}

// Exemple d'utilisation
const liste = [5, 3, 8, 1, 2];
triParInsertion(liste);
console.log(liste); // Sortie : [1, 2, 3, 5, 8]
```

3. Tri à bulles :
Le tri à bulles est un algorithme de tri qui compare les éléments adjacents et les échange s'ils sont dans le mauvais ordre. Il répète ce processus jusqu'à ce que toute la liste soit triée.

Pseudo-code :
```
TriABulles(liste)
    n <- longueur(liste)
    pour i de 0 à n - 1
        pour j de 0 à n - i - 1
           

 si liste[j] > liste[j+1] alors
                échanger(liste[j], liste[j+1])
            fin si
        fin pour
    fin pour
```

JavaScript :
```javascript
function triABulles(liste) {
    const n = liste.length;
    for (let i = 0; i < n - 1; i++) {
        for (let j = 0; j < n - i - 1; j++) {
            if (liste[j] > liste[j + 1]) {
                [liste[j], liste[j + 1]] = [liste[j + 1], liste[j]];
            }
        }
    }
}

// Exemple d'utilisation
const liste = [5, 3, 8, 1, 2];
triABulles(liste);
console.log(liste); // Sortie : [1, 2, 3, 5, 8]
```

4. Tri fusion :
Le tri fusion est un algorithme de tri récursif qui divise la liste en deux parties, trie récursivement chaque partie, puis fusionne les parties triées pour obtenir la liste triée finale.

Pseudo-code :
```
TriFusion(liste)
    si longueur(liste) <= 1 alors
        retourner liste
    fin si

    milieu <- longueur(liste) div 2
    gauche <- TriFusion(liste de 0 à milieu - 1)
    droite <- TriFusion(liste de milieu à longueur(liste) - 1)

    retourner Fusionner(gauche, droite)
```

JavaScript :
```javascript
function triFusion(liste) {
    if (liste.length <= 1) {
        return liste;
    }

    const milieu = Math.floor(liste.length / 2);
    const gauche = triFusion(liste.slice(0, milieu));
    const droite = triFusion(liste.slice(milieu));

    return fusionner(gauche, droite);
}

function fusionner(gauche, droite) {
    const resultat = [];
    let i = 0;
    let j = 0;

    while (i < gauche.length && j < droite.length) {
        if (gauche[i] < droite[j]) {
            resultat.push(gauche[i]);
            i++;
        } else {
            resultat.push(droite[j]);
            j++;
        }
    }

    return resultat.concat(gauche.slice(i)).concat(droite.slice(j));
}

// Exemple d'utilisation
const liste = [5, 3, 8, 1, 2];
const listeTriee = triFusion(liste);
console.log(listeTriee); // Sortie : [1, 2, 3, 5, 8]
```

5. Tri rapide :
Le tri rapide est un algorithme de tri récursif basé sur la technique de partitionnement. Il choisit un élément pivot, partitionne la liste en deux parties autour du pivot, puis trie récursivement les deux parties.

Pseudo-code :
```
TriRapide(liste, debut, fin)
    si debut < fin alors
        pivot <- Partitionner(liste, debut, fin)
        TriRapide(liste, debut, pivot - 1)
        TriRapide(liste, pivot + 1, fin)
    fin si

Partitionner(liste, debut, fin)
    pivot <- liste[fin]
    i <- debut - 1

    pour j de debut à fin - 1
        si liste[j]

 < pivot alors
            i <- i + 1
            échanger(liste[i], liste[j])
        fin si
    fin pour

    échanger(liste[i + 1], liste[fin])
    retourner i + 1
```

JavaScript :
```javascript
function triRapide(liste, debut, fin) {
    if (debut < fin) {
        const pivot = partitionner(liste, debut, fin);
        triRapide(liste, debut, pivot - 1);
        triRapide(liste, pivot + 1, fin);
    }
}

function partitionner(liste, debut, fin) {
    const pivot = liste[fin];
    let i = debut - 1;

    for (let j = debut; j <= fin - 1; j++) {
        if (liste[j] < pivot) {
            i++;
            [liste[i], liste[j]] = [liste[j], liste[i]];
        }
    }

    [liste[i + 1], liste[fin]] = [liste[fin], liste[i + 1]];
    return i + 1;
}

// Exemple d'utilisation
const liste = [5, 3, 8, 1, 2];
triRapide(liste, 0, liste.length - 1);
console.log(liste); // Sortie : [1, 2, 3, 5, 8]
```

Ces exemples illustrent les algorithmes de tri couramment utilisés. N'hésitez pas à les adapter ou à explorer d'autres algorithmes de tri en fonction de vos besoins spécifiques.