# Herbier — app d'identification de plantes

4 fichiers : `index.html`, `manifest.json`, `sw.js`, `icons/`. Aucune base de données locale — chaque photo est envoyée à l'API **Pl@ntNet** (gratuite, 500 identifications/jour) au moment de l'analyse.

## 1. Obtenir les clés API (gratuit, 5 min au total)

**Pl@ntNet (identification)**
1. Va sur **my.plantnet.org**, crée un compte.
2. Dans ton espace, section "API", récupère ta **clé API**.
3. Sur la page "Manage API Key", active **"expose my API key"**, ajoute ton domaine d'hébergement (ex. `https://tonpseudo.github.io`) dans "Authorized domains", puis **Update key settings**.

**Perenual (fiche soins & état)**
1. Va sur **perenual.com/user/developer**, crée un compte gratuit.
2. Récupère ta clé API sur le tableau de bord (100 requêtes/jour gratuites).
3. Si tu obtiens une erreur CORS en utilisant l'appli, cherche un réglage équivalent d'autorisation de domaine sur ton compte Perenual et ajoute le même domaine que pour Pl@ntNet.

Colle les deux clés dans l'appli via l'icône réglages (⚙).

## 2. Héberger l'appli (nécessaire pour l'installer sur ton téléphone)

Un fichier ouvert directement (`file://`) ne peut pas s'installer comme appli. Il faut un hébergement en HTTPS — **GitHub Pages** est gratuit et prend 5 minutes :

1. Crée un compte sur **github.com** si tu n'en as pas.
2. Crée un nouveau dépôt (repository), par exemple `herbier-app`, en public.
3. Mets-y les 4 éléments (`index.html`, `manifest.json`, `sw.js`, le dossier `icons/`) — via "Add file → Upload files" sur le site GitHub, glisser-déposer suffit.
4. Dans le dépôt : **Settings → Pages → Branch: main → Save**.
5. GitHub te donne une adresse du type `https://tonpseudo.github.io/herbier-app/`. Attends 1-2 minutes qu'elle s'active.

*Alternative encore plus rapide sans compte GitHub : dépose les fichiers sur **Netlify Drop** (netlify.com/drop) par glisser-déposer — tu obtiens une adresse HTTPS instantanément.*

## 3. Installer sur ton OnePlus 10 Pro

1. Ouvre l'adresse obtenue à l'étape précédente dans **Chrome**.
2. Menu **⋮** (trois points en haut à droite) → **Ajouter à l'écran d'accueil** (ou une bannière d'installation apparaît automatiquement).
3. L'icône "Herbier" apparaît sur ton écran d'accueil, comme une vraie appli, en plein écran, sans barre d'adresse.

## 4. Utilisation

- **Prendre une photo** : ouvre directement l'appareil photo natif.
- **Depuis la galerie** : choisis une photo déjà prise.
- Bouton **Identifier cette plante** → envoie la photo à Pl@ntNet, affiche les 3 espèces les plus probables avec score de confiance, nom commun et famille botanique.
- Sur chaque résultat :
  - **Soins & état** → ouvre une fiche détaillée (arrosage, exposition, entretien, toxicité, signes à surveiller) via Perenual, avec liens Wikipédia et recherche web en secours.
  - **Ajouter au carnet** → enregistre cette identification (avec une miniature de la photo) dans l'historique local du téléphone.
- Icône **carnet** (en haut, à côté des réglages) → consulte l'historique des plantes enregistrées, retape une entrée pour revoir sa fiche soins, supprime une entrée ou vide tout le carnet.
- Les clés API sont stockées uniquement sur ton téléphone (jamais transmises ailleurs qu'à Pl@ntNet / Perenual).

## Limites à connaître

- 500 identifications gratuites/jour (Pl@ntNet), 100 requêtes gratuites/jour pour les fiches soins (Perenual).
- Perenual free tier ne couvre que les espèces les plus courantes — certaines plantes rares n'auront pas de fiche (liens Wikipédia/recherche web proposés en secours).
- Nécessite une connexion internet à chaque identification ou consultation de fiche soins.
- Le carnet est stocké localement dans le navigateur : il peut être perdu si tu vides les données du site ou changes de téléphone (pas de synchronisation cloud).
- Meilleure précision avec une photo nette, centrée sur une feuille, fleur ou fruit isolé plutôt qu'une plante entière à distance.
