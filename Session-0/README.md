# Session #0: Premiers pas et logique de programmation.

* Pré-requis: Aucun

* Matériel:  
-Une carte Arduino Uno  
![arduino](https://user-images.githubusercontent.com/29465741/27254447-62f8ec7a-5388-11e7-8e5b-8612e45e7a85.png)  
-Un cable USB type AB  
![usbab](https://user-images.githubusercontent.com/29465741/27254453-8fda0314-5388-11e7-8c57-2a60cd037466.png)

---
# Au commencement...
---
Bravo, vous êtes l'heureux propriétaire d'une carte arduino. Félicitation!!

Et là c'est le moment où vous vous dites "Ok... Et maintenant j'en fais quoi de mon bout de plastique bleu?"  

Pas de panique! je vous conseil de visionner cette vidéo dans un premier temps.  
https://www.youtube.com/watch?v=A84Mtf9-Thc  
Attention !!! la vidéo date de 2015, le logiciel et les codes exemples présentés peuvent ne pas correspondre à la version actuelle.  
Pour cette première session le *prototype shield* n'est pas nécessaire.

Une fois votre carte arduino en main, la première étape est de télécharger le logiciel arduino sur le lien suivant:  
https://www.arduino.cc/en/Main/Software  
Le Logiciel en entièrement gratuit, sur la page suivante cliquez sur **JUST DOWNLOAD** et le téléchargement débutera.

Une fois le logiciel installé et lancé, le fenetre suivante s'ouvrira. Cette fenetre est l'**IDE** d'arduino ou l'**environement de développement** d'arduino.

![ide](https://user-images.githubusercontent.com/29465741/27223035-167e8f5c-528f-11e7-9b70-f77dd8f65dbe.png)

---
# Premier programme:
---

Pour réaliser notre premier programme, cliquez sur Fichier/Exemple/01.Basics/Blink  
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

Maintenant appuiyez sur le bouton **V** situé en haut à gauche de l'ide. Ce bouton permet de **compiler** le code, c'est à dire de vérifier si il ny a pas d'erreur. A la fin de la compilation, vous recevrez un message en bas de l'ide indiquant qu'il n'y a pas d'erreur; ce qui est le cas vu qu'il s'agit d'un code exemple. 

![v](https://user-images.githubusercontent.com/29465741/27225991-0a7507e6-529d-11e7-9a70-e3747e78837e.png)  
![compilok](https://user-images.githubusercontent.com/29465741/27225999-134c3178-529d-11e7-9eb6-53d7778f52f9.png)

La vérification est faite? Excelent, nous allons pouvoir passer à la suite!

1. Allez sur Outils/Type de carte et selectionnez la carte Arduino/Genuino Uno si ce n'est pas déjà fait.

![typecarteok](https://user-images.githubusercontent.com/29465741/27238641-003b4d0e-52ce-11e7-8ed8-945631701f61.png)

2. Connectez votre carte sur un port USB de votre PC et allez dans Outils/Port et verifiez que COM5(Arduino/Genuino Uno) est sélectionné. Cela signifie que votre carte est bien connectée. Si ce n'est pas le cas, débranchez la carte et répétez l'opération.  
NB: le numéro du COM peut être différent en fonction de votre PC.

![portok](https://user-images.githubusercontent.com/29465741/27238670-126bd49e-52ce-11e7-8823-5e98981b9cec.png)

3. Appuyez sur le bouton **->** situé à coté du bouton **V**. Ce bouton permet de charger le code sur la carte arduino.  
L'ide va recompiler le code avant de le téléverser. Une fois le chargement effectué, vous verrez un message de confirmation dans la fenetre de dialogue.

![tele](https://user-images.githubusercontent.com/29465741/27239065-b0b59170-52cf-11e7-9d29-682dab705137.png)  
![teleok](https://user-images.githubusercontent.com/29465741/27239071-b68cefbc-52cf-11e7-8ed6-3cc062d15a41.png)

Félicitation vous venez programmer votre carte arduino! Vous devez maintenant voir une led clignoté.

![arduino_builtin_led](https://user-images.githubusercontent.com/29465741/27239941-4227401a-52d3-11e7-86c9-880908a9b226.jpg)

---
# Logique de programmation:
---

## 1. Commen fonctionne un code?

Maintenant que nous avons réussis à faire clignoter notre led, interessons nous au code.  
Vous remarquerez que les lignes de codes ont des couleurs différentes. Ces couleurs sont générées automatiquement par l'ide afin d'avoir une lecture du code plus aisée.  
Interessont nous d'abord aux parties de code en gris. Ces lignes sont des commentaires, celà signifie qu'elles n'ont aucune influence sur le code. Leur seul but est d'aider les programmeurs à comprendre un code et à le structurer pour faciliter sa lisibilité.  

Il existe 2 façons de créer un commentaire:  

* Une ligne en commentaire:  
```arduino
//Ligne à mettre en commantaire
```

* Un paragraphe en commentaire:  
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

```arduino
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

Une fois tout les commentaire suprimés, nous allons réorganiser le code pour faciliter sa lecture. Pour celà, nous allons alligner les accolades. Ces accolades permettent de délimiter des blocs de codes. 
Ce que nous venons de faire ne change en rien le fonctionnement du code, pour le vérifier vous pouver enregistrer votre code en le renommant *monPremierProgramme* et le téléverser sur la carte. 
Je vous conseil de prendre l'habitude de commenter vos codes.

```arduino
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

Interessons nous au deuxième bloc de code. On peut remarquer 3 éléments :

1. **void loop()**, c'est ce que nous appelrons pour le moment le *nom* du bloc.  
2. **{}** les deux accolades délimitent le bloc.
3. Les **instrcutions**, ce sont les lignes de codes qui composent le bloc.  
Notez que les lignes d'instructions se terminent d'un **;** contrairement au nom du bloc.

Maintenant que nous savons ce qu'est un bloc regardons comment fonctionne un programme. Pour celà, nous allons analyser le **logigramme** de notre code:

![logigramme](https://user-images.githubusercontent.com/29465741/27247071-fecc3082-52f5-11e7-872c-f4f6f35c6e9d.png)

Un programme est executé de manière séquentielle, ce qui veut dire qu'il execute son code ligne par ligne. 
Lorsque un programme est chargé sur la carte arduino, le programme débute par la première ligne de code.  
Pour notre programme, on commence par le bloc **Setup**. Ce bloc est utilisé pour faire des initalisation, ici la ligne *pinMode(LED_BUILTIN, OUTPUT);* signifie qu'on utilise la pin LED_BUILTIN en *sortie* (nous verrons ce qu'est une sortie à la prochaine session). Une fois cette instruction effectuée, le programme entre dans le bloc **Loop** et effectue l'instruction *digitalWrite(LED_BUILTIN, HIGH);* qui allume la led ensuite *delay(1000);* permet d'attendre 1000 ms soit 1 seconde. Ensuite l'instruction *digitalWrite(LED_BUILTIN, LOW);* qui éteind notre led puis on attend encore 1 seconde avec l'instruction suivante.  Et maintenant il n'y a plus d'instrction alors que faire? Et bien le bloc **Loop** est un bloc particulier qui se répete à l'infini tant que la carte est allimentée. Le programme va donc allumer la led, attendre 1 seconde, éteindre la led, attendre encore 1 seconde et recommence. Si on appuis sur le bouton **reset** de la carte ou si on déconnecte le cable USB et qu'on rebranche la carte, le programme recommence au début, fait son initialisation en entre dans la boucle.

#### A vous de jouer !

* **Changer le temps:**

Maintenant que vous savez comment fonctionne notre code, vous allez pouvoir le modifier. Après avoir commenté votre code vous allez modifier les délais et ainsi changer le temps de clignotement. Une fois les modifications effectuées, téléversez le code et admirez le résultat.

```arduino
void setup()                        //initialisation
{
  pinMode(LED_BUILTIN, OUTPUT);     //configuration de la led en sortie
}

void loop()                         //boucle infinie
{
  digitalWrite(LED_BUILTIN, HIGH);  //allumer la led   
  delay(100);                       //attendre 0,1 s                       
  digitalWrite(LED_BUILTIN, LOW);   //éteindre la led
  delay(1500);                      //attendre 1,5 s
}
```

* **Deux clignotements différents:**

Pour ce deuxième exercice, je vous propose de faire clignoter led rapidement puis lentement. Réalisez votre code avant de regarder ma solution.

```arduino
void setup()                        //initialisation
{
  pinMode(LED_BUILTIN, OUTPUT);     //configuration de la led en sortie
}

void loop()                         //boucle infinie
{
  digitalWrite(LED_BUILTIN, HIGH);  //allumer la led   
  delay(100);                       //attendre 0,1 s                       
  digitalWrite(LED_BUILTIN, LOW);   //éteindre la led
  delay(1500);                      //attendre 1,5 s
  
  digitalWrite(LED_BUILTIN, HIGH);  //allumer la led   
  delay(1000);                       //attendre 1 s                       
  digitalWrite(LED_BUILTIN, LOW);   //éteindre la led
  delay(1500);                      //attendre 1,5 s
}
```

## 2. Tests et boucles:
---

Les tests et les boucles sont les bases fondamentale de la programmation, c'est garce à eux que les programmeurs peuvent créer des algorythmes complexes.

Avant d'aborder ces notions, nous allons aborder deux notion qui sont les variable et les comparateurs logiques.

Une variable est une zone mémoire à laquelle on donne un nom et qui comporte une valeur. Cette valeur pourra ensuite être modifiée ou utilisée.  
Pour utiliser une variable il faut la **déclarer** et l'initaliser. La déclaration permet d'indiquer au programme qu'une variable existe dans le code. 

La déclaration et l'initialisation d'une variable s'effectue avent le setup de la manière suivante:

```arduino

int a=0;                            //déclaration d'une variable que s'appel 'a' à laquel on a affecté la valeur 0

void setup()                        //initialisation
{
  pinMode(LED_BUILTIN, OUTPUT);     //configuration de la led en sortie
}
```


Un comparateur logique est une comparaison entre 2 variable ou une variable et une valeur fixe.
* x == y (x est égal à y)  
* x != y (x est différent de y)  
* x < y (x est inférieur à y)  
* x > y (x est supérieur à y)  
* x <= y (x est inférieur ou égal à y)  
* x >= y (x est supérieur ou égal à y)  
!!ne pas confondre **=** qui est une affectation et **==** qui est une comparaison!!

**2.1. Les tests:**

Un test peut être considéré comme une question dont la réponse peut uniquement être oui ou non: 
Si je vous dis *êtes vous une femme?* vous me réponderez par soit *oui, je suis une femme* ou *non, je suis un homme*.

En programmation, un test est contitué d'une **condition** et peut se lire 'Si la condtion est vérifiée alor le test est vrais'.
Ce type de test est un test **if**

![if](https://user-images.githubusercontent.com/29465741/27248948-49af3846-530b-11e7-931f-65b3e3cef486.png)
```arduino
if(a<5)     //est ce que a est plus petit que 5?
{
  //Faire quelque chose
}
```

Le deuxième type de test est **if else** et permet de faire une autre action si la condition du test n'est pas respectée.  
![ifelse](https://user-images.githubusercontent.com/29465741/27249084-6de1405e-530d-11e7-95bd-b7aa3bfae0f5.png)
```arduino
if(a>5)     //est ce que a est plus grand que 5?
{
  //Faire quelque chose
}
else
{
  //Faire autre chose
}
```
Nous pouvons réaliser deux tests à la suite si besoin.  
![ififelse](https://user-images.githubusercontent.com/29465741/27249226-b8e3aee0-5310-11e7-9e4e-e402347e4a0d.png)
```arduino
if(a>5)     //est ce que a est plus grand que 5?
{
  //Faire quelque chose
}
if(a>3)     //est ce que a est plus grand que 3?
{
  //Faire quelque chose d'autre
}
else        //autrement
{
  //Faire autre chose
}
```
Enfin, il existe un troisième type de test qui permet de faire des tests en cascade. Ce test est le test **if else if else** qui peut se traduire par 'Si... sinon si... autrement...'.  
![ifelseifelse](https://user-images.githubusercontent.com/29465741/27249305-6156fc8e-5312-11e7-872f-87921a708eb5.png)
```arduino
if(a>5)          //est ce que a est plus grand que 5?
{
  //Faire quelque chose
}
else if(a>3)     //si a n'est pas plus grand que 5 est ce que a est plus grand que 3?
{
  //Faire quelque chose d'autre
}
else             //autrement
{
  //Faire autre chose
}
```

** 2. La boucle 'tant que':**

Une boucle **tant que** est constitué d'un test, la condition de ce test est vrais alors le programme rentre dans une boucle qui se répete tant que la condition est vérifiée.
![while](https://user-images.githubusercontent.com/29465741/27249491-25728684-5317-11e7-93c3-3a698eeba0d4.png)
```arduino
a=0;                //affecter la valeur 0 à la variable 'a'
while(a<5)          //est ce que 'a' est plus petit que 5?
{
  //Faire quelque chose
  a=a+1;            //augmenter la valeur de 'a' de 1
} 
```

Vous pouvez remarquer une nouvelle instruction *a=a+1* qui permet d'augmenter la valeur de *a* de 1. Celà s'appel une incrémentation  
L'inverse est appelé une décrémentation et est noté *a=a-1*.  
L'incrémentation et la décrémentation permet de réaliser des compteur. Dans notre exemple, on initialise *a* à zéro avant de rentrer dans la boucle. Une fois le test effectué, on *fait quelque chose* et on incrémente ensuite la valeur de *a* qui vaudra alors 1 avant de repasser le test.  
De cette manière on passera 5 fois dans la boucle (0, 1, 2, 3, 4 sont plus petit que 5). Lors du 5é passage la valeur de *a* passera à 5 après l'incrémentation, le test ne sera alors plus valide et le programme quittera alors la boucle.

NB: En programmation, il existe un racourcis d'écriture pour l'incrémentation et la décrémentation qui sont a++ et a--.

** 3. La boucle 'jusqu'à ce que':**

La boucle **jusqu'à ce que** est un dérivé de la boucle **tant que** qui initialise automatiquement la variable à incrémenter lorsqu'on rentre dans la boucle et qui l'incrémente à chaque fin de cycle.

![for](https://user-images.githubusercontent.com/29465741/27249694-a9411a62-531b-11e7-943d-a6db7a912de5.png)
```arduino
for(a=0; a<5;a ++)          //est ce que 'a' est plus petit que 5?
{
  //Faire quelque chose
} 
```

Vous remarquerez que la condition du test est différentes des conditions rencontrée jusqu'à présent. Cette notation est propre aux boucles **jusqu'à ce que**.  
La condition est composée de 3 éléments séparés par un **;**  
* **a=0** initialise la valeur de *a* à zéro lorsqu'on entre dans la boucle.  
* **a<5** fixe la condition pour rester dans la boucle.
* **a++** fixe le pas d'incrémentation à la fin de chaque cycle, si nous mettions a=a+2 alors la valeur de *a* serait incrémenté de 2 à la fin de chaque cycle.

D'où vient l'appellation **jusqu'à ce que**? Ce type de boucle peut être lut de la manière suivante:  
'En initialisant mon compteur à zéro, j'incrémente le compteur de 1 à la fin de chaque cycle jusqu'à ce que ma condition ne soit plus respectée'.

** 4. La boucle 'do while':**

Cette boucle est une variante de la boucle **tant que**. La diférence est la place du test. Le test est réalisé à la fin de la boucle. De cette manière, les instruction de la boucle sont effectuée au moins une fois même si le test n'est pas valide.  
Ce type de boucle est très peu utilisé.  
![dowhile](https://user-images.githubusercontent.com/29465741/27249883-a38c705e-531f-11e7-8c03-4ab73e535be6.png)
```arduino
a=0;
do
{
  //Faire quelque chose
} while (a>5);
```

!! il y a un **;** après le while pour cette boucle !!

### A vous de jouer:

Félicitation, vous avez maintenant les outils nécéssaires pour réaliser un programme.  
Maitrisez les boucles et tests grâce à quelques exercices afin de terminer cette session.

1. Faites 5 clignotements rapides suivis de 3 clignotements lents à l'aide d'une boucle while.

2. Faites 5 clignotements rapides suivis de 3 clignotements lents à l'aide d'une boucle for.

3. Arretez le clignotement apèrs 5 clignotement rapide à l'aide d'un test if.

3. Arretez le clignotement apèrs 5 clignotement rapide suivi de 2 clignotement lent à l'aide d'un test if/else.

3. Arretez le clignotement apèrs 5 clignotement rapide suivi de 2 clignotement lent et 3 clignotement rapide   
à l'aide d'un test if/else if/ else.

Bibliographie et iconographie:  
https://www.youtube.com/channel/UCVqx3vXNghSqUcVg2nmegYA  
http://learn.acrobotic.com/tutorials/post/arduino-activity-01-blink-led  
http://www.mysti2d.net/polynesie/SIN/08/ServoLent/files/documents/Revision/Branchements.pdf
