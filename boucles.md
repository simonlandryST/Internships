# Boucle For

 La boucle ```for``` permet de parcourir des éléments d'un type de donnée : 

 * Parcourir les caractères d'une string : ```for char in "Arya Stark": print(char)```
<details>
  <summary>Résultat</summary>
 
```
>>> for char in "Arya Stark": print(char)
A
r
y
a

S
t
a
r
k
```

 </details>

* Parcourir les éléments d'une liste : ```for i in [1,2,3,"go"]: print(i)```
<details>
  <summary>Résultat</summary>
 
```
>>> for i in [1,2,3,"go"]: print i
1
2
3
"go"
```

</details>

* Parcourir les clés d'un dictionnaire : ```for key in {'prenom':'Raphaelle','taille':172}: print(key)```
<details>
  <summary>Résultat</summary>
 
```
>>> for key in {'name':'Raphaelle','taille':172}: print key
prenom
taille
```

</details>

* Parcourir les valeurs d'un dictionnaire : ```for value in {'prenom':'Raphaelle','taille':172}.values(): print(value)```
 <details>
  <summary>Résultat</summary>
 
```
>>> for value in {'prenom':'Raphaelle','taille':172}.values(): print(value)
Raphaelle
172
```

</details>

**À ton tour !** Soit une string ```s = "anniversaire"```. Parcours les éléments de la liste s. 
<details>
  <summary>Résultat</summary>
 
```
>>> s = "anniversaire"
>>> for i in s: print i
a
n
n
i
v
e
r
s
a
i
r
e
```

</details>

* Tu peux aussi utiliser le mot clé ```range()``` pour parcourir des entiers :
  * Si un seul argument est donné : ```range(a)``` retourne les entiers de l'intervalle ```[0,a[```
  * Si 2 arguments sont donnés : ```range(a,b)``` retourne les entiers de l'intervalle ```[a,b[```
  * Si 3 arguments sont donnés : ```range(a,b,c)``` retourne les entiers de l'intervalle ```[a,b[``` avec un écart de c entre chaque entier
* Tu peux parcourir les éléments d'un type de données (liste, string, dictionnaire) en utilisant le mot clé ```range()```.  

**À ton tour !** Parcours les éléments de la liste ```L = [1,3,2,5]``` en utilisant le mot clé ```range()```.
<details>
  <summary>Indice 1</summary>

  Tu dois pour cela connaître la taille de ta liste. Le calcul se fait soit à la main, soit en utilisant la fonction ```len()``` vue précédemment.

</details>

<details>
  <summary>Indice 2</summary>

  Tu dois savoir comment accéder à un élément de ta liste. 

</details>

<details>
  <summary>Solution</summary>
 
```
>>> L = [1,3,2,5]
>>> for i in range(len(L)): print(L[i])
1
3
2
5
```

</details>
