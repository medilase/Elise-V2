# Elise v2

L'assistante de consultation qui écoute, transcrit et rédige vos notes, entièrement sur votre Mac, en s'en tenant à ce que vous avez dit ou écrit.

**[Télécharger Elise v2 pour Mac](https://github.com/medilase/elise-v2/releases/latest/download/Elise-v2-mac-arm64.zip)** (144 Mo, Mac à puce Apple, macOS 13 ou plus récent) · [Toutes les versions](https://github.com/medilase/elise-v2/releases)

L'installation prend 5 minutes. Si Elise est déjà installée sur le Mac, Elise v2 reprend ses modèles d'IA et s'ouvre aussitôt prête ; sinon, elle les télécharge une seule fois, en 10 minutes à une heure selon la connexion. Après, tout fonctionne sur le Mac, sans connexion.

## Elise v2, en bref

Elise v2 est Elise 0.3.2 limitée à ce que le praticien a dit ou écrit : elle n'ajoute aucune information clinique. Tout le reste est identique.

| Fonction | Elise | Elise v2 |
| --- | --- | --- |
| Tâches | Actions relevées dans la consultation | Seulement les actions annoncées, chacune retrouvée dans la transcription et affichée avec sa phrase |
| Courriers reçus | Résumé avec les valeurs importantes, actions demandées ou implicites | Résumé tel que l'auteur l'écrit, seulement les actions demandées en toutes lettres |
| Préparation de consultation | Inclut des points à vérifier | Seulement ce que disent les notes et les tâches en attente |
| Demander à Elise | Peut croiser la consultation et votre bibliothèque | Bibliothèque interrogée seule, sans les données du patient ; aucune conduite à tenir proposée |

## Ce qu'il faut

- **Un Mac à puce Apple** (M1 ou plus récent). Pour vérifier : menu Pomme → À propos de ce Mac, ligne « Puce ». Les Mac à processeur Intel ne sont pas pris en charge.
- **macOS 13 Ventura** ou plus récent.
- **16 Go de mémoire** conseillés. Avec 8 Go, Elise v2 fonctionne avec des modèles plus légers.
- **De la place sur le disque** : 370 Mo pour l'app, plus les modèles d'IA (tableau ci-dessous), sauf s'ils sont déjà là pour Elise.
- **Internet au premier lancement** seulement, et seulement s'il faut télécharger les modèles.

| Mémoire du Mac | Modèle de rédaction | Modèle de transcription | À télécharger |
| --- | --- | --- | --- |
| 8 Go | Gemma 4 E4B (Google) | Whisper large-v3-turbo allégé | 5,2 Go |
| 16 ou 18 Go | Ministral 3 8B (Mistral AI) | Whisper large-v3-turbo | 6,8 Go |
| 24 Go | Ministral 3 14B (Mistral AI) | Whisper large-v3-turbo | 9,9 Go |
| 32 Go et plus | Gemma 4 26B (Google) | Whisper large-v3-turbo | 16,2 Go |

En option, dans Réglages → Intelligence artificielle : **Parakeet TDT v3** (NVIDIA, 487 Mo), une transcription bien plus rapide que Whisper pour le français et 24 autres langues européennes.

## 1. Installer l'app

1. Téléchargez **Elise-v2-mac-arm64.zip** avec le lien ci-dessus. Safari le décompresse tout seul ; sinon, double-cliquez sur le fichier zip.
2. Glissez **Elise v2** du dossier Téléchargements vers le dossier **Applications**, avant de l'ouvrir. Lancée depuis Téléchargements, l'app peut être refusée par macOS. Elise, si elle est installée, reste en place : les deux apps cohabitent.
3. Double-cliquez sur l'app dans Applications. macOS indique qu'Apple n'a pas pu vérifier l'absence de logiciel malveillant. Cliquez sur **Terminé**, surtout pas sur « Placer dans la corbeille ».
4. Ouvrez **Réglages Système → Confidentialité et sécurité** et descendez jusqu'à la rubrique Sécurité. À côté du message sur Elise v2, cliquez sur **Ouvrir quand même**.
5. Confirmez avec Touch ID ou votre mot de passe, puis cliquez à nouveau sur **Ouvrir quand même**.

Elise v2 s'ouvre. macOS ne refait cette vérification qu'après une mise à jour de l'app.

## 2. Premier lancement : les modèles d'IA

Si Elise a déjà téléchargé ses modèles sur ce Mac, Elise v2 les utilise et s'ouvre directement, sans écran Bienvenue. Sinon, l'écran **Bienvenue** affiche les deux modèles choisis pour votre Mac et leur taille : cliquez sur **Télécharger**.

- Laissez Elise v2 ouverte et le Mac branché pendant le téléchargement. S'il est interrompu, il reprend là où il s'était arrêté.
- Les modèles viennent de Hugging Face (huggingface.co), et Parakeet de github.com : le réseau du cabinet doit autoriser ces sites.
- macOS peut demander l'accès au trousseau pour « Elise v2 Safe Storage ». Saisissez votre mot de passe de session et choisissez **Toujours autoriser** : c'est la clé qui chiffre vos consultations.
- Vous utilisez déjà whisper-server et LM Studio ? Cliquez sur « J'utilise déjà whisper-server et LM Studio » : rien n'est téléchargé.

Faites ensuite une consultation d'essai de quelques minutes pour vérifier le micro et la note.

## 3. Autorisations macOS

macOS demande chaque autorisation la première fois qu'elle sert, pour chaque app : celles déjà données à Elise ne valent pas pour Elise v2. Cliquez sur **Autoriser** ou **OK**.

| Autorisation | Demandée | À quoi elle sert |
| --- | --- | --- |
| Micro | À la première consultation ou dictée | Entendre la consultation. Le son n'est jamais conservé. |
| Enregistrement de l'écran et de l'audio système | À la première téléconsultation | Capter la voix du patient qui sort de l'ordinateur. Elise v2 n'enregistre pas l'écran. |
| Accessibilité | Au premier « Coller dans l'app active » | Taper la note dans votre logiciel métier. |
| Automatisation (System Events) | Au même moment | Idem. |

Refusée par erreur ? Ouvrez **Réglages Système → Confidentialité et sécurité**, choisissez l'autorisation, activez Elise v2, puis quittez-la et rouvrez-la.

## 4. Activer la licence

La clé d'Elise vaut pour Elise v2, et l'essai de **14 jours** est commun aux deux apps : il commence au premier lancement de l'une ou de l'autre.

1. Après l'achat, vous recevez un e-mail avec votre clé (elle commence par ELISE-) et le prénom et le nom auxquels elle est liée.
2. Dans Elise v2, ouvrez **Réglages → Licence**.
3. Saisissez votre prénom et votre nom tels qu'ils figurent dans l'e-mail, collez la clé, puis cliquez sur **Activer**.

- Une clé déjà activée dans Elise doit être saisie une fois dans Elise v2 : chaque app garde ses propres réglages.
- La licence est personnelle : la même clé s'active sur tous vos Mac, et votre nom figure sur les documents produits.
- Elle est vérifiée sur le Mac, sans connexion.
- Licence annuelle : Elise v2 vous prévient 30 jours avant l'échéance, puis laisse 7 jours de grâce.
- Sans licence valide, l'enregistrement et la rédaction s'arrêtent, mais vos consultations restent lisibles, copiables et exportables.

## Avec Elise sur le même Mac

Les deux apps sont indépendantes : une consultation faite dans l'une n'apparaît pas dans l'autre. Elles partagent seulement les modèles d'IA, la période d'essai et le dossier des documents exportés.

- **Modèles partagés** : supprimer un modèle dans les Réglages de l'une le supprime aussi pour l'autre.
- **Raccourcis clavier** : les deux apps ont les mêmes par défaut (⌃⌥⌘R, ⌃⌥⌘V, ⌃⌥⌘D). Ouvertes en même temps, seule la première lancée les reçoit ; changez-les dans Réglages → Raccourcis et Stream Deck, ou n'en ouvrez qu'une.
- **Stream Deck** : les liens d'Elise v2 commencent par `elise-v2://` ; ceux d'Elise restent en `elise://`.

## Où sont vos données

Tout reste sur votre Mac. Le son n'est jamais écrit sur le disque.

- **Consultations, réglages, licence** : chiffrés dans ~/Library/Application Support/Elise v2.
- **Modèles d'IA** : dans ~/Library/Application Support/Elise/models s'ils venaient d'Elise, sinon dans le dossier d'Elise v2.
- **Documents exportés** (PDF, Word) : Documents → Profession Libérale → Documents générés, modifiable dans Réglages → Documents et en-tête. Si iCloud synchronise votre dossier Documents, Elise v2 vous prévient et propose un autre dossier.
- **Effacement automatique** : transcriptions après 30 jours, consultations après 1 an, réglable dans Réglages → Confidentialité.

Elise v2 ne remplace pas votre dossier patient : reportez chaque document validé dans votre logiciel métier. C'est une aide à la documentation qui n'ajoute aucune information clinique ; les documents produits sont des brouillons, à relire et valider par le praticien. Elle n'est pas destinée au diagnostic ni au choix d'un traitement.

## Mettre à jour et désinstaller

**Mettre à jour.** Vos consultations, réglages, licence et modèles sont conservés.

1. Quittez Elise v2 (⌘Q).
2. Téléchargez la nouvelle version et glissez-la dans Applications, puis choisissez **Remplacer**.
3. Ouvrez-la. Si macOS la bloque, refaites les étapes 3 à 5 de « Installer l'app ».

Après une mise à jour, macOS peut redemander l'accès au trousseau : choisissez **Toujours autoriser**. Si « Coller dans l'app active » ne colle plus, ouvrez Réglages Système → Confidentialité et sécurité → Accessibilité, retirez Elise v2 avec le bouton −, puis rajoutez-la avec +.

**Désinstaller.** Glissez Elise v2 d'Applications vers la Corbeille. Pour effacer aussi vos consultations : dans le Finder, menu Aller → Aller au dossier, tapez ~/Library/Application Support/Elise v2, puis mettez ce dossier à la Corbeille. C'est définitif : exportez d'abord ce que vous voulez garder. Les modèles repris d'Elise restent dans le dossier d'Elise.

## En cas de problème

| Ce que vous voyez | Que faire |
| --- | --- |
| macOS refuse d'ouvrir l'app et aucun bouton « Ouvrir quand même » n'apparaît | Vérifiez que l'app est dans Applications, puis refaites les étapes 3 à 5 de « Installer l'app ». |
| « Elise v2 » est endommagé et ne peut pas être ouvert | Téléchargez à nouveau le zip et rangez l'app dans Applications. Si le message reste, utilisez la commande ci-dessous. |
| « Cette app n'est pas prise en charge sur ce Mac » | Le Mac a un processeur Intel ou une version de macOS antérieure à 13 : Elise v2 ne peut pas y fonctionner. |
| Le téléchargement des modèles n'avance pas | Vérifiez la connexion et que le réseau autorise huggingface.co (et github.com pour Parakeet). Il reprend où il s'était arrêté. |
| « Aucun son reçu » pendant une consultation | Autorisez le Micro pour Elise v2 (section 3), puis choisissez le bon micro dans Réglages → Son. |
| En téléconsultation, la voix du patient manque | Autorisez « Enregistrement de l'écran et de l'audio système », puis quittez et rouvrez Elise v2. |
| « Coller dans l'app active » ne fait rien | Autorisez Accessibilité et Automatisation (section 3). |
| Un raccourci clavier ne répond pas | Elise est peut-être ouverte et l'utilise déjà : quittez-la, ou changez le raccourci dans Réglages → Raccourcis et Stream Deck. |

En dernier recours, si l'app reste bloquée : ouvrez l'app Terminal, collez cette ligne, appuyez sur Entrée, puis rouvrez Elise v2. Cette commande retire seulement le marquage « téléchargé d'Internet » d'Elise v2.

```
xattr -dr com.apple.quarantine "/Applications/Elise v2.app"
```

---

Modèles : Whisper (OpenAI, MIT), Parakeet TDT v3 (NVIDIA, CC-BY-4.0), Mistral AI (Apache 2.0), Gemma (Google, Apache 2.0).

© SAS MEDILASE 2026 · [neolaser.eu](https://neolaser.eu)
