# Série TD/TP n°1 — Future et async/await

**Chapitre :** Programmation asynchrone, exceptions et API REST — cours Dart & Flutter  
**Enseignant :** Pr. Abdelfattah Abassi — Département Physique Appliquée, LAVETE, FST Settat, Université Hassan I  
**Durée :** 2 h — **Barème :** 20 points

## Identification de l'étudiant

| Champ | À remplir |
|---|---|
| Nom | |
| Prénom | |
| N° d'apprenant / CNE | |
| Groupe | |
| Date | |

## Consignes de remplissage

1. Lisez l'énoncé complet dans le PDF de la série (`serie1_future_async_await.pdf`). Les énoncés sont rappelés ici en abrégé.
2. Répondez **uniquement** aux emplacements prévus : zones `> **Réponse :**`, blocs ```` ```dart ```` (code) et ```` ```text ```` (sortie console), cases des tableaux.
3. Ne modifiez pas les titres ni les énoncés. N'ajoutez pas de captures d'écran : collez le texte.
4. **Testez votre code** avant de le coller. Collez la sortie réelle, pas celle que vous imaginez.
5. Pour la partie TD, répondez **d'abord sans ordinateur**, puis vérifiez dans la partie TP.
6. Rendu : `git add`, `git commit`, `git push` de ce fichier sur le dépôt GitHub indiqué par l'enseignant.

---

## Préparation (10 min)

### Préparation — Environnement de travail

Vous pouvez aussi utiliser DartPad (`dartpad.dev`) pour les exercices sans package externe. Créez un fichier par exercice (par exemple `bin/ex6.dart`) et lancez-le avec `dart run bin/ex6.dart`.

**a)** Ouvrez un terminal et exécutez `dart --version`. Recopiez la version affichée.

**Sortie observée :**

```text

```

**b)** Créez le projet avec `dart create -t console tp1`, placez-vous dans le dossier, puis lancez `dart run`. Que s'affiche-t-il ?

**Sortie observée :**

```text

```

---

## Partie A -- TD : prédire et raisonner (40 min)

**Sans ordinateur.** Répondez d'abord de tête, puis vérifiez dans la partie TP.

### Exercice 1 — Vrai ou faux ? — 1,5 pts

**a)** Indiquez Vrai ou Faux et justifiez en une phrase.

| Affirmation | Vrai / Faux | Justification |
|---|---|---|
| Dart exécute le code Dart sur plusieurs fils en parallèle. | | |
| Un `Future<int>` représente un entier qui sera disponible plus tard. | | |
| Une fonction marquée `async` renvoie toujours un `Future`. | | |
| `await` peut être utilisé dans n'importe quelle fonction. | | |
| Un `Future` peut changer d'état plusieurs fois. | | |
| `await` bloque toute l'application pendant l'attente. | | |
| Asynchrone et parallèle désignent la même chose. | | |

---

### Exercice 2 — Ordre d'affichage avec `Future.delayed` — 1,5 pts

```dart
void main() {
  print('1');
  Future.delayed(Duration(seconds: 2), () => print('2'));
  Future.delayed(Duration.zero, () => print('3'));
  print('4');
}
```

**a)** Quel est l'ordre exact d'affichage ?

> **Réponse :** 

**b)** Pourquoi `3` s'affiche-t-il après `4` alors que le délai est nul ?

> **Réponse :** 

---

### Exercice 3 — Que fait `await` exactement ? — 2 pts

```dart
Future<int> calculer() async {
  print('calcul : début');
  await Future.delayed(Duration(seconds: 1));
  print('calcul : fin');
  return 5;
}

void main() async {
  print('a');
  var attente = calculer();
  print('b');
  var x = await attente;
  print('c : $x');
}
```

**a)** Donnez l'ordre exact d'affichage.

> **Réponse :** 

**b)** Pourquoi `calcul : début` s'affiche-t-il avant `b` ?

> **Réponse :** 

**c)** Quel est le type de la variable `attente` ? Et celui de `x` ?

> **Réponse :** 

---

### Exercice 4 — Trouver les erreurs — 2 pts

**Extrait A**

```dart
void main() {
  var nom = await chargerNom();
  print(nom);
}
```

**Extrait B** (on suppose `chargerNom()` définie comme dans le cours : elle renvoie `Future<String>`)

```dart
void main() async {
  var nom = chargerNom();
  print('Bonjour ${nom.toUpperCase()}');
}
```

**Extrait C**

```dart
int doubler(int x) async {
  await Future.delayed(Duration(seconds: 1));
  return x * 2;
}
```

**a)** Pour chaque extrait, expliquez l'erreur.

- Extrait A

  > **Réponse :** 

- Extrait B

  > **Réponse :** 

- Extrait C

  > **Réponse :** 

**b)** Écrivez la version corrigée de chaque extrait.

**Votre code :**

```dart
// Écrivez votre code ici
```

---

### Exercice 5 — Séquentiel ou simultané ? — 1 pt

On dispose de trois tâches indépendantes : A dure 3 s, B dure 2 s, C dure 1 s.

**a)** Quel est le temps total si on écrit `await A; await B; await C;` ?

