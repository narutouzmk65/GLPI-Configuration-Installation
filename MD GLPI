GLPI
Gestion Libre de Parc Informatique
BTS SIO  ·  SISR  ·  Documentation complète

Installation  ·  Configuration  ·  Agents  ·  Tests

 
Architecture GLPI — Serveur Debian + Agents Windows & Linux

Sommaire
Sommaire	1
Partie 1 — La gestion de parc informatique	1
1.1 Composition d'un parc informatique	1
1.2 Inventaire et suivi du parc	1
1.3 Le référentiel ITIL	1
Partie 2 — Démarche qualité et référentiels	1
2.1 Définition d'une démarche qualité	1
2.2 ITIL — Information Technology Infrastructure Library	1
2.3 COBIT — Control Objectives for IT	1
2.4 CMMI — Capability Maturity Model Integration	1
2.5 ISO 27001 — Sécurité de l'information	1
Partie 3 — Le logiciel GLPI	1
3.1 Présentation de GLPI	1
3.2 Fonctionnalités du plugin Agent GLPI	1
3.3 Valeur ajoutée du serveur GLPI	1
Partie 4 — Installation du serveur GLPI	1
4.1 Mise à jour du système	1
4.2 Installation des extensions PHP 8.4	1
4.3 Sécurisation de MariaDB	1
4.4 Création de la base de données	1
4.5 Téléchargement et décompression de GLPI 11	1
4.6 Organisation des répertoires et permissions	1
4.7 Configuration du VirtualHost Apache	1
4.8 Configuration via l'interface web	1
Partie 5 — Installation de l'agent sur Debian	1
5.1 Téléchargement de l'installeur	1
5.2 Exécution de l'installeur	1
5.3 Activation et démarrage du service	1
5.4 Vérification du fichier de configuration	1
Partie 6 — Installation de l'agent sur Windows	1
6.1 Téléchargement	1
6.2 Installation graphique (méthode simple)	1
6.3 Installation silencieuse (ligne de commande)	1
6.4 Installation via Winget	1
6.5 Vérification du service	1
Partie 7 — Tests et validation	1
7.1 Test 1 — Accessibilité du serveur GLPI	1
7.2 Test 2 — Forcer un inventaire depuis Debian	1
7.3 Test 3 — Forcer un inventaire depuis Windows	1
Méthode 1 — Via le navigateur (la plus simple)	1
Méthode 2 — Via l'invite de commandes (administrateur)	1
Méthode 3 — Statut de l'agent	1
7.4 Test 4 — Vérifier l'inventaire dans GLPI	1
7.5 Test 5 — Activer l'inventaire natif GLPI	1
7.6 Checklist de sécurité post-installation	1
Partie 8 — Gestion des incidents (Helpdesk)	1
8.1 Créer un utilisateur de type normal	1
8.2 Créer un ticket d'incident	1
8.3 Créer un utilisateur technicien	1
8.4 Suivi et clôture du ticket	1

Partie 1 — La gestion de parc informatique
1.1 Composition d'un parc informatique
Le parc informatique d'une organisation est un assemblage, parfois hétéroclite, de matériels et de logiciels accumulés tout au long des années. On y trouve des :

▶	Équipements matériels (hardware) : ordinateurs fixes et portables, serveurs, imprimantes, scanners, smartphones, équipements réseau (switchs, routeurs, bornes Wi-Fi).
▶	Logiciels (software) : systèmes d'exploitation, suites bureautiques, logiciels métiers, antivirus, outils de supervision, licences diverses.
▶	Équipements réseau et télécoms : câblage, commutateurs, routeurs, DSLAM, systèmes téléphoniques VoIP.
▶	Infrastructure physique : baies serveurs, onduleurs, climatisation salle serveurs, systèmes de sauvegarde.
▶	Ressources documentaires : contrats de maintenance, garanties, documentations techniques, manuels, certificats de licences.

1.2 Inventaire et suivi du parc
La gestion du parc informatique recouvre la fonction d'inventaire des éléments mais aussi le suivi et l'évolution :

