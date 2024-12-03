# **Radar cu Arduino pentru Detectarea Obiectelor**

## **Descriere Proiect**
Acest proiect este un sistem radar care utilizează un senzor ultrasonic HC-SR04 și un servo-motor SG90 pentru a scana mediul și a detecta obstacolele într-un anumit interval unghiular. Datele colectate sunt afișate într-o interfață grafică pe PC, oferind o simulare vizuală a unui radar real.

### **Caracteristici**
- Detectarea obstacolelor pe o rază de până la 4 metri.
- Scanare unghiulară între 0° și 180°.
- Afișare în timp real pe interfața grafică a PC-ului.

## **Scopul Proiectului**
Acest proiect a fost realizat pentru a explora integrarea hardware-ului (Arduino, senzori, servo-motoare) cu software-ul (codul pentru Arduino și interfața grafică de pe PC). Este util pentru educație, dezvoltarea de roboți autonomi și înțelegerea principiilor de bază ale senzorilor de proximitate, cat si invățarea principiilor de bază ale electronicii, programării și utilizării senzorilor pentru aplicații practice.

## ** Ideea de pornire: **
    S-a pornit de la ideea de a realiza un sistem simplu, dar intuitiv, care să demonstreze utilizarea senzorilor de distanță într-un mod interactiv.

## *Utilitate:*
    Proiectul poate fi folosit pentru aplicații educative, precum și ca prototip pentru sisteme de detectare a obstacolelor în roboți sau alte dispozitive autonome.



## *Schema bloc:*

    Arduino UNO
    Rol: Controlul general al senzorului și servo-motorului.
    Senzor ultrasonic (HC-SR04):
    Rol: Măsoară distanțele față de obstacole.
    Servo-motor:
    Rol: Permite rotirea senzorului ultrasonic într-un interval de unghiuri.
    PC (Interfață grafică):
    Rol: Primește datele prin serial și afișează o simulare radar în timp real.
    Conexiuni hardware:
    Fire pentru alimentare și comunicare.

## *Modul de interacțiune:*

    Arduino primește comenzi pentru a roti servo-motorul și colectează date de la senzorul ultrasonic. Datele sunt transmise prin portul serial către un PC, unde sunt procesate și afișate într-un program dedicat.

(Exemplu generic de schemă bloc pentru un sistem Arduino radar)
Hardware Design

### *Listă de piese:*

    Arduino UNO/Mega (1 buc.)
    Senzor ultrasonic HC-SR04 (1 buc.)
    Servo-motor SG90 sau MG995 (1 buc.)
    Breadboard și fire de conexiune
    Cablu USB pentru conectare la PC

### **Cerințe Hardware**
- Arduino UNO/Mega
- Senzor ultrasonic HC-SR04
- Servo-motor SG90
- Breadboard și fire de conexiune
- Cablu USB




