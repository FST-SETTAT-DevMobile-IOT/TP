# Série 1 — Synchrone, asynchrone et fonctions comme valeurs

**Nom :** …………………  **Prénom :** …………………  **Groupe :** ………  **Date :** ………

> Mode d'emploi : répondez sous chaque question, à la place des points de suspension (`…`). Les blocs `dart` sont pour votre code, les blocs sans langage pour la sortie observée dans le terminal.

## Partie A — TD

### TD 1 — Vocabulaire
**a)** Classez en *synchrone* / *asynchrone* :
1. Attendre au guichet jusqu'à son tour : …
2. Lancer une machine à laver et ranger la cuisine : …
3. Appeler un ami et attendre qu'il décroche sans rien faire d'autre : …
4. Commander un plat et s'asseoir pendant la préparation : …
5. Calculer `3 * 4` dans un programme : …

**b)** Rapide ou lent ? Trier 10 nombres : … | Télécharger une image : … | Lire un capteur Bluetooth : … | Comparer deux entiers : …

**c)** Images perdues pendant 200 ms à 60 images/s (détaillez le calcul) :

…

**d)** Différence entre concurrence et parallélisme :

…

### TD 2 — Pourquoi bloquer est un problème
Pourquoi `sleep(Duration(seconds: 2))` fige-t-il l'écran ? Quel adjectif décrit une opération qui ne fige pas le programme ?

…

### TD 3 — Types de fonctions
a) `(int a, int b) => a + b` : …
b) `(String s) => s.length` : …
c) `() => print('ok')` : …
d) `(double x) => x > 0` : …
e) `(List<int> l) => l.first` : …

### TD 4 — Prédire la sortie
Sortie du programme (une valeur par ligne) :
```
…
```
Différence entre `f` et `f(4)` :

…

### TD 5 — Paramètres nommés
**a)** Appels valides ? (oui/non + justification si refus)
1. `inscrire('Sara', filiere: 'MIP');` : …
2. `inscrire('Sara');` : …
3. `inscrire('Sara', 20, filiere: 'MIP');` : …
4. `inscrire('Lina', filiere: 'GI', age: 20);` : …
5. `inscrire(nom: 'Omar', filiere: 'GI');` : …

**b)** Valeur de `age` dans l'appel 1 : …

**c)** Réécriture de `estPair` en syntaxe flèche :
```dart
…
```
Pourquoi la flèche est-elle impossible avec deux instructions ?

…

## Partie B — TP

### TP 1 — Mesurer le blocage
**1. Code (3 messages, `sleep`, `Stopwatch`) :**
```dart
…
```
Sortie observée :
```
…
```
**2. Sortie observée du programme avec `Future.delayed` :**
```
…
```
**3. Pourquoi `C` apparaît-il après `B` ?**

…

### TP 2 — Boîte à outils de fonctions
```dart
// 1. triple


// 2. repeter


// 3. transformer


// 4. seuil (bonus)


// main
```
Sortie observée :
```
…
```

### TP 3 — Mini-calculatrice
```dart
// 1-2. tester + quatre appels


// 3. choisir


// 4. afficherFiche + trois appels
```
Sortie observée :
```
…
```

## Remarques / difficultés rencontrées
…
