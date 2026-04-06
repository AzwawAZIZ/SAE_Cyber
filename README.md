# 🔐 SAE Cyber - Outils de chiffrement et gestion d’archives

## 📖 Description

Ce projet regroupe un ensemble d’outils développés en **Bash** et en **C** permettant de :

- Chiffrer et déchiffrer des fichiers
- Trouver des clés de chiffrement
- Gérer des archives (import, restauration, vérification)
- Manipuler une "toolbox" d’outils de cybersécurité

Il est structuré en deux parties principales :
- `SAEBASH` → scripts Bash (gestion et automatisation)
- `SAEC` → programmes en langage C (chiffrement)

---

## 📁 Structure du projet

```
SAE_Cyber/
│
├── PROJET/
│   ├── SAEBASH/        # Scripts Bash
│   └── SAEC/           # Code C (crypto)
│
└── client1-*.tar.gz    # Archive exemple
```

---

## ⚙️ Installation

### 🔧 Prérequis

- Linux / WSL / macOS
- gcc
- make
- Bash

### 📦 Compilation (partie C)

```bash
cd PROJET/SAEC/src
make
```

---

## 🚀 Utilisation

### 🔐 Chiffrement / Déchiffrement
Chiffrement
```bash
echo -n 'CLE' | base64
base64 fichier.txt > fichier.b64 
./cipher <cleenBase64> <fichier.b64> > <fichier.vigenere>
base64 -d fichier.vigenere > fichier.bin
```
Déchiffrement 
```bash
base64 fichier.bin >  fichier.vig
./decipher <cleenBase64> <fichier.vigenere> > fichier.b64
base64 -d fichier.b64 > fichier.txt 

```
Remarque : une perte d'information sur le dernier bit
### 🔎 Recherche de clé

```bash
./findkey <fichierclair> <fichierchiffre>
```

---

## 🧰 Scripts Bash (Toolbox)

Se placer dans :

```bash
cd PROJET/SAEBASH
```

### Initialiser la toolbox

```bash
./init-toolbox.sh
```

### Lister les outils

```bash
./ls-toolbox.sh
```

### Restaurer la toolbox

```bash
./restore-toolbox.sh
```

---

## 📦 Gestion des archives

### Importer une archive

```bash
./import-archive.sh <archive.tar.gz>
```

### Vérifier une archive

```bash
./check-archive.sh <archive>
```

### Restaurer une archive

```bash
./restore-archive.sh <archive>
```

---

## 📘 Documentation

Un guide d’utilisation est disponible ici :

PROJET/SAEBASH/guide_d'utilisation.txt

---

## 🛠️ Technologies utilisées

- Bash
- C
- Makefile
- Outils Linux

---

## 👨‍💻 Auteurs

Projet réalisé dans le cadre d’une SAE (Situation d’Apprentissage et d’Évaluation) en Licence 2 Informatique .

---

## ⚠️ Remarques

- Assurez-vous de donner les droits d’exécution aux scripts :

```bash
chmod +x *.sh
```

- Certains scripts nécessitent des chemins relatifs corrects.

---

## ✅ Objectifs pédagogiques

- Comprendre les bases du chiffrement
- Manipuler des scripts système
- Gérer des archives
- Automatiser des tâches en cybersécurité
