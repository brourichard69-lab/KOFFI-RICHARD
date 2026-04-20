# Guide de déploiement GitHub Pages

Ton site sera accessible à l'adresse :
**https://TON-USERNAME-GITHUB.github.io/portfolio-koffi/**

---

## ÉTAPE 1 — Créer le repository sur GitHub

1. Va sur https://github.com (connecte-toi)
2. En haut à droite, clique sur **+** → **New repository**
3. Remplis :
   - **Repository name** : `portfolio-koffi`
   - **Description** : Portfolio — Ingénieur Génie Civil
   - Coche **Public** (obligatoire pour GitHub Pages gratuit)
   - **NE COCHE RIEN** d'autre (pas de README, pas de .gitignore, pas de licence — on les a déjà)
4. Clique **Create repository**

GitHub t'affiche alors une page avec des commandes. **Ignore-les**, suis plutôt les étapes ci-dessous.

---

## ÉTAPE 2 — Installer Git (si pas déjà fait)

Vérifie dans PowerShell :
```powershell
git --version
```

Si Git n'est pas installé, télécharge-le sur : https://git-scm.com/download/win

---

## ÉTAPE 3 — Pousser le dossier sur GitHub

Ouvre **PowerShell** dans le dossier du portfolio :
- Clique-droit dans le dossier `Portfolio koffi` → "Ouvrir dans Terminal" (ou `cd` manuellement)

Puis exécute ces commandes **une par une** (remplace `TON-USERNAME` par ton pseudo GitHub) :

```powershell
git init
git add .
git commit -m "Initial commit : portfolio KOFFI Richard"
git branch -M main
git remote add origin https://github.com/TON-USERNAME/portfolio-koffi.git
git push -u origin main
```

**Lors du `push`**, Git te demandera tes identifiants :
- **Username** : ton pseudo GitHub
- **Password** : ⚠️ colle ICI ton **Personal Access Token** (pas ton mot de passe)

> Git stockera tes credentials en local — c'est normal et sécurisé.
> NE PARTAGE JAMAIS ton token, même avec moi.

---

## ÉTAPE 4 — Activer GitHub Pages

1. Retourne sur ton repo : `https://github.com/TON-USERNAME/portfolio-koffi`
2. Onglet **Settings** (en haut à droite du repo)
3. Menu de gauche : **Pages**
4. Section **Source** :
   - **Branch** : sélectionne `main`
   - **Folder** : `/ (root)`
   - Clique **Save**
5. Attends 1-2 minutes
6. Rafraîchis la page → tu verras :
   > Your site is live at https://TON-USERNAME.github.io/portfolio-koffi/

**C'est en ligne !** 🎉

---

## Pour mettre à jour le site plus tard

Après chaque modification locale :
```powershell
git add .
git commit -m "Mise à jour du portfolio"
git push
```

Le site se met à jour automatiquement en 30 secondes.

---

## Bonus : nom de domaine personnalisé

Si tu veux `koffi-richard.com` au lieu de `github.io` :
1. Achète un domaine (Namecheap, OVH, etc. — ~10€/an)
2. Dans Settings → Pages → **Custom domain** : entre ton domaine
3. Chez ton registrar, ajoute un enregistrement CNAME pointant vers `TON-USERNAME.github.io`

---

## Problème ?

Si `git push` échoue :
- Vérifie que tu as bien un **Personal Access Token** avec la permission `repo`
- Créer un token : https://github.com/settings/tokens → Generate new token (classic) → coche `repo` → Generate

**RAPPEL SÉCURITÉ** : Un token = une clé de ton compte. Ne le colle jamais dans un chat, un mail, ou un fichier partagé.
