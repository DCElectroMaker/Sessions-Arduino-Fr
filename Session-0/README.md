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







Bibliographie et iconographie:  
https://www.youtube.com/channel/UCVqx3vXNghSqUcVg2nmegYA  
http://learn.acrobotic.com/tutorials/post/arduino-activity-01-blink-led  
