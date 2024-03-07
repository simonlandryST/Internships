<[back](./prerequismaths.md) - [accueil](./README.md) - [next](./typededonnees.md)>

# Affichage à l'écran

Le même nombre peut être affiché à l'écran sous plusieurs formats en fonction de la base souhaitée. Les fonctions python utilisées sont ```hex()``` pour afficher en base hexadécimale et ```bin()``` pour afficher en base binaire. 

Une manière d'afficher un texte et un nombre à l'écran est d'utiliser la syntaxe des *f-strings* encadré par des guillemets simple ```'``` ou doubles ```"``` et le nombre entre accolades ```{}```. Par exemple :

```
>>> f'Ceci est une f-string, le nombre est {30/2}.'
'Ceci est une f-string, le nombre est 15.'
``` 

La notation ```:02X``` demande une longueur minimale de 2 caractères en majuscules (```:02x``` pour des minuscules). Si le nombre est trop petit et tient sur un seul caractère, un 0 se met à gauche.

**À ton tour !** Affiche à l'écran l'écriture hexadécimale de 14 et 240, avec minimum 2 caractères en majuscules.
<details>
  <summary>Solution possible</summary>

```
>>> f'L'écriture hexadécimale de 14 est {hex(14)}, que je peux écrire en majuscules comme ça {14:02X}.'
L'écriture hexadécimale de 14 est 0xe, que je peux écrire en majuscules comme ça 0E.

>>> f'L'écriture hexadécimale de 240 est {hex(240)}, que je peux écrire en majuscules comme ça {240:02X}.'
L'écriture hexadécimale de 240 est 0xf0, que je peux écrire en majuscules comme ça F0.
``` 

 </details>

# Autres cours

* [Prérequis mathématiques](./prerequismaths.md)
* [Type de Données](./typededonnees.md)
* [Variables](./variables.md)
* [Boucle For](./boucles.md)
* [Fonctions](./fonctions.md)
* [Conditions](./conditions/md)
 
<[back](./prerequismaths.md) - [accueil](./README.md) - [next](./typededonnees.md)>