▶	Inventaire complet du matériel et des logiciels installés sur chaque poste.
▶	Suivi des licences logicielles et vérification de leur conformité.
▶	Gestion des garanties, des contrats de maintenance et des dates d'expiration.
▶	Suivi de la localisation physique de chaque équipement dans l'organisation.
▶	Gestion du cycle de vie du matériel (achat, utilisation, renouvellement, mise au rebut).
▶	Suivi des mises à jour système et des correctifs de sécurité (patching).
▶	Gestion des droits d'accès, des comptes utilisateurs et des habilitations.
▶	Planification des renouvellements matériels à court et moyen terme.
▶	Suivi financier et comptable des équipements (valeur d'achat, amortissement).
▶	Gestion des incidents, tickets d'assistance et demandes utilisateurs (helpdesk).
▶	Analyse des besoins et planification des évolutions du système d'information.

ℹ La gestion de parc permet de répondre aux questions quotidiennes de l'administrateur réseau :
Quelles versions de Windows sont installées et sur quels postes ? Y a-t-il des disques proches de la saturation ? Quels postes sont encore sous garantie ? Combien de machines à renouveler dans 2 ans ?

1.3 Le référentiel ITIL
La tendance actuelle des DSI est l'adoption d'un référentiel de bonnes pratiques. ITIL (Information Technology Infrastructure Library) est le référentiel majoritairement adopté ; il couvre les métiers de la production informatique et du support.

Partie 2 — Démarche qualité et référentiels
2.1 Définition d'une démarche qualité
Une démarche qualité est un ensemble structuré de méthodes, processus et outils mis en place par une organisation pour garantir que ses produits, services et processus répondent à des exigences définies et s'améliorent continuellement. Elle repose sur quatre principes fondamentaux : planifier (Plan), faire (Do), vérifier (Check) et améliorer (Act) — le cycle PDCA de Deming.

Dans le contexte de la gestion des incidents informatiques, une démarche qualité vise à réduire les temps de résolution, améliorer la satisfaction des utilisateurs, et prévenir la réapparition des incidents.

 
Référentiels qualité — ITIL, COBIT, CMMI, ISO 27001

2.2 ITIL — Information Technology Infrastructure Library
ITIL est le référentiel de bonnes pratiques IT le plus utilisé au monde. Il structure la gestion des services informatiques en processus clairs. Dans la gestion des incidents, ITIL définit un cycle précis : détection → enregistrement → classification → priorisation → diagnostic → résolution → clôture.

▶	Forces : très complet, reconnu mondialement, aligné sur les besoins métier.
▶	Lien avec GLPI : GLPI est conçu pour appliquer les recommandations ITIL — tickets, SLA, CMDB intégrée.

2.3 COBIT — Control Objectives for IT
COBIT est un cadre de gouvernance IT développé par l'ISACA. Il aligne la DSI sur les objectifs stratégiques de l'entreprise et fournit des métriques pour mesurer la performance des processus IT. Dans la gestion des incidents, COBIT s'intéresse à la traçabilité et à la conformité des réponses.

2.4 CMMI — Capability Maturity Model Integration
CMMI évalue et améliore la maturité des processus d'une organisation sur une échelle de 1 (initial/chaotique) à 5 (optimisé). Appliqué à la gestion des incidents, CMMI permet de mesurer à quel point les processus de résolution sont répétables, définis, mesurés et en amélioration continue.

2.5 ISO 27001 — Sécurité de l'information
La norme ISO 27001 définit les exigences pour un Système de Management de la Sécurité de l'Information (SMSI). Elle impose de gérer les incidents de sécurité de façon structurée : identification, classification, réponse, documentation et retour d'expérience. Elle est complémentaire à ITIL pour les incidents liés à la cybersécurité.

Partie 3 — Le logiciel GLPI
3.1 Présentation de GLPI
GLPI (Gestion Libre de Parc Informatique) est un logiciel open source français de gestion de parc informatique et de service desk. Il implémente les bonnes pratiques ITIL et permet de gérer l'intégralité d'un système d'information depuis une seule interface.

▶	Version actuelle : GLPI 11.0.x (sortie octobre 2025)
▶	Licence : GNU GPL v2 — gratuit et open source
▶	Technologies : PHP 8.4, MariaDB/MySQL, Apache2, Debian 13
▶	Site officiel : https://glpi-project.org

3.2 Fonctionnalités du plugin Agent GLPI
L'agent GLPI (GLPI Agent) est un outil de collecte automatisée installé sur chaque poste client. Il permet :

▶	Inventaire automatique : collecte et remontée de toutes les informations matérielles et logicielles de la machine (CPU, RAM, disques, OS, logiciels installés, adresses MAC/IP...).
▶	Détection des changements : surveillance en continu des modifications de configuration des postes et alerte du serveur en cas de changement.
▶	Découverte réseau : scan du réseau local pour détecter automatiquement les équipements connectés (imprimantes, switchs, NAS...).
▶	Synchronisation automatique : envoi régulier de l'inventaire vers le serveur GLPI selon une fréquence configurable (par défaut toutes les 24h).

3.3 Valeur ajoutée du serveur GLPI
Le serveur GLPI centralise toutes les données remontées par les agents et offre :

▶	Interface de gestion complète de tous les éléments du parc informatique.
▶	Gestion comptable et financière des équipements (valeur, amortissement, garanties).
▶	Module Helpdesk complet avec gestion des tickets d'incident (ouverture, suivi, SLA, clôture).
▶	CMDB intégrée (Configuration Management DataBase) pour tracer les relations entre équipements.
▶	Tableaux de bord et rapports statistiques sur l'état du parc et des incidents.
Partie 4 — Installation du serveur GLPI

 
Processus d'installation en 7 étapes — GLPI 11 sur Debian 13

⚠ Prérequis : Debian 13 Trixie, PHP 8.2 minimum (8.4 recommandé), MariaDB 10.6+, Apache 2.4. Ces commandes sont validées pour GLPI 11 en 2025.

4.1 Mise à jour du système
apt update && apt upgrade -y
apt install apache2 mariadb-server php php-fpm -y
systemctl enable apache2 mariadb && systemctl start apache2 mariadb

4.2 Installation des extensions PHP 8.4
apt install php8.4-mysqli php8.4-mbstring php8.4-curl php8.4-gd \
        php8.4-simplexml php8.4-xml php8.4-intl php8.4-zip \
        php8.4-bz2 php8.4-ldap php8.4-apcu php8.4-xmlrpc -y

4.3 Sécurisation de MariaDB
mariadb-secure-installation
Répondre Oui à toutes les questions de sécurisation : définir un mot de passe root fort, supprimer les utilisateurs anonymes, désactiver l'accès root distant, supprimer la base de test.

4.4 Création de la base de données
mariadb -u root -p
CREATE DATABASE glpi CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'glpiuser'@'localhost' IDENTIFIED BY 'mdpglpi';
GRANT ALL PRIVILEGES ON glpi.* TO 'glpiuser'@'localhost';
FLUSH PRIVILEGES;
EXIT;

4.5 Téléchargement et décompression de GLPI 11
cd /tmp
wget https://github.com/glpi-project/glpi/releases/download/11.0.4/glpi-11.0.4.tgz
tar xzf glpi-11.0.4.tgz -C /var/www/
ℹ Consultez https://github.com/glpi-project/glpi/releases pour récupérer le lien de la dernière version disponible.

4.6 Organisation des répertoires et permissions
chown -R www-data:www-data /var/www/glpi
chmod -R 775 /var/www/glpi
mkdir /etc/glpi && chown www-data /etc/glpi
mv /var/www/glpi/config /etc/glpi
mkdir /var/lib/glpi && chown www-data /var/lib/glpi
mv /var/www/glpi/files /var/lib/glpi
mkdir /var/log/glpi && chown www-data /var/log/glpi

4.7 Configuration du VirtualHost Apache
nano /etc/apache2/sites-available/glpi.conf
<VirtualHost *:80>
  ServerName glpi.local
  DocumentRoot /var/www/glpi/public
  <Directory /var/www/glpi/public>
    Require all granted
    AllowOverride All
    RewriteEngine On
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteRule ^(.*)$ index.php [QSA,L]
  </Directory>
</VirtualHost>
a2enmod rewrite && a2ensite glpi.conf && a2dissite 000-default.conf
systemctl restart apache2

4.8 Configuration via l'interface web
1.	Ouvrir un navigateur : http://@IpServeurGLPI
2.	Choisir la langue : Français
3.	Accepter la licence et cliquer sur Installer
4.	Paramètres BDD : localhost / glpiuser / mdpglpi — sélectionner glpi
5.	Finaliser et cliquer sur Utiliser GLPI

 
Comptes par défaut — à changer immédiatement après la première connexion

⚠ Sécurité obligatoire après installation : supprimer le dossier /install, changer tous les mots de passe par défaut. Commande : rm -rf /var/www/glpi/install

Partie 5 — Installation de l'agent sur Debian

ℹ Ces commandes sont à exécuter sur le poste CLIENT Debian, pas sur le serveur GLPI.

5.1 Téléchargement de l'installeur
cd /tmp
wget https://github.com/glpi-project/glpi-agent/releases/latest/\
     download/glpi-agent-linux-installer.pl
Vérifier la dernière version sur : https://github.com/glpi-project/glpi-agent/releases

5.2 Exécution de l'installeur
perl glpi-agent-linux-installer.pl \
  --type=typical \
  --server=http://@IpServeurGLPI \
  --no-ssl-check
Remplacer @IpServeurGLPI par l'adresse IP réelle du serveur. Ajouter --tag=NomPoste pour identifier la machine.

5.3 Activation et démarrage du service
systemctl enable glpi-agent
systemctl start glpi-agent
systemctl status glpi-agent

5.4 Vérification du fichier de configuration
cat /etc/glpi-agent/agent.cfg
Vérifier que la ligne server = pointe bien vers l'adresse du serveur GLPI.

 
Partie 6 — Installation de l'agent sur Windows

⚠ L'installation requiert des droits administrateur. L'agent est disponible en 64 bits depuis la version 1.8.

6.1 Téléchargement
Se rendre sur https://github.com/glpi-project/glpi-agent/releases et télécharger le fichier .msi 64 bits (ex : GLPI-Agent-1.16-x64.msi).

6.2 Installation graphique (méthode simple)
6.	Double-cliquer sur le fichier .msi et accepter l'élévation UAC.
7.	Choisir le type d'installation : Typical.
8.	Dans Remote Targets (GLPI Server URL), saisir : http://@IpServeurGLPI
9.	Cliquer sur Install puis Finish.

6.3 Installation silencieuse (ligne de commande)
msiexec /i GLPI-Agent-1.16-x64.msi /quiet ^
  SERVER=http://@IpServeurGLPI ^
  RUNNOW=1
L'option RUNNOW=1 force un inventaire immédiat après l'installation. Idéal pour un déploiement GPO.

6.4 Installation via Winget
winget install glpi-project.glpi-agent

6.5 Vérification du service
Dans les Services Windows (services.msc), vérifier que le service GLPI Agent est en état Démarré avec le démarrage Automatique.

 
Partie 7 — Tests et validation

 
Workflow de test — 5 étapes de validation de l'installation

✔ Objectif : valider que chaque composant fonctionne correctement avant de passer en production.

7.1 Test 1 — Accessibilité du serveur GLPI
Ouvrir un navigateur et accéder à :
http://@IpServeurGLPI
Résultat attendu : la page de connexion GLPI s'affiche. Se connecter avec glpi / glpi.

Vérifier que les services sont actifs sur le serveur :
systemctl status apache2
systemctl status mariadb
✔ Les deux services doivent être en état active (running) affiché en vert.

7.2 Test 2 — Forcer un inventaire depuis Debian
Sur le poste client Debian, forcer une remontée immédiate :
glpi-agent --force

Consulter les logs pour confirmer l'envoi :
journalctl -u glpi-agent -n 50 --no-pager
Chercher la ligne : Inventory sent successfully ou New Inventory from [NomDuPoste].

7.3 Test 3 — Forcer un inventaire depuis Windows
Méthode 1 — Via le navigateur (la plus simple)
Ouvrir un navigateur sur le poste Windows et accéder à :
http://localhost:62354/now
La page affiche OK si l'inventaire a bien été envoyé au serveur GLPI.

Méthode 2 — Via l'invite de commandes (administrateur)
cd "C:\Program Files\GLPI-Agent"
glpi-agent.bat --force

Méthode 3 — Statut de l'agent
http://localhost:62354
Cette page affiche le statut de l'agent, la date du dernier inventaire et le serveur cible.

7.4 Test 4 — Vérifier l'inventaire dans GLPI
10.	Se connecter à GLPI avec glpi / glpi.
11.	Aller dans Parc > Ordinateurs.
12.	Vérifier que les postes clients apparaissent bien (attendre 1-2 minutes après l'inventaire forcé).
13.	Cliquer sur un poste pour voir le détail : matériel, logiciels, réseau, utilisateur.

7.5 Test 5 — Activer l'inventaire natif GLPI
14.	Dans GLPI : Administration > Inventaire.
15.	Cocher Activer l'inventaire et sauvegarder.
16.	Optionnel : installer le plugin GLPI Inventory depuis Configuration > Plugins.

7.6 Checklist de sécurité post-installation
▶	Supprimer le dossier d'installation : rm -rf /var/www/glpi/install
▶	Changer les mots de passe des 4 comptes par défaut (glpi, tech, normal, post-only).
▶	Vérifier que /config et /files ne sont pas accessibles depuis un navigateur.
▶	Configurer un certificat HTTPS (Let's Encrypt recommandé pour la production).

✔ Si tous les tests passent : l'installation est opérationnelle. Les postes remontent leur inventaire automatiquement toutes les 24h.

 
Partie 8 — Gestion des incidents (Helpdesk)

Le module Helpdesk de GLPI permet de gérer les demandes d'assistance et les incidents selon les bonnes pratiques ITIL. Voici le travail à réaliser :

8.1 Créer un utilisateur de type normal
17.	Aller dans Administration > Utilisateurs > Ajouter un utilisateur.
18.	Renseigner : Identifiant = votre nom, Profil = Self-Service (normal).
19.	Affecter à cet utilisateur un élément matériel inventorié (un PC du parc).

8.2 Créer un ticket d'incident
Se connecter avec le compte normal et créer un ticket en s'inspirant d'un incident réel :

▶	Exemple d'incident : Poste de travail impossible à démarrer — écran noir au démarrage.
▶	Catégorie : Matériel > Ordinateur
▶	Priorité : Haute
▶	Description : Le PC ref DESKTOP-XXX ne démarre plus depuis ce matin. Dernier usage hier soir.

8.3 Créer un utilisateur technicien
20.	Aller dans Administration > Utilisateurs > Ajouter un utilisateur.
21.	Renseigner : Identifiant = technicien01, Profil = Technicien (admin).
22.	En tant qu'administrateur (glpi/glpi), attribuer le ticket au technicien créé.

8.4 Suivi et clôture du ticket
23.	Le technicien se connecte et consulte son ticket assigné.
24.	Ajouter un suivi : « Diagnostic en cours — vérification de l'alimentation et de la RAM ».
25.	Ajouter une autre action : « Remplacement du module RAM défectueux — poste redémarré avec succès ».
26.	Changer le statut : En cours > Résolu.
27.	Renseigner la solution et fermer le ticket.

✔ Le ticket est clôturé avec le détail de la solution appliquée. L'historique est conservé dans GLPI pour analyse ultérieure.

# 🖥️ GLPI — Gestion Libre de Parc Informatique

> **BTS SIO · SISR · Documentation complète 2025**  
> `GLPI 11` · `Debian 13` · `PHP 8.4` · `MariaDB` · `Apache 2.4`

---

## 📋 Sommaire

- [Partie 1 — La gestion de parc informatique](#partie-1--la-gestion-de-parc-informatique)
- [Partie 2 — Démarche qualité et référentiels](#partie-2--démarche-qualité-et-référentiels)
- [Partie 3 — Le logiciel GLPI](#partie-3--le-logiciel-glpi)
- [Partie 4 — Installation du serveur GLPI](#partie-4--installation-du-serveur-glpi)
- [Partie 5 — Installation de l'agent sur Debian](#partie-5--installation-de-lagent-sur-debian)
- [Partie 6 — Installation de l'agent sur Windows](#partie-6--installation-de-lagent-sur-windows)
- [Partie 7 — Tests et validation](#partie-7--tests-et-validation)
- [Partie 8 — Gestion des incidents (Helpdesk)](#partie-8--gestion-des-incidents-helpdesk)

---

## Partie 1 — La gestion de parc informatique

### 1.1 Composition d'un parc informatique

Le parc informatique d'une organisation est un assemblage, parfois hétéroclite, de matériels et de logiciels accumulés tout au long des années. On y trouve des :

| Catégorie | Exemples |
|-----------|----------|
| **Matériel (hardware)** | Ordinateurs fixes/portables, serveurs, imprimantes, scanners, smartphones, switchs, routeurs, bornes Wi-Fi |
| **Logiciels (software)** | Systèmes d'exploitation, suites bureautiques, logiciels métiers, antivirus, outils de supervision, licences |
| **Réseau & télécoms** | Câblage, commutateurs, routeurs, DSLAM, systèmes téléphoniques VoIP |
| **Infrastructure physique** | Baies serveurs, onduleurs, climatisation salle serveurs, systèmes de sauvegarde |
| **Ressources documentaires** | Contrats de maintenance, garanties, documentations techniques, certificats de licences |

---

### 1.2 Inventaire et suivi du parc lali

La gestion du parc informatique recouvre la fonction d'inventaire des éléments mais aussi le suivi et l'évolution :

- 📦 Inventaire complet du matériel et des logiciels installés sur chaque poste
- 📄 Suivi des licences logicielles et vérification de leur conformité
- 🛡️ Gestion des garanties, contrats de maintenance et dates d'expiration
- 📍 Suivi de la localisation physique de chaque équipement
- 🔄 Gestion du cycle de vie du matériel (achat → utilisation → renouvellement → rebut)
- 🔧 Suivi des mises à jour système et des correctifs de sécurité (patching)
- 🔐 Gestion des droits d'accès, des comptes utilisateurs et des habilitations
- 📅 Planification des renouvellements matériels à court et moyen terme
- 💶 Suivi financier et comptable (valeur d'achat, amortissement)
- 🎫 Gestion des incidents, tickets d'assistance et demandes utilisateurs (helpdesk)
- 📈 Analyse des besoins et planification des évolutions du système d'information

> 💡 **Exemples de questions auxquelles répond la gestion de parc :**  
> Quelles versions de Windows sont installées et sur quels postes ? Y a-t-il des disques proches de la saturation ? Quels postes sont encore sous garantie ? Combien de machines à renouveler dans 2 ans ?

---

### 1.3 Le référentiel ITIL

La tendance actuelle des DSI est l'adoption d'un référentiel commun de bonnes pratiques.  
**ITIL (Information Technology Infrastructure Library)** est le référentiel majoritairement adopté ; il couvre les métiers de la production informatique et du support.

---

## Partie 2 — Démarche qualité et référentiels

### 2.1 Définition d'une démarche qualité

Une **démarche qualité** est un ensemble structuré de méthodes, processus et outils mis en place par une organisation pour garantir que ses produits, services et processus répondent à des exigences définies et s'améliorent continuellement.

Elle repose sur le **cycle PDCA de Deming** :

```
Plan → Do → Check → Act
  ↑________________________↓
```

Dans la gestion des incidents informatiques, une démarche qualité vise à :
- Réduire les temps de résolution
- Améliorer la satisfaction des utilisateurs
- Prévenir la réapparition des incidents

---

### 2.2 ITIL — Information Technology Infrastructure Library

**ITIL** est le référentiel de bonnes pratiques IT le plus utilisé au monde. Il structure la gestion des services informatiques en processus clairs.

Cycle de gestion des incidents selon ITIL :

```
Détection → Enregistrement → Classification → Priorisation
    → Diagnostic → Résolution → Clôture
```

| ✅ Forces | 🔗 Lien avec GLPI |
|-----------|------------------|
| Très complet et reconnu mondialement | GLPI implémente les recommandations ITIL |
| Aligné sur les besoins métier | Tickets, SLA, CMDB intégrée |
| Processus structurés et mesurables | Helpdesk conforme aux bonnes pratiques |

---

### 2.3 COBIT — Control Objectives for IT

**COBIT** est un cadre de gouvernance IT développé par l'ISACA. Il aligne la DSI sur les objectifs stratégiques de l'entreprise et fournit des métriques pour mesurer la performance des processus IT.

- Traçabilité et conformité des réponses aux incidents
- Alignement métier / IT
- Gestion des risques informatiques

---

### 2.4 CMMI — Capability Maturity Model Integration

**CMMI** évalue et améliore la maturité des processus sur une échelle de **1 à 5** :

| Niveau | Nom | Description |
|--------|-----|-------------|
| 1 | Initial | Processus chaotiques, non définis |
| 2 | Géré | Processus planifiés et suivis |
| 3 | Défini | Processus standardisés à l'organisation |
| 4 | Géré quantitativement | Processus mesurés et contrôlés |
| 5 | En optimisation | Amélioration continue et innovation |

---

### 2.5 ISO 27001 — Sécurité de l'information

La norme **ISO 27001** définit les exigences pour un Système de Management de la Sécurité de l'Information (SMSI).

Elle impose de gérer les incidents de sécurité de façon structurée :

```
Identification → Classification → Réponse → Documentation → Retour d'expérience
```

> ℹ️ ISO 27001 est complémentaire à ITIL pour les incidents liés à la cybersécurité.

---

## Partie 3 — Le logiciel GLPI

### 3.1 Présentation de GLPI

**GLPI** (Gestion Libre de Parc Informatique) est un logiciel open source français de gestion de parc informatique et de service desk. Il implémente les bonnes pratiques ITIL.

| Propriété | Valeur |
|-----------|--------|
| **Version actuelle** | GLPI 11.0.x (octobre 2025) |
| **Licence** | GNU GPL v2 — gratuit et open source |
| **Technologies** | PHP 8.4, MariaDB/MySQL, Apache 2.4 |
| **OS serveur** | Debian 13 Trixie (recommandé) |
| **Site officiel** | https://glpi-project.org |

---

### 3.2 Fonctionnalités du plugin Agent GLPI

L'agent GLPI est un outil de collecte automatisée installé sur chaque poste client. Il permet :

- 🔍 **Inventaire automatique** — collecte CPU, RAM, disques, OS, logiciels installés, adresses MAC/IP
- 🔔 **Détection des changements** — surveillance en continu des modifications de configuration
- 🌐 **Découverte réseau** — scan du LAN pour détecter imprimantes, switchs, NAS
- 🔄 **Synchronisation automatique** — envoi vers GLPI selon une fréquence configurable (défaut : 24h)

---

### 3.3 Valeur ajoutée du serveur GLPI

Le serveur GLPI centralise toutes les données remontées par les agents :

- 🖥️ Interface de gestion complète de tous les éléments du parc
- 💰 Gestion comptable et financière (valeur, amortissement, garanties)
- 🎫 Module Helpdesk complet (tickets, SLA, clôture)
- 🗄️ CMDB intégrée pour tracer les relations entre équipements
- 📊 Tableaux de bord et rapports statistiques

---

## Partie 4 — Installation du serveur GLPI

> ⚠️ **Prérequis :** Debian 13 Trixie · PHP 8.2 minimum (8.4 recommandé) · MariaDB 10.6+ · Apache 2.4  
> Ces commandes sont validées pour **GLPI 11** en 2025.

### Processus d'installation en 7 étapes

```
[1] Mise à jour  →  [2] Socle LAMP  →  [3] Extensions PHP
     →  [4] Base de données  →  [5] Téléchargement GLPI
          →  [6] Permissions & VirtualHost  →  [7] Config navigateur
```

---

### 4.1 Mise à jour du système

```bash
apt update && apt upgrade -y
apt install apache2 mariadb-server php php-fpm -y
systemctl enable apache2 mariadb && systemctl start apache2 mariadb
```

---

### 4.2 Installation des extensions PHP 8.4

```bash
apt install php8.4-mysqli php8.4-mbstring php8.4-curl php8.4-gd \
        php8.4-simplexml php8.4-xml php8.4-intl php8.4-zip \
        php8.4-bz2 php8.4-ldap php8.4-apcu php8.4-xmlrpc -y
```

---

### 4.3 Sécurisation de MariaDB

```bash
mariadb-secure-installation
```

> 💡 Répondre **Oui** à toutes les questions : définir un mot de passe root fort, supprimer les utilisateurs anonymes, désactiver l'accès root distant, supprimer la base de test.

---

### 4.4 Création de la base de données

```sql
mariadb -u root -p

CREATE DATABASE glpi CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'glpiuser'@'localhost' IDENTIFIED BY 'mdpglpi';
GRANT ALL PRIVILEGES ON glpi.* TO 'glpiuser'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```

---

### 4.5 Téléchargement et décompression de GLPI 11

```bash
cd /tmp
wget https://github.com/glpi-project/glpi/releases/download/11.0.4/glpi-11.0.4.tgz
tar xzf glpi-11.0.4.tgz -C /var/www/
```

> ℹ️ Vérifiez la dernière version sur : https://github.com/glpi-project/glpi/releases

---

### 4.6 Organisation des répertoires et permissions

```bash
chown -R www-data:www-data /var/www/glpi
chmod -R 775 /var/www/glpi

# Sécurité : déplacer config/files/logs hors de la racine web
mkdir /etc/glpi       && chown www-data /etc/glpi
mv /var/www/glpi/config /etc/glpi

mkdir /var/lib/glpi   && chown www-data /var/lib/glpi
mv /var/www/glpi/files /var/lib/glpi

mkdir /var/log/glpi   && chown www-data /var/log/glpi
```

---

### 4.7 Configuration du VirtualHost Apache

```bash
nano /etc/apache2/sites-available/glpi.conf
```

```apache
<VirtualHost *:80>
    ServerName glpi.local
    DocumentRoot /var/www/glpi/public

    <Directory /var/www/glpi/public>
        Require all granted
        AllowOverride All
        RewriteEngine On
        RewriteCond %{REQUEST_FILENAME} !-f
        RewriteRule ^(.*)$ index.php [QSA,L]
    </Directory>
</VirtualHost>
```

```bash
a2enmod rewrite
a2ensite glpi.conf
a2dissite 000-default.conf
systemctl restart apache2
```

---

### 4.8 Configuration via l'interface web

1. Ouvrir un navigateur : `http://@IpServeurGLPI`
2. Choisir la langue : **Français**
3. Accepter la licence et cliquer sur **Installer**
4. Paramètres BDD : `localhost` / `glpiuser` / `mdpglpi` — sélectionner `glpi`
5. Finaliser et cliquer sur **Utiliser GLPI**

#### Comptes par défaut

| Identifiant | Mot de passe | Rôle |
|-------------|-------------|------|
| `glpi` | `glpi` | Administrateur |
| `tech` | `tech` | Technicien |
| `normal` | `normal` | Utilisateur normal |
| `post-only` | `postonly` | Post-only |

> ⚠️ **Sécurité obligatoire après installation :**
> ```bash
> rm -rf /var/www/glpi/install
> ```
> Changer immédiatement tous les mots de passe par défaut !

---

## Partie 5 — Installation de l'agent sur Debian

> ℹ️ Ces commandes sont à exécuter sur le poste **CLIENT** Debian, pas sur le serveur GLPI.

### 5.1 Téléchargement de l'installeur

```bash
cd /tmp
wget https://github.com/glpi-project/glpi-agent/releases/latest/\
     download/glpi-agent-linux-installer.pl
```

> Vérifier la dernière version sur : https://github.com/glpi-project/glpi-agent/releases

---

### 5.2 Exécution de l'installeur

```bash
perl glpi-agent-linux-installer.pl \
  --type=typical \
  --server=http://@IpServeurGLPI \
  --no-ssl-check
```

> 💡 Remplacer `@IpServeurGLPI` par l'adresse IP réelle. Ajouter `--tag=NomPoste` pour identifier la machine.

---

### 5.3 Activation et démarrage du service

```bash
systemctl enable glpi-agent
systemctl start glpi-agent
systemctl status glpi-agent
```

---

### 5.4 Vérification du fichier de configuration

```bash
cat /etc/glpi-agent/agent.cfg
```

> Vérifier que la ligne `server =` pointe bien vers l'adresse du serveur GLPI.

---

## Partie 6 — Installation de l'agent sur Windows

> ⚠️ L'installation requiert des **droits administrateur**. Agent disponible en 64 bits depuis la version 1.8.

### 6.1 Téléchargement

Se rendre sur https://github.com/glpi-project/glpi-agent/releases et télécharger le fichier `.msi` 64 bits.

Exemple : `GLPI-Agent-1.16-x64.msi`

---

### 6.2 Installation graphique (méthode simple)

1. Double-cliquer sur le fichier `.msi` et accepter l'élévation UAC
2. Choisir le type d'installation : **Typical**
3. Dans **Remote Targets (GLPI Server URL)**, saisir : `http://@IpServeurGLPI`
4. Cliquer sur **Install** puis **Finish**

---

### 6.3 Installation silencieuse (ligne de commande)

```cmd
msiexec /i GLPI-Agent-1.16-x64.msi /quiet ^
  SERVER=http://@IpServeurGLPI ^
  RUNNOW=1
```

> 💡 `RUNNOW=1` force un inventaire immédiat après l'installation. Idéal pour un déploiement **GPO**.

---

### 6.4 Installation via Winget

```powershell
winget install glpi-project.glpi-agent
```

---

### 6.5 Vérification du service

Dans `services.msc`, vérifier que le service **GLPI Agent** est :
- État : `Démarré`
- Type de démarrage : `Automatique`

---

## Partie 7 — Tests et validation

> ✅ **Objectif :** valider que chaque composant fonctionne correctement avant de passer en production.

### Workflow de validation

```
[Test 1] Serveur web
    ↓
[Test 2] Agent Debian  →  inventaire forcé
    ↓
[Test 3] Agent Windows  →  inventaire forcé
    ↓
[Test 4] Vérification dans GLPI  →  Parc > Ordinateurs
    ↓
[Test 5] Helpdesk  →  ticket créé, suivi, clôturé
    ↓
✅ Installation validée
```

---

### 7.1 Test 1 — Accessibilité du serveur GLPI

```bash
# Ouvrir dans un navigateur
http://@IpServeurGLPI

# Vérifier les services sur le serveur
systemctl status apache2
systemctl status mariadb
```

> ✅ Les deux services doivent être en état `active (running)`.

---

### 7.2 Test 2 — Forcer un inventaire depuis Debian

```bash
# Forcer une remontée immédiate
glpi-agent --force

# Consulter les logs
journalctl -u glpi-agent -n 50 --no-pager
```

> Chercher la ligne : `Inventory sent successfully` ou `New Inventory from [NomDuPoste]`

---

### 7.3 Test 3 — Forcer un inventaire depuis Windows

#### Méthode 1 — Via le navigateur (la plus simple)

```
http://localhost:62354/now
```

> La page affiche `OK` si l'inventaire a bien été envoyé.

#### Méthode 2 — Via l'invite de commandes (administrateur)

```cmd
cd "C:\Program Files\GLPI-Agent"
glpi-agent.bat --force
```

#### Méthode 3 — Statut de l'agent

```
http://localhost:62354
```

> Affiche le statut, la date du dernier inventaire et le serveur cible.

---

### 7.4 Test 4 — Vérifier l'inventaire dans GLPI

1. Se connecter à GLPI avec `glpi` / `glpi`
2. Aller dans **Parc > Ordinateurs**
3. Vérifier que les postes clients apparaissent *(attendre 1-2 min après l'inventaire forcé)*
4. Cliquer sur un poste pour voir le détail : matériel, logiciels, réseau, utilisateur

---

### 7.5 Test 5 — Activer l'inventaire natif GLPI

1. Aller dans **Administration > Inventaire**
2. Cocher **Activer l'inventaire** et sauvegarder
3. *(Optionnel)* Installer le plugin GLPI Inventory via **Configuration > Plugins**

---

### 7.6 Checklist de sécurité post-installation

- [ ] Supprimer le dossier d'installation : `rm -rf /var/www/glpi/install`
- [ ] Changer les mots de passe des 4 comptes par défaut (`glpi`, `tech`, `normal`, `post-only`)
- [ ] Vérifier que `/config` et `/files` ne sont pas accessibles depuis un navigateur
- [ ] Configurer un certificat HTTPS *(Let's Encrypt recommandé pour la production)*

> ✅ Si tous les tests passent : l'installation est opérationnelle. Les postes remontent leur inventaire automatiquement toutes les **24h**.

---

## Partie 8 — Gestion des incidents (Helpdesk)

Le module **Helpdesk** de GLPI permet de gérer les demandes d'assistance et les incidents selon les bonnes pratiques ITIL.

---

### 8.1 Créer un utilisateur de type normal

1. Aller dans **Administration > Utilisateurs > Ajouter un utilisateur**
2. Renseigner : Identifiant = `votre nom`, Profil = `Self-Service (normal)`
3. Affecter à cet utilisateur un élément matériel inventorié (un PC du parc)

---

### 8.2 Créer un ticket d'incident

Se connecter avec le compte `normal` et créer un ticket :

| Champ | Valeur |
|-------|--------|
| **Exemple d'incident** | Poste de travail impossible à démarrer — écran noir au démarrage |
| **Catégorie** | Matériel > Ordinateur |
| **Priorité** | Haute |
| **Description** | Le PC ref `DESKTOP-XXX` ne démarre plus depuis ce matin. Dernier usage hier soir. |

---

### 8.3 Créer un utilisateur technicien

1. Aller dans **Administration > Utilisateurs > Ajouter un utilisateur**
2. Renseigner : Identifiant = `technicien01`, Profil = `Technicien (admin)`
3. En tant qu'administrateur (`glpi`/`glpi`), attribuer le ticket au technicien créé

---

### 8.4 Suivi et clôture du ticket

1. Le technicien se connecte et consulte son ticket assigné
2. Ajouter un suivi :  
   > *« Diagnostic en cours — vérification de l'alimentation et de la RAM »*
3. Ajouter une action :  
   > *« Remplacement du module RAM défectueux — poste redémarré avec succès »*
4. Changer le statut : `En cours` → `Résolu`
5. Renseigner la solution et **fermer le ticket**

> ✅ Le ticket est clôturé avec le détail de la solution appliquée. L'historique est conservé dans GLPI pour analyse ultérieure.

---

*Documentation générée pour BTS SIO SISR · GLPI 11 · Debian 13 · 2025*
