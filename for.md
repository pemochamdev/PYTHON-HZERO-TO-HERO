
## Les boucles for en Python

### 1. Introduction aux boucles for

La boucle `for` en Python est utilisée pour itérer sur une séquence (comme une liste, un tuple, un dictionnaire, un ensemble ou une chaîne) ou tout autre objet itérable. Elle permet d'exécuter un bloc de code pour chaque élément de la séquence.

### 2. Syntaxe de base

La syntaxe générale d'une boucle `for` en Python est la suivante :

```python
for element in sequence:
    # Code à exécuter pour chaque élément
```

### 3. Exemples d'utilisation

#### Exemple 1 : Itération sur une liste

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

#### Exemple 2 : Itération sur une chaîne de caractères

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

#### Exemple 3 : Utilisation de range()

La fonction `range()` est souvent utilisée avec les boucles `for` pour générer une séquence de nombres.

```python
for i in range(5):
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

### 4. Fonctionnalités avancées

#### 4.1 Énumération

La fonction `enumerate()` permet d'obtenir à la fois l'index et la valeur de chaque élément.

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

#### 4.2 Zip

La fonction `zip()` permet d'itérer sur plusieurs séquences en parallèle.

```python
noms = ["Alice", "Bob", "Charlie"]
ages = [25, 30, 35]
for nom, age in zip(noms, ages):
    print(f"{nom} a {age} ans")
```

Sortie :
```
Alice a 25 ans
Bob a 30 ans
Charlie a 35 ans
```

#### 4.3 Compréhensions de liste

Les compréhensions de liste offrent une syntaxe concise pour créer des listes basées sur des boucles `for`.

```python
carres = [x**2 for x in range(5)]
print(carres)
```

Sortie :
```
[0, 1, 4, 9, 16]
```

### 5. Contrôle de flux dans les boucles for

#### 5.1 break

L'instruction `break` permet de sortir prématurément d'une boucle.

```python
for i in range(10):
    if i == 5:
        break
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

#### 5.2 continue

L'instruction `continue` passe à l'itération suivante de la boucle.

```python
for i in range(5):
    if i == 2:
        continue
    print(i)
```

Sortie :
```
0
1
3
4
```

#### 5.3 else

La clause `else` dans une boucle `for` est exécutée si la boucle se termine normalement (sans `break`).

```python
for i in range(3):
    print(i)
else:
    print("Boucle terminée normalement")
```

Sortie :
```
0
1
2
Boucle terminée normalement
```

### Exercices

#### Exercice 1
Écrivez une fonction qui prend une liste de nombres et retourne la somme de tous les nombres pairs.

#### Exercice 2
Créez une fonction qui prend une chaîne de caractères et retourne un dictionnaire avec le nombre d'occurrences de chaque caractère.

#### Exercice 3
Écrivez un programme qui imprime le motif suivant :
```
*
**
***
****
*****
```

### Solutions

#### Solution de l'exercice 1

```python
def somme_pairs(nombres):
    return sum(num for num in nombres if num % 2 == 0)

# Test
print(somme_pairs([1, 2, 3, 4, 5, 6]))  # Devrait afficher 12
```

#### Solution de l'exercice 2

```python
def compter_caracteres(chaine):
    return {char: chaine.count(char) for char in set(chaine)}

# Test
print(compter_caracteres("hello world"))
```

#### Solution de l'exercice 3

```python
for i in range(1, 6):
    print('*' * i)
```

### Exercices supplémentaires

#### Exercice 4
Écrivez une fonction qui prend une liste de mots et retourne une liste de tuples (mot, longueur) triée par longueur décroissante.

#### Exercice 5
Créez une fonction qui génère une table de multiplication (de 1 à 10) pour un nombre donné.

### Solutions des exercices supplémentaires

#### Solution de l'exercice 4

```python
def trier_mots_par_longueur(mots):
    return sorted([(mot, len(mot)) for mot in mots], key=lambda x: x[1], reverse=True)

# Test
print(trier_mots_par_longueur(["python", "est", "un", "langage", "de", "programmation"]))
```

#### Solution de l'exercice 5

```python
def table_multiplication(n):
    for i in range(1, 11):
        print(f"{n} x {i} = {n*i}")

# Test
table_multiplication(7)
```

Ce cours couvre les aspects fondamentaux et avancés des boucles `for` en Python. Les boucles `for` sont un outil essentiel en programmation Python, permettant d'itérer efficacement sur des séquences et d'effectuer des opérations répétitives. La pratique régulière et l'expérimentation avec différents types de séquences et de structures de contrôle vous aideront à maîtriser pleinement leur utilisation.