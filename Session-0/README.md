# Session #0: 
# Premiers pas et logique de programmation.

* Durée: 1h
 
* Pré-requis: Aucun
 
* Matériel:  
-Une carte Arduino Uno  
![arduino](https://user-images.githubusercontent.com/29465741/27254447-62f8ec7a-5388-11e7-8e5b-8612e45e7a85.png)  
-Un cable USB type AB  
![usbab](https://user-images.githubusercontent.com/29465741/27254453-8fda0314-5388-11e7-8c57-2a60cd037466.png)
 
---
# Au commencement...
---
Bravo, vous êtes l'heureux propriétaire d'une carte arduino. Félicitations!
 
Et là c'est le moment où vous vous dites "Ok... Et maintenant j'en fais quoi de mon bout de plastique bleu?"  
 
Pas de panique! Je vous conseille de visionner cette vidéo dans un premier temps.  
https://www.youtube.com/watch?v=A84Mtf9-Thc  

/!\ Attention /!\ 

La vidéo date de 2015, le logiciel et les codes exemples présentés peuvent ne pas correspondre à la version actuelle.  
Pour cette première session le *prototype shield* n'est pas nécessaire.
 
Une fois votre carte arduino en main, la première étape est de télécharger le logiciel arduino sur le lien suivant:  
https://www.arduino.cc/en/Main/Software  
Le Logiciel est entièrement gratuit, sur la page suivante cliquez sur **JUST DOWNLOAD** et le téléchargement débutera.
 
Une fois le logiciel installé et lancé, le fenêtre suivante s'ouvrira. Cette fenêtre est l'**IDE** d'arduino ou l'**environnement de développement** d'arduino.
 
![ide](https://user-images.githubusercontent.com/29465741/27223035-167e8f5c-528f-11e7-9b70-f77dd8f65dbe.png)
 
---
# Premier programme:
---
 
Pour réaliser notre premier programme, cliquez sur Fichier/Exemple/01.Basics/Blink  
![clicblink](https://user-images.githubusercontent.com/29465741/27224076-9702bb36-5293-11e7-89e1-de6c9e86ec05.png)
 
Le texte suivant va apparaître dans l'ide. Ce texte est notre programme ou code. Il va permettre de faire clignoter une led située sur la carte arduino.  Pour le moment, nous n'allons pas nous attarder sur le programme.
 
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
 
Maintenant appuyez sur le bouton **V** situé en haut à gauche de l'ide. Ce bouton permet de **compiler** le code, c'est à dire de vérifier s’il n’y a pas d'erreur. À la fin de la compilation, vous recevrez un message en bas de l'ide indiquant qu'il n'y a pas d'erreur; ce qui est le cas vu qu'il s'agit d'un code exemple. 
 
![v](https://user-images.githubusercontent.com/29465741/27225991-0a7507e6-529d-11e7-9a70-e3747e78837e.png)  
![compilok](https://user-images.githubusercontent.com/29465741/27225999-134c3178-529d-11e7-9eb6-53d7778f52f9.png)
 
La vérification est faite? Excellent, nous allons pouvoir passer à la suite!
 
1. Allez sur Outils/Type de carte et sélectionnez la carte Arduino/Genuino Uno si ce n'est pas déjà fait.
 
![typecarteok](https://user-images.githubusercontent.com/29465741/27238641-003b4d0e-52ce-11e7-8ed8-945631701f61.png)
 
2. Connectez votre carte sur un port USB de votre PC et allez dans Outils/Port et vérifiez que COM5(Arduino/Genuino Uno) est sélectionné. Cela signifie que votre carte est bien connectée. Si ce n'est pas le cas, débranchez la carte et répétez l'opération.  
NB: le numéro du COM peut être différent en fonction de votre PC.
 
![portok](https://user-images.githubusercontent.com/29465741/27238670-126bd49e-52ce-11e7-8823-5e98981b9cec.png)
 
3. Appuyez sur le bouton **->** situé à côté du bouton **V**. Ce bouton permet de charger le code sur la carte arduino.  
L'ide va recompiler le code avant de le téléverser. Une fois le chargement effectué, vous verrez un message de confirmation dans la fenêtre de dialogue.
 
![tele](https://user-images.githubusercontent.com/29465741/27239065-b0b59170-52cf-11e7-9d29-682dab705137.png)  
![teleok](https://user-images.githubusercontent.com/29465741/27239071-b68cefbc-52cf-11e7-8ed6-3cc062d15a41.png)
 
Félicitations, vous venez de programmer votre carte arduino! Vous devez maintenant voir une led clignoter.
 
![arduino_builtin_led](https://user-images.githubusercontent.com/29465741/27239941-4227401a-52d3-11e7-86c9-880908a9b226.jpg)
 
---
# Logique de programmation:
---
 
## 1. Comment fonctionne un code?
 
Maintenant que nous avons réussi à faire clignoter notre led, intéressons-nous au code.  
Vous remarquerez que les lignes de codes ont des couleurs différentes. Ces couleurs sont générées automatiquement par l'ide afin d'avoir une lecture de code plus aisée.  
Intéressons-nous d'abord aux parties de code en gris. Ces lignes sont des commentaires, cela signifie qu'elles n'ont aucune influence sur le code. Leur seul but est d'aider les programmeurs à comprendre un code et à le structurer pour faciliter sa lisibilité.  
 
Il existe 2 façons de créer un commentaire:  
 
* Une ligne en commentaire:  
```arduino
//Ligne à mettre en commentaire
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
Je vous conseille de prendre l'habitude de commenter votre code mais pour notre analyse nous allons supprimer tous les commentaire du programme **BLINK** pour garder l'essentiel du code.
 
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
 
Une fois tous les commentaire supprimés, nous allons réorganiser le code pour faciliter sa lecture. Pour cela, nous allons aligner les accolades. Ces accolades permettent de délimiter des blocs de codes. 
Ce que nous venons de faire ne change en rien le fonctionnement du code, pour le vérifier vous pouvez enregistrer votre code en le renommant *monPremierProgramme* et le téléverser sur la carte. 
 
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
 
Intéressons-nous au deuxième bloc de code. On peut remarquer 3 éléments :
 
1. **void loop()**, c'est ce que nous appellerons pour le moment le *nom* du bloc.  
2. **{}** les deux accolades délimitent le bloc.
3. Les **instructions**, ce sont les lignes de codes qui composent le bloc.  
Notez que les lignes d'instructions se terminent d'un **;** contrairement au nom du bloc.
 
Maintenant que nous savons ce qu'est un bloc regardons comment fonctionne un programme. Pour cela, nous allons analyser le **logigramme** de notre code:
 
![logigramme](https://user-images.githubusercontent.com/29465741/27255851-330a012e-53a7-11e7-86e8-3d7e50460449.png)
 
Un programme est exécuté de manière séquentielle, ce qui veut dire qu'il exécute son code ligne par ligne. 
Lorsque un programme est chargé sur la carte arduino, le programme débute par la première ligne de code.  
Pour notre programme, on commence par le bloc **Setup**. Ce bloc est utilisé pour faire des initialisation, ici la ligne *pinMode(LED_BUILTIN, OUTPUT);* signifie qu'on utilise la pin LED_BUILTIN en *sortie* (nous verrons ce qu'est une sortie à la prochaine session). Une fois cette instruction effectuée, le programme entre dans le bloc **Loop** et effectue l'instruction *digitalWrite(LED_BUILTIN, HIGH);* qui allume la led ensuite *delay(1000);* permet d'attendre 1000 ms soit 1 seconde. Ensuite l'instruction *digitalWrite(LED_BUILTIN, LOW);* qui éteint notre led puis on attend encore 1 seconde avec l'instruction suivante.  Et maintenant il n'y a plus d'instruction alors que faire? Et bien le bloc **Loop** est un bloc particulier qui se répète à l'infini tant que la carte est alimentée. Le programme va donc allumer la led, attendre 1 seconde, éteindre la led, attendre encore 1 seconde et recommencer. Si on appuie sur le bouton **reset** de la carte ou si on déconnecte le câble USB et qu'on rebranche la carte, le programme recommence au début, fait son initialisation en entre dans la boucle.
 
#### À vous de jouer !
 
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
 
Pour ce deuxième exercice, je vous propose de faire clignoter la led rapidement puis lentement. Réalisez votre code avant de regarder ma solution.
 
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
 
Les tests et les boucles sont les bases fondamentales de la programmation, c'est grâce à eux que les programmeurs peuvent créer des algorithmes complexes.
 
Avant d'aborder ces notions, nous allons aborder deux notions qui sont les variables et les comparateurs logiques.
 
Une variable est une zone mémoire à laquelle on donne un nom et qui comporte une valeur. Cette valeur pourra ensuite être modifiée ou utilisée.  
Pour utiliser une variable il faut la **déclarer** et l'initialiser. La déclaration permet d'indiquer au programme qu'une variable existe dans le code. 
 
La déclaration et l'initialisation d'une variable s'effectuent avant le setup de la manière suivante:
 
```arduino
 
int a=0;                            //déclaration d'une variable qui s'appel 'a' à laquel on a affecté la valeur 0 
 
void setup()                        //initialisation
{
  pinMode(LED_BUILTIN, OUTPUT);     //configuration de la led en sortie
}
```

/!\ Les variables qu'on utilise pour le moment ne peuvent pas êtres des nombres à virgule, celà fera l'objet d'une prochaine session /!\
 
 
Un comparateur logique est une comparaison entre 2 variables ou une variable et une valeur fixe.
* x == y (x est égal à y)  
* x != y (x est différent de y)  
* x < y (x est inférieur à y)  
* x > y (x est supérieur à y)  
* x <= y (x est inférieur ou égal à y)  
* x >= y (x est supérieur ou égal à y)  
/!\ Ne pas confondre **=** qui est une affectation et **==** qui est une comparaison /!\
 
**2.1. Les tests:** 
---
 
Un test peut être considéré comme une question dont la réponse peut uniquement être oui ou non: 
Si je vous dis *Êtes-vous une femme?* vous me répondrez par soit *Oui, je suis une femme* ou *Non, je suis un homme*.
 
**2.1.1. Le test *IF* :**
 
En programmation, un test est constitué d'une **condition** et peut se lire 'Si la condition est vérifiée, alors le test est vrai'.  
L'exemple suivant montre un code qui fait quelque chose si la variable *a* est plus petite que 5.
 
![if](https://user-images.githubusercontent.com/29465741/27248948-49af3846-530b-11e7-931f-65b3e3cef486.png)
```arduino
if(a<5)     //est-ce que ‘a’ est plus petit que 5?
{
  //Faire quelque chose
}
```
 
 
#### À vous de jouer !
 
Pour cet exercice, je vous propose de déclarer une variable *a* dont vous déciderez de sa valeur d'initialisation.  
Le but du programme est de faire clignoter la led si *a* est plus petit que 5. 
Pour celà, je vous propose le logigramme à utiliser et je vous laisse faire.
**Cliquez ici pour ma solution**
 
NB: attention aux **;** et aux **{}** !!!
 
 
![ifexo](https://user-images.githubusercontent.com/29465741/27255613-c6d7fd08-53a1-11e7-9e61-8ae2ecd18e8e.png)
 
```arduino
int a=3;  //déclaration de 'a' et initialisation de sa valeur
 
void setup()                        //initialisation
{
  pinMode(LED_BUILTIN, OUTPUT);     //configuration de la led en sortie
}
 
void loop()                         //boucle infinie
{
  if(a<5)                           //est ce que 'a' est plus petit que 5?
  {
    digitalWrite(LED_BUILTIN, HIGH);  //allumer la led   
    delay(100);                       //attendre 0,1 s                       
    digitalWrite(LED_BUILTIN, LOW);   //éteindre la led
    delay(100);                       //attendre 0,1 s 
  }
}
```
 
**2.1.2. Le test *IF/ELSE* :**
 
Le deuxième type de test permet de faire une autre action si la condition du test n'est pas respectée.  
Pour cet exemple, si *a* est plus grand que 5 alors on fait *quelque chose*, autrement on *fait autre chose*.
![ifelse](https://user-images.githubusercontent.com/29465741/27249084-6de1405e-530d-11e7-95bd-b7aa3bfae0f5.png)
```arduino
if(a>5)     //est-ce que ‘a’ est plus grand que 5?
{
  //Faire quelque chose
}
else
{
  //Faire autre chose
}
```
 
#### À vous de jouer !
 
L'exercice consiste à créer un programme qui devra faire un clignotement rapide si la variable *a* est plus petite que 5, autrement la led clignotera lentement. Comme pour l'exercice précédent, je vous propose un logigramme et c'est à vous de créer le code.
**Cliquez ici pour ma solution**
 
![ifelseexo](https://user-images.githubusercontent.com/29465741/27255682-39370ac2-53a4-11e7-9a8a-98cf8932deab.png)
 
```arduino
int a=3;  //déclaration de 'a' et initialisation de sa valeur
 
void setup()                        //initialisation
{
  pinMode(LED_BUILTIN, OUTPUT);     //configuration de la led en sortie
}
 
void loop()                         //boucle infinie
{
  if(a<5)                           //est-ce que 'a' est plus petit que 5?
  {
    digitalWrite(LED_BUILTIN, HIGH);  //allumer la led   
    delay(100);                       //attendre 0,1 s                       
    digitalWrite(LED_BUILTIN, LOW);   //éteindre la led
    delay(100);                       //attendre 0,1 s 
  }
  else
  {
    digitalWrite(LED_BUILTIN, HIGH);  //allumer la led   
    delay(500);                       //attendre 0,5 s                       
    digitalWrite(LED_BUILTIN, LOW);   //éteindre la led
    delay(500);                       //attendre 0,5 s
  }
}
```
 
**2.1.3. Deux tests à la suite :**
 
Nous pouvons réaliser deux tests à la suite si besoin.
 
L’exemple suivant teste si *a* est plus grand que 5, si c’est le cas le programme *fait quelque chose* ensuite on teste si *a* est plus grand que 3 et le programme *fait quelque chose d’autre autrement il faut *autre chose*. 
 
![ififelse](https://user-images.githubusercontent.com/29465741/27249226-b8e3aee0-5310-11e7-9e4e-e402347e4a0d.png)
```arduino
if(a>5)     //est-ce que a est plus grand que 5?
{
  //Faire quelque chose
}
if(a>3)     //est-ce que a est plus grand que 3?
{
  //Faire quelque chose d'autre
}
else        //autrement
{
  //Faire autre chose
}
```
#### À vous de jouer !
 
Faites un programme qui se comporte de la manière suivante:  
* Si a est plus grand que 5, la led clignote une fois rapidement puis une fois lentement.
* Si a est compris entre 3 et 5 inclus, la led clignote lentement.
* Si a est plus petit ou égale à 3, la led clignote **très** lentement.  
**Cliquez ici pour ma solution**

![ififelseexo](https://user-images.githubusercontent.com/29465741/27256464-ca9bc65e-53b5-11e7-8852-e7225da47823.png)

```arduino
int a=2;  //déclaration de 'a' et initialisation de sa valeur

void setup()                        //initialisation
{
  pinMode(LED_BUILTIN, OUTPUT);     //configuration de la led en sortie
}

void loop()                         //boucle infinie
{
  if(a>5)                           //est ce que 'a' est plus grand que 5?
  {
    digitalWrite(LED_BUILTIN, HIGH);  //allumer la led   
    delay(100);                       //attendre 0,1 s                       
    digitalWrite(LED_BUILTIN, LOW);   //éteindre la led
    delay(100);                       //attendre 0,1 s 
  }

  if(a>3)                           //est ce que 'a' est plus grand que 3?
  {
    digitalWrite(LED_BUILTIN, HIGH);  //allumer la led   
    delay(500);                       //attendre 0,5 s                       
    digitalWrite(LED_BUILTIN, LOW);   //éteindre la led
    delay(500);                       //attendre 0,5 s 
  }
  else                              //autrement
  {
    digitalWrite(LED_BUILTIN, HIGH);  //allumer la led   
    delay(1500);                       //attendre 1,5 s                       
    digitalWrite(LED_BUILTIN, LOW);   //éteindre la led
    delay(1500);                       //attendre 1,5 s
    
  }
}
```

**2.1.4. Le test *IF/ELSE IF/ELSE* :**

Enfin, le troisième type de test permet de faire des tests en cascade. Contrairement à deux tests *if* à la suite, le premiers test doit être invalide pour passer au test suivant. Un test en cascade peut se lire 'Si... sinon si... autrement...'.  
Dans l'exemple, si *a* est plus grand que 5 on *fait quelque chose* sinon si *a* est plus grand que 3, le programme *fait quelque chose d'autre*. Si aucun des test n'est validé, le programme *fait autre chose*.
![ifelseifelse](https://user-images.githubusercontent.com/29465741/27249305-6156fc8e-5312-11e7-872f-87921a708eb5.png)
```arduino
if(a>5)          //est-ce que ‘a’ est plus grand que 5?
{
  //Faire quelque chose
}
else if(a>3)     //si ‘a’ n'est pas plus grand que 5, est-ce qu’il est plus grand que 3?
{
  //Faire quelque chose d'autre
}
else             //autrement
{
  //Faire autre chose
}
```

#### À vous de jouer !
 
Réalisez un programme qui se comporte de la façon suivante:  
* Si a est plus petit que 3, la led clignote rapidement.
* Si a est compris entre 3 inclus et 5, la led clignote lentement.
* Si a est plus grand ou égale à 5, la led clignote **très** lentement.  
**Cliquez ici pour ma solution**
 
 ```arduino
 int a=4;  //déclaration de 'a' et initialisation de sa valeur

void setup()                        //initialisation
{
  pinMode(LED_BUILTIN, OUTPUT);     //configuration de la led en sortie
}

void loop()                         //boucle infinie
{
  if(a<3)                           //est ce que 'a' est plus petit que 3?
  {
    digitalWrite(LED_BUILTIN, HIGH);  //allumer la led   
    delay(100);                       //attendre 0,1 s                       
    digitalWrite(LED_BUILTIN, LOW);   //éteindre la led
    delay(100);                       //attendre 0,1 s 
  }

  else if(a<5)                           //est ce que 'a' est plus petit que 5?
  {
    digitalWrite(LED_BUILTIN, HIGH);  //allumer la led   
    delay(500);                       //attendre 0,5 s                       
    digitalWrite(LED_BUILTIN, LOW);   //éteindre la led
    delay(500);                       //attendre 0,5 s 
  }
  else                              //autrement
  {
    digitalWrite(LED_BUILTIN, HIGH);  //allumer la led   
    delay(1500);                       //attendre 1,5 s                       
    digitalWrite(LED_BUILTIN, LOW);   //éteindre la led
    delay(1500);                       //attendre 1,5 s
    
  }
}
 ```

**2.2. Les Boucles:** 

Pour aborder les boucles, nous allons apprendre une nouvelle notion qui nous permettra de modifier la valeur d'une variable:

**L'incrémentaton** est le fait d'augmenter la valeur d'une variable.  
Pour l'exemple suivant, la variable *a* a déjà été déclarée. 

```arduino
a=0;
a=a+1;  //a=0+1 donc 'a' vaut 1 après cette instruction
a=a+2;  //a=1+2 donc 'a' vaut 3 après cette instruction
a=a+2;  //a=3+2 donc 'a' vaut 5 après cette instruction
```
En programmation, il existe un raccourcis d'écriture pour l'incrémentation. Écrire *a+=2* reviens à écrire *a=a+2*.  
Il existe néamoins un deuxième raccourcis valable uniquement pour des incrémentations de 1: *a++* reviesn à écrire *a=a+1*.

L'inverse d'une incrémentation  est une décrémentation est s'utilise de la manière suivante: 

```arduino
a=10;
a=a-3;  //a=10-3 donc 'a' vaut 7 après cette instruction
a-=2;   //a=7-2  donc 'a' vaut 5 après cette instruction
a--;    //a=5-1  donc 'a' vaut 4 après cette instruction
```

Ces 2 instructions vous nous permettre de réaliser des compteurs.

**2.2.1. La boucle *WHILE* :** 
 
La boucle **while** est la boucle la plus basique. Elle est constituée d'un test qui permet de rentrer dans la boucle si les conditions du test sont validée. Une fois dans la boucle, le code qu'elle contenu est répété tant que le test est vrais.  
Dans l'exemple, on affecte la valeur zéro à la variable *a* avant de vérifier si *a* est plus petit que 5, ce qui est le cas!  
Après le test, le programme *fait quelque chose* avant d'incrémanter *a* et de refaire le test.  
De cette manière on passera 5 fois dans la boucle (0, 1, 2, 3, 4 sont plus petit que 5). Lors du 5e passage la valeur de *a* passera à 5 après l'incrémentation, le test ne sera alors plus valide et le programme quittera alors la boucle.
![while](https://user-images.githubusercontent.com/29465741/27249491-25728684-5317-11e7-93c3-3a698eeba0d4.png)
```arduino
a=0;                //affecter la valeur 0 à la variable 'a'
while(a<5)          //est-ce que 'a' est plus petit que 5?
{
  //Faire quelque chose
  a=a+1;            //augmenter la valeur de 'a' de 1
} 
```
 
#### À vous de jouer !

Le programme a réaliser doit faire 5 clignotements rapides suivis de 3 clignotements lent.
**Cliquez ici pour ma solution**
 
 ![whileexo](https://user-images.githubusercontent.com/29465741/27257351-a506932e-53d3-11e7-81b8-f5fc3e5d6938.png)
```arduino
 int a=0;  //déclaration de 'a' et initialisation de sa valeur

void setup()                        //initialisation
{
  pinMode(LED_BUILTIN, OUTPUT);     //configuration de la led en sortie
}

void loop()                         //boucle infinie
{
  a=0;                                 //mise à zéro de 'a'
  
  while(a<5)                           //est ce que 'a' est plus petit que 5?
  {
    digitalWrite(LED_BUILTIN, HIGH);  //allumer la led   
    delay(100);                       //attendre 0,1 s                       
    digitalWrite(LED_BUILTIN, LOW);   //éteindre la led
    delay(500);                       //attendre 0,5 s 
    a++;                              //incrémentation de 'a'
  }
  
  a=0;                                 //mise à zéro de 'a'

  while(a<3)                           //est ce que 'a' est plus petit que 3?
  {
    digitalWrite(LED_BUILTIN, HIGH);  //allumer la led   
    delay(500);                       //attendre 0,5 s                       
    digitalWrite(LED_BUILTIN, LOW);   //éteindre la led
    delay(500);                       //attendre 0,5 s 
    a++;                              //incrémentation de 'a'
  }
}
```
 
**2.2.3. La boucle *FOR* :** 
 
La boucle **FOR** est un dérivé de la boucle **WHILE** qui initialise automatiquement la variable à incrémenter lorsqu'on rentre dans la boucle et qui l'incrémente à chaque fin de cycle. Ce type de boucle est utilisée lorsqu'il faut répéter un nombre de fois précis une série d'instruction.  
![for](https://user-images.githubusercontent.com/29465741/27249694-a9411a62-531b-11e7-943d-a6db7a912de5.png)
```arduino
for(a=0; a<5;a ++)          //est-ce que 'a' est plus petit que 5?
{
  //Faire quelque chose
} 
```
 
Vous remarquerez que la condition du test est différente des conditions rencontrées jusqu'à présent. Cette notation est propre aux boucles **FOR**.  
La condition est composée de 3 éléments séparés par un **;**  
* **a=0** initialise la valeur de *a* à zéro lorsqu'on entre dans la boucle.  
* **a<5** fixe la condition pour rester dans la boucle.
* **a++** fixe le pas d'incrémentation à la fin de chaque cycle, si nous mettions a=a+2 alors la valeur de *a* serait incrémentée de 2 à la fin de chaque cycle.
 
#### À vous de jouer !

Pour cet exercice, je vous propose de reprendre l'exercice de la boucle **WHILE** mais en utilisant cette fois une boucle **FOR**.  
**Cliquez ici pour ma solution**
```arduino
 int a=0;  //déclaration de 'a' et initialisation de sa valeur

void setup()                        //initialisation
{
  pinMode(LED_BUILTIN, OUTPUT);     //configuration de la led en sortie
}

void loop()                         //boucle infinie
{
  for(a=0;a<5;a++)   //remettre 'a' à zéro;est-ce que 'a' est plus petit que 5?;incrémenter'a'de 1à la fin de chaque cycle
  {                                   
    digitalWrite(LED_BUILTIN, HIGH);  //allumer la led   
    delay(100);                       //attendre 0,1 s                       
    digitalWrite(LED_BUILTIN, LOW);   //éteindre la led
    delay(500);                       //attendre 0,5 s  
  } 
  
  for(a=0;a<3;a++)  //remettre 'a' à zéro;est-ce que 'a' est plus petit que 3?;incrémenter'a'de 1 à la fin de chaque cycle
  {
    digitalWrite(LED_BUILTIN, HIGH);  //allumer la led   
    delay(500);                       //attendre 0,5 s                       
    digitalWrite(LED_BUILTIN, LOW);   //éteindre la led
    delay(500);                       //attendre 0,5 s  
  }
}
```
 
**2.2.2. La boucle *DO WHILE* :** 
 
Cette boucle est une variante de la boucle **WHILE**. La différence est la place du test qui est réalisé à la fin de la boucle.  
De cette manière, les instructions de la boucle sont effectuées au moins une fois même si le test n'est pas valide.  
![dowhile](https://user-images.githubusercontent.com/29465741/27249883-a38c705e-531f-11e7-8c03-4ab73e535be6.png)
```arduino
a=0;
do
{
  //Faire quelque chose
} while (a>5);
```
 
/!\ il y a un **;** après le while pour cette boucle /!\

### À vous de ... :

Ce type de boucle etant très peu utilisé. Je vous propose de passer à la suite sans faire d'exercice.  

---
# Une instruction bien utile:
---

Avant de conclure cette session, nous allons voir une dernière instruction dont vous ne pourrez plus vous passer !

Cette instruction permet d'afficher du texte sur votre ordinnateur. Pour pouvoir l'utiliser, vous devez écrire *Serial.begin(9600);* comme dernière instruction dans le bloc **Setup** pour démarrer la communication avec votre PC.
```
void setup()                        //initialisation
{
  pinMode(LED_BUILTIN, OUTPUT);     //configuration de la led en sortie
  Serial.begin(9600);               //démarrer la communication
}
```

Vous êtes impatient de faire parler votre carte Arduino n'est ce pas? Alors je ne vais pas créer plus de suspense!
```arduino
Serial.print("Bonjour, je suis votre carte Arduino ;)");
```
Cette instruction envois le texte sité entre guillemets. Ici, elle permet à votre carte Arduino d'envoyer la phrase *Bonjour, je suis votre carte arduino ;)*.

Vous pouvez également afficher la valeur d'une variable. Pour celà il vous suffit de mettre le nom de la variable sans utiliser de guillemets.
```arduino
Serial.print(a);
```

/!\ Cette instruction ne génère pas d'espace, ce sera donc à vous de les inclure. De plus, cette instruction ne permet pas de faire de retour à la ligne. Pour réaliser un retour à la ligne après avoir affiché un texte il faut utiliser une autre instruction fort semblable:  
```arduino
Serial.println("Le prochain texte sera à la ligne");
```

Pour mieux comprendre l'utilisation de cette instruction nous allons réaliser un petit programme qui va afficher le message bonjours puis la valeur de la variable *a*.  
![print](https://user-images.githubusercontent.com/29465741/27257648-84134602-53de-11e7-8545-18ff1e5196d1.png)
```arduino
 int a=5;  //déclaration de 'a' et initialisation de sa valeur

void setup()                        //initialisation
{
  Serial.begin(9600);               //debut de la communication
}

void loop()                         //boucle infinie
{
 Serial.print("Bonjour, la variable a vaut ");  //afficher le texte sans retour à la ligne
 Serial.println(a);                             //afficher la valeur de 'a' puis revenir à la ligne
}
```

Une fois le programme téléversé, cliquez sur la loupe située en à droite de l'ide.  
![btnterminal](https://user-images.githubusercontent.com/29465741/27257698-0565f668-53e0-11e7-8e4f-5c02e2432f6c.png)

La fenêtre qui souvre devant vous est le **moniteur série**. C'est là que sont affichée les donnée provennant de la carte arduino.  
![terminal](https://user-images.githubusercontent.com/29465741/27257718-f68c272e-53e0-11e7-989c-aaa2b84d2e7f.png)

/!\ si vous n'obtenez pas le même affichage, assurez vous que **9600 baud** est bien selectionné (en bas à droite du moniteur).

---
# Conclusion :
---

Félicitations, vous avez maintenant les outils nécessaires pour réaliser vos premiers programme.  
Vous êtes à présent capable de:
* programmer votre carte.
* modifer un code.
* controler le clignotement d'une led.
* afficher des messages sur votre ordinateur.

### Conseils et astuces :

* Commentez vos codes. Celà vous permettra de vous relire et de partager vos codes.
* Les **;** sont la première cause d'erreur n'oubliez pas d'en mettre un à la fin de chaque instruction. Il n'en faut pas après le *nom* d'un bloc.
* Les **{}** sont la deuxième cause d'erreur, n'oubliez pas de délimiter vos blocs. Si vous cliquez sur une accolade, l'ide met en surbrillance l'accolade qui lui est liée.
* Lorsque vous êtes sur l'ide, ctrl+Maj+m permet d'ouvrir le moniteur série.
* Utilisez Serial.println() pour vérifiez si vous passer dans une boucle ou dans un test. Celà vous permettra de trouver vos erreurs.
* Lorsque vous faites du copier-collé, n'oubliez pas de relire votre code et de faire vos modification si il y en a.

/!\ L'ide prend en comptre les majuscules:  **S**erial.begin(9600); est différent de **s**erial.begin(9600);

---
# Exercice complémentaire :
---

Afficher le message SOS en code morse sur la led en affichant chaque lettre sur le moniteur série avant de faire le clignotement de cette led. l'espacement entre les lettres et les mots doit respecter le code morse international.

![sos](https://user-images.githubusercontent.com/29465741/27257814-babbf71a-53e5-11e7-95e6-9122ad2a6eee.png)
![morse](https://user-images.githubusercontent.com/29465741/27257808-3e710fec-53e5-11e7-8131-8607c02d4b0d.png)


--- 
Sources :  
https://www.youtube.com/channel/UCVqx3vXNghSqUcVg2nmegYA  
http://learn.acrobotic.com/tutorials/post/arduino-activity-01-blink-led  
http://www.mysti2d.net/polynesie/SIN/08/ServoLent/files/documents/Revision/Branchements.pdf
https://fr.wikipedia.org/wiki/Morse_(alphabet)
 
 
