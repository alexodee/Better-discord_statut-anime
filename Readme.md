# Statut animé pour Better Discord

* [Installation](#Installation)
* [Utilisation](#Usage)
  * [Temps d'exécution](#Temps-d'exécution)
  * [L'éditeur](#L'éditeur)
  * [Emojis](#Emojis)
    * [Emojis basiques](#Emojis-basiques)
    * [Emojis nitro](#Emojis-nitro)

## Installation
Installez Better Discord avec ce lien [BetterDiscord installer](https://github.com/BetterDiscord/Installer/releases/latest) \
Téléchargez [Statut-anime.plugin.js](/Statut-anime.plugin.js?raw=true) \
## Utilisation
Ouvrez Discord, et allez dans les paramètres de Discord jusqu'à plugins l'onglet plugin. Cliquez ensuite sur ouvrir dossier plugin. Dans la fenêtre qui s'ouvre, déposez alors le fichier [Animated_Status.plugin.js](/Animated_Status.plugin.js?raw=true) dans le dossier. Redémarrez Discord et, toujours dans le menu des plugins, activez Statut animé et paramétrez vos statuts avec la roue crantée.

### Temps d'exécution
La valeur spécifie la longueur de chaque étape d'animation en millisecondes.
Exemple : avec un délai d'attente de 2000, l'animation suivante prendrait 4 secondes pour se terminer, car 2 images clés durent 2 secondes chacune.
Pour éviter que le serveur Discord ne soit spammé avec des demandes, le délai d'attente minimum autorisé est codé en dur à 2,9 secondes. 
Logiquement, le délai d'attente de l'animation devrait être d'au moins `2900`. Au mieux, il devrait être d'environ `10000` millisecondes (10 secondes) pour que l'animation soit fluide sur les autres clients. 
Dans l'application mobile, le statut n'est pas mis à jour de manière cohérente, c'est-à-dire que la liste des membres du serveur est mise à jour en fonction des actions des utilisateurs dans l'application. Ne soyez pas surpris si l'animation n'est pas fluide ou saute des images. 

### L'éditeur
Chaque cellule ajoutée avec le bouton `+` ajoute une nouvelle étape à l'animation d'état. 
Cliquer sur le bouton `-` supprimera la dernière étape. 
Une cellule vide désactivera temporairement votre statut. Cela a été ajouté en raison d'une demande, mais est sujet à changement à l'avenir.

Dans la dernière version, la décision a été prise de supprimer l'éditeur brut du plugin. Il s'agissait simplement d'une interface textuelle instable vers le fichier de configuration JSON. 
**Vous pouvez toujours utiliser le mode RAW** en cliquant sur "Ouvrir le dossier des plugins" dans les paramètres et en modifiant "AnimatedStatus.config.json". Faites cela à vos risques et périls, vous pourriez casser des choses.

### Emojis
#### Emojis basiques
Utilisez un sélecteur emoji (Windows : <kbd>Win</kbd>+<kbd>.</kbd>). 
Vous pouvez également utiliser [un tableau Unicode](https://unicode.org/emoji/charts/full-emoji-list.html) et copier l'emoji que vous souhaitez avoir comme statut. 
Le champ `emoji_name` **ne doit pas contenir d'espace**. Sinon, le serveur Discord ignorera silencieusement votre demande de statut.
En raison d'incertitudes concernant les noms des nitro emoji, le plugin ne supprime actuellement pas automatiquement les espaces blancs.

#### Emojis nitro
- Ouvrez un chat discord, tapez `\`. 
- Sélectionnez l'emoji que vous souhaitez inclure dans votre statut à l'aide du sélecteur d'emoji. 
- Notez que le message est devenu `<:emojiname:emojiid>`. Les valeurs entre parenthèses (emojiname et emojiid) sont les valeurs requises pour le statut. 
- Modifiez les paramètres