> **Réponse :** 

**b)** Quel est le temps total avec `await Future.wait([A, B, C]);` ? Justifiez.

> **Réponse :** 

**c)** Si C a besoin du résultat de A, peut-on encore tout mettre dans `Future.wait` ? Pourquoi ?

> **Réponse :** 

---

## Partie B -- TP : programmer et vérifier (70 min)

### Exercice 6 — Vérifier vos prédictions — 1,5 pts

**a)** Exécutez les programmes des exercices 2 et 3. Collez le code puis la sortie observée pour l'exercice 3.

**Votre code :**

```dart
// Écrivez votre code ici
```

**Sortie observée :**

```text

```

**b)** Votre prédiction de l'exercice 3 était-elle correcte ? Si non, qu'avez-vous mal compris ?

> **Réponse :** 

---

### Exercice 7 — Doubler un nombre : `await` puis `then` — 2 pts

**a)** Écrivez `Future<int> doubler(int x)` qui attend 1 seconde puis renvoie `x * 2`. Dans `main` (marqué `async`), affichez `doubler(21)` avec `await`.

**Votre code :**

```dart
// Écrivez votre code ici
```

**Sortie observée :**

```text

```

**b)** Réécrivez l'appel avec `then` à la place de `await`, et ajoutez un `print('Je continue')` juste après l'appel. Que constatez-vous sur l'ordre d'affichage ?

**Votre code :**

```dart
// Écrivez votre code ici
```

**Sortie observée :**

```text

```

---

### Exercice 8 — Mesurer le gain de `Future.wait` — 2,5 pts

```dart
Future<int> tache(String nom, int s) async {
  await Future.delayed(Duration(seconds: s));
  print('$nom terminée');
  return s;
}
```

**a)** Avec un `Stopwatch`, mesurez le temps total des tâches de 1 s, 2 s et 3 s lancées l'une après l'autre avec `await`.

**Votre code :**

```dart
// Écrivez votre code ici
```

**Sortie observée :**

```text

```

**b)** Mesurez le temps total avec `Future.wait`. Récupérez aussi la liste des résultats et calculez leur somme.

**Votre code :**

```dart
// Écrivez votre code ici
```

**Sortie observée :**

```text

```

**c)** Complétez le tableau (temps en secondes, arrondis).

| Version | Temps prévu (TD) | Temps mesuré |
|---|---|---|
| Séquentielle | | |
| Future.wait | | |

---

### Exercice 9 — Un capteur simulé — 2 pts

**a)** Écrivez `Future<String> lireCapteur()` qui renvoie `'23.5'` après 1 seconde.

**Votre code :**

```dart
// Écrivez votre code ici
```

**b)** Dans `main`, convertissez le résultat en `double` avec `double.parse`, puis affichez `Alerte : trop chaud` si la température dépasse 25, sinon `Température normale`. Testez avec une valeur renvoyée de `'27.1'`.

**Votre code :**

```dart
// Écrivez votre code ici
```

**Sortie observée :**

```text

```

---

### Exercice 10 — Connexion simulée : `then`, `catchError`, `whenComplete` — 2,5 pts

**a)** Écrivez `Future<String> connexion(String mdp)` qui attend 1 seconde, renvoie `'Bienvenue'` si `mdp == '1234'`, sinon lance `Exception('Mot de passe incorrect')`.

**Votre code :**

```dart
// Écrivez votre code ici
```

**b)** Appelez-la deux fois (bon puis mauvais mot de passe) en utilisant uniquement `then`, `catchError` et `whenComplete` pour afficher le résultat, l'erreur, et `Tentative terminée` dans tous les cas.

**Votre code :**

```dart
// Écrivez votre code ici
```

**Sortie observée :**

```text

```

**c)** Quelle est la différence entre `catchError` et un bloc `try`/`catch` autour d'un `await` ? Laquelle préférez-vous et pourquoi ?

> **Réponse :** 

---

### Exercice 11 (défi) — Chaîne de dépendances — 1,5 pts

Trois fonctions simulées, chacune attend 1 s : `Future<int> trouverIdUtilisateur(String login)` renvoie 7, `Future<String> trouverNom(int id)` renvoie `'Sara'`, `Future<String> composerMessage(String nom)` renvoie `'Bonjour Sara'`. Chaque étape dépend de la précédente.

**a)** Écrivez les trois fonctions et enchaînez-les avec `await`. Quel est le temps total ?

**Votre code :**

```dart
// Écrivez votre code ici
```

**Sortie observée :**

```text

```

**b)** Réécrivez l'enchaînement uniquement avec `then`. Quelle version est la plus lisible ?

**Votre code :**

```dart
// Écrivez votre code ici
```

**Sortie observée :**

```text

```

---

## Auto-évaluation

- [ ] J'ai répondu à la partie TD avant de toucher à l'ordinateur
- [ ] Tous mes programmes s'exécutent sans erreur
- [ ] J'ai collé la sortie réelle de chaque programme
- [ ] J'ai relu mes réponses et corrigé mes prédictions fausses
- [ ] J'ai fait au moins une tentative sur le défi

## Difficultés rencontrées / remarques

> 
