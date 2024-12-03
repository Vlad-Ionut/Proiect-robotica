# **Radar cu Arduino pentru Detectarea Obiectelor**

## **Descriere Proiect**
Acest proiect este un sistem radar care utilizează un senzor ultrasonic HC-SR04 și un servo-motor SG90 pentru a scana mediul și a detecta obstacolele într-un anumit interval unghiular. Datele colectate sunt afișate într-o interfață grafică pe PC, oferind o simulare vizuală a unui radar real.

### **Caracteristici**
- Detectarea obstacolelor pe o rază de până la 4 metri.
- Scanare unghiulară între 0° și 180°.
- Afișare în timp real pe interfața grafică a PC-ului.

## **Scopul Proiectului**
Acest proiect a fost realizat pentru a explora integrarea hardware-ului (Arduino, senzori, servo-motoare) cu software-ul (codul pentru Arduino și interfața grafică de pe PC). Este util pentru educație, dezvoltarea de roboți autonomi și înțelegerea principiilor de bază ale senzorilor de proximitate, cat si invățarea principiilor de bază ale electronicii, programării și utilizării senzorilor pentru aplicații practice.

# **Ideea de Pornire**

S-a pornit de la ideea de a realiza un sistem simplu, dar intuitiv, care să demonstreze utilizarea senzorilor de distanță într-un mod interactiv.

## **Utilitate**

Proiectul poate fi utilizat pentru:  
- **Aplicații educative**: Un exemplu practic pentru înțelegerea senzorilor, a servo-motoarelor și a microcontrolerelor.  
- **Prototipuri**: Bază pentru sisteme de detectare a obstacolelor în roboți sau alte dispozitive autonome.  

---

## **Schema Bloc**

- **Arduino UNO**  
  - **Rol**: Controlul general al senzorului și al servo-motorului.  

- **Senzor Ultrasonic (HC-SR04)**  
  - **Rol**: Măsoară distanțele față de obstacole.  

- **Servo-motor**  
  - **Rol**: Permite rotirea senzorului ultrasonic într-un interval de unghiuri.  

- **PC (Interfață Grafică)**  
  - **Rol**: Primește datele prin portul serial și afișează o simulare radar în timp real.  

- **Conexiuni Hardware**  
  - Fire pentru alimentare și comunicare între module.  

---

## **Modul de Interacțiune**

1. Arduino primește comenzi pentru a roti servo-motorul într-un anumit unghi.  
2. Senzorul ultrasonic măsoară distanțele față de obstacole la fiecare unghi.  
3. Datele sunt transmise prin portul serial către un PC.  
4. Un program dedicat procesează și afișează datele sub formă de simulare radar.

---

## **Listă de Piese**

- **Arduino UNO/Mega** (1 buc.)  
- **Senzor ultrasonic HC-SR04** (1 buc.)  
- **Servo-motor SG90 sau MG995** (1 buc.)  
- **Breadboard și fire de conexiune**  
- **Cablu USB** pentru conectare la PC  

### **Cerințe Hardware**
- Arduino UNO/Mega
- Senzor ultrasonic HC-SR04
- Servo-motor SG90
- Breadboard și fire de conexiune
- Cablu USB




