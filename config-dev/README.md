# Protection du site dev

Ces fichiers servent à protéger **dev.petittonnerre.fr** par mot de passe (hébergement FTP IONOS).

## Fichiers à mettre dans le dossier `dev/` sur le serveur

1. **.htaccess** — déjà prêt dans ce dossier. À envoyer par FTP dans `htdocs/dev/` (ou `www/dev/`).

2. **.htpasswd** — à créer toi-même (il contient le mot de passe hashé, ne doit pas être dans le dépôt).

### Créer le fichier .htpasswd

**Où le créer :** sur ton ordinateur (n’importe où, par ex. sur ton Bureau ou dans le dossier du projet), puis tu l’envoies par FTP dans le dossier **`dev/`** sur le serveur (à côté du `.htaccess`).

**Option A – En ligne (rapide)**  
1. Va sur https://htpasswdgenerator.net/ (ou un outil équivalent).  
2. Saisis un **identifiant** (ex. `staging`) et un **mot de passe**.  
3. Génère le hash, puis **copie** la ligne affichée (ex. `staging:$apr1$...`).  
4. Sur ton PC : crée un **nouveau fichier texte**, nomme-le exactement **`.htpasswd`** (avec le point au début), colle dedans uniquement cette ligne, enregistre.  
5. Envoie ce fichier **par FTP** dans le dossier **`dev/`** sur le serveur (même dossier que le `.htaccess`).

**Option B – En ligne de commande (si tu as `htpasswd`)**  
```bash
htpasswd -c .htpasswd staging
```  
(remplace `staging` par l’identifiant voulu). Envoie le fichier `.htpasswd` généré dans `dev/` sur le serveur.

### Erreur 500 (Internal Server Error) après avoir mis .htaccess

Sur IONOS, un chemin relatif (`.htpasswd`) provoque souvent une erreur 500. Il faut utiliser le **chemin absolu** du dossier `dev/` sur le serveur.

**Trouver le chemin absolu :**

1. **Espace client IONOS** → Hébergement → **Gestionnaire de fichiers** (ou FTP). Ouvre le dossier `dev/` (celui où sont `index.html` et `.htpasswd`). L’interface affiche parfois le chemin complet en haut (ex. `/kunden/12345_xxx/web/htdocs/dev`).

2. **Ou en FTP** (FileZilla, etc.) : connecte-toi, va dans le dossier `dev/`. Certains clients affichent le chemin serveur dans la barre d’adresse du panneau distant. Sur IONOS le chemin ressemble souvent à :  
   `/kunden/XXXXX/web/htdocs/dev`  
   ou  
   `/kunden/XXXXX/web/public/dev`  
   (XXXXX = identifiant de ton contrat).

3. **Dans le fichier .htaccess**, remplace la ligne `AuthUserFile` par ce chemin absolu + `/.htpasswd` :
   ```apache
   AuthUserFile /kunden/XXXXX/web/htdocs/dev/.htpasswd
   ```
   (adapte avec le chemin réel de ton dossier `dev/`).

4. Enregistre le `.htaccess` et **ré-envoie-le par FTP** dans le dossier `dev/` (en écrasant l’ancien).
