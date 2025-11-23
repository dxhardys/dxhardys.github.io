---
title: "Reporting Semaine du 03/11/2025"
institute: "DU Capteur et Technologie Innovante - Projet | Fablab | Paris Saclay"
author: "B. Ishak"
date: \today
theme: metropolis
colortheme: orchid
fonttheme: structurebold
toc: true
toc-depth: 2
slide-level: 2
header-includes:
  - \metroset{sectionpage=progressbar}
---
J'ai téléchargé le logiciel friztzing c'est un logiciel qui permet de faire des simulation sur les différents composants electroniques , et le code arduino 

Pour notre cas de systeme d'arrosage automatique et controle de reservoir moi et sofiane on a decidé d'utilise un capteur ultrasonique [HC -SR04](https://www.gotronic.fr/art-module-de-detection-us-hc-sr04-20912.htm)  qui permet de savoir le niveau d'eau dans le reservoir 

Comme indiqué sur l'images j'ai fait un teste avec un tasse de 12 cm de hauteur  j'ai testé dans les deux le deux niveau remplie et presque vide 
```arduino
// === Serre intelligente ===
// Mesure du niveau d'eau (réservoir de 12 cm de haut)
// Capteur : HC-SR04
// Auteur : Ishak & équipe Serre connectée 🌿

#define TRIG_PIN 9
#define ECHO_PIN 10

#define HAUTEUR_RESERVOIR 12.0  // cm - adapter à ton réservoir

long duree;
float distance;
float niveauEau;
int pourcentage;

void setup() {
  Serial.begin(9600);
  pinMode(TRIG_PIN, OUTPUT);
  pinMode(ECHO_PIN, INPUT);
  
  Serial.println("=== Mesure du niveau d'eau (réservoir 12 cm) ===");
  delay(1000);
}

void loop() {
  // Envoi de l'impulsion ultrasonique
  digitalWrite(TRIG_PIN, LOW);
  delayMicroseconds(2);
  digitalWrite(TRIG_PIN, HIGH);
  delayMicroseconds(10);
  digitalWrite(TRIG_PIN, LOW);

  // Lecture du signal de retour
  duree = pulseIn(ECHO_PIN, HIGH);

  // Conversion en distance (cm)
  distance = duree * 0.0343 / 2;

  // Calcul du niveau d’eau (cm)
  niveauEau = HAUTEUR_RESERVOIR - distance;
  if (niveauEau < 0) niveauEau = 0;
  if (niveauEau > HAUTEUR_RESERVOIR) niveauEau = HAUTEUR_RESERVOIR;

  // Pourcentage d’eau
  pourcentage = (niveauEau / HAUTEUR_RESERVOIR) * 100;

  // Affichage série
  Serial.print("Distance : ");
  Serial.print(distance);
  Serial.print(" cm | Niveau d'eau : ");
  Serial.print(niveauEau);
  Serial.print(" cm | ");
  Serial.print(pourcentage);
  Serial.println(" %");

  // Alerte niveau bas
  if (pourcentage < 20) {
    Serial.println("⚠️  Niveau d'eau faible !");
  }

  delay(1000);
}
```

<figure style="text-align: center;">
  <img src="/ishak/images/ultra_sound_sensor_test.jpg"  width="800">
  <figcaption> Test capteur HC-SR04 </figcaption>
</figure>


<figure style="text-align: center;">
  <img src="/ishak/images/ultra_sound_sensor_test_2.jpg"  width="800">
  <figcaption> Test capteur HC-SR04 - Profil</figcaption>
</figure>

<figure style="text-align: center;">
  <img src="/ishak/images/ultra_sound_sensor_test_seral_output.jpg"  width="800">
  <figcaption> Sortie du Programme - Distance & Niveau d'eau</figcaption>
</figure>

<figure style="text-align: center;">
  <img src="/ishak/images/ultra_sound_sensor_test_seral_output_2.jpg"  width="800">
  <figcaption> Sortie du Programme - Detection niveau d'eau faible</figcaption>
</figure>