
# Session #2: 
# Un bouton pour les gouverner tous.
# Et la lumière fut. 
---

### Au Programme:  

1. Les boutons poussoirs.  
  - Présentation des boutons poussoirs.  
  - Comment câbler?
  - Comment programmer? 
  - Mise en pratique:
    - Allumer une led.
    - Lancer un compteur. 
2. Les signaux PWM.  
  - Présentation des signaux PWM.   
  - Comment programmer?
  - Mise en pratique:   
    - Faire varier la luminausité d'une led.
3. Les Leds RGB.  
  - Présentation des Leds RGB : 
  - Comment câbler?  
  - Comment programmer?
  - Mise en pratique:   
    - Obtenir 3 couleurs.
    - Obtenir 7 couleurs. 

### Durée: **?**
 
### Pré-requis:  
- avoir suivis les sessions précédentes.
- savoir cabler et utiliser une led.
- savoir afficher un message sur le moniteur série.
 
### Matériel:  
-Une carte Arduino Uno   
-Un cable USB type AB   
-Quelques leds 5mm de diamètre    
-Quelques résistances   
-Quelques boutons poussoirs  
-Une led RGB  
-Une breadboard

---
# 1. Les boutons poussoirs:
---

## 1.1 Présentation des boutons poussoirs.

Une fois n'est pas coutume, je vous propose de visionner cette courte vidéo de présentation:  
https://www.youtube.com/watch?v=9f9KYO8Hzzg  

Un bouton poussoir est un composant permettant de réaliser un contact électrique. Lorsque le bouton est appuyé, il crée un contact entre ses 2 bornes permettant ainsi le passage du courant; on parle alors de circuit fermé et de circuit ouvert lorsque le boutonn'est pas appuyé.

Autres symboles que celui utilisé dans la vidéo :

