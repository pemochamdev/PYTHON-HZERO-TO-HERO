## L'opérateur ternaire en Python

### Introduction

L'opérateur ternaire en Python est une construction syntaxique qui permet d'écrire une instruction conditionnelle sur une seule ligne. C'est une forme concise d'écrire une instruction if-else simple. Il est particulièrement utile lorsque vous voulez assigner une valeur à une variable basée sur une condition.

### Syntaxe

La syntaxe générale de l'opérateur ternaire en Python est la suivante :

```python
valeur_si_vrai if condition else valeur_si_faux
```

### Fonctionnement détaillé

1. La `condition` est évaluée en premier.
2. Si la condition est vraie (True), l'expression `valeur_si_vrai` est évaluée et retournée.
3. Si la condition est fausse (False), l'expression `valeur_si_faux` est évaluée et retournée.

### Avantages

1. Concision : permet d'écrire des conditions simples en une seule ligne.
2. Lisibilité : pour des conditions simples, peut rendre le code plus lisible.
3. Expressivité : utile dans des contextes où une expression est attendue (par exemple, dans une liste en compréhension).

### Exemples détaillés

#### Exemple 1 : Utilisation basique

```python
age = 20
statut = "majeur" if age >= 18 else "mineur"
print(statut)  # Affiche: majeur
```

#### Exemple 2 : Dans une fonction

```python
def abs_value(number):
    return number if number >= 0 else -number

print(abs_value(5))   # Affiche: 5
print(abs_value(-3))  # Affiche: 3
```

#### Exemple 2 : Dans une liste en compréhension

```python
numbers = [1, -2, 3, -4, 5]
abs_numbers = [num if num >= 0 else -num for num in numbers]
print(abs_numbers)  # Affiche: [1, 2, 3, 4, 5]
```

#### Exemple 4 : Chaînage d'opérateurs ternaires

```python
score = 75
grade = "A" if score >= 90 else "B" if score >= 80 else "C" if score >= 70 else "D" if score >= 60 else "F"
print(grade)  # Affiche: C
```

### Bonnes pratiques

1. Utilisez l'opérateur ternaire pour des conditions simples et courtes.
2. Évitez de chaîner trop d'opérateurs ternaires, car cela peut rendre le code difficile à lire.
3. Si la condition ou les expressions deviennent complexes, préférez une structure if-else classique.

### Exercices

#### Exercice 1

Écrivez une fonction `est_pair` qui prend un nombre en entrée et retourne "pair" si le nombre est pair, et "impair" sinon, en utilisant l'opérateur ternaire.

#### Exercice 2

Créez une liste de nombres de 1 à 10, puis utilisez une liste en compréhension avec un opérateur ternaire pour créer une nouvelle liste où chaque nombre est remplacé par "fizz" s'il est divisible par 3, "buzz" s'il est divisible par 5, et le nombre lui-même sinon.

#### Exercice 3

Écrivez une fonction `note_to_letter` qui prend une note sur 100 en entrée et retourne la lettre correspondante (A pour 90-100, B pour 80-89, C pour 70-79, D pour 60-69, F pour moins de 60) en utilisant des opérateurs ternaires chaînés.

### Solutions

#### Solution de l'exercice 1

```python
def est_pair(nombre):
    return "pair" if nombre % 2 == 0 else "impair"

print(est_pair(4))  # Affiche: pair
print(est_pair(7))  # Affiche: impair
```

#### Solution de l'exercice 2

```python
numbers = list(range(1, 11))
fizzbuzz = ["fizz" if n % 3 == 0 else "buzz" if n % 5 == 0 else n for n in numbers]
print(fizzbuzz)
# Affiche: [1, 2, 'fizz', 4, 'buzz', 'fizz', 7, 8, 'fizz', 'buzz']
```

#### Solution de l'exercice 3

```python
def note_to_letter(note):
    return "A" if note >= 90 else "B" if note >= 80 else "C" if note >= 70 else "D" if note >= 60 else "F"

print(note_to_letter(95))  # Affiche: A
print(note_to_letter(82))  # Affiche: B
print(note_to_letter(68))  # Affiche: D
print(note_to_letter(55))  # Affiche: F
```

### Conclusion

L'opérateur ternaire en Python est un outil puissant pour écrire des conditions simples de manière concise. Il est particulièrement utile dans des situations où vous avez besoin d'une expression conditionnelle courte. Cependant, il est important de l'utiliser judicieusement pour maintenir la lisibilité du code. Pour des conditions plus complexes, il est généralement préférable d'utiliser des structures if-else traditionnelles.