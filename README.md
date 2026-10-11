# 🎓 Smart Presence

> Système intelligent de gestion des présences basé sur l'IoT, la reconnaissance faciale et des services Cloud.

Smart Presence est une solution conçue pour automatiser le suivi des présences dans les établissements éducatifs.

L'objectif est de remplacer les méthodes manuelles de gestion des absences par un système capable de détecter les présences, centraliser les données et automatiser certaines actions, notamment l'envoi d'alertes en cas d'absence prolongée.

---

## 🎥 Demo

Une démonstration du projet est disponible ici :

▶️ **./demo/demo.mp4**

📑 **./docs/Presentation_Smart_Presence.pdf**

---

## 📌 Problématique

La gestion traditionnelle des présences dans les établissements éducatifs repose souvent sur des méthodes manuelles.

Cela peut entraîner :

- des erreurs dans le suivi des présences ;
- un manque de fiabilité ;
- une gestion administrative peu efficace.

Smart Presence propose d'utiliser l'IoT et l'intelligence artificielle afin d'automatiser et de moderniser ce processus.

---

## 💡 Solution proposée

Smart Presence combine plusieurs composants :

- reconnaissance faciale ;
- dispositifs IoT ;
- traitement des données ;
- stockage Cloud ;
- interface de suivi ;
- automatisation des alertes.

Le système repose notamment sur **YOLOv8** pour la reconnaissance faciale et sur une architecture Cloud pour le stockage et le traitement des informations.

---

## ⚙️ Fonctionnalités

### Reconnaissance automatique des présences

La présence peut être détectée automatiquement grâce à la reconnaissance faciale.

### Collecte des données

Les informations de présence sont collectées et stockées dans une base de données Cloud.

### Consultation des présences

Une interface basée sur **Streamlit** permet de consulter les informations de présence.

### Alertes automatiques

Le système prévoit l'envoi automatique d'e-mails lorsqu'une absence prolongée est détectée.

### Évolutivité

L'architecture permet d'envisager de nouvelles fonctionnalités, notamment l'analyse prédictive des absences.

---

## 🏗️ Architecture

L'architecture présentée pour Smart Presence combine les couches IoT, IA et Cloud.

```text
                 ┌──────────────────┐
                 │     Caméra       │
                 └────────┬─────────┘
                          │
                          ▼
                 ┌──────────────────┐
                 │ Reconnaissance   │
                 │ faciale YOLOv8   │
                 └────────┬─────────┘
                          │
                          ▼
                 ┌──────────────────┐
                 │   Jetson Nano    │
                 └────────┬─────────┘
                          │
                          ▼
                 ┌──────────────────┐
                 │ Google Firestore │
                 └────────┬─────────┘
                          │
              ┌───────────┴───────────┐
              ▼                       ▼
     ┌────────────────┐      ┌─────────────────┐
     │    Streamlit   │      │ Cloud Functions │
     │   Dashboard    │      │ / Scheduler     │
     └────────────────┘      └────────┬────────┘
                                     │
                                     ▼
                              Alertes par e-mail