![bpsymb](https://user-images.githubusercontent.com/29465741/30281691-608aae00-9713-11e7-822b-46e4aa79415f.png)

## 1.2 Comment câbler?

Comme expliqué précédement, un bouton pousoir est un *pont* entre deux point du circuit mais vous remarquerez vite que le composant que vous avez en mains n'a pas 2 mais 4 pins...

![4b5228f476a13f023e30147a1eb70f4a--funny-internet-memes-funny-memes](https://user-images.githubusercontent.com/29465741/29925761-a8adc010-8e61-11e7-91c6-5d532c0283fb.jpg)

Pas de panique, tout s'explique !!!  

La présence de pins au lieu de 2 permet une meilleurs résistance mécanique lorsque ces composants sont soudés sur une carte électronique. Les pins sont connectées 2 par 2 à l'interieur du composant.

![bp](https://user-images.githubusercontent.com/29465741/30281444-bae3993a-9712-11e7-938d-0286175f45ac.png)

Pour détecter les paires de pins il vous suffit de faire un test de continuité avec un multimètre. Si vous ne savez pas comment vous servir d'un multimètre ou tout simplement si vous n'en posédez pas, La meilleur solution est d'utiliser 2 pins qui sont diamétralement opposées pour réaliser votre *pont*.

Une fois les pins repérée, il vous suffit de mettre en série le bouton avec une résistance de 10 KΩ et de connecter le point millieu à une pin de la carte arduino. Lorsque le bouton est enffoncé, le montage envois un niveau haut, c'est à dire une tension de 5V vers la carte Arduino et un niveau bas, donc 0V lorsque le bouton est relaché.

![bpcabl](https://user-images.githubusercontent.com/29465741/30282059-74a4e5b2-9714-11e7-92b0-63065c2cfd99.png)

/!\ En inversant la position du bouton pousoir et de la résistance, on inverse le fonctionnement du montage: un niveau haut est généré lorsque le bouton est relaché et un niveau bas est généré lorsque le bouton est enfoncé. C'est ce qu'on appel travailler en **logique inverse**. Pour la suite des sessions, nous n'utiliserons pas ce type de montage!

/!\ La vidéo précédente vous indique la possibilité d'utiliser les résistances internes de la carte Arduino masi prenez l'habitude d'inclure des résistances dans vos montages!

## 1.3 Comment Programmer?

Avant d'utiliser le bouton pousoir dans un code, il faut dans un premier temps configurer dans le setup la pin de la carte arduino sur laquelle le bouton est connecté.  
Contrairement aux pins sur lesquelles sont connectées les Leds qui sont des sorties, les pins des boutons poussoirs sont des entrées vu qu'elle reçoivent une information au lieu d'en délivrer. Pour celà on utilise l'instruction suivante si vous vous ête branché sur la pin9 :  
```arduino
void setup() 
{
  pinMode(9, INTPUT);   //configuration de la pin 9 en entrée.
} 
```
Tout comme l'instruction **digitalWrite()** qui permet *d'écrire* une valeur sur une sortie, l'instruction **digitalRead()** permet de *lire* une entrée. Néamoins lors d'une lecture, la valeur lue doit être stockée dans une variable si elle n'est pas imédiattement utilisée.  
Si vous vous êtes branché sur la pin 9, la lecture du bouton se fera de la manière suivante:  
```arduino
  MaVariable=digitalRead(9);   //la valeur lue sur la pin 9 est stockée dans MaVariable
```  
De cette manière MaVariable vaudra *HIGH* lorsque le bouton est appuyé et *LOW* lorsqu'il sera relaché.

/!\ N'oubliez pas de déclarer votre variable avant le setup!  
  
```arduino
int MaVariable;   //déclaration de MaVariable

void setup() 
{
  pinMode(9, INTPUT);   //configuration de la pin 9 en entrée.
} 
```


## 1.4 Mise en pratique:

### Allumer une Led  

Réalisez un montage comprenant une led branchée sur la pin 9 de votre carte arduino et un bouton pousoir branché sur la pin 5.

a) Allumez la Led lorsque le bouton est appuyé comme montré dans la vidéo.
  
```arduino
int MaVariable;     //déclaration de MaVariable.
const int Bouton=5; //déclaration du bouton qui sera utilisé sur la pin 5.
const int Led=9; //déclaration de la led qui sera utilisé sur la pin 9.

void setup() 
{
  pinMode(Bouton, INTPUT);  //configuration de la pin 5 en entrée.
  pinMode(Led, OUTPUT);     //configuration de la pin 9 en sortie.
} 

void loop() 
{
  //à remplir.
  
  if (MaVariable==HIGH)
  {
    //à remplir
  }
  else
  {
    //à remplir
  }
}
```
b) Même exercice mais sans utiliser de variable de stockage.

```arduino
int MaVariable;     //déclaration de MaVariable.
const int Bouton=5; //déclaration du bouton qui sera utilisé sur la pin 5.
const int Led=9; //déclaration de la led qui sera utilisé sur la pin 9.

void setup() 
{
  pinMode(Bouton, INTPUT);  //configuration de la pin 5 en entrée.
  pinMode(Led, OUTPUT);     //configuration de la pin 9 en sortie.
} 

void loop() 
{
  //à remplir.
}
```

### Lancer un compteur

a) A l'aide d'un bouton poussoir connecté sur la pin 5, réalisez un compteur s'incrémantant toute les secondes et comptant de 0 à 9 avant de se remettre à zéro. Le compteur devra se lancer lorsqu'on appuis sur le bouton. Affichez la valeur du compteur sur le moniteur 
série à chaque incrémentation. Vous aurez besoin d'un test **if** pour lancer le compteur et d'une boucle **for** pour incrémenter et afficher le compteur.

```arduino
int MaVariable;     //déclaration de MaVariable.
const int Bouton=5; //déclaration du bouton qui sera utilisé sur la pin 5. 

void setup() 
{
  pinMode(Bouton, INTPUT);  //configuration de la pin 5 en entrée.
  serial.begin(9600);
} 

void loop() 
{
  //à remplir.
  
  if (MaVariable==HIGH)
  {
    for(int i=0; i<10; i++)
    {
      //à remplir
    }
  } 
}
```
b) Même exercice mais l'incrémentation devra se faire uniquement **tant que** le bouton est enfoncé. Vous aurez besoin d'une boucle **while** pour réaliser le compteur.

```arduino
int Compteur=0;     //déclaration de Compteur.
const int Bouton=5; //déclaration du bouton qui sera utilisé sur la pin 5. 

void setup() 
{
  pinMode(Bouton, INTPUT);  //configuration de la pin 5 en entrée.
  serial.begin(9600);
} 

void loop() 
{ 
  while (digitalRead(Bouton)==HIGH)
  {
    serial.println(Compteur);
    
    if(Compteur<10)
    {
      //à remplir
    }
    else
    {
      //à remplir
    }
    delay(1000);
  } 
}
```
---
# 2. Les signaux PWM: 
---

