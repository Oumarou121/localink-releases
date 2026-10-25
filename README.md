<h1 align="center">LocaLink — téléchargements</h1>

<p align="center">
Messagerie, fichiers et appels pour les équipes, sur le réseau local. Sans Internet, sans cloud.
</p>

<p align="center">
<a href="https://nexistec.com/logiciels/localink">Site officiel</a> ·
<a href="https://github.com/Oumarou121/localink-releases/releases/latest">Dernière version</a> ·
<a href="#licence">Licence</a>
</p>

---

Ce dépôt sert uniquement à **distribuer les installateurs de LocaLink**. Il ne contient pas le code source.

## Télécharger

| Système | Fichier | Configuration requise |
|---|---|---|
| Windows | [LocaLink-windows-x64-setup.exe](https://github.com/Oumarou121/localink-releases/releases/latest/download/LocaLink-windows-x64-setup.exe) | Windows 10 (1809) ou plus récent, 64 bits |
| macOS | [LocaLink-macos-universal.dmg](https://github.com/Oumarou121/localink-releases/releases/latest/download/LocaLink-macos-universal.dmg) | macOS 12 ou plus récent, Apple Silicon et Intel |
| Linux (.deb) | [LocaLink-linux-amd64.deb](https://github.com/Oumarou121/localink-releases/releases/latest/download/LocaLink-linux-amd64.deb) | Ubuntu 22.04, Debian 12 ou équivalent |
| Linux (AppImage) | [LocaLink-linux-x86_64.AppImage](https://github.com/Oumarou121/localink-releases/releases/latest/download/LocaLink-linux-x86_64.AppImage) | Toute distribution 64 bits récente |

Ces liens pointent toujours vers la dernière version. Les versions précédentes et leurs notes se trouvent dans l'onglet [Releases](https://github.com/Oumarou121/localink-releases/releases).

## Ce que fait LocaLink

- Découverte automatique des postes du réseau local
- Messagerie individuelle et de groupe, utilisable même quand le serveur est éteint
- Transferts de fichiers et dossiers partagés synchronisés
- Appels vocaux et vidéo, partage d'écran
- Comptes, rôles et journal d'audit, administrés depuis un poste serveur
- Chiffrement des échanges (TLS) entre postes autorisés

Les données restent sur vos postes. Aucune connexion Internet n'est nécessaire pour l'usage quotidien.

## Installer

**Windows** : lancez `LocaLink-windows-x64-setup.exe`. L'installateur ajoute la règle de pare-feu nécessaire.

**macOS** : ouvrez le `.dmg` et glissez LocaLink dans le dossier Applications.

**Linux** :
```sh
sudo apt install ./LocaLink-linux-amd64.deb
```
ou, avec l'AppImage :
```sh
chmod +x LocaLink-linux-x86_64.AppImage && ./LocaLink-linux-x86_64.AppImage
```

Installez LocaLink sur chaque poste. Au premier lancement, choisissez un poste **serveur** (il gère les comptes et la licence) ; les autres postes s'y rattachent.

### Réseau

Les postes doivent pouvoir se joindre sur ces ports :

| Port | Protocole | Usage |
|---|---|---|
| 45454 | UDP | découverte des postes |
| 12345 | TCP | messagerie, comptes, synchronisation (vers le serveur) |
| 12346 | TCP | transferts de fichiers, dossiers partagés |
| 12347 | TCP | signalisation des appels |
| 12348–12447 | UDP | audio et vidéo des appels |

Si vos postes sont sur plusieurs sous-réseaux, saisissez l'adresse du serveur dans les paramètres de chaque poste.

## Vérifier un téléchargement

Chaque version publie un fichier `SHA256SUMS.txt` avec l'empreinte de chaque installateur.

```powershell
# Windows (PowerShell)
Get-FileHash .\LocaLink-windows-x64-setup.exe -Algorithm SHA256
```
```sh
# macOS / Linux
shasum -a 256 LocaLink-macos-universal.dmg
sha256sum LocaLink-linux-amd64.deb
```

L'empreinte affichée doit être identique à celle de `SHA256SUMS.txt`.

## Licence

LocaLink est gratuit pour les petites équipes. Les plans **Pro** (5, 10 ou 25 postes) et **Entreprise** (26 postes et plus) débloquent les fonctions avancées. Ce sont des licences définitives, payées une seule fois, toutes les versions 1.x comprises.

Après l'achat, votre code d'activation (`NXL-XXXX-XXXX-XXXX`) apparaît dans le tableau de bord Nexis de votre organisation. Saisissez-le dans LocaLink, sur le poste serveur : **Administration → Licence → Activer en ligne**. Sans Internet, téléchargez le fichier de licence depuis le tableau de bord et importez-le.

Devis et achat : [nexistec.com/logiciels/localink](https://nexistec.com/logiciels/localink)

L'utilisation des installateurs est soumise au [contrat de licence](LICENSE).

## Support

Pour une question ou un problème, passez par [nexistec.com](https://nexistec.com). Indiquez votre version de LocaLink et votre système.

---

© 2026 Nexis. Tous droits réservés.
