# Test-ia – Démo OpenRouter avec interface web et backend sécurisé

Ce projet propose une interface web simple pour dialoguer avec un modèle IA via l'API [OpenRouter](https://openrouter.ai/), en protégeant la clé API grâce à un backend proxy Node.js/Express.

---

## Fonctionnement

- **Frontend** : formulaire web (`public/index.html`) pour poser des questions à l’IA.
- **Backend** : proxy Express (`api/openrouter-proxy.ts`) qui relaie la demande à OpenRouter et masque la clé API en toute sécurité.

---

## Installation rapide

### 1. Cloner le dépôt

```bash
git clone https://github.com/sashahino14/Test-ia.git
cd Test-ia
```

### 2. Installer les dépendances

```bash
npm install express node-fetch dotenv
```

### 3. Configurer la clé API

- Crée un fichier `.env` à la racine du projet (tu peux copier `.env.example`)
- Mets ta clé OpenRouter à l’intérieur :

```
OPENROUTER_API_KEY=ta_cle_openrouter_ici
```

### 4. Lancer le projet

Si tu utilises TypeScript en natif :

```bash
npx ts-node server.ts
```

Ou compile le projet puis lance avec node :

```bash
tsc
node dist/server.js
```

### 5. Utilisation

- Ouvre [http://localhost:3000](http://localhost:3000)
- Pose une question, l’IA te répondra !

---

## Structure des fichiers

```
public/
  index.html               # Interface web
src/
  openrouter-frontend.ts   # JS/TS côté navigateur
api/
  openrouter-proxy.ts      # Proxy Express sécurisé
server.ts                  # Serveur principal Express
.env.example               # Modèle pour la clé API
```

---

## Sécurité

**Ne mets jamais ta clé OpenRouter dans le code côté client ou sur GitHub.**  
Le backend proxy se charge de la sécuriser.

---

## Déploiement

- Pour Netlify, Vercel ou autre (serverless), adapte le proxy à leur système de fonctions (demande-moi si besoin !).
- Pour la prod, sécurise bien les routes et variables d’environnement.

---

## Aide & Questions

Besoin d’aide ? Ouvre une issue sur le repo ou contacte le mainteneur.

---
