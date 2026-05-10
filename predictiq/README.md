# PredictIQ — Landing Page Statique

## Structure du projet

```
predictiq/
├── index.html       ← page principale
├── vercel.json      ← config Vercel (clean URLs, pas de slash final)
└── README.md
```

## Déploiement sur GitHub + Vercel

### 1. Créer le repo GitHub
```bash
git init
git add .
git commit -m "init: PredictIQ landing page"
gh repo create predictiq --public --push
```
*(ou créer le repo manuellement sur github.com et faire `git remote add origin ...`)*

### 2. Connecter à Vercel
1. Aller sur [vercel.com](https://vercel.com) → **Add New Project**
2. Importer le repo GitHub `predictiq`
3. Framework Preset → **Other** (pas de build, fichier statique pur)
4. Laisser Build Command et Output Directory **vides**
5. Cliquer **Deploy**

Vercel détecte automatiquement `index.html` à la racine → aucune config supplémentaire.

### 3. Auto-redeploy
Chaque `git push` sur `main` redéploie automatiquement. C'est tout.

## Notes
- Pas de variables d'environnement nécessaires (page 100% statique)
- Les images sont hébergées sur les CDN Google (lh3.googleusercontent.com) — elles resteront accessibles
- Pour un domaine custom : Settings → Domains dans le dashboard Vercel
