# Mieux-discord_statut-anime

* [Installation](#Installation)
* [Utilisation](#Utilisation)
* [Paramètres] (#Paramètres)
  * [Timeout](#Timeout)
  * [L'éditeur](#L'éditeur)
  * [Émojis](#Émojis)
    * [Emoji régulier] (#Emoji régulier)
    * [Nitro Emoji](#Nitro-Emoji)
  * [Exemples](#Exemples)

## Installation
Installez à l'aide du [programme d'installation de BetterDiscord] (https://github.com/BetterDiscord/Installer/releases/latest) très pratique \
Téléchargez [Animated_Status.plugin.js](/Animated_Status.plugin.js?raw=true) dans le répertoire suivant \
Mac : `~/Bibliothèque/Préférences/BetterDiscord`\
Windows : `%appdata%\BetterDiscord\plugins`\
Linux : `~/.config/BetterDiscord/plugins`

## Utilisation
Ouvrez Discord, allez dans Paramètres\>Plugins, activez AnimatedStatus et cliquez sur Paramètres.\
Entrez les informations requises dans les champs de saisie et cliquez sur le bouton "enregistrer".
Si vous cliquez sur "Terminé" sans enregistrer, vos paramètres seront supprimés.

## Réglages
<table align=center">
  <td> <img src="Captures d'écran/Settings_Dark.png"> </td>
  <td> <img src="Captures d'écran/Settings_Light.png"> </td>
</table>

### Temps libre
La valeur spécifie la longueur de chaque étape d'animation en millisecondes.
Exemple : avec un délai d'attente de 2000, l'animation suivante prendrait 4 secondes pour se terminer, car 2 images clés durent 2 secondes chacune.
```
abc
définitivement
```
Pour éviter que le serveur Discord ne soit spammé avec des demandes, le délai d'attente minimum autorisé est codé en dur à 2,9 secondes. \
Logiquement, le délai d'attente de l'animation devrait être d'au moins `2900`. Au mieux, il devrait être d'environ `10000` millisecondes (10 secondes) pour que l'animation soit fluide sur les autres clients. \
Dans l'application mobile, le statut n'est pas mis à jour de manière cohérente, c'est-à-dire que la liste des membres du serveur est mise à jour en fonction des actions des utilisateurs dans l'application. Ne soyez pas surpris si l'animation n'est pas fluide ou saute des images. \
^ Selon [@pintoso](https://github.com/pintoso)

### L'éditeur
Chaque cellule ajoutée avec le bouton `+` ajoute une nouvelle étape à l'animation d'état. \
Cliquer sur le bouton `-` supprimera la dernière étape. \
Une cellule vide désactivera temporairement votre statut. Cela a été ajouté en raison d'une demande, mais est sujet à changement à l'avenir.

Dans la dernière version, la décision a été prise de supprimer l'éditeur brut du plugin. Il s'agissait simplement d'une interface textuelle instable vers le fichier de configuration JSON. \
**Vous pouvez toujours utiliser le mode RAW** en cliquant sur "Ouvrir le dossier des plugins" dans les paramètres et en modifiant "AnimatedStatus.config.json". Faites cela à vos risques et périls, vous pourriez casser des choses.

### Émojis
#### Emoji régulier
Utilisez un sélecteur emoji (Windows : <kbd>Win</kbd>+<kbd>.</kbd>). \
Vous pouvez également utiliser [un tableau Unicode](https://unicode.org/emoji/charts/full-emoji-list.html) et copier l'emoji que vous souhaitez avoir comme statut. \
Le champ `emoji_name` **ne doit pas contenir d'espace**. Sinon, le serveur Discord ignorera silencieusement votre demande de statut.
En raison d'incertitudes concernant les noms des nitro emoji, le plugin ne supprime actuellement pas automatiquement les espaces blancs.

#### Nitro Emoji
- Ouvrez un chat discord, tapez `\`. \
  <img src="Captures d'écran/nitro0.png">
- Sélectionnez l'emoji que vous souhaitez inclure dans votre statut à l'aide du sélecteur d'emoji. \
  <img src="Captures d'écran/nitro1.png">
- Notez que le message est devenu `<:emojiname:emojiid>`. Les valeurs entre parenthèses (emojiname et emojiid) sont les valeurs requises pour le statut. \
  <img src="Captures d'écran/nitro2.png">
- Modifiez les paramètres en conséquence \
  <img src="Captures d'écran/nitro3.png">

### Exemples
Certaines captures d'écran sont accélérées, de sorte que le ReadMe semble plus attrayant.

#### L'horloge
- **Résultat:** \
  <img src="Captures d'écran/JS_Clock.gif">
- **Champ Emoji :** \
  <code> eval ['🕛','🕐','🕑','🕒','🕓','🕔','🕕','🕖','🕗','🕘','🕙',' 🕚'][((nouvelle date()).getHours()%12)] ; </code>

#### Horloge et texte
- **Résultat:** \
  <img src="Captures d'écran/JS_ClockText.png">
- **Champ Emoji :** \
  <code> eval ['🕛','🕐','🕑','🕒','🕓','🕔','🕕','🕖','🕗','🕘','🕙',' 🕚'][((nouvelle date()).getHours()%12)] ; </code>
- **Champ de texte:** \
  <code> eval let fmt=t=>(t<10?'0':'')+t;let d=new Date();`${fmt(d.getHours())}:${fmt( d.getMinutes())} :${fmt(d.getSeconds())}` ; </code>
