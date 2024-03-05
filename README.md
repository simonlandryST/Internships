# Sujet de stage : étude de la résistance d'un algorithme de chiffrement symétrique contre la cryptanalyse

## Organisation du stage

|   Durée       |   Contenu |   Compétences acquises
|---            |---        |--- 
| Lundi am | Présentation cryptologie dans les puces Présentation du stage | Comprendre l'environnement de travail Notions de cryptologie | 
| Lundi pm - mardi am | Support python, papier/ordi, premier chiffrement symétrique (César) et tests | Bases en python, réflexion mathématique et algorithmique
| Mardi pm - jeudi pm | Réflexion contre-mesures, codes python et tests | Réflexion sur un sujet en cryptographie Autonomie
| Vendredi | Conclusion, présentation des résultats | Restitution des connaissances |

## Support Python

Lancer un interpréteur _python_ :
* Installer [Spyder](https://www.spyder-ide.org/)
* Sinon, lancer une console dans le navigateur : [console](https://pyodide.org/en/stable/console.html)

### Bases
* Base 10 : système décimal 0, 1, 2, 3, ..., 9, 10. 
* Base 2 : système binaire basé sur des bits, 0 et 1. Pour écrire un nombre, on compte en puissances de 2 de droite à gauche.
  * Par exemple, 10 = 2^3 + 2^2, 8 = 2^3, 3 = 2^2 + 2^0. L'écriture binaire en 4 bits de 10 est 1100, celle de 8 est 1000 et celle de 3 est 0011.
* Base 16 : système hexadécimal basé sur les 16 caractères : 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E et F. Les lettres peuvent s'écrire en minuscules. Pour écrire un nombre, on compte en puissances de 16, de droite à gauche.
  * Par exemple, 1237 = 4 × 16^2 + 13 × 16^1 + 5 × 16^0. L'écriture hexadécimale de 1237 est 4D5.

Pour indiquer la base souhaitée dans du code python, il faut utiliser un préfixe :

* Base 10 : rien devant
* Base 2 : 0b
* Base 16 : 0x

**À ton tour !** Utilise la console pour voir les valeurs des nombres suivants : 0b10101010, 0xaa, 0xAA, 170
<details open>
  <summary>Solution</summary>
 
```
>>> 0b10101010
170
>>> 0xaa
170
>>> 0xAA
170
>>> 170
170
```
</details>

### Calculs arithmétiques

On peut coder les différentes opération mathématiques :

* Addition : 1+1
* Soustraction : 2-1
* Multiplication : 3*4
* Puissance : 3**2
* Division simple : 5/2
* Division entière : 5//2
* Modulo : 30%4

 **À ton tour !** Calcule la moyenne de 127, 45 et 72.6

<details open>
  <summary>Solution</summary>

```
>>> (127+45+72.6)/3
81.5333333333
>>> (127+45+72.6)//3
81.0
```

 </details>

 ### Affichage à l'écran

Le même nombre peut être affiché à l'écran sous plusieurs formats en fonction de la base souhaitée. Les fonctions python utilisées sont ```hex()``` pour afficher en base hexadécimale et ```bin()``` pour afficher en base binaire. 

Une manière d'afficher un texte et un nombre à l'écran est d'utiliser la syntaxe des *f-strings* encadré par des guillemets " ou ' et le nombre entre accolades {}. Par exemple la commande ```f'Ceci est une f-string, le nombre est {30/2}.'``` retourne la phrase 'Ceci est une f-string, le nombre est 15.'

La notation ```:02X``` demande une longueur minimale de 2 caractères en majuscules (```:02x``` pour des minuscules). Si le nombre est trop petit et tient sur un seul caractère, un 0 se met à gauche.

**À ton tour !** Affiche à l'écran l'écriture hexadécimale de 14 et 240, avec minimum 2 caractères en majuscules.
<details open>
  <summary>Solution possible</summary>

```
>>> f'L'écriture hexadécimale de 14 est {hex(14)}, que je peux écrire en majuscules comme ça {14:02X}.'
L'écriture hexadécimale de 14 est 0xe, que je peux écrire aussi comme ça 0E.
>>> f'L'écriture hexadécimale de 240 est {hex(240)}, que je peux écrire en majuscule comme ça {240:02X}.'
L'écriture hexadécimale de 240 est 0xf0, que je peux écrire aussi comme ça F0.
``` 

 </details>

 ## Nombres Booléens

 Les nombres booléens retourne soit vrai ```True``` soit faux ```False``` en fonction de la commande testée. Pour vérifier l'égalité entre deux nombres, on utilise le symbole ```==```. 

 **À ton tour !** Vérifie si les équations suivantes sont justes : 2**6 + 7*8 = 40*3 et hex(18) = 0x13 
<details open>
  <summary>Solution</summary>

```
>>> f'{2**6 + 7*8 == 40*3}'
True
>>> f'{hex(18) == "0x13"}'
False
``` 

 </details>

## Strings

Une string est une chaîne de caractères délimitée par des guillemets simples ' ou doubles ". On peut écrire un texte de plusieurs lignes en sautant des lignes avec le caractère ```\n```. 

Quelques manipulations sont possibles sur les strings :

* On définit une string par un nom à gauche d'un = : ```S = 'ceci est une string'```
* Addition et multiplication : ```'test*4 + fin'``` donne 'test test test test fin'
* Vérifier qu'un caractère est présent dans la string : ```'a' in 'on teste si la lettre est presente'``` retourne True
* On calcule la longueur de la string : ```len('test longueur')``` retourne 13. L'espace compte comme un caractère.
* Accéder à un élément de la string avec les crochets [] : ```Batman[0]+Tarzan[3]+Mooglie[-1]``` retourn 'Bze'
* Accéder à une sous-partie de la string en indiquant la position du début et la position de fin entre crochets : ```'kangourou'[2:6]``` retourne les caractères entre la position 2 et 5 (on remarque que ```:6]``` veut vraiment dire **avant** 6) soit 'ngou'. Si la position du début est omise, elle est égale par défaut à 0. Si la position de fin est omise, elle est égale au dernier caractère de la string par défaut.

**À ton tour !** Ecris une phrase de plus de 20 caractères. Isole les 10 premiers caractères. Vérifie si la lettre k appartient à ta phrase. 
<details open>
  <summary>Solution</summary>
```
>>> S = "Ceci est une phrase de plus de vingts caractères."
>>> S[:10]
'Ceci est '
>>> k in S
False
``` 
 </details>


