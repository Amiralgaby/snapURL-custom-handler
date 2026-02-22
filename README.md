
# Snap URL déclencheur customisé

![Aperçu de la fenêtre de dialogue](/snapurl-handle-snap-install.png)


Lorsque vous lancer une URI commençant par "snap://" alors le handler associé au "scheme" snap est lancé.

```
xdg-open snap://vlc
```

Malheureusement, le handler par défaut lance le [snap-store](https://snapcraft.io/store)

Ce script permet d'éviter l'installation du store et lance une fenêtre de dialogue avec possibilité d'installer ou non.

## Installation
 - exécuter le programme sans argument
 ```
 $ ./snapURL 
voulez-vous installer le handler et remplacer snap-handle-link.desktop (Y/n) ?
y
Fichier /home/gabriel/.local/share/applications/snap-handler.desktop créé.
Déplacement dans /usr/share/applications/
 ```

## Verification de l'installation

Dans votre navigateur web, tapez "snap://vlc", la fenêtre identique à la capture d'écran s'ouvrira

## Note développement
Le script utilise [zenity](https://doc.ubuntu-fr.org/zenity) pour la fenêtre de dialogue

## Comment fonctionne-t-il :
  - on récupère le nom du programme dans l'URI
  - on réalise la commande `snap info nom-du-programme`
  - on parse la sortie de la commande précédente pour pouvoir formater les informations affichées dans la fenêtre de dialogue
  - la fenêtre de dialogue demande confirmation de l'installation
  - l'installation se fait via la commande `snap install nom-du-programme`

## Auteur
Gabriel Theuws