## 2.1 Présentation des signaux PWM:

Il y a fort longtemps dans une vidéo de présentation lointaine...  
https://www.youtube.com/watch?v=CSReyYwbGRY  

Comme expliqué dans la vidéo, un signal PWM est un signal qui va être au niveau haut pendant un certain temps puis être au niveau bas avant de se répéter.  
Le rapport cyclique est le temps pendant lequelle le signal est au niveau haut par rapport à la période du signal. Pour un signal se répetant toutesles 10 secondes, le rapport cyclique sera de 0% lorsque le signal n'est jamais au niveau haut, de 50% lorsque le signal est au niveau haut pendant 5 secondes et à 100% lorsque le signal est au niveau haut pendant 10 seconde.

Si on utilise ce signal pour allimenter une led, la led va succesivement s'allumer et s'éteindre. On va alors obtenir un effet de peristance rétiniene comme pour une vidéo.  
Plus le rapport cyclique sera élevé, plus la led paraitra lumineuse et inversement.  

Ce type de signal est aussi utilisé pour controler des moteurs mais ce sera pour une prochaine session...

## 2.2 Comment câbler?

/!\ Toutes les pins de la carte Arduino UNO ne sont pas capables de générer un signal PWM! Seul les pins 3, 5, 6, 9, 10 et 11 peuvent êtres utilisées pour cette appication. Elles sont indiquées sur la carte par un **~** à coté du numéro de pin.

## 2.3 Comment programmer?

Comme nous l'avons vu, un signal PWM est caractérisé par une période et un rapport cyclique. Lors de l'utilisation d'un signal PWM avec une carte Arduino, seul le rapport cyclique doit être paramettré car la carte génere un signal de période fixe propre à la carte.  

L'instruction à utiliser est la suivante:   
```arduino
  AnalogWrite(NumeroDePin,RapportCyclique);
```  

/!\ Le rapport cyclique n'est pas exprimé en %! Il faut réaliser une règle de 3 pour laquelle 100% correspond à 254.

Donc pour générer un signal PWM de rapport cyclique 50% sur la pin 9, il faut utiliser l'instruction suivante:  
```arduino
  AnalogWrite(9,127);
```  

## 2.4 Mise en pratique:

### Faire varier la luminausité d'une led.

Réalisez un montage comprenant une led branchée sur la pin 9 et allumez la de manière progressive (100%) puis l'éteindre de la même façon (0%).
Pour celà vous aurez besoin d'une boucle **for** pour l'allumage et une boucle **for** pour l'extinction. Chaque boucle contient un délais pour temporiser l'incrémentation et la décrémentation. 
A vous de jouer sur la valeur des délais et des pas d'incrémentation pour obtenir une variation fluide.

```arduino

const int Led=9; //déclaration de la led qui sera utilisé sur la pin 9. 

void setup() 
{
  pinMode(Led, OUTPUT);     //configuration de la pin 9 en sortie.
}

void loop() 
{
  for (int i=0;i<255;i=i+5)
  {
    analogWrite(Led, i);
    delay(50);
  }
  
  
  for (int i=255;i>0;i=i-5)
  {
    analogWrite(Led, i);
    delay(50);
  } 
}
```

---
# 2. Les Leds RGB: 
---

## 3.1 Présentation des Leds RGB:

Une Led RGB est une led composée d'une led rouge, verte et bleu en interne dont les cathodes sont communes (ou  anodes en fonction des modèles). Pour rappel l'anode est la borne positive et la cathode est la borne négative!   

Ce seul composant permet de générer 6 couleurs primaires en associant ses 3 leds:

Rouge vert  bleu  couleur  
on    off   off   rouge  
off   on    off   vert  
off   off   off   bleu  
on    on    off   jaune  
on    off   on    mangate  
off   on    on    turquoise  

En jouant sur l'intensitée lumineuse de chaque led, on peut alors obtenir une palette de couleur infinie.

## 3.2 Comment câbler?

Une led RGB est composée de 4 pins dont la plus longue est la cathodes commune (ou anode en fonction des modèles). Les 3 autres sont chacune reliée aux anodes de chaque led. 

