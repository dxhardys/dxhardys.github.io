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
 Communication reseau 
Lire en temps réel les données de capteurs (température, humidité, CO₂…) dans une serre.


Afficher ces données sur une page web accessible depuis le réseau local et à distance.


Permettre à terme le contrôle des actionneurs (ventilateurs, pompes, éclairage) pour automatiser la serre.



 Matériel utilisé
Matériel
Description / Modèle
Raspberry Pi 3 Model B
1 Go, serveur pour collecter les données et héberger la page web
Arduino Metro Adafruit
Capteur TMP235 connecté à A2 (lecture analogique)
TMP235
Capteur de température analogique
Câbles USB
Liaison Arduino ↔ Raspberry Pi
Connexion Internet
Pour accès distant (4G/5G)
Modem Bbox
Pour redirection de port NAT et accès à distance


Principe de fonctionnement 
L’Arduino lit la température du TMP235 → génère des données JSON sur le port série.


Le Raspberry Pi récupère les données via USB.


Un script Python avec Flask crée un serveur web et affiche les données en temps réel.


Le serveur Flask est accessible :


Sur le réseau local via Wi-Fi


À distance via Port Forwarding sur le modem Bbox



 Étapes réalisées
a) Lecture du capteur TMP235
Arduino lit la valeur analogique sur A2.


Conversion en tension et calcul de la température en °C.


Envoi des données JSON sur le port série (USB vers Raspberry Pi).


Exemple de sortie :
{"temperature": 23.80}

Remarque : la formule de conversion TMP235 a été corrigée pour correspondre à la vraie température (Vout - 0.25) / 0.01.

b) Mise en place du serveur web sur Raspberry Pi
Installation de Python 3, Flask et pyserial.


Script Python pour lire le port série et afficher la température dans une page HTML simple.


Page rafraîchie toutes les secondes pour un affichage en temps réel.



c) Accès depuis le réseau local
Vérification de l’IP locale du Raspberry Pi.


Accès depuis PC ou téléphone sur le réseau Wi-Fi via :


http://192.168.x.x:5000


d) Accès à distance via Port Forwarding
Configuration de la Bbox : Redirection du port 5000 vers l’IP locale du Pi.


Vérification de l’IP publique.


Accès externe depuis un smartphone 4G :


http://IP_PUBLIQUE:5000


e) (Optionnel) Sécurité et extensions futures
Ajout futur de Cloudflare Tunnel ou HTTPS pour sécuriser l’accès externe.


Possibilité d’intégrer d’autres capteurs et actionneurs.


Création d’un tableau de bord interactif avec graphiques temps réel.



 Résultat obtenu
Le Raspberry Pi récupère et affiche la température du TMP235 sur une page web.


La page est accessible localement et depuis Internet via Port Forwarding.


Les données sont affichées en JSON et converties en °C.


Le système fonctionne en temps réel et peut être étendu à d’autres capteurs et actionneurs.



 Conclusion
Le projet montre la mise en réseau d’un microcontrôleur (Arduino) et d’un mini-ordinateur (Raspberry Pi).
