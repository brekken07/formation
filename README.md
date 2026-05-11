# 📚 Formation — Portail de formation personnelle

> Parcours de formation progressif, construit module par module, accessible depuis n'importe où via GitHub Pages.

🌐 **[Accéder au portail](https://brekken07.github.io/formation/)**

---

## 🗂️ Structure du repo

```
formation/
├── index.html              # Portail principal (généré dynamiquement)
├── modules.json            # ⚙️ Fichier de configuration des modules
├── devops/                 # Formation DevOps
│   ├── cicd-github-guide-v2.html
│   ├── module2-git-pratique.html
|   └── etc...
├── Linux/
|   ├── LPIC 1
|   └── etc...
└── .github/
    └── workflows/
        └── deploy.yml      # Déploiement automatique sur GitHub Pages
```

## ➕ Ajouter un nouveau module

1. **Ajoute le fichier HTML** dans le sous-dossier de la formation concernée :
   ```bash
   cp nouveau-module.html devops/
   ```

2. **Mets à jour `modules.json`** — ajoute un bloc dans la liste `modules` de la formation :
   ```json
   {
     "file": "nouveau-module.html",
     "title": "Titre du module",
     "description": "Description courte.",
     "tags": ["TAG1", "TAG2"],
     "status": "new"
   }
   ```
   Les statuts possibles : `done` · `new` · `soon`

3. **Pousse sur GitHub** — le déploiement est automatique :
   ```bash
   git add .
   git commit -m "feat: add module XX - titre"
   git push
   ```

Le numéro du module (`MODULE 01`, `MODULE 02`...) est calculé automatiquement selon la position dans la liste.

---

## ⚙️ CI/CD

Ce repo utilise GitHub Actions pour déployer automatiquement sur GitHub Pages à chaque push sur `main`.

```
git push → GitHub Actions → GitHub Pages
```

---

## 🛠️ Stack

![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-deployed-34d399?style=flat-square&logo=github)
![HTML](https://img.shields.io/badge/HTML-static-4f9cf9?style=flat-square)
![JSON](https://img.shields.io/badge/Config-modules.json-a78bfa?style=flat-square)
