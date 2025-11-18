---
title: "Reporting Semaine du 10/11/2025"
institute: "DU Capteur et Technologie Innovante - Projet | Fablab | Paris Saclay"
author: "A. Sofiane"
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

Suivie de la formation modélisation 3D avec Selena PERE ce matin, prise en main du logiciel Fusion360.

Conception d'un petit légo pour comprendre la création de volume l'extrudation le mirroring de volume avec l'aide de Selena et dicussion avec elle sur les logiciels, le principe de modélisation et d'utilisation des imprimantes 3D (présentation de SlicerPrusa, supports etc..)

En suivant la formation on arrive au résultat suivant 

<figure style="text-align: center;">
  <img src="images/fusion360_test_cube.jpeg" alt="Descriptive text" width="800">
  <figcaption> Fusion360 - Conception et moélisation d'un LEGO - Formation Selena PERE</figcaption>
</figure>


Qu'on exporteras au format `.stl` puis sur PrusaSlicer on importe ce fichier


<figure style="text-align: center;">
  <img src="images/prusa_test_cube.jpeg" alt="Descriptive text" width="800">
  <figcaption> PrusaSlicer - Importation du fichier f360 de sortie de fusion360</figcaption>
</figure>

Par la suite on sélectionne le bon filament en fonction de la bobine monté sur l'imprimante ici du Prusa PETG de couleur orange, on sélectionne le bon modèle d'imprimmante MK4S et le diamètre de la buse par défaut 0.4mm puis on exporte ça en gcode qui est un format lu reconnu par l'imprimmante qui contient les instructions d'impression :

<figure style="text-align: center;">
  <img src="images/cube_printing.jpeg" alt="Descriptive text" width="400">
  <figcaption> Impression en cours sur Prusa MK4S - PETG - 0.4mm</figcaption>
</figure>

L'impression poursuit son cours convenablement et le résultat et le suivant 


<figure style="text-align: center;">
  <img src="images/cube_printed.jpeg" alt="Descriptive text" width="200">
  <figcaption> Résultat Impression cube test</figcaption>
</figure>

Et on retrouve le rapport d'impression sur l'écran de l'imprimmante : 


<figure style="text-align: center;">
  <img src="images/printing_report_cube_test.jpeg" alt="Descriptive text" width="800">
  <figcaption> Rapport d'impression sur Prusa MKS4</figcaption>
</figure>

qui nous retourne notamment le temps d'impression (Temps de chauffage + calibration + impression) la quantité de PETG consomé, on a donc un totale de 17m21 de bout en bout pour un cube de 12mm x 12 mm.


#### Test capteur de temperature (TMP235)


<figure style="text-align: center;">
  <img src="images/temperature_sensor.jpeg" alt="Descriptive text" width="400">
  <figcaption> Capteur temperature TMP235 - avec echelle  </figcaption>
</figure>


Ce capteur est trés basique on peut retrouver sa datasheet [ici](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/1096/4686_Web.pdf)


<figure style="text-align: center;">
  <img src="images/fritzing_temperature_sensor_test.jpeg" alt="Descriptive text" width="800">
  <figcaption> Schéma de câblage de test capteur de temperature - Fritzing </figcaption>
</figure>


$$T(C^°) = \frac{V_{out} - 500 mV}{10 mV /C^°}$$

```arduino
const int sensorPin = A0;

void setup() {
  Serial.begin(9600);
}

void loop() {
  int rawValue = analogRead(sensorPin);
  float voltage = rawValue * (5.0 / 1023.0); // conversion en volts

  float temperatureC = (voltage - 0.5) / 0.01;

  Serial.print("Tension : ");
  Serial.print(voltage, 3);
  Serial.print(" V   |   Temperature : ");
  Serial.print(temperatureC, 1);
  Serial.println(" °C");

  delay(500);
}

```

Ce test permet de conclure que le capteur est fonctionnel et qu'il mesure correctement la temperature ambiante du Fablab ~22° et en rapprochant simplement le capteur de la baie d'aération de ma mahcine fait grimper la temperature.



<figure style="text-align: center;">
  <img src="images/output_temperature_test_code.jpeg" alt="Descriptive text" width="800">
  <figcaption> Sortie serial evolution de la temperature </figcaption>
</figure>