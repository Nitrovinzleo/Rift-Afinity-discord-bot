# 🤖 Bot Discord RiftAffinity

Bot Discord officiel pour **RiftAffinity**, l'application d'évaluation d'affinité et de compatibilité amoureuse/amicale pour les joueurs de **League of Legends**.

---

## 🌟 Fonctionnalités

- **`/rafinity`** : Calcule le score de compatibilité (sur 100) entre 2 joueurs à partir de l'API Riot Games et de l'algorithme psychologique.
  - Exemples :
    - `/rafinity player1: PrincessPinkyUp#8ï8 player2: PrincessDarkyUp#8ï8`
    - `/rafinity player1: @jd0xan player2: PrincessDarkyUp#8ï8`
  - Génère un Embed avec la barre de progression, l'archétype duo, le winrate commun, les shared kills, la synergie des rôles et des conseils d'analyse.
- **`/link`** : Associe votre identifiant Discord à votre Riot ID (`/link riot_id: Pseudo#TAG`).
- **`/unlink`** : Délie votre compte Discord.
- **`/profile`** : Affiche le profil et le Riot ID lié d'un membre.
- **`/help`** : Guide complet des commandes.

---

## 🛠️ Configuration & Installation

### 1. Prérequis
- Python 3.10+
- Le serveur backend FastAPI **RiftAffinity** (dans `../RIFT AFINITY/backend`) lancé ou hébergé en ligne.

### 2. Créer le Bot sur le Discord Developer Portal
1. Rendez-vous sur le [Discord Developer Portal](https://discord.com/developers/applications).
2. Cliquez sur **New Application** et nommez-la `RiftAffinity`.
3. Allez dans le menu **Bot** (à gauche) :
   - Cliquez sur **Add Bot** ou **Reset Token** pour obtenir votre **Bot Token**.
   - Copiez ce jeton.
4. Allez dans **OAuth2 > URL Generator** :
   - Cochez les scopes : `bot` et `applications.commands`.
   - Cochez les permissions de bot : `Send Messages`, `Embed Links`, `Read Message History`.
   - Copiez l'URL générée pour inviter le bot sur votre serveur Discord.

### 3. Fichier de Configuration (`.env`)
Créez ou modifiez le fichier `.env` dans ce dossier avec vos clés :

```env
DISCORD_BOT_TOKEN=VOTRE_BOT_TOKEN_DISCORD
API_URL=https://rift-afinity-ri-ft-afinity.vercel.app
RIOT_API_KEY=VOTRE_CLÉ_RIOT_API_ICI
DATABASE_URL=postgresql://user:password@ep-xxxx.eu-central-1.aws.neon.tech/neondb?sslmode=require
```

### 4. Installation des Dépendances
Dans votre terminal :
```bash
pip install -r requirements.txt
```

### 5. Démarrage
1. **Lancez le backend FastAPI** (si en local) :
   ```bash
   cd "../RIFT AFINITY/backend"
   uvicorn app.main:app --reload --port 8000
   ```
2. **Lancez le Bot Discord** :
   ```bash
   python bot.py
   ```

---

## 📊 Structure des Fichiers

- `bot.py` : Script principal du bot Discord (Slash commands & embeds).
- `requirements.txt` : Dépendances Python (`discord.py`, `httpx`, `dotenv`, etc.).
- `.env` : Variables d'environnement secrètes (Token Bot Discord, API_URL, etc.).
- `.env.example` : Modèle de configuration exemple.
