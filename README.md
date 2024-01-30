
# Snap URL déclencheur customisé

![Aperçu de la fenêtre de dialogue](/snapurl-handle-snap-install.png)


lorsque vous avez une URI contenant le scheme "snap", alors cela déclenche un "handler".

```
xdg-open snap://vlc
```

Malheureusement, le handler par défaut lance le [snap-store](https://snapcraft.io/store)

Ce script permet d'éviter cela et lance une fenêtre de dialogue pour savoir si vous voulez installer puis install via un simple appel "snap install"

Le script utilise [zenity](https://doc.ubuntu-fr.org/zenity) pour avoir une fenêtre de dialogue

## Comment fonctionne-t-il :
  - on récupère le nom du programme dans l'URI
  - on réalise la commande `snap info nom-du-programme`
  - on parse la sortie de la commande précédente pour pouvoir formater les informations affichées dans la fenêtre de dialogue
  - la fenêtre de dialogue demande confirmation de l'installation
  - l'installation se fait via la commande `snap install nom-du-programme`

## Auteur
Gabriel Theuws
