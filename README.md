
Snap URL déclencheur customisé
------

lorsque vous avez une URI contenant le scheme "snap", alors cela déclenche un "handler".

```
xdg-open snap://vlc
```

Malheureusement, le handler par défaut lance le snap-store

Ce script permet d'éviter cela et lance une fenêtre de dialogue pour savoir si vous voulez installer puis install via un simple appel "snap install"

Le script utilise zenity pour avoir une interface de dialogue

Auteur : Gabriel Theuws
