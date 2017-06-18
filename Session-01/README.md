
# Session #1: 
# Arduino c'est quoi au juste? 
# Notions d'éléctronique de base.
---

### Au Programme:  
- Présentation de la carte Arduino.  
- Notions de base en électronique.  
  - Courant électrique, tension électrique? qu'est ce que c'est?  
  - Montage série  
  - Montage parallèle  
  - La *planche à pain*   
- Allumer une led sans Arduino.
- Controler plusieurs leds avec Arduino

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

Maintenant que vous savez ce qu'est *Arduino*, regardons de plus près notre carte.  

Commençons par l'élément le plus évident de la carte, le port USB. Celui-ci permet de connecter votre carte à votre PC mais aussi de l'alimenter avec une tension de 5V.  
![boardusb](https://user-images.githubusercontent.com/29465741/27262158-2dc6f208-5451-11e7-82cb-acbb390f8dea.png)

Les différents composants qui se situe en bas à droite de la carte constituent ce qu'on appelle un régulateur de tension. Celà permet d'alimenter la carte sans USB avec une source comprise idéalement entre 7 et 12V. Cette source peut être une pile ou un transfrmateur.  
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

Finalement nous avons une série de connecteurs de part et d'autres de la carte. Ces connecteurs sont les points d'entrée et de sortie de la carte et lui permettent d'interragir avec le monde exterieur.  
![boardpin](https://user-images.githubusercontent.com/29465741/27262546-01034cd2-5459-11e7-860d-63c61b69a374.png)  
NB: chaque point de connection est ce qu'on appelle une *Pin*
 
 

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

 
 
