# Optimisation des Performances Web : Le Cas du Glassmorphism

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![Status](https://img.shields.io/badge/status-Étude_Terminée-success)

## 📖 Présentation du Projet
Ce projet s'inscrit dans le cadre d'une étude d'ingénierie Web portant sur le compromis entre esthétique visuelle et performance technique. 

Le **Glassmorphism** (effet de flou d'arrière-plan) est devenu un standard du design moderne. Cependant, son implémentation via la propriété CSS `backdrop-filter` génère une charge de calcul massive pour le GPU, impactant la fluidité (FPS) et l'autonomie des terminaux.

**Objectif :** Déterminer et implémenter la stratégie la plus efficace pour garantir un rendu fluide (60 FPS) sur des terminaux hétérogènes (allant du PC haute performance au smartphone d'entrée de gamme).

---

## 🧪 Protocole de Test
L'étude repose sur un benchmark automatisé développé spécifiquement pour ce projet.

- **Méthodologie :** Injection progressive de 10 à 80 cartes à effet Glassmorphism.
- **Indicateur Clé (KPI) :** Fréquence d'images par seconde (Frames Per Second - FPS).
- **Matériel :** Comparatif entre PC fixe et terminaux mobiles limités.

👉 **[Consulter le Protocole de Test](https://pierrebvn.github.io/Glossmorphism/)**

---

## 📊 Solutions Évaluées & Résultats
Quatre approches techniques ont été testées :
1. **Standard :** Utilisation directe de `backdrop-filter`.
2. **Optimisation CSS :** Forçage de l'accélération matérielle via `will-change`.
3. **Conception Adaptative (Fallback) :** Détection des capacités matérielles via JavaScript.
4. **Illusion d'optique :** Utilisation d'images statiques pré-floutées.

**Conclusion :** La **Conception Adaptative** est la solution retenue, permettant de maintenir 60 FPS constants en adaptant l'interface aux capacités de l'appareil de l'utilisateur.

---

## 📚 Bibliographie & Références Techniques

Cette étude s'appuie sur des ressources académiques et techniques de référence pour analyser l'impact du rendu graphique sur les performances web.

### 🌐 Fondements du Rendu Web & Pipeline
* **Google Developers** – *Critical Rendering Path* : Analyse détaillée des étapes du moteur de rendu, de la construction du DOM/CSSOM à la composition finale. [Consulter](https://web.dev/articles/critical-rendering-path)
* **Intel Software** – *Web Graphics Performance* : Étude sur la délégation des calculs au GPU et l'impact de l'accélération matérielle sur le cycle de "repaint". [Consulter](https://web.dev/articles/speed-html5?hl=fr)

### 📐 Mathématiques et Algorithmique du Flou
* **W3C Working Group** – *Filter Effects Module Level 1* : Spécifications techniques du flou gaussien et implémentation via la distribution normale. [Consulter](https://www.w3.org/TR/filter-effects-1/#feGaussianBlurElement)
* **Mozilla (MDN Web Docs)** – *Performance et CSS : Backdrop-filter* : Guide sur le coût de calcul des filtres dynamiques sur les calques de composition. [Consulter](https://developer.mozilla.org/fr/docs/Web/CSS/backdrop-filter)

### 🔬 Publications Scientifiques
* **SciTePress (2021)** – *Gaussian Blur through Parallel Computing* : Étude démontrant la lourdeur de la convolution matricielle et comparaison des temps de calcul CPU vs GPU. [Consulter](https://www.scitepress.org/Papers/2021/105133/105133.pdf)
* **NVIDIA GPU Gems** – *Incremental Computation of the Gaussian* : Optimisation des calculs mathématiques exponentiels pour les architectures GPU. [Consulter](https://developer.nvidia.com/gpugems/gpugems3/part-vi-gpu-computing/chapter-40-incremental-computation-gaussian)
* **IEEE Xplore (2025)** – *Accelerating Web Rendering Performance* : Analyse des goulots d'étranglement mémoire lors du rendu d'applications complexes. [Consulter](http://ieeexplore.ieee.org/iel8/52/11024032/11024090.pdf)

### 🛠️ Outils & Méthodologie Intégrés
* **API Web Native (`requestAnimationFrame`)** : Utilisation de cette interface JavaScript pour calculer le temps (delta) entre chaque rafraîchissement d'écran. C'est le cœur algorithmique du script de benchmark permettant de mesurer les FPS en temps réel avec une précision native. [Documentation MDN](https://developer.mozilla.org/fr/docs/Web/API/window/requestAnimationFrame)
* **Chart.js** : Bibliothèque JavaScript open-source de visualisation de données. Utilisée pour interpréter le tableau de bord des résultats généré par le benchmark et tracer les courbes d'effondrement des performances en fonction de la charge GPU. [Documentation Officielle](https://www.chartjs.org/)

---

## 👤 Contact
**Pierre BOIVIN** *Étudiant à CESI École d'Ingénieurs* 
📧 [boivin.pierre60@gmail.com](mailto:boivin.pierre60@gmail.com)  
📅 Avril 2026
