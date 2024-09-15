La boucle `while` en Python est un outil essentiel qui permet d'exécuter un bloc de code tant qu'une condition spécifiée est vraie. Cette structure est particulièrement utile lorsque le nombre d'itérations n'est pas connu à l'avance, ce qui la distingue de la boucle `for`.

## Qu'est-ce qu'une boucle `while` ?

La boucle `while` exécute un ensemble d'instructions tant qu'une condition est vraie. Si la condition devient fausse, la boucle s'arrête et le programme continue avec le code qui suit.

### Syntaxe de la boucle `while`

La syntaxe de base d'une boucle `while` est la suivante :

```python
while condition:
    # bloc d'instructions
```

- **condition** : Une expression qui est évaluée avant chaque itération. Si elle est vraie, le bloc d'instructions est exécuté.
- Le bloc d'instructions doit être indenté pour indiquer qu'il fait partie de la boucle.

## Exemple de boucle `while`

Voici un exemple simple qui affiche les nombres de 0 à 4 :

```python
i = 0
while i < 5:
    print(i)
    i += 1  # Incrémente i de 1 à chaque itération
```

**Résultat :**

```
0
1
2
3
4
```

Dans cet exemple, la boucle continue tant que `i` est inférieur à 5. À chaque itération, `i` est incrémenté de 1.

## Utilisation de `break` et `continue`

### L'instruction `break`

L'instruction `break` permet de sortir immédiatement de la boucle, peu importe si la condition est toujours vraie. Voici un exemple :

```python
i = 0
while True:  # Boucle infinie
    if i >= 5:
        break  # Sort de la boucle si i est supérieur ou égal à 5
    print(i)
    i += 1
```

**Résultat :**

```
0
1
2
3
4
```

### L'instruction `continue`

L'instruction `continue` permet de sauter le reste du code dans la boucle pour l'itération actuelle et de passer à l'itération suivante. Exemple :

```python
i = 0
while i < 5:
    i += 1
    if i == 3:
        continue  # Saute l'affichage de 3
    print(i)
```

**Résultat :**

```
1
2
4
5
```

## Exercices

### Exercice 1 : Compter jusqu'à 10

**Consigne :** Écrivez un programme qui affiche les nombres de 1 à 10 en utilisant une boucle `while`.

**Solution :**

```python
i = 1
while i <= 10:
    print(i)
    i += 1
```

### Exercice 2 : Somme des nombres

**Consigne :** Écrivez un programme qui demande à l'utilisateur d'entrer des nombres jusqu'à ce qu'il entre 0, puis affiche la somme de ces nombres.

**Solution :**

```python
somme = 0
nombre = None

while nombre != 0:
    nombre = int(input("Entrez un nombre (0 pour arrêter) : "))
    somme += nombre

print("La somme est :", somme)
```

### Exercice 3 : Compter les voyelles

**Consigne :** Écrivez un programme qui demande à l'utilisateur d'entrer une phrase et compte le nombre de voyelles dans cette phrase.

**Solution :**

```python
phrase = input("Entrez une phrase : ")
voyelles = "aeiouyAEIOUY"
compteur = 0
i = 0

while i < len(phrase):
    if phrase[i] in voyelles:
        compteur += 1
    i += 1

print("Nombre de voyelles :", compteur)
```

## Conclusion

La boucle `while` est un outil puissant en Python qui permet d'exécuter des instructions de manière répétée tant qu'une condition est vraie. En utilisant des instructions comme `break` et `continue`, vous pouvez contrôler le flux de votre programme de manière flexible.

Citations:
[1] https://www.data-bird.co/blog/boucle-while-python
[2] https://courspython.com/boucles.html
[3] https://docs.python.org/fr/3/tutorial/datastructures.html
[4] https://python.doctor/page-apprendre-listes-list-tableaux-tableaux-liste-array-python-cours-debutant
[5] https://www.pythoniste.fr/python/enumerer-des-listes-avec-la-fonction-enumerate-de-python/
[6] https://python.doctor/page-apprendre-boucles-python-loop
[7] https://www.youtube.com/watch?v=em3F1crPa7Y
[8] https://talks.freelancerepublik.com/tout-savoir-fonction-enumerate-python-comment-ca-marche/