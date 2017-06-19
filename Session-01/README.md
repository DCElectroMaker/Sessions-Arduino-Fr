
# Session #1: 
# Arduino c'est quoi au juste? 
# Notions d'éléctronique de base.
---

### Au Programme:  
- Présentation de la carte Arduino :  
  - Qu'y a-t-il sur la carte?
  - À quoi correspondent les pins?
- Notions de base en électronique :  
  - Courant électrique, tension électrique? qu'est ce que c'est?  
  - Montage série  
  - Montage parallèle  
  - La *planche à pain*  
- Mise en pratique :  
  - Allumer une led sans Arduino.
  - Controler plusieurs leds avec Arduino.

### Durée: **?**
 
### Pré-requis:  
Notions de base en mathématique (savoir lire une équation).
 
### Matériel:  
-Une carte Arduino Uno  
![arduino](https://user-images.githubusercontent.com/29465741/27254447-62f8ec7a-5388-11e7-8e5b-8612e45e7a85.png)  
-Un cable USB type AB  
![usbab](https://user-images.githubusercontent.com/29465741/27254453-8fda0314-5388-11e7-8c57-2a60cd037466.png)  
-Quelques leds  
![led](https://user-images.githubusercontent.com/29465741/27261760-dcb38202-5449-11e7-8d24-9cc7d96db89c.png)  
-Quelques résistances  
![resistances](https://user-images.githubusercontent.com/29465741/27261781-5069832c-544a-11e7-8496-076269d5d1c1.png)


 
---
# Arduino c'est quoi au juste? 
---

Avant de commencer la présentation de la carte Arduino Uno, je vous propose de visionner cette courte vidéo qui explique ce qu'est *Arduino*.  
https://www.youtube.com/watch?v=9f9KYO8Hzzg  

## 1. Qu'y a-t-il sur la carte?

Maintenant que vous savez ce qu'est *Arduino*, regardons de plus près notre carte.  

Commençons par l'élément le plus évident de la carte, le port USB. Celui-ci permet de connecter votre carte à votre PC mais aussi de l'alimenter avec une tension de 5V.  
![boardusb](https://user-images.githubusercontent.com/29465741/27262158-2dc6f208-5451-11e7-82cb-acbb390f8dea.png)

Les différents composants qui se situe en bas à droite de la carte constituent ce qu'on appelle un régulateur de tension. Celà permet d'alimenter la carte sans USB avec une source comprise idéalement entre 7 et 12V via le connecteur *Jack*. Cette source peut être une pile ou un transfrmateur.  
Le rôle du régulateur est de convertir la tension fournie par votre source en une tension de 5V.  
![boardreg](https://user-images.githubusercontent.com/29465741/27262224-80169562-5452-11e7-9bda-a0263503f7f4.png)  
NB: La carte peut être alimenté entre 6V et 20V mais votre carte risque de mal fonctionner si la tension est trop faible ou de déteriorer votre carte si elle est trop élevée.

Le composant suivant est l'oscillateur, il est le *coeur* de la carte. C'est lui qui va donner le rythme de fonctionnement de la carte.  
![boardquartz](https://user-images.githubusercontent.com/29465741/27262258-461e3d46-5453-11e7-8ec2-604555a2e53c.png)

Le composant principal de la carte est le microcontroleur, il est le *cerveau* de la carte. C'est lui qui va garder en mémoire le programme qui lui sera téléversé et executer le code qu'il contient.  
![boardup](https://user-images.githubusercontent.com/29465741/27262329-bb07f6f0-5454-11e7-9565-8f4fddb91da8.png)

Nous trouverons ensuite un convertisseur USB/Série qui fait office d'*interprète* entre le PC et le microcontroleur.
![boardconvertpng](https://user-images.githubusercontent.com/29465741/27262392-1d123cf6-5456-11e7-94e0-773202424a62.png)

La carte comporte aussi un bouton reset qui permet de relancer le programme du microcontraleur ainsi que différentes leds qui permettent de visualiser l'état de la carte.  
![boardbtnled](https://user-images.githubusercontent.com/29465741/27262454-7951cfd0-5457-11e7-88b6-af69dc617630.png)

Finalement nous avons une série de connecteurs femelles de part et d'autres de la carte. Ces connecteurs sont les points d'entrée et de sortie de la carte et lui permettent d'interragir avec le monde exterieur.  
![boardpin](https://user-images.githubusercontent.com/29465741/27262546-01034cd2-5459-11e7-860d-63c61b69a374.png)  
NB: chaque point de connection est ce qu'on appelle une *Pin*
 
## 2. À quoi correspondent les pins?

Je l'avoue je viens juste de vous mentir... Et là c'est le moment où vous dites "Je viens de perdre 10 minutes de ma vie!".

Rassurez vous ce n'est pas le cas. Je m'explique! Toutes les pins ne permettent pas d'interragir avec le monde exterieur.  
Il existe 2 types de pins:  

**Les pins d'alimentation :**  
![boardpower](https://user-images.githubusercontent.com/29465741/27264816-d7ec7c72-5487-11e7-8d4a-341b37b6b732.png)

Les pins *3.3V* et *5V* fournissent respectivement 3,3V et 5V.  
![obvious](https://user-images.githubusercontent.com/29465741/27264867-39125944-5489-11e7-85bb-32c7d2de9f6e.png)  
Elles permettent d'utiliser la carte arduino comme source d'alimentation (ce que nous ferons dans la 2e partie de la session).

La pin *Vin* permet d'alimenter la carte sans passer par le port USB ou le connecteur Jack et le régulateur. On peut par exemple alimenter la carte en utilisant la pin 5V d'une autre carte.

Finalement la pin *GND (ground)* fournis 0V. C'est ce qu'on appel la **masse** de la carte, ce qui peut être comparé à la borne **-** d'une pile.  
Vous remarquerez qu'il y a plusieurs pins *GND*. Celà ne veut pas dire qu'il y a différentes **masses** mais que ces pins sont connectées entre elles à l'interrieur de la carte. Il est fréquent de retrouver plusieurs fois la même connection sur une carte électronique pour des question de facilité de câblage.

**Les entrées/sorties digitales :**  
![boardpindig](https://user-images.githubusercontent.com/29465741/27265004-99ff2810-548c-11e7-8a6b-3a4c4a5395a0.png)

Ce sont nos fameuses pins qui permettent d'interragir avec le monde exterieur. Elles peuvents êtres configurée soit en entrée soit en sortie.  
Lorsqu'une pin est configurée en entrée, elle permet l'acquisition de donnée comme par exemple la température d'un capteur de température.  
Lorsqu'une pin est configurée en sortie, elle permet de controler des éléments exterieurs à la carte comme par exemple faire clignoter une led ou contrôler un moteur.

Contrairement aux inscription de la carte, **toutes** les pins encadrée sont des entrées/sorties digitales.
Je m'explique! Sur la figure suivante vous pouvez voir en bleu claire toutes les pins digitales de la carte et vous constaterez que même les pins *ANALOG IN* sont en bleu claire.  
![boardpinout](https://user-images.githubusercontent.com/29465741/27265163-c547f296-5490-11e7-964b-2cf12ee31478.png)  
Celà s'explique par le fait que certaines pins digitales ont d'autres fonctionnalités supplémentaire.  
En effet les pins 14 à 19 peuvent en effet être utilisée comme entrée analogique d'où l'inscription *ANALOG IN* sur la carte Arduino (nous reviendrons plus tard sur la différence entre le digitale et l'analogique).

Le mystère est résolut! Gardez votre attention sur la pin 19, vous verrez écrit en jaune PC5. Nous en aurons besoin pour la suite.

NB: Vous remarquerez que les pins 18 et 19 sont en deux exemplaire (en bas à gauche et en haut à droite). Celà signifies qu'elle sont connectées respectivement ensemble, tout comme les pins *GND*.

**Encore plus loin !**

Interessont nous cette fois au microcontroleur. En le penchant légèrement, vous pouvez lire *ATMEGA328*.  
Cette inscription est la référence du microcontroleur. En regardant sur sa fiche technique, vous trouverez le nom de ses broches ainsi que leurs fonctionnalités suplémentaire.  
![atmega328-pinout](https://user-images.githubusercontent.com/29465741/27265358-7bb407ec-5494-11e7-9eae-e9310e44e6b3.png)  
Regardez le nom de la première pin de droite.  
Une senstion de dèjà vu?  
Et oui, celà veut dire que la broche PC5 du microcontroleur et directement connecté à la pin 19 de la carte Arduino.
Vus pouvez voir les lettres *ADC* à coté de la proche PC5,ce qui correspond à *Analog to Digital Converter*. Celà veut dire que cette broche peut fonctionner en entrée analogique. La boucle est bouclée.

Petite astuce avant de conclure la première partie de la session. Vous avez sans doute remarquez le petit creux et le point en haut à gauche du microcontroleur. Ce sont des repères visuel pour distinguer le sens de celui-ci.

**En résumé :**

Après avoir analysé la carte en détails nous pouvons en conclure qu'une carte arduino est simplement l'extension d'un microcontroleur dont l'accès aux broches a été facilité et qui contient, en plus des leds témoins et de l'interface de communication USB, un circuit d'alimentation.

---
# Notions de base en électronique.
---

#### À vous de jouer !
 
**Cliquez ici pour ma solution**
 

---
# Conclusion :
---



### Conseils et astuces :



---
# Exercice complémentaire :
---


--- 
Sources :  
https://www.youtube.com/channel/UCVqx3vXNghSqUcVg2nmegYA  
Iconographie :  
https://libraries.io/github/Bouni/Arduino-Pinout
http://boutique.semageek.com/fr/2-arduino-uno-dip-rev3-8058333490090.html  
http://www.i-am-bored.com/2014/04/captain-obvious-to-the-rescue-pic.html
https://fr.dreamstime.com/photo-stock-r%C3%A9sistance-%C3%A9lectronique-image48668083


 
 
