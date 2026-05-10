# Matrice de Durcissement GNU/Linux (Standard ANSSI)

Bienvenue sur le dépôt de la **Matrice de durcissement Linux Standart ANSSI**. Il simplifie l'application des recommandations de sécurité de l'ANSSI.
Ce projet transforme le guide de 80+ pages de l'ANSSI en une checklist pour les administrateurs système et RSSI.

---

## Version Complète (Premium)

Pour accéder à la matrice interactive complète (80+ règles), aux graphiques de score automatiques et à l'intégralité des configurations techniques prêtes à l'emploi :

[![Prendre la version complète](https://img.shields.io/badge/Télécharger-Matrice_Complète_(80+_règles)-blue?style=for-the-badge&logo=gumroad)](https://mrnd.gumroad.com/l/eykkop)

---

## Aperçu des Recommandations (Version Free)

Voici un extrait des premières mesures de sécurité (Niveau Minimal & Intermédiaire) incluses dans l'outil :

| ID | Thème | Description | Niveau |
|:---|:---|:---|:---|
| **R1** | Support Matériel | Suivre les recommandations de configuration matérielle x86 | MIR |
| **R2** | BIOS/UEFI | Appliquer les recommandations de la configuration du BIOS/UEFI mentionnées dans la note technique « Recommandations de configuration matérielle de postes clients et serveurs x86 » | MI |
| **R3** | Secure Boot | Activer le démarrage sécurisé UEFI pour protéger des rootkits | MI |
| **R8** | Configuration de la mémoire | Paramétrer les options de protection mémoire (PTI, Page Poison, etc.) | MI | Voir Annexes_Techniques |
| **R11** | Configuration des processus | Activer et configurer le LSM Yama: charger le module de sécurité Yama lors du démarrage, par exemple en passant la directive security=yama au noyau et affecter à l’option de  configuration du noyau kernel.yama.ptrace_scope une valeur au moins égale à 1. | MI |
| **R13** | Configuration du réseau | Désactiver le support d'IPv6 si non utilisé | MI | Quand IPv6 n’est pas utilisé !! Voir liste conf dans le guide. À défaut, le plan IPv6 doit, tout comme le plan IPv4, être sécurisé |
| **R21** | Configuration statique: Configuration indépendante de la cible matérielle | Paramétrer les options de compilation pour les plugins du compilateur | MIRE | Configuration avancée (30+ paramètres) |
| **R28** | Partitions | Partitionnement type | MI | Voir Annexes_Techniques |
| **R33** | Comptes d'accès: Comptes administrateur | Assurer l'imputabilité des actions d'administration - utiliser compté dédiés pour chaque admin et utiliser sudo pour tte commande privilégier - identifier user de manière unique sur le systeme et journaliser la création de tt processus avec auditd | MI | Guide "Recommandations relatives à l’administration sécurisée des systèmes d’information" |
| **R37** | Contrôle d'accès: Modèle traditionnel Unix | Utiliser des fonctionnalités de contrôle d'accès obligatoire MAC. | MI | DAC a pas mal de restrictions. En complément, on peut utiliser MAC Mandatory Access Control |

---

## Pourquoi utiliser cette matrice ?

1. **Gain de temps :** Vous n'avez pas besoin de lire les 80 pages. Avec la matrice, vous pouvez passer directement à l'audit.
2. **Score en temps réel :** Visualisez votre niveau de conformité (M, MI, MIR, MIRE).
3. **Preuve de conformité :** Idéal pour les dossiers de mise en conformité **NIS2**.

---

## Informations Importantes et Avertissements 

2. L'application des mesures de durcissement (notamment sur le noyau et les droits sudo) peut rendre certains systèmes instables ou bloquer des services légitimes. Testez impérativement chaque mesure sur un environnement de pré-production avant tout déploiement sur un serveur critique. L'auteur décline toute responsabilité en cas de perte de données ou d'interruption de service.
3. Avant toute modification d'un fichier système (/etc/sysctl.conf, /etc/ssh/sshd_config, etc.), créez systématiquement une copie de sauvegarde : cp fichier fichier.bak. Cela vous permettra de restaurer la configuration d'origine en cas de problème.
4. Le durcissement d'un système est un processus continu. Une mise à jour système ou l'installation d'un nouveau service peut écraser certaines configurations. Il est recommandé de re-vérifier cette matrice après chaque changement majeur sur le serveur.
6. Ce document est une synthèse opérationnelle basée sur le guide officiel de l'ANSSI : 'Recommandations de configuration d'un système GNU/Linux'. Pour approfondir les concepts théoriques, la lecture du guide complet est vivement recommandée.

---

## Comment obtenir l'outil complet ?

Le fichier complet est un classeur Excel (.xlsx) automatisé et protégé contre les erreurs de manipulation.

**[Cliquez ici pour obtenir la Matrice Complète sur Gumroad](https://mrnd.gumroad.com/l/eykkop)**

---
*Note : Ce projet est une synthèse opérationnelle et n'est pas affilié officiellement à l'ANSSI.*
