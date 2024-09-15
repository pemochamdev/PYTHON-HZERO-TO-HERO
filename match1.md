## L'opérateur `match` en Python

### 1. Introduction

L'opérateur `match`, introduit dans Python 3.10, permet de faire du **pattern matching** (correspondance de motifs). Il offre une alternative plus puissante et plus lisible aux structures conditionnelles traditionnelles comme `if`/`elif`/`else`, surtout lorsque vous devez traiter des structures de données complexes ou de multiples conditions.

### 2. Syntaxe de base

La syntaxe générale de l'instruction `match` est la suivante :

```python
match variable:
    case motif1:
        # Code à exécuter si motif1 correspond
    case motif2:
        # Code à exécuter si motif2 correspond
    case _:
        # Code à exécuter si aucun motif ne correspond
```

### 3. Exemples d'utilisation

#### Exemple 1 : Correspondance simple

```python
jour = "lundi"

match jour:
    case "lundi":
        print("C'est le premier jour de la semaine.")
    case "mardi":
        print("C'est le deuxième jour de la semaine.")
    case "mercredi":
        print("C'est le milieu de la semaine.")
    case "jeudi":
        print("C'est le quatrième jour de la semaine.")
    case "vendredi":
        print("C'est le dernier jour de la semaine de travail.")
    case "samedi" | "dimanche":
        print("C'est le week-end.")
    case _:
        print("Jour invalide.")
```

Sortie :
```
C'est le premier jour de la semaine.
```

#### Exemple 2 : Correspondance avec des types

```python
valeur = 42

match valeur:
    case int():
        print("C'est un entier.")
    case str():
        print("C'est une chaîne de caractères.")
    case list():
        print("C'est une liste.")
    case _:
        print("Type non reconnu.")
```

Sortie :
```
C'est un entier.
```

#### Exemple 3 : Correspondance avec des tuples

```python
coordonnees = (10, 20)

match coordonnees:
    case (0, 0):
        print("C'est l'origine.")
    case (x, 0):
        print(f"Sur l'axe X à {x}.")
    case (0, y):
        print(f"Sur l'axe Y à {y}.")
    case (x, y):
        print(f"Point à ({x}, {y}).")
    case _:
        print("Point non valide.")
```

Sortie :
```
Point à (10, 20).
```

#### Exemple 4 : Utilisation de guards (conditions supplémentaires)

```python
age = 25

match age:
    case n if n < 0:
        print("Âge invalide.")
    case n if n < 18:
        print("Mineur.")
    case n if n < 65:
        print("Adulte.")
    case _:
        print("Senior.")
```

Sortie :
```
Adulte.
```

### 4. Avantages de l'opérateur `match`

1. **Lisibilité améliorée** : Le code est souvent plus facile à lire et à comprendre que les longues chaînes d'instructions `if`/`elif`/`else`.
2. **Correspondance de motifs** : Permet de déstructurer des données complexes (comme des tuples ou des dictionnaires) directement dans le `case`.
3. **Conditions supplémentaires** : Vous pouvez ajouter des conditions supplémentaires (guards) pour affiner la correspondance.

### 5. Exercices

#### Exercice 1

Déclarez une variable `animal` et assignez-lui une valeur parmi "chien", "chat", "oiseau" ou "autre". Utilisez `match` pour imprimer un message différent selon l'animal.

#### Exercice 2

Déclarez une variable `note` avec une valeur entre 0 et 100. Utilisez `match` pour déterminer la lettre correspondante (A, B, C, D, F) et imprimez-la.

#### Exercice 3

Déclarez une variable `point` qui est un tuple représentant un point en 2D (par exemple, (3, 4)). Utilisez `match` pour déterminer si le point est dans le premier, deuxième, troisième ou quatrième quadrant, ou s'il est sur un axe.

### Solutions aux exercices

#### Solution de l'exercice 1

```python
animal = "chat"

match animal:
    case "chien":
        print("C'est un chien.")
    case "chat":
        print("C'est un chat.")
    case "oiseau":
        print("C'est un oiseau.")
    case _:
        print("C'est un autre animal.")
```

Sortie :
```
C'est un chat.
```

#### Solution de l'exercice 2

```python
note = 85

match note:
    case n if n >= 90:
        print("A")
    case n if n >= 80:
        print("B")
    case n if n >= 70:
        print("C")
    case n if n >= 60:
        print("D")
    case _:
        print("F")
```

Sortie :
```
B
```

#### Solution de l'exercice 3

```python
point = (3, 4)

match point:
    case (x, y) if x > 0 and y > 0:
        print("Le point est dans le premier quadrant.")
    case (x, y) if x < 0 and y > 0:
        print("Le point est dans le deuxième quadrant.")
    case (x, y) if x < 0 and y < 0:
        print("Le point est dans le troisième quadrant.")
    case (x, y) if x > 0 and y < 0:
        print("Le point est dans le quatrième quadrant.")
    case (0, y):
        print("Le point est sur l'axe Y.")
    case (x, 0):
        print("Le point est sur l'axe X.")
    case _:
        print("Le point n'est pas valide.")
```

Sortie :
```
Le point est dans le premier quadrant.
```

### Conclusion

L'opérateur `match` en Python est un outil puissant pour effectuer des correspondances de motifs de manière claire et concise. Il améliore la lisibilité du code et facilite la gestion des structures de données complexes. En pratiquant avec des exemples et des exercices, vous pourrez mieux comprendre comment l'utiliser efficacement dans vos programmes Python. 