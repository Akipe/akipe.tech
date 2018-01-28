---
title: 'Configurer Git Sync pour Grav'
published: false
date: '28-01-2018 18:42'
publish_date: '28-01-2018 18:42'
taxonomy:
    tag:
        - grav
        - git
        - git-sync
twittercardoptions: summary
articleenabled: false
musiceventenabled: false
orgaenabled: false
orga:
    ratingValue: 2.5
orgaratingenabled: false
eventenabled: false
personenabled: false
restaurantenabled: false
restaurant:
    priceRange: $
---

# Configurer Git Sync pour Grav

Git Sync est une extension pour le CMS Grav qui permet de syncrhoniser les fichiers du site sur un repositorie git, avec comme choix de plateforme Github, Bitbucket, Gitlab et le repositorie git simples. La synchronisation fonctionne dans les deux sens.

## Installation

Pour installer l'extension ont peut soit passer par l'interface d'administration et chercher avec le nom "git-sync", soit passer en ligne de commande dans le répertoire du site :

```bash
bin/gpm install git-sync
```

## Initialiser

J'ai eu quelques problèmes pour initialiser l'extension.

Avant de lancer l'asstsiant de configuration, il faut remettre l'adresse de l'administration par default ("/admin") si vous l'avez modifié.

Je n'ai pas réussi à initialiser un nouveau repostiory directement depuis l'extension, donc je l'ai initialisé directement depuis le terminal.

```bash
cd dossier-site-web/user # C'est dans le dossier user que git sync
git init
git remote remove origin # On supprime le repo ajouté depuis l'assistant de configuration de Git Sync
git remote add origin "url-repository" #
git push -u origin master # On initialise le repo externe
```

Une fois le repo en ligne synchronisé, il faudra remodifier les paramèetres dans Git Sync, notamment :

- "Git Repository" : l'url de votre repository
- "Git User" : votre nom d'utilisateur pour accéder au repository
- "Git Password or Token" : et le mot de passe 

Si vous aviez modifier l'url de l'administration, il ne faudra pas oublier de le remettre ;)