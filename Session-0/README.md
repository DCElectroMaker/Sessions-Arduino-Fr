# Session #0

## Au commencement...

Bravo, vous êtes l'heureu propriétaire d'une carte arduino. Félicitation!!

Et là c'est le moment où vous vous dites "Ok... Et maintenant j'en fais quoi de ce bout de plastique bleu?"  

Pas de panique! je vous conseil de visionner cette vidéo dans un premier temps.  
Attention !!! la vidéo date de 2015, le logiciel et les codes exemples présentés peuvent ne pas correspondre à la version actuelle.  
Pour cette première session le *prototypr shield* n'est pas nécessaire.

https://www.youtube.com/watch?v=A84Mtf9-Thc

Une fois votre carte arduino en main, la première étape est de télécharger le logiciel arduino sur le lien suivant:  
https://www.arduino.cc/en/Main/Software  
Le Logiciel en entièrement gratuit, sur la page suivante cliquez sur **JUST DOWNLOAD** et le téléchargement débutera.

Une fois le logiciel installé et lancé, le fenetre suivante s'ouvrira. Cette fenetre est l'**IDE** d'arduino ou l'**environement de développement** d'arduino.

![ide](https://user-images.githubusercontent.com/29465741/27223035-167e8f5c-528f-11e7-9b70-f77dd8f65dbe.png)

## Premier programme:

Pour réaliser notre premier programme, vous allez cliquer sur Fichier/Exemple/01.Basics/Blink  
![clicblink](https://user-images.githubusercontent.com/29465741/27224076-9702bb36-5293-11e7-89e1-de6c9e86ec05.png)

Le texte suivant va apparaitre dans l'ide. Ce texte est notre programme ou code. Il va permettre de faire clignoter une led située sur la carte arduino.  Pour le moment nous n'allons pas nous attarder su le programme.
```arduino
/*
  Blink
  Turns on an LED on for one second, then off for one second, repeatedly.

  Most Arduinos have an on-board LED you can control. On the UNO, MEGA and ZERO 
  it is attached to digital pin 13, on MKR1000 on pin 6. LED_BUILTIN is set to
  the correct LED pin independent of which board is used.
  If you want to know what pin the on-board LED is connected to on your Arduino model, check
  the Technical Specs of your board  at https://www.arduino.cc/en/Main/Products
  
  This example code is in the public domain.

  modified 8 May 2014
  by Scott Fitzgerald
  
  modified 2 Sep 2016
  by Arturo Guadalupi
  
  modified 8 Sep 2016
  by Colby Newman
*/


// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(LED_BUILTIN, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(1000);                       // wait for a second
  digitalWrite(LED_BUILTIN, LOW);    // turn the LED off by making the voltage LOW
  delay(1000);                       // wait for a second
}
```
**Code Blink**

Maintenant appuiyez sur le bouton **V** situé en haut à gauche de l'ide. Ce bouton permet de **compiler** le code, c'est à dire de vérifier si il ny a pas d'erreur. A la fin de la compilation, vous devrez recevoir un message en bas de l'ide indiquant qu'il n'y a pas d'erreur; ce qui est le cas vu qu'il s'agit d'un code exemple. 

![v](https://user-images.githubusercontent.com/29465741/27225991-0a7507e6-529d-11e7-9a70-e3747e78837e.png)  
![compilok](https://user-images.githubusercontent.com/29465741/27225999-134c3178-529d-11e7-9eb6-53d7778f52f9.png)

La vérification est faite? Excelent, nous allons pouvoir passer à la suite!

1. Allez sur Outils/Type de carte et selectionnez la carte Arduino/Genuino Uno si ce n'est pas déjà fait.

![typecarteok](https://user-images.githubusercontent.com/29465741/27238641-003b4d0e-52ce-11e7-8ed8-945631701f61.png)

2. Connectez votre carte sur un port USB de votre PC et allez dans Outils/Port et verifiez que COM5(Arduino/Genuino Uno) est sélectionné. Cela signifie que votre carte est bien connectée. Si ce n'est pas le cas, débranchez la carte et répétez l'opération.  
NB: le numéro du COM peut être différent en fonction de votre PC.

![portok](https://user-images.githubusercontent.com/29465741/27238670-126bd49e-52ce-11e7-8823-5e98981b9cec.png)

3. Appuyez sur le bouton **->** situé à coté du bouton **V**. Ce bouton permet de charger le code sur la carte arduino.  
L'ide va recompiler le code avant de le téléverser. Une fois le chargement vous vérez un message de confirmation dans la fenetre de dialogue.

![tele](https://user-images.githubusercontent.com/29465741/27239065-b0b59170-52cf-11e7-9d29-682dab705137.png)  
![teleok](https://user-images.githubusercontent.com/29465741/27239071-b68cefbc-52cf-11e7-8ed6-3cc062d15a41.png)

Félicitation vous venez programmer votre carte arduino! Vous devez maintenant voir une led clignoté.

![arduino_builtin_led](https://user-images.githubusercontent.com/29465741/27239941-4227401a-52d3-11e7-86c9-880908a9b226.jpg)

## Logique de programmation:

Maintenant que nous avons réussis à faire clignoter notre led, interessons nous au code.  
Vous remarquerez que les lignes de codes ont des couleurs différentes. Ces couleurs sont générées automatiquement par l'ide affin d'avoir une lecture du code plus aisée.  
Interessont nous d'abord aux parties de code en gris. Ces lignes sont des commentaires, celà signifie qu'elles n'ont aucune influence sur le code. Leur seul but ai d'aider les programmeurs à comprendre un code et à le structurer pour faciliter sa lisibilité.  

Il existe 2 façons de créer un commentaire:  

1. Mettre une ligne en commentaire:  
```arduino
//Ligne à mettre en commantaire
```

2. Mettre un paragraphe en commentaire:  
```arduino
/*  
paragraphe  
à  
mettre  
en  
commentaire  
*/
```
Je vous conseil de prendre l'habitude de commenter votre code mais pour notre analyse nous allons supprimer tout les commentaire du programme **BLINK** pour garder l'essentiel du code.

```
void setup() {
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop() {
  digitalWrite(LED_BUILTIN, HIGH);   
  delay(1000);                       
  digitalWrite(LED_BUILTIN, LOW);    
  delay(1000);                       
}
```

Une fois tout les commentaire suprimé, nous allons réorganiser le code pour faciliter sa lecture. Pour celà, nous allons alligner les accolades. Les accolades permettent de délimiter des blocs de codes. Ce que nous venons de faire ne change en rien le fonctionnement du code. Je vous conseil de prendre cette habitude pour organiser vos codes.

```
void setup() 
{
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop() 
{
  digitalWrite(LED_BUILTIN, HIGH);   
  delay(1000);                       
  digitalWrite(LED_BUILTIN, LOW);    
  delay(1000);                       
}
```

Interessons nous au deuxième bloc de code. On peut remarquer 3 élément :

1. **void loop()** c'est ce que nous appelrons pour le moment le *nom* du bloc.  
2. **{}** les deux accolades délimitent le bloc.
3. Les **instrcutions** ce sont les lignes de codes qui composent le bloc. Notez que les lignes d'instructions se terminent d'un **;** contrairement au nom du block.


Bibliographie et iconographie:  
https://www.youtube.com/channel/UCVqx3vXNghSqUcVg2nmegYA  
http://learn.acrobotic.com/tutorials/post/arduino-activity-01-blink-led  
