# La Coupe du Monde de la Coupe

Application de duels de coupes de cheveux, en un seul fichier, sans serveur ni dépendance.

## Les deux fichiers

| Fichier | Contenu | Où il va |
|---|---|---|
| `coupe-du-monde-de-la-coupe.html` | Fichier maître : l'application et les textes privés, en clair | Sur ton ordinateur uniquement |
| `index.html` | Page publiée : l'application et un coffre chiffré (photos + textes) | Dans ce dépôt |

## Mise en ligne (une seule fois)

1. Créer un dépôt GitHub et y pousser ce dossier sur la branche `main`.
2. Dans le dépôt : **Settings → Pages → Build and deployment → Source : GitHub Actions**.
3. L'adresse du site s'affiche dans l'onglet **Actions**, au job `deploy`.

## Créer le lien pour les potes

1. Ouvrir le fichier maître sur ton ordinateur et y ajouter les photos.
2. Cliquer sur **🔗 Créer le lien**, indiquer l'adresse du site : un `index.html` est téléchargé et le lien secret s'affiche.
3. Remplacer `index.html` dans le dépôt par ce fichier, puis pousser.
4. Envoyer le lien, en privé. Il se termine par `#cle=…`.

Pour couper l'accès : recréer le lien en décochant « Garder le même lien », puis republier. L'ancien lien ne s'ouvre plus.

## Confidentialité

- Dans `index.html`, les photos et les textes privés sont chiffrés (AES-GCM, clé aléatoire de 128 bits). La clé n'est que dans le lien, après le `#` : le navigateur ne l'envoie jamais au serveur.
- Sans la clé, la page affiche « Jeu privé » et rien d'autre.
- Toute personne qui a le lien peut voir les photos, et quelqu'un qui a déjà ouvert le jeu a pu en garder une copie.
- Le workflow refuse de publier si le dépôt contient une photo, un fichier pour les potes ou le fichier maître.
