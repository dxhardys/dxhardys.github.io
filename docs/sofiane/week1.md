---
title: "Reporting Semaine du 03/11/2025"
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

Aujourd'hui nous avons tester plusieurs capteurs essentiel au projet de la serre notamment

- Capteur CO2 (DFrobot REF SEN0219).
- Capteur humidité (ELB0625).
- Capteur de Temperature.
- Ecran (12864B)

Avant de tester les différent capteurs, on prendra en main la carte d'acquisition Metro basé sur Mega328P (Chip similaire a ce qui se fait sur Arduino).

Cette carte necessite d'installer les drivers de communications trouvable [ici](https://github.com/adafruit/Adafruit_Windows_Drivers/releases/download/2.5.0.0/adafruit_drivers_2.5.0.0.exe)

Par la suite les schémas de cablâges décrit seront fait en utilisant `Fritzing`, à noté que les sprites des capteurs et cartes dans ce logiciel ne sont pas toujours disponible on utiliseras donc les composant les plus proches pour décrire le système de test (ex. Dessin d'une Arduino UNO au lieu d'une Metro Mega328P)
Test de l'ecran 


#### Test de l'écran 

L'écran qu'on utiliseras trés probablement pour afficher certaines informations sur les conditions à l'intérieur de la serre est un écran LCD de 128x64 point, la datatsheet [ici](https://roboeq.ir/files/id/4341/name/YXY12864A%20datasheet.pdf/).


<figure style="text-align: center;">
  <img src="/sofiane/images/lcd_screen.jpeg"  width="800">
  <figcaption> Ecran LCD 128x64 - 12864B - avec echelle</figcaption>
</figure>


Afin de tester l'écran nous utiliserons le schéma de cablage suivant :


<figure style="text-align: center;">
  <img src="/sofiane/images/fritzing_lcd_screen_test.jpeg"  width="800">
  <figcaption> Schéma Cablâge de test Ecran - Fritzing</figcaption>
</figure>

Pour la partie code on fera en sorte d'importer la labrairie `U8glib.h` via l'outil correspondant sur ArduinoIDE :


<figure style="text-align: center;">
  <img src="/sofiane/images/arduino_ide_import_lib.jpeg"  width="300">
  <figcaption> Importer une Librairie sur ArduinoIDE</figcaption>
</figure>

Puis on utiliseras le code test suivant afin de verifier le bon fonctionnement de l'écran et afficher à l'écran le message "Hello World"

```arduino
#include "U8glib.h"

// SPI Com:  ST7920 128x64  -->  SCK = EN =13  , MOSI = RW =11 ,  CS = DI =10
U8GLIB_ST7920_128X64 u8g(13, 11, 10, U8G_PIN_NONE);

void draw(void) {
  u8g.setFont(u8g_font_unifont);
  u8g.drawStr( 0, 22, "Hello World!");
}

void setup(void) {
  if ( u8g.getMode() == U8G_MODE_R3G3B2 )
    u8g.setColorIndex(255); // white
  else if ( u8g.getMode() == U8G_MODE_GRAY2BIT )
    u8g.setColorIndex(16); // max intensity
  else if ( u8g.getMode() == U8G_MODE_BW )
    u8g.setColorIndex(1); // pixel on
}

void loop(void) {
  u8g.firstPage();
  do {
    draw();
  } while( u8g.nextPage() );
  delay(500);
}
```
Voici le résultat à l'écran, la luminosité laisse à désirer pour le moment mais la datasheet indique cue c'est contrôlable, pour le moment nous avons la confirmation que l'écran fonctionne.

<figure style="text-align: center;">
  <img src="/sofiane/images/lcd_screen_success_test.jpeg"  width="800">
  <figcaption> Affichage du message "Hello World!" - Luminosité médiocre</figcaption>
</figure>

#### Test du capteur d'eau (SE045)
Par la suite on passe à l'utilisation du capteur d'Humidité qui nous serviras à évaluer le taux d'humidité (d'eau) à l'interieur de la terre et potentiellement dans l'air ambient à l'interieur de la serre.


<figure style="text-align: center;">
  <img src="/sofiane/images/water_level_sensor.jpeg"  width="800">
  <figcaption> Capteur d'eau - SE045</figcaption>
</figure>

Pour le tester on se baseras sur le schémas de cablâge suivant :

<figure style="text-align: center;">
  <img src="/sofiane/images/fritzing_water_level_sensor_test.jpeg"  width="800">
  <figcaption> Schéma de câblage de test du capteur d'eau - Fritzing</figcaption>
</figure>

et le simple code suivant qui affiche le niveau d'eau détecté :

```arduino
#define POWER_PIN  7
#define SIGNAL_PIN A5

int value = 0; // variable to store the sensor value

void setup() {
  Serial.begin(9600);
  pinMode(POWER_PIN, OUTPUT);   // configure D7 pin as an OUTPUT
  digitalWrite(POWER_PIN, LOW); // turn the sensor OFF
}

void loop() {
  digitalWrite(POWER_PIN, HIGH);  // turn the sensor ON
  delay(10);                      // wait 10 milliseconds
  value = analogRead(SIGNAL_PIN); // read the analog value from sensor
  digitalWrite(POWER_PIN, LOW);   // turn the sensor OFF

  Serial.print("Sensor value: ");
  Serial.println(value);

  delay(1000);
}
```
