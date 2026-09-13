# PerfLens

Application Windows de **diagnostic et de benchmark PC**, en français.
Elle répond à une question : *mon PC fonctionne-t-il à la hauteur de sa configuration ?*

- Détection du matériel : processeur, carte graphique, mémoire, stockage, carte mère, Windows
- Benchmarks CPU, GPU (scène 3D Direct3D 11), RAM et stockage
- Diagnostic en trois niveaux, avec la cause et la solution de chaque problème
- Monitoring en temps réel et test de stabilité
- « Qu'est-ce qui limite mon PC ? »

PerfLens n'invente jamais une mesure : une valeur que le PC ne fournit pas est affichée « Information non disponible », avec la raison.

## Télécharger

➡️ **[PerfLens-Setup.exe](https://github.com/Wertors/PerfLens/releases/latest/download/PerfLens-Setup.exe)** (45,6 Mo) — toujours la dernière version

Toutes les versions : [Releases](https://github.com/Wertors/PerfLens/releases)

## Installer

1. Lancez `PerfLens-Setup.exe`.
2. Windows affiche probablement **« Windows a protégé votre ordinateur »** : l'application n'est pas signée par un certificat payant. Cliquez sur **Informations complémentaires**, puis **Exécuter quand même**.
3. Suivez l'assistant. Aucun droit administrateur n'est nécessaire.

**Rien d'autre à installer** : le runtime .NET est inclus.

## Mises à jour

À partir de la version **1.1.0**, PerfLens se met à jour depuis l'application : quand une nouvelle version est publiée, un bandeau « Mise à jour disponible » apparaît. Un clic sur **Mettre à jour** la télécharge, vérifie son empreinte, l'installe et redémarre PerfLens. L'historique des résultats est conservé. Rien n'est installé sans ce clic.

Versions 1.0.0 et 1.0.1 : installez une fois la dernière version à la main, en lançant `PerfLens-Setup.exe` par-dessus.

La vérification peut être désactivée avec la case « Vérifier les mises à jour », en bas de la barre latérale.

## Configuration requise

- Windows 10 version 1809 ou plus récent, ou Windows 11, **64 bits**
- Carte graphique compatible Direct3D 11 (pour le benchmark GPU)

## Pour des résultats fiables

- PC portable : branchez-le **sur secteur**, en mode d'alimentation « Performances optimales ».
- Fermez les jeux et applications lourdes pendant les tests.

## Aider à vérifier votre matériel

Vous pouvez produire un rapport de vérification du processeur et de la carte graphique en trois minutes environ. Fermez vos jeux et applications lourdes, ouvrez une invite de commandes (`cmd`) et lancez :

```
"%LOCALAPPDATA%\Programs\PerfLens\PerfLens.exe" --gpu-report "%USERPROFILE%\Desktop"
```

Un fichier `perflens-gpu-report.txt` apparaît sur le Bureau. Il ne contient que le matériel, les valeurs des capteurs et la version du pilote : aucun nom d'utilisateur, aucun nom de machine, aucun fichier personnel. Si PerfLens a été installé « pour tous les utilisateurs », remplacez le chemin par `"C:\Program Files\PerfLens\PerfLens.exe"`.

## Confidentialité

Les mesures, benchmarks et diagnostics sont réalisés et enregistrés **uniquement sur votre PC**, dans `%LOCALAPPDATA%\PerfLens`. **Aucun résultat ni aucune information sur votre matériel n'est envoyé sur Internet.**

Une seule connexion est établie : au démarrage, PerfLens demande à GitHub quelle est la dernière version publiée. Comme pour toute visite d'un site web, GitHub voit alors votre adresse IP. Rien d'autre n'est transmis. Cette vérification se désactive avec la case « Vérifier les mises à jour ».
