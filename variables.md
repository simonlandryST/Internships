 # Variables

Une variable est utilisée pour donner un nom à un type de donnée : une string, une liste, un dictionnaire, une valeur. Par exemple, quand on définit la liste ```L = [1,2,3]```, L est une variable de type list. 

* Une variable est constituée d'un caractère entre a et z en minuscules ou majuscules.
* Une variable est reconnue partout dans le code. Par exemple, si on définit ```V = 30```, partout V vaudra 30 (sauf si la variable V est modifiée quelque part dans le code).
* Une même variable peut être ré-utilisée pour définir des types de donnée différents. Par exemple, ```V = 30``` au début puis ```V = "Hello"``` plus tard.

**À ton tour !** Quel est le résultat de la variable ```result``` tel que :

```
>>> ABC = 25
>>> result = ABC*3
>>> result
```
<details>
  <summary>Solution</summary>
 
75

 </details>

 **À ton tour !** Soit le dictionnaire suivant : 

```
dict = {'invites'         : ["Thomas","Ibrahima","Yanis","Morgane"],
        'prixparpersonne' : 120
       }
```

Q1/ Quel est le nombre d'invités ? 

<details>
  <summary>Solution</summary>
 
```
>>> dict = {'invites'         : ["Thomas","Ibrahima","Yanis","Morgane"],
            'prixparpersonne' : 120
           }
>>> n = len(dict['invites'])
>>> n
4
```

 </details>
 
Q2/ Quel est le prix d'une nuit ? 

<details>
  <summary>Solution</summary>
 
```
>>> p = dict['prixparpersonne']
>>> p
120
```

 </details>
 
Q3/ Quel est le prix total ? 

<details>
  <summary>Solution</summary>
 
```
>>> n*p
>>> 480
```

 </details>