Avant de câbler la led RGB il est important de repérer le type de led utilisé ainsi que les pins associée à chaque couleur. Pour celà consultez la fiche technique du composant. 

Une fois la led identifiée, vous pouvez calculer la résistance de série de chaque led mais une résistance 220 ohms par led fera l'affaire.

![fibn3](https://user-images.githubusercontent.com/29465741/30280947-5b86567c-9711-11e7-8f23-55729035ef9f.png)


## 3.3 Comment programmer?

Comme dit plus tôt, une led RGB est une led composée de trois leds. Celà revient donc à controler individuellement 3 leds.

Controle on/off pour cathode commune:

 ```arduino
 digitalWrite(LedR,LOW);    //led rouge éteinte
 digitalWrite(LedG,LOW);    //led verte éteinte
 digitalWrite(LedB,HIGH);   //led bleu allumée
 ```

Controle PWM pour cathode commune:

 ```arduino
 analogWrite(LedR,128);   //led rouge à 50%
 analogWrite(LedG,254);   //led verte à 100%
 analogWrite(LedB,0);     //led bleu à 0%
 ```
 
 /!\ Une Led RGB à anode commune fonctionne en inverse elle sera éteinte pour digitalWrite(LedR,HIGH) et analogWrite(LedR,254).

## 3.4 Mise en pratique:

Branchez respectivement la led rouge, verte et bleu sur les pins 9, 10 et 11. Connectez la longue pin sur la masse pour une led RGB à cathode commune et sur le 5V pour une anode commune. N'oubliez pas d'intégrer une résistances en série de 220 ohms pour chacune des leds!

### Obtenir 6 couleurs en on/off: 

Faites variez la couleur de la led RGB toute les secondes en utilisant l'instruction digitalWrite.

```arduino 
const int LedR=9; //déclaration de la led rouge qui sera utilisé sur la pin 9. 
const int LedG=10; //déclaration de la led verte qui sera utilisé sur la pin 10. 
const int LedB=11; //déclaration de la led bleu qui sera utilisé sur la pin 11. 

void setup() 
{
  pinMode(LedR, OUTPUT);     //configuration de la pin 9 en sortie.
  pinMode(LedG, OUTPUT);     //configuration de la pin 10 en sortie.
  pinMode(LedB, OUTPUT);     //configuration de la pin 11 en sortie.
} 

void loop() 
{ 
  digitalWrite(LedR,HIGH);
  digitalWrite(LedG,LOW);
  digitalWrite(LedB,LOW);
  delay(1000);
  
  digitalWrite(LedR,LOW);
  digitalWrite(LedG,HIG);
  digitalWrite(LedB,LOW);
  delay(1000);
   
  //à remplir
}
```


### Obtenir 6 couleurs en PWM: 

Faites variez la couleur de la led RGB toute les secondes en utilisant l'instruction analogWrite.

```arduino 
const int LedR=9; //déclaration de la led rouge qui sera utilisé sur la pin 9. 
const int LedG=10; //déclaration de la led verte qui sera utilisé sur la pin 10. 
const int LedB=11; //déclaration de la led bleu qui sera utilisé sur la pin 11. 

void setup() 
{
  pinMode(LedR, OUTPUT);     //configuration de la pin 9 en sortie.
  pinMode(LedG, OUTPUT);     //configuration de la pin 10 en sortie.
  pinMode(LedB, OUTPUT);     //configuration de la pin 11 en sortie.
} 

void loop() 
{ 
  analogWrite(LedR,254);
  analogWrite(LedG,0);
  analogWrite(LedB,0);
  delay(1000);
  
  analogWrite(LedR,0);
  analogWrite(LedG,254);
  analogWrite(LedB,254);
  delay(1000);
   
  //à remplir
}
```

Sources:

Iconographie:
http://theawesomedaily.com/43-meme-faces-rage-comics-to-finally-explain-you-what-they-all-mean/
http://www.robotshop.com/eu/fr/mini-bouton-poussoir-5pk.html
https://sti2d.ecolelamache.org/norme_elec.png
https://arlontronique.wordpress.com/lecture-dun-encodeur-rotatif-attiny2313-et-assembleur/
https://electronics.stackexchange.com/questions/241446/common-cathode-vs-common-anode-rgb-led
