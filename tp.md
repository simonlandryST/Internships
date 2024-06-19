# Sommaire

[Lundi](#lundi) - les listes et les strings

[Mardi](#mardi) - chiffrement de César et analyse fréquentielle

[Mercredi](#mercredi) - contremesures contre l'attaque par analyse fréquentielle

[Jeudi](#jeudi) - TP sur la journée

# <a name="lundi"></a> Lundi 

## Exercice 1 

Soit la fonction ```exercice1(L)``` avec la liste L en paramètre. 

Q1. Changer tous les 5 en 10. Il faut parcourir les éléments de la liste L, si un élément est égal à 5, on le change en 10.

Q2. Soit la variable S = 0. Calculer la somme des 4 premiers éléments de la liste L et stocker le résultat dans la variable S.

Q3. Ajouter le mot "ajout" après chaque 10 de la liste L. Il faut parcourir les élements de la liste L, si un élément est égal à 10, il faut ajouter le mot "ajout" après cet élément. 

Q4. Retourner la liste L et l'entier S.

Q5. Tester la fonction sur la liste [5,78,92,100,5,67,5]

<details>
  <summary>Solution</summary>
  
```
def exercice1(L):
  # Q1
  for i in range(len(L)):
    if L[i] == 5:
      L[i] = 10
  # Q2
  S = 0
  for i in range(4):
    S = S + L[i]
  # Q3
  for i in range(len(L)):
    if L[i] == 10:
      L.insert(i+1,"ajout")
  # Q4
  return L,S

>>> ma_liste = [5,78,92,100,5,67,5]
>>> print(exercice1(ma_liste))
[10,"ajout",78,92,100,10,"ajout",67,10,"ajout"], 280
```

</details>

## Exercice 2 

Soit la fonction ```exercice2(str)``` avec ```str``` une chaîne de caractère.

Q1. Parcourir les éléments de la chaîne de caractères str. Si deux éléments consécutifs sont les mêmes, les changer tous les deux par la lettre "e". 

Q2. Décaler toutes les lettres "c" de 3 positions dans l'alphabet. 

Q3. Tester la fonction sur la chaîne "chiffrement du message securite".

# <a name="mardi"></a> Mardi 

## Rappel sur les fonctions

On définit une fonction de cette manière : 

```
def nom_fonction(parametres):
  ...corps de la fonction...
  ...en utilisant les parametres...
  return resultat
```

On fait appel à la fonction par : 

```
print(nom_fonction(mes_parametres)
```

Par exemple, la fonction suivante calcule la somme entre l'élément a et l'élément b. 

```
def somme(a,b):
  return a+b

>>> print(somme(6,8))
14
```
## Exercice 1 - à la main

Q1. Ecrire sur une feuille le mot "cryptologie". Reproduire le tableau suivant :

|A|B|C|D|E|F|G|H|I|J|K|L|M|N|O|P|Q|R|S|T|U|V|W|X|Y|Z|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|0|1|2|3|4|5|6|7|8|9|10|11|12|13|14|15|16|17|18|19|20|21|22|23|24|25|26|
| | | | | | | | | | | | | | | | | | | | | | | | | | |

Q2. Ecrivez les positions dans l'alphabet des lettres du mot "cryptologie" et ajouter 4 à ces positions. Par exemple, pour la première lettre on a :

C -> position 2 -> +4 = position 6 -> C devient G

Q3. Que donne le chiffrement symétrique du mot "cryptologie" avec la clé secrète 4 ?

Q4. Détaillez les différentes étapes de réflexion. En premier on fait quoi, puis en deuxième, etc. 

Q5. Déchiffrer à la main le mot chiffré obtenu en Q3. Comment faut-il procéder ? 

## Exercice 2 - à la main et avec python

La fonction suivante permet de trouver l'index d'une lettre dans l'alphabet français. Par exemple, la lettre i dans "tim" est à l'index 1 dans le mot "tim" et à l'index 8 dans l'alphabet (c'est la 9e lettre de l'alphabet).

```
alphabet = "abcdefghijklmnopqrstuvwxyz"
def position_alphabet(letter):
    return alphabet.find(letter)

>>> print(position_alphabet("c")
2
```

Q1. Quel est l'index de la lettre "r" dans la chaîne de caractère S = "cryptologie" ? Manuellement et en python.

Q2. Quelle est la position de la lettre "r" dans l'alphabet français ? Manuellement et en python. 

Q3. On veut décaler la lettre "r" de 2 positions dans l'alphabet sans utiliser la manipulation ```S[:i]+"t"+S[i+1:]```. Comment peut-on faire (en python) ? 

## Exercice 3

Soit ```elt``` un élément de la chaîne de caractère. La commande ```elt.isalpha()``` retourne ```True``` si elt est une lettre et retourne ```False``` si ce n'est pas le cas (par exemple un espace ou un chiffre).

Soit les chaînes de caractères suivantes :
* S = "on veut chiffrer le mot securite"
* alphabet = "abcdefghijklmnopqrstuvwxyz"

Ecrire une boucle qui parcours les éléments de la string S. Tester si chaque élément est une lettre. Si oui, décalez cette lettre de 3 positions vers la droite en utilisant la variable ```alphabet```. Sinon, ne faites rien (il suffit de ne pas mettre de boucle ```else:```). Retourner S. 

Vous venez de coder une fonction de chiffrement symétrique de César. 

## Exercice 4

Trouver d'autre(s) manière(s) de coder un chiffrement de César sur la phrase de votre choix. On peut par exemple passer en paramètres :

* Le message à chiffrer et la clé secrète
* Le message à chiffrer et une chaîne de caractère

## Exercice 5 - Attaques à la main

Q1. Comptez la fréqence de chaque lettre de votre message chiffré. 

Q2. Comparez ces fréquences à celles des lettres de l'alphabet français et associer les lettres du messages chiffré à une lettre possible de l'alphabet.

E A I S N R T O L U D C M P G B V H F Q Y X J K W Z 

Q3. Tentez de déchiffrer votre message chiffré. 

Q4. Quelles conclusions faites-vous ?

## Exercice 6

Rendez-vous [ici](https://github.com/simonlandryST/Internships/tree/main?tab=readme-ov-file#point-de-d%C3%A9part) dans la partie "Point de départ". 

L'alphabet de référence des fréquence des lettres de ce texte est : 

e t s a n l u r o d i m c f y p q v h g j b z x k w

```
# Compter le nombre d'occurrences de chaque lettre dans un dictionnaire
    letter_count = {}
    for char in range(0,len(cipher)):
        # si le caractère est une lettre (sinon on ne fait rien)
        if cipher[char].isalpha():
            # s'il est déjà présent dans le dictionnaire on ajoute 1
            if cipher[char] in letter_count:
                letter_count[cipher[char]] += 1
            # sinon on initialise à 1
            else:
                letter_count[cipher[char]] = 1

    # Trier les lettres par ordre décroissant de fréquence
    sorted_letters = sorted(letter_count.items(), key=lambda x: x[1], reverse=True)
    print("\n",sorted_letters,len(sorted_letters),"\n")

    # Ranger les lettres par ordre d'occurrences de manière décroissante
    cipher_letters = ""
    for i in range(len(sorted_letters)):
        cipher_letters += sorted_letters[i][0]

    # Pour les lettres qui n'apparaissent jamais 
    for char in alphabet:
        if char not in cipher_letters:
            cipher_letters += char

    return cipher_letters

def dec_freq(cipher,freq_alphabet):
    freq_cipher   = freq_analysis(cipher)

    print("\nFréquence des lettres du message chiffré     :",freq_cipher)
    print("Fréquence des lettres de la langue française :", freq_alphabet) # etsanlurodimcfypqvhgjbzxkw
    
    #Créer un dictionnaire de lettres chiffré et françaises
    mapping = dict(zip(freq_cipher,freq_alphabet))

    #Associer les lettres du texte chiffré aux lettres de la langue française
    decipher = ""
    for char in range(len(cipher)):
        if cipher[char].isalpha():
            decipher += mapping[cipher[char]]
        else:
            decipher += cipher[char]
    
    return decipher
```
# <a name="mercredi"></a> Mercredi 

Vous savez chiffrer un message clair avec le chiffrement de César. Je sais attaquer votre message chiffré avec une attaque par analyse fréquentielle des lettres. Pour cela, je compte la fréquence de toutes les lettres de votre message chiffré, je les trie dans l'ordre décroissant et je compare les lettres correspondantes avec celles de l'alphabet français.

Par exemple, si j'obtiens ces lettres de la fréquence la plus haute à la plus basse :

q h i t p x w r s v k j b d g l u f a o c m z e y n

et que je compare avec les lettres de l'alphabet qui apparaissent le plus ou moins possible dans la langue française :

 e t s a n l u r o d i m c f y p q v h g j b z x k w

Alors q devient e, h devient t, i devient s, ..., n devient w. Je peux ainsi déchiffrer votre message chiffré en remplaçant chaque lettre par sa correspondante. 

**Votre but :** empêcher que je puisse faire cette correspondance d'une lettre à une autre.

**Indice :** il faut casser les fréquences que je calcule.

**Consigne et questions :** 
* Il est interdit de modifier le message original.
* Il est nécessaire de savoir déchiffrer son message chiffré.
* Est-il possible de partager votre clé secrète à votre destinataire de manière sécurisée ? 

## Astuces

**Aléatoire entiers**
```
import random
alea = random.randint(0,10000)
```

**Aléatoire lettre**
```
import string

for i in range(n):
  random_letter = random.choice(string.ascii_letters)
  print(random_letter)
```

## Echange de clés de Diffie Hellman

Alice et Bob souhaitent échanger une clé secrète partagée sans se la communiquer entre eux.

* Alice génère deux nombres aléatoires ```a``` et ```g``` et transmet à Bob $A = g^a$ et $g$.
* Bob génère un nombre aléatoire ```b``` et transmet à Alice $B = g^b$. Sa clé est $K = A^b$.
* Alice calcule sa clé $K = B^a$.

Q1. Prouver qu'Alice et Bob possède la même clé secrète.

Q2. Prouver qu'une tierce personne ne peut pas reconstuire cette clé secrète. 

## Vos idées pour contrer l'attaque par analyse fréquentielle

* Eliot : changer la clé secrète pour chaque lettre du message clair grâce à un nombre aléatoire : ```cle += random.randint(0,25)```
* Amélie : changer la clé secrète pour chaque lettre du message clair grâce à une fonction affine aléatoire : ```cle = (m*pos + k) % 26``` avec ```m``` et ```k``` tirés aléatoirement : ```m = random.randint(0,25), p = random.randint(0,25)```.
* Max : attribuer aléatoirement une autre lettre à chaque lettre du message clair et utiliser sa position dans l'alphabet pour décaler la lettre du message clair dans l'alphabet. Par exemple, dans le message clair "je m'appelle max", on attribue aléatoirement la lettre ```b``` à la lettre ```j```. Comme la position de  ```b``` dans l'alphabet est 1, alors la lettre ```j``` est décalée de 1 position et devient ```k``` dans le message chiffré.
* Milo : créer un dictionnaire tel que les lettres de l'alphabet (les clés du dictionnaire) prennent un ou plusieurs caractères en valeurs. Par exemple le dictionnaire D = {'a':['x','y','z'], 'b':['a','e'],....}

## Autres idées

* Chiffrer toutes les lettres du message clair avec un alphabet de sortie différent pour chaque lettre. Pour toutes les lettres du message clair, on peut décaler de 1 position l'alphabet. Par exemple, dans le message clair "je m'appelle amelie", avec la clé "bcdefghijklmnopqrstuvwxyza", la lettre ```j``` à la position 0 du message clair est chiffrée par un ```k```, avec la clé "cdefghijklmnopqrstuvwxyzab", la lettre ```e``` à la position 1 du message clair est chifrée par un ```g```. etc...
* Chiffrer toutes les lettres du messages clair avec un mot clé. Il s'agit du chiffrement de Vigenere. La première lettre du mot clé donne la position à rajouter à la position de la première lettre du mot clair. Et ainsi de suite...

# <a name="jeudi"></a> Jeudi

## Nouveau chiffrement symétrique

Le premier qui code la fonction de chiffrement symétrique décrite [ici](https://fr.wikipedia.org/wiki/Cryptographie_sym%C3%A9trique#Petite_taxinomie_du_chiffrement_sym%C3%A9trique_classique) a gagné. 

## Petit théorème de Fermat

Soit le petit théorème de Fermat, très utilisé en mathématiques et en cryptographie. 

$$ a^{p-1} = 1 modulo\ p$$





