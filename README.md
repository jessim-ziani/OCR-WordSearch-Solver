# 🔍 OCR Word Search Solver (C / GTK / CNN)

> **Note :** Le code source de ce projet (réalisé à l'EPITA) est privé pour respecter les règles anti-plagiat de l'école. Cette page présente le fonctionnement visuel de notre algorithme.

Ce projet est un moteur de Reconnaissance Optique de Caractères (OCR) codé entièrement en **C** (sans OpenCV), capable de lire une grille de mots mêlés depuis une image et de la résoudre.

---

## 📸 Le Pipeline de Traitement (Comment ça marche)

### 1. Interface Graphique (GTK3)
Nous avons développé une interface utilisateur complète en C/GTK3 permettant de charger une image et d'appliquer les différents algorithmes étape par étape.
<div align="center">
  <img src="screenshots/GTKfenetre.png" width="700">
</div>

### 2. Prétraitement de l'Image (Filtres)
L'image brute subit plusieurs transformations : passage en niveaux de gris, flou gaussien, binarisation d'Otsu et suppression du bruit pour faire ressortir l'encre noire.
<div align="center">
  <img src="screenshots/pretraitement_image1_niveau_1_avant.png" width="400">
  <img src="screenshots/pretraitement_image1_niveau_1_apres.png" width="400">
</div>

### 3. Segmentation (Composantes Connexes)
Notre algorithme de détection isole la zone de la grille (encadrés verts) et extrait chaque lettre individuellement (encadrés rouges).
<div align="center">
  <img src="screenshots/detection_lettre_image1_niveau_1.png" width="700">
</div>

### 4. Intelligence Artificielle & Algorithme de Résolution
Chaque lettre extraite est analysée par notre **Réseau de Neurones Convolutif (CNN)** fait maison. Une fois la grille virtuelle recréée en mémoire, notre solveur scanne les 8 directions possibles, trouve les mots cachés, et les surligne directement sur l'image d'origine.
<div align="center">
  <img src="screenshots/reponse_lettre_image1_niveau_1.png" width="700">
</div>

---
**🛠️ Technologies :** C, GTK3, Make, Bash, Git.