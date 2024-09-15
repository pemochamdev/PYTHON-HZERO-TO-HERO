Bien sûr, je vais vous préparer un cours complet et détaillé sur les itérables en Python, avec des exemples et des exercices corrigés.

## Les itérables en Python

### 1. Introduction aux itérables

Un itérable en Python est un objet capable de renvoyer ses éléments un à la fois. En termes simples, c'est tout objet que vous pouvez parcourir dans une boucle.

Les types de données itérables les plus courants en Python sont :
- Listes
- Tuples
- Chaînes de caractères
- Dictionnaires
- Ensembles
- Fichiers

### 2. Caractéristiques des itérables

Les itérables ont plusieurs caractéristiques importantes :

1. Ils peuvent être utilisés dans une boucle `for`.
2. Ils peuvent être convertis en une liste avec la fonction `list()`.
3. On peut obtenir un itérateur à partir d'eux avec la fonction `iter()`.

### 3. Exemples d'utilisation des itérables

#### Exemple 1 : Parcourir une liste

```python
fruits = ["pomme", "banane", "cerise"]
for fruit in fruits:
    print(fruit)
```

Sortie :
```
pomme
banane
cerise
```

#### Exemple 2 : Parcourir une chaîne de caractères

```python
mot = "Python"
for lettre in mot:
    print(lettre)
```

Sortie :
```
P
y
t
h
o
n
```

#### Exemple 3 : Parcourir un dictionnaire

```python
personne = {"nom": "Dupont", "age": 30, "ville": "Paris"}
for cle in personne:
    print(f"{cle}: {personne[cle]}")
```

Sortie :
```
nom: Dupont
age: 30
ville: Paris
```

### 4. Création d'itérables personnalisés

Vous pouvez créer vos propres itérables en implémentant la méthode `__iter__()` dans une classe.

```python
class Compteur:
    def __init__(self, limite):
        self.limite = limite

    def __iter__(self):
        self.n = 0
        return self

    def __next__(self):
        if self.n < self.limite:
            resultat = self.n
            self.n += 1
            return resultat
        else:
            raise StopIteration

# Utilisation
for i in Compteur(5):
    print(i)
```

Sortie :
```
0
1
2
3
4
```

### 5. Fonctions utiles pour travailler avec les itérables

Python offre plusieurs fonctions intégrées pour travailler avec les itérables :

- `len()` : Retourne la longueur d'un itérable
- `sum()` : Calcule la somme des éléments d'un itérable numérique
- `max()` et `min()` : Trouvent respectivement le plus grand et le plus petit élément
- `enumerate()` : Retourne un objet énuméré (index, valeur)
- `zip()` : Combine deux itérables en paires

Exemple d'utilisation de `enumerate()` :

```python
fruits = ["pomme", "banane", "cerise"]
for index, fruit in enumerate(fruits):
    print(f"Index {index}: {fruit}")
```

Sortie :
```
Index 0: pomme
Index 1: banane
Index 2: cerise
```

### 6. Compréhensions de liste

Les compréhensions de liste sont une façon concise de créer des listes à partir d'itérables existants.

```python
nombres = [1, 2, 3, 4, 5]
carres = [n**2 for n in nombres]
print(carres)
```

Sortie :
```
[1, 4, 9, 16, 25]
```

### Exercices

#### Exercice 1
Écrivez une fonction qui prend une chaîne de caractères en entrée et renvoie une nouvelle chaîne avec toutes les voyelles en majuscules.

#### Exercice 2
Créez une classe `FibonacciSequence` qui génère les nombres de Fibonacci jusqu'à une limite donnée.

#### Exercice 3
Utilisez une compréhension de liste pour créer une liste de tous les nombres pairs entre 1 et 20.

### Solutions

#### Solution de l'exercice 1

```python
def majuscules_voyelles(chaine):
    voyelles = "aeiou"
    return ''.join(c.upper() if c.lower() in voyelles else c for c in chaine)

# Test
print(majuscules_voyelles("hello world"))
```

Sortie :
```
hEllO wOrld
```

#### Solution de l'exercice 2

```python
class FibonacciSequence:
    def __init__(self, limite):
        self.limite = limite
        self.a, self.b = 0, 1

    def __iter__(self):
        return self

    def __next__(self):
        if self.a > self.limite:
            raise StopIteration
        resultat = self.a
        self.a, self.b = self.b, self.a + self.b
        return resultat

# Test
for num in FibonacciSequence(100):
    print(num, end=" ")
```

Sortie :
```
0 1 1 2 3 5 8 13 21 34 55 89
```

#### Solution de l'exercice 3

```python
nombres_pairs = [n for n in range(1, 21) if n % 2 == 0]
print(nombres_pairs)
```

Sortie :
```
[2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
```

Ce cours couvre les aspects fondamentaux des itérables en Python, avec des exemples pratiques et des exercices pour renforcer la compréhension. Les itérables sont un concept central en Python, et une bonne maîtrise de leur utilisation peut grandement améliorer l'efficacité et la lisibilité de votre code.

Citations:
[1] https://zestedesavoir.com/tutoriels/954/notions-de-python-avancees/1-starters/2-iterables/
[2] https://kinsta.com/fr/blog/iterables-python/
[3] https://fr.eitca.org/computer-programming/eitc-cp-ppf-python-programming-fundamentals/advancing-in-python/iterators-iterables/examination-review-iterators-iterables/give-an-example-of-an-iterable-and-an-iterator-in-python-programming-and-explain-how-they-can-be-used-in-a-loop/
[4] https://nbhosting.inria.fr/builds/ue12-p23-python/handouts/latest/4-01-iterations-1-nb.html
[5] https://docs.python.org/fr/3.7/library/itertools.html
[6] https://sites.google.com/site/pythonpasapas/methodes/iter
[7] https://www.docstring.fr/glossaire/iterable/
[8] https://docs.python.org/fr/dev/reference/compound_stmts.html