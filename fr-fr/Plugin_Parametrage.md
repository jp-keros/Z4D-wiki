# Paramétrage du Plugin

Cette étape est la deuxième du processus d'installation du plugin ZigBeeForDomoticZ.

Vous devez donc avoir suivi et terminé l'[étape 1 Installation du Plugin](Plugin_Installation.md)



## Le paramétrage

* Ouvrir __DomoticZ__ dans votre navigateur

* Aller dans le menu __Configuration__ puis __Matériel__

* Pour ajouter le Plugin ZigBeeForDomoticZ, renseigner les informations suivantes :

| Paramètre    | Description | Information |
| ------------ | ------------------ | ----------- |
| __Nom__                  | Renseigner un Nom du coordinateur  | Si vous utiliser plusieurs coordinateur, vous aurez besoin de plusieurs instances du matériel ZigBeeForDomoticZ et le nom permettra de les identifier.<br/><br/>Il est conseillé de ne pas mettre d'espace ou de caractère spécial dans le nom du Plugin. Ce nom peut être utiliser dans une URL et un espace ou des caractères spéciaux peuvent générer des problèmes. |
| __Type__                 | Sélectionner `ZigBeeForDomoticZ plugin` | Si ZigBeeForDomoticZ plugin n’apparaît pas en bas de la liste, c'est que le Plugin n'est pas correctement installé.
| __Coordinator Model__         | Sélectionner le modèle de coordinateur | - ZiGate (modèle V1)<br/> - ZiGate+ (modèle V2)<br/> - Texas Instruments ZNP<br/> - Silicon Labs EZSP<br/> - ConBee/RasBee|
| __Coordinator  Type__         | Sélectionner mode de communication | -  USB<br/>-  DIN<br/>- PI<br/>- TCPIP (Wifi ou Ethernet)<br/>- Aucun|
| __Port série__           | Sélectionner le port USB sur lequel est branché le coordinateur | Penser à fixer le port de vos équipements usb [Méthode persistent USB](https://easydomoticz.com/mon-premier-peripherique-z-wave-2)|
| __IP__                   | Renseigner l'IP du coordinateur | Pour le mode TCPIP uniquement<br/>Laisser 0.0.0.0 pour les autres modes |
| __Port__                 | Renseigner le Port du coordinateur (9999 par défaut)| Pour le mode TCPIP uniquement<br/>Laisser 9999 pour les autres modes |
| __API base url__ | Renseigner l'adresse du serveur DomoticZ | Adresse sous la forme http://username:password@127.0.0.1:port <br/>Par défaut http://127.0.0.1:8080 |
| __WebUI Port__| Renseigner le port pour accéder à l'administration web du Plugin (9440 par défaut). | A modifier en cas d'utilisation de plusieurs instances du Plugin. |
| __Initialize Coordinator__ | Sélectionner True pour initialiser le coordinateur avec les paramètres du Plugin (False par défaut). <br/>À __activer obligatoirement__ lors de la configuration initiale (ou après un Erase EEPROM d'une ZiGate). | __ATTENTION :__ L'activation va effacer toutes des informations d'appairage du coordinateur.<br/> Redémarrer le Plugin pour lancer l'initialisation. Vérifier que le paramètre est à l'état False après le redémarrage. |
| __Debugging__ | Laisser vide |

* Si c'est pour une première installation du Plugin avec un nouveau coordinateur, mettre Initialize Coordinator à __True__, sinon toujours laisser à __False__ (ce paramètre efface les informations du coordinateur).

* Cliquer sur __Ajouter__.

La ligne correspondante à votre plugin ZigBeeForDomoticZ (avec le nom défini) est normalement apparue dans la liste des matériels.

* Cliquer sur la ligne de votre plugin ZigBeeForDomoticZ.

__ATTENTION :__ à partir de maintenant, il ne faut surtout plus cliquer sur le bouton __Ajouter__ en bas : cela aurait pour effet de dupliquer le plugin. Remontez toujours en haut des paramètres pour utiliser le bouton __Modifier__.

* Mettre __Initialize ZCoordinator (Erase Memory)__ à __False__.

* Décoché __Activé__ pour désactiver le plugin.

* Cliquer sur __Modifier__ (ne pas cliquer sur Ajouter car cela dupliquera le plugin).

* Recliquer sur la ligne du plugin ZigBeeForDomoticZ.

* Recocher __Activé__ pour réactiver le Plugin.

* Cliquer sur __Modifier__ pour relancer le Plugin.

Vérifier les logs que le plugin ZigBeeForDomoticZ s'initialise correctement.

![Domoticz Hardware Menu for Plugin](Images/FR_Plugin-Parametrage.png)

*Cette image est susceptible d'avoir évolué depuis l'écriture de cette documentation.*

## Les widgets du Plugin

A l'installation, le Plugin créé 2 widgets dans l'onglet __Mesures__ de DomoticZ.

![Administration Widgets](../Images/Widgets_Admin.png)

### Widget Statut

Le widget s'appelle 'ZigBee4DomoticZ Status XX' avec XX correspondant au numéro de matériel du plugin ZigBeeForDomoticZ. Il indiquera l'état du Plugin. Le Log du widget permettra d'avoir l'historique des états du Plugin.

Les différents états possibles sont :

| État | Couleur | Description |
| ---- | ------- | ----------- |
| Off | Rouge | Le Plugin s'éteint ou il y a un problème de communication |
| Démarrage | Gris | Le Plugin démarre |
| Prêt | Vert | Le Plugin est en fonctionnement normal |
| Appairage | Ambre | Le Plugin est en mode appairage |
| Saturation | Ambre | Le Plugin sature : il peut y avoir des délais de transmissions rallongés |


### Widget Texte

Liste non-exhaustive des notifications :

* Succès d'appairage
* Échec d'appairage
* Exclusion d'un objet
* Rapport de topologie réseau disponible
* Rapport d'interférences réseau disponible
* Problème réseau
* Canal ZigBee

Un exemple de l'historique des notifications (en anglais)

![Notification Widgets](../Images/Widget_Notifications.png)


Si tout semble fonctionner normalement, passer à l'[étape 3 Configuration du Plugin](Plugin_Configuration.md)
