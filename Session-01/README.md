
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
  - La loi d'ohm
  - Les montages série  
  - Les montages parallèle  
  - La *planche à pain*
  - La Led
  - Mise en pratique   
    - Allumer une led.
    - Faire clignoter une led.
    - Faire clignoter deux leds.

### Durée: **?**
 
### Pré-requis:  
- avoir quelques notions de base en mathématique (savoir lire une équation).
- savoir charger un programme sur la carte Arduino.
 
### Matériel:  
-Une carte Arduino Uno  
![arduino](https://user-images.githubusercontent.com/29465741/27254447-62f8ec7a-5388-11e7-8e5b-8612e45e7a85.png)  
-Un cable USB type AB  
![usbab](https://user-images.githubusercontent.com/29465741/27254453-8fda0314-5388-11e7-8c57-2a60cd037466.png)  
-Quelques leds 5mm de diamètre 
![led](https://user-images.githubusercontent.com/29465741/27261760-dcb38202-5449-11e7-8d24-9cc7d96db89c.png)  
-Quelques résistances  
![resistances](https://user-images.githubusercontent.com/29465741/27261781-5069832c-544a-11e7-8496-076269d5d1c1.png)  
-Une breadboard  
 ![bread](https://user-images.githubusercontent.com/29465741/27311643-934b8e56-5562-11e7-8421-d89f169b38d3.png)  


 
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

* **Les pins d'alimentation :**  
![boardpower](https://user-images.githubusercontent.com/29465741/27264816-d7ec7c72-5487-11e7-8d4a-341b37b6b732.png)

Les pins *3.3V* et *5V* fournissent respectivement 3,3V et 5V.  
![obvious](https://user-images.githubusercontent.com/29465741/27264867-39125944-5489-11e7-85bb-32c7d2de9f6e.png)  
Elles permettent d'utiliser la carte arduino comme source d'alimentation (ce que nous ferons dans la 2e partie de la session).

La pin *Vin* permet d'alimenter la carte sans passer par le port USB ou le connecteur Jack et le régulateur. On peut par exemple alimenter la carte en utilisant la pin 5V d'une autre carte.

Finalement la pin *GND (ground)* fournis 0V. C'est ce qu'on appel la **masse** de la carte, ce qui peut être comparé à la borne **-** d'une pile.  
Vous remarquerez qu'il y a plusieurs pins *GND*. Celà ne veut pas dire qu'il y a différentes **masses** mais que ces pins sont connectées entre elles à l'interrieur de la carte. Il est fréquent de retrouver plusieurs fois la même connection sur une carte électronique pour des question de facilité de câblage.

* **Les entrées/sorties digitales :**  
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

Avant d'aller plus loin, il est primordial d'aborder quelques notions de base en électronique pour vous permettre de réaliser vos premiers montages.

## 1. Courant électrique, tension électrique? qu'est ce que c'est?

Pour répondre à cette question, je ne vais pas réinventer la roue. C'est pourquoi je vous invite à visionner cette vidéo qui vous explique parfaitement ces deux notions.  
https://www.youtube.com/watch?v=4iXh5YD2yOg&t=2s  
Notez que l'unitée de la tension est le volt [V] et celui du courant est l'ampère [A].

/!\ contrairement aux électriciens, les électroniciens ont horreur d'utiliser les générateur de courant. En effet, vous constaterez assez vite qu'en électronique on travail principalement avec des tension. C'est pourquoi je vais vous demander de vous dire que les générateurs de courant *"n'existent pas"*.

## 2. La loi d'ohm :

Base fondamentale de l'électronique, la loi d'ohm est une loi de la physique qui doit être ancrée dans votre mémoire.  Elle permet de connaitre le courant traversant une résistance en connaisant la tension aux borne de celle-ci.

La loi d'ohm nous dit que la tension aux borne d'une résistance est égale au produit du courant qui la traverse et de la valeur de la résistance.  
**U=R.I**

Imaginons une résistance de 100 Ω alimenté par une pile 9V.  
Nous savons que **U=R.I** donc **9=100.I**  
Pour obtenir le courant qui traverse la résistance, il suffit de transformer la formule pour isoler le courtant.  
**U=R.I -> I=U/R**  
Si on reprend notre exemple on aura donc **I=9/100=0,09A** soit **90mA*

## 3. Les montages séries :

Faire un montage en série reviens à monter les composants l'un à la suite de l'autre comme dans la vidéo précédente.

Lorsque plusieurs résistances sont mise en série:
- Le courant traversant chaque résistance est identique.
- La somme des tensions aux bornes de chaque résistance est égale à la tension d'alimentation.
- Plusieurs résistances mises en série peuvent êtres remplacé par une seul résistance équivalante dont la valeur est égale à la somme des résistance. **Rtot=R1+R2+R3**

## 4. Les montages parallèles :

Contrairement aux montages séries, ce type de montage consiste à mettre plusieurs résistances côte à côte.

Imaginez un fleuve qui se sépare en deux rivières avant de se jeter du haut d'une falaise. Les deux chute d'eau créée on donc la même hauteur.  
![cascade](https://user-images.githubusercontent.com/29465741/27310148-7d5e74a0-5558-11e7-82af-b8c704abd4dd.png)  
De la même manière, deux résistances en parallèle auront donc la même tension à leurs bornes.  
![rpara](https://user-images.githubusercontent.com/29465741/27310540-3548b862-555b-11e7-9f3f-62652f9ee37f.png)

Pour se qui est du débit, il se divise lorsque le fleuve se sépare. Celà veut dire que la somme des débits des rivière est égale au dévit du fleuve. Il en va de même lorsque les rivière se rejoignent pour reformer le fleuve après la chute.  
En électronique, lorsqu'une branche se sépare où lorsque plusieurs branches se rejoingent, on obtient ce qu'on appel un noeud.  
Lorsqu'une branche se sépare, la somme des courant sortant du noeud est égale au courant entrant dans le noeud.  
De même, la somme des courants entrant dans un noeud est égale à la somme du courant sortant du noeud lorsque plusieurs branches se rejoignent.

Finalement, plusieurs résistances en parallèle peuvent être remplacées par une seul résistance équivalente dont la valeur se calcule de la manière suivante:  
**1/Rtot=1/R1+1/R2+1/R3**     
Lorsqu'il n'y a que deux résistances en parallèle, la valeur de la résistance équivalente peut s'obtenir d'une autre façon.
**Rtot=(R1.R2)/(R1+R2)

/!\ 1/Rtot est différent de Rtot

#### À vous de jouer !
 
 En guise d'éxercice, je vous propose de regarder cette vidéo qui aborde les notions de mise en parallèle et de mise en série sous une autre approche et qui vous propose des exercices avec correction.  
 https://youtu.be/uSPjmneXnpY?t=4m19s
 
 ## 4. La *planche à pain* :
 
 En électronique, on utilise ce qu'on appel un *breadboard* ou *plaque de prototypage*. Cet outils est une plaque sur laquel on peut réaliser des montages sans devoir souder les composant et qui dispose de connections internnes.  
 ![bread](https://user-images.githubusercontent.com/29465741/27311643-934b8e56-5562-11e7-8421-d89f169b38d3.png)  
La disposition des connections internnes sont faites de façon à pouvoir alimenter facilement un montage et de monter des composants comme des microcontroleurs.  
![breadcon](https://user-images.githubusercontent.com/29465741/27311848-2344dd40-5564-11e7-9302-9a4e0e3e8f9d.png)  
![breadic](https://user-images.githubusercontent.com/29465741/27311854-2a4bfd3a-5564-11e7-8f50-c30581f11a7d.png)
 
 Le saviez vous?
 Historiquement, les premières plaques de prototypage étaient des planche à pain sur lesquelles on plantais des clous et sur lesquels on enroulait des fils de cuivre pour faire les connections.
 
 ## La led :
 
 Une led (ou del en français) est une diode électroluminécente.  
 ![ledschem](https://user-images.githubusercontent.com/29465741/27335790-025ce068-55ce-11e7-99e9-010022bf9b24.png)  
 Les flèches sur le symbole indiquent qu'il s'agit d'une diode qui émet de la lumière.
 
 Comme toute diode, la led a un sens de branchement. Lorsqu'elle est branchée en *passante*, la broche + (ou anode) est branchée sur le potentiel le plus élevé et la broche - (ou cathode) est branchée sur le potentiel le moins élevé. Dans cette configuration, elle laisse passer librement le courant.  
 Si elle est branchée en inverse, elle est dite *bloquante* car elle ne laisse passer aucun courant. Le courant qui la traverse sera donc égale à zéro.
 C'est la présence d'un courant qui la traverse qui crée la lumière dans la led. Il vous faudra donc faire attention à son branchement.  
 ![ancat](https://user-images.githubusercontent.com/29465741/27336536-243de068-55d0-11e7-8f71-e6310a6e9b9b.png)  
 NB: les diodes sont souvant utilisée en mode bloquant pour de nombreuses applications que nous n'aborderons pas ici.
 
 /!\ Une led doit toujours être mis en série avec une résistance pour limiter le courant. Un courant trop élevé va claquer votre led /!\
 
 Caractéristiques:
1. **Couleur:** Les caractéristiques d'une led varient d'une couleur à une autre, ce sera donc la première caractéristique à vérifier.  
2. **Diamètre:** Pour une même couleurs, la tension de seuil et le courant maximal d'une led varie en fonction de son diamètre.  
3. **Tension de seuil:** Même si une led est montée en passant, il faut une tension minimale aux borne de la led qui correspond à la tension de seuil autrement la led ne s'allumera pas. Une fois que la tension de seuil est atteinte, la tension aux bornes de la led sera égale à la tension de seuil. La tensiond'alimentation doit être supperieur à la tension de seuil car la réssistance en série va *pomper* une partie de la tension d'alimenttion.

#### À vous de jouer !

* Pour chaque montage, expliquez pourquoi la led s'allume ou non. La tension de seuil de la led est de 2,1V.

![ledexo1](https://user-images.githubusercontent.com/29465741/27387535-47a1c7f8-5699-11e7-9660-3fb38e50aa4e.png)  

**Solution:**  
**A)** La led ne s'allume pas car elle est montée en sens bloquant, aucun courant ne la traverse et donc elle n'émet pas de lumière. De plus il n'y a pas de résistance en série.  
**B)** Tout comme pour le A) la led reste éteinte car elle est montée en sens bloquant.  
**C)** La led ne s'allume pas car elle n'a pas de résistance en série pour limiter le courant. La led est donc grillée.  
**D)** La led ne s'allume pas car la tension d'allimentation est inferieur à la tension de seuil de la led.  
**E)** La led s'allume car elle est dans le bon sens, elle est en série avec un résistance et a une alimentation suffisament grande.

* Pour une led de 2,1V/20mA alimentée par une source de 5V:  
**A)** Trouvez la tension de la résistance.  
**B)** Trouvez la valeur de la résistance.
/!\ le courant est exprimé en mA, il faudra donc le convertir en A pour vos calculs /!\

**Solution:**
**A)** Les composants sont en série, ce qui veut dire que la somme de leurs tensions est égale à la tension d'alimentation. Connaitssant la tension de la led ainsi que celle de l'alimentation, on peut en déduire que **Ualim=Uled+Ur**.  
En isolant Ur on obtient **Ur=Ualim-Uled**, donc **Ur=5-2,1=2,9V**.  
**B)** Le montage étant en série, le courant parcouru par tout les composant est identique. Nous connaisons donc la tension de la résistance et le courant maximal qui doit la parcourir.  
Il ne reste plus qu'à appliquer la loi d'ohm pour retrouver la valeur de la résistance:  
**Ur=R.I  ->  R=Ur/I  ->  R=2,9/0,02= 145 Ω**

## Mise en pratique:

Vous l'attendiez avec impatience avec cette session lourde en théorie, la pratique !
Mais... Une fois n'est pas coutume, je vous propose cette courte vidéo qui vous permettra de lire la valeur de vos résistances:  
https://www.youtube.com/watch?v=TEAoO9MMG9g

Vous êtes capble de lire une résistance? alors c'est parti!

# 1. Allumer une led :

Nous allons mettre en pratique le dernier exercice sur les leds, pour celà vous aures besion d'une résistance d'au moins 145 Ω, d'une led jaune de 5mm (ou une autre couleurs mais dont les caractéristiques sont 2,1V/20mA), d'une breadboard et d'une carte arduino.  

/!\ La carte arduino nous servira uniquement de source d'alimentation /!\

Réalisez le montage suivant et vous constaterez que la led est allumée une fois la carte arduino alimentée.

**Schéma de câblage à venir**

ça ne fonctionne pas? Pas de panique!  
Les problèmes courants avec ce type de montages sont les suivants:  
- vérifiez si votre montage est bien cablé.
- vérifiez le sens de votre led.  
- vérifiez votre résistance, une résistance trop grande ne permet pas de fournir suffisament de courant pour allumer la led.  
- changez de led, il se peut que la led que vous utilisez est déjà claquée.

ça fonctionne? Félicitation!  
Vous venez de créer un petit montage qui vous permet de tester vos leds et ainsi vérifier si vos leds ne sont pas claquée.

# 2. Faire clignoter une led :

Avant de réaliser le montage, copiez chargez le programme suivant dans votre carte arduino :  
```àrduino
void setup() 
{
  pinMode(4, OUTPUT);   //configuration de la pin 4 en sortie
}

void loop() 
{
  digitalWrite(4, HIGH);  //allumer la led
  delay(1000);            //attendre 1 seconde
  digitalWrite(4, LOW);   //éteindre la led
  delay(1000);            //attendre 1 seconde
}
```

Nous allons ensuite reprendre le montage précédent et brancher l'alimentation de la led sur la pin *4* au lieu de la pin *5V*.  
Une fois le montage réalisé, branchez votre carte pour l'alimenter.

**Schéma de câblage à venir**

Votre led clignote? Félicitation!  
Vous venez de franchir la frontière entre l'électronique et la programmation en controllant un montage à partir de votre carte.

Quelques explications ne seront pas de trop! L'instruction *digitalWrite(4, HIGH);* permet de générer une tension de 5V sur la pin *4*, c'est ce qu'on appel en programmation un **niveau logique haut**. A l'inverse, l'instruction *digitalWrite(4, LOW);* permet de générer une tension de 0V, c'est ce qu'on appel un **niveau logique bas**.  
Vous l'aurez compris, celà permet d'alimenter ou non le montage et donc d'allumer ou non la led.

Nous allons maintenant modifier le code afin qu'il soit plus *propre*.  
- Déclarez une variable et nommez la *Led*.  
- Lors de la déclaration, initialisez la variable avec le numéro de la pin sur laquel est branchée la led.  
- Finalement remplacez dans le code les *4* par *led*. De cette manière, il ne vous reste plus qu'a changer la valeur de *Led* lors de la déclaration si vous branchez votre montage sur une autre pin.
```arduino
int Led=4;  //déclaration de la variable Led dont la valeur est 4

void setup() 
{
  pinMode(Led, OUTPUT);   //configuration de la pin 4 en sortie
}

void loop() 
{
  digitalWrite(Led, HIGH);  //allumer la led
  delay(1000);            //attendre 1 seconde
  digitalWrite(Led, LOW);   //éteindre la led
  delay(1000);            //attendre 1 seconde
}
```  

NB: Si vous branchez votre montage sur la pin *13*, vous remarquez que la led de la carte arduino clignote en même temps que celle de votre montage. Celà est dut au fait que la led de la carte arduino est montée en parallèle à la pin *13* sur votre carte. 

# 3. Faire clignoter deux leds :

Pour faire clignoter deux leds, il vous suffit de réaliser un deuxième montage de led en série avec une résistance et de brancher son alimentation sur une autre pin. 

**Schéma de cablage à venir**

Pour le code, déclarez une deuxième variable dont la valeur est celle de la pin de la deuxième led. Une fois la variable déclarée, il ne vous reste plus qu'a éteindre la deuxième led lorsque la première est allumée et inversement.
```arduino
int Led_1=4;  //déclaration de la variable Led_1 dont la valeur est 4
int Led_2=5;  //déclaration de la variable Led_2 dont la valeur est 5

void setup() 
{
  pinMode(Led_1, OUTPUT);   //configuration de la pin 4 en sortie
  pinMode(Led_2, OUTPUT);   //configuration de la pin 4 en sortie
}

void loop() 
{
  digitalWrite(Led_1, HIGH);  //allumer la première led
  digitalWrite(Led_2, LOW);   //éteindre la deuxième led
  delay(1000);                //attendre 1 seconde 
  
  digitalWrite(Led_1, Low);   //éteindre la première led
  digitalWrite(Led_2, HIGH);  //allumer la deuxième led
  delay(1000);                //attendre 1 seconde
}
```  

---
# Conclusion :
---


Félicitation, vous avez maintenant en moins tout les outils nécésaires pour réaliser vos premiers jeux de leds.
Vous êtes à présent capable de:
* cabler une led.
* controler plusieurs leds. 


### Conseils et astuces :

* **Triez vos composant par type et par valeur**, celà peut vous prendre du temps mais vous évitera plus tard de perdre du temps lors de vos prochains projets. 
* écrivez les valeurs sur vos bandes de résistances.  
* vérifiez vos montages avant de les alimenter.
* vérifiez le sens de vos leds avant de vous dires qu'elles sont claquées.

---
# Exercice complémentaire :
---

Réalisez un chanillard à 8 leds. Aidez vous des boucles apprises lors de la session#0 pour écrir votre code.
Libre à vous d'imaginer vos propre séquences.

Example de chenillard: https://www.youtube.com/watch?v=nflcVYwpXik

--- 
Sources :  
https://www.youtube.com/channel/UCVqx3vXNghSqUcVg2nmegYA  
https://www.youtube.com/channel/UCNDybCEVgyROIXEIeWgp7hA  
https://www.youtube.com/channel/UCKePSV3VZrLFDexdTNh5PTw  
https://www.youtube.com/channel/UCeUpjZW7WywpFxASPRd6FDw  
https://www.youtube.com/channel/UCgD_RoKhcgufgEsuMQxqKtA  
Iconographie :  
https://libraries.io/github/Bouni/Arduino-Pinout  
http://boutique.semageek.com/fr/2-arduino-uno-dip-rev3-8058333490090.html  
http://www.i-am-bored.com/2014/04/captain-obvious-to-the-rescue-pic.html  
https://fr.dreamstime.com/photo-stock-r%C3%A9sistance-%C3%A9lectronique-image48668083  
https://en.wikipedia.org/wiki/Breadboard  
https://zombiebothq.com/challenge-two-signal-box-v2/  
https://electronics.stackexchange.com/questions/211885/why-are-my-components-unconnected-in-the-middle-of-the-breadboard  
http://www.pinsdaddy.com/led-symbol_%7CxMV5OGmMxn2yhHrJJ8lYkUdc54ipx5j%7CQ%7CZ7BxppZ4/  
http://www.pcrc.org.uk/blog/2012/12/16/working_leds_part   
 
