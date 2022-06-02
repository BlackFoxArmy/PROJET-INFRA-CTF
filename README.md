# **Présentation du projet INFRA**

##### Groupe Maxime Chasson | Grégoire Mathieu

---

## **Contexte du projet :**

<br>

### **Pourquoi ce projet ? :**

- Le but de ce projet infra est de créer une plateforme d’apprentissage à la sécurité informatique et au hacking. L’apprentissage se fait sous la forme de défis/challenges, on peut donc y connaître ses compétences et ses points faibles.
  Le site est ainsi fait pour l’apprentissage pour les intéressés et curieux dans le domaine de la sécurité.

<br>

### **Les Capture The Flag**

- Appeler en français capture de drapeau, et CTF en abrégé est un challenge très enrichissant pour les hackeurs, il permet de s’attaquer à une victime fictive afin de s’entraîner. Le but est de trouver le fichier (appelé flag) où contient le mot de passe en s’introduisant dans une machine virtuelle.

- Sur Root-me par exemple, le Capture The Flag se fait tous les jours. Le but est de compromettre la machine en allant jusqu’à l’obtention des privilèges d’administrateurs. Il y a des containers dockers qui sont de ce fait prévu à cet effet.

<br>

## **Guide d'installation :**

### Vous pouvez télécharger le .ova de la machine virtuel préconfiguré

<br>

- identifiant = yoloctf

- mot de passe = infractf

#### **VM :**

```
https://1fichier.com/?m1of7msbaf1uwko2ni6u
```

Ou télécharger les fichiers présent au dessus :

- 1. Pour commencer, il faut télécharger les fichiers du git au préalable :
- 2. Ensuit, il faut se rendre dans le dossier /mon_premier_ctf et exécuter le fichier ctf_install

```
 cd mon_premier_ctf
 ./ctf_install
```

Si Docker n'était pas installé ou si l'utilisateur n'était pas dans le groupe Docker, il faut REBOOTER le serveur.

Si vous avez déjà fait l'installation du serveur et des containeurs, vous pouvez juste lancer le fichier :

```
 cd mon_premier_ctf
 ./ctf_run
```

- 3. Vous pouvez personnaliser votre serveur Web en modifiant le fichier :

```
web_server/.env
```

Pour pousser un peu la personnalisation, vous pouvez dans le fichier de config changer le Titre.

```
CTF_TITLE=PROJET INFRA
```

```
CTF_SUBTITLE=Notre Premiere Plateforme de CTF
```

<br>

## **Lancer le serveur :**

Lancez le serveur.

```
./ctf_run
```

### **Une des principales fonctionnalités :**

<br>

À travers le navigateur Web, tous les challenges sont accessibles. Il n'y a aucune installation à faire sur le poste des utilisateurs.

Pour pouvoir accéder au site internet du CTF, il faut soit se connecter en ssh sur la machine (.ova) car il n'y a pas d'interface graphique. Ou sinon utiliser une machine ubuntu graphique.

<br>

### **SSH**

Récupérer l'adresse IP du serveur et découvré les challenges du CTF

<br>

```
http://IP_DU_SERVEUR/
```

Pour la connexion en HTTP (tous les messages sont en claires) va être redirigée vers une connexion en HTTPS (les messages sont chiffrés et le serveur est authentifié). Vous allez avoir une alerte de sécurité. C'est normal.
Le serveur Web a généré ses propres certificats pour utiliser une liaison HTTPS (HTTP Sécurisée). Nous sommes prévenus qu'aucune autorité de certification 'officielle' ne valide les clefs de sécurité de ce site, et qu'il peut donc y avoir un risque.

<br>

## **Pour Administrer un CTF :**

Les logins pour se connecter au site son présent dans le terminal au lancement, ils ont configurables.
Exemple :

- admin
- 159753

L'onglet [Admin] en bas à gauche permet de voir :

- Le nombre de sessions actives
- Le nombre d'utilisateurs
- Les flags soumis par les utilisateurs
- Les containers démarrés par les utilisateurs
- Dès l'instant ou le serveur est démarré, les participants peuvent commencer à valider les flags. Vous pouvez aussi vouloir tester un peu. Le lien [ClearFlags] en bas de page permet d'effacer tous les flags validés.

<br>

## **Consommation CPU et mémoire par les containers**

- Pour savoir si notre machine virtual consomme beaucoup, on marque cette commande :

```
docker stats --format "table {{.Container}}\t{{.CPUPerc}}\t{{.MemUsage}}"
```

- Elle nous permet d’accéder à toute la liste des containers docker avec le %CPU et la mémoire

---

Vous pouvez, si vous le voulez, supprimer tous containers docker avec la commande :

```
./go_clean_all
```

<br>

## **En ce qui concerne les challenges :**

- Sur notre site , plusieurs challenges sont mis à disposition :

```
* Premier Flag
* Terminal
* Ghost in the Shell
* Password
* Privilege Escalation
* Network Protocol
* SQLI
* Buffer overflows
* Decode
* File Upload
* Exploit
* Python
```

### Mais aussi nous avons fait en sorte d'avoir une Kali Like sur notre site web (il faut etre connecté):

<br>

```
[Mon Terminal]
```

### Pour finir, nous avons créé un Score Board avec les classements des users ainsi que les admins sous forme de graphique :

![](https://i.imgur.com/iC8PJEW.png)
