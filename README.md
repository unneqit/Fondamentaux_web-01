# Exposé histoire de l'internet
Shell / Interface graphique / Liste des commandes essentielles du shell

### Profils

Nicolas : https://github.com/WebFaker

Mahel : https://github.com/M00NBOY

Quentin : https://github.com/unneqit

Valentine : https://github.com/Vlry

Christella : https://github.com/altesyrk

Thomas : https://github.com/WebbyStalker

---

### 01 - Définition du shell

Le shell est le programme qui interprète les commandes. C’est un outil en mode texte qui permet l’exploitation d’un grand nombre de ressources de l’ordinateur via le kernel. Pour exploiter le shell, il faut passer par un terminal. Le shell c'est la manière de dire à l'ordi ce qu'il doit faire en entrant des commandes.

Par analogie, on peut dire que l'ordinateur est un morceau de chocolat enrobé d'une coquille dure. Le kernel est le chocolat à l'intérieur et le shell est l'enrobage à l'extérieur. Vous ne pouvez pas communiquer directement avec le chocolat parce qu'il va fondre dans votre main. On utilise donc la coque pour intéragir avec le kernel

Shell ou en français interface système est en réalité l’interface utilisateur du système d’exploitation. Ne pas confondre avec interface graphique. L’appellation Shell est une métaphore désignant la couche supérieure de tous les systèmes Unix, qui représente la plupart des appareils, en opposition au noyau.
Commande Line Interface (CLI)
Shell = interpréteur de commandes. Interprète puis exécute les commandes de l’utilisateur et enfin retourne le résultat à l’écran.

Le shell d'un système d'exploitation peut prendre deux formes distinctes :

- L'interface en ligne de commande (CLI, de l'anglais « Command Line Interface ») permet à l'utilisateur d'interagir avec le système à partir de commandes qui sont adaptées au mode texte.
- La coque logicielle de type graphique fournit à l'utilisateur un environnement graphique (GUI, pour Graphical User Interface), généralement un environnement de bureau ou un écran d'accueil.


### 02 - Histoire du shell

L'introduction du Bourne shell en 1977 marque le début des shells modernes. Ce shell, créé par Stephen Bourne reste un shell utilisable aujourd'hui, parfois il est même choisi comme shell par défaut.

Le Bourne shell avait pour but de servir à la fois de shell interactif mais aussi de pouvoir écrire et exécuter des scripts. Il apportait de nombreux avantages, des commandes de contrôle de flux, des boucles, des variables dans les scripts, etc.

En 1978, Bill Joy, alors étudiant à l'Université de Californie à Berkeley, crée csh (C shell), une évolution du shell dont la syntaxe s'inspire de celle du langage C. Il permet notamment la réutilisation de l'historique des commandes. Une version plus moderne du csh est ensuite publiée sous le nom tcsh.

Le Korn shell (ksh) est publié en 1983 par David Korn. Il est compatible avec le Bourne shell, reprend certaines fonctionnalités de csh et ajoute des fonctions de scripts avancées disponibles dans des langages plus évolués tel que le Perl.

Le Bourne-Again shell (bash) apparait quant à lui en 1988. Il est écrit par Brian Fox pour la Free Software Foundation dans le cadre du projet GNU. C'est le shell de nombreuses implémentations libres d'Unix, tel que les systèmes GNU/Linux. Il est compatible avec le Bourne shell dont il se veut une implémentation libre.

Paul Falstad crée Zsh en 1990 alors qu'il est étudiant à l'université de Princeton. Ce shell reprend les fonctions les plus pratiques de bash, Csh, tcsh.


### 03 - Principe d'exécution du shell

Le shell :
1. Lit une ligne de commande soit à partir du terminal, soit à partir d’un fichier script
2. Effectue une première analyse qui détermine quels sont les mots de cette ligne, et quels en sont les délimiteurs (espace, ‘, ", tabulations).
3. Catégorise les mots trouvés en : opérateurs, chaînes de caractères, et mots ordinaires.
4. Compile la ligne de commande en commandes simples, en appliquant un jeu de priorités fixé sur les opérateurs identifiés
5. Évalue chaque commande simple en attendant (exécution séquentielle) ou en n’attendant pas (exécution parallèle) sa terminaison pour évaluer suivante selon la présence de l’opérateur &.


### 04 - Démonstration des commandes essentielles

#### Naviguer dans les répertoires

Code	| Action
----- | -------
**ls** |	Liste les fichier dans le répertoire courant
**cd** *path*	| Changer de répertoire
**cd**	| Retourner au répertoire home
**cd** *..*	| Retourner au répertoire parent
**pwd**	| Afficher le répertoire courant

La plupart des arguments de ces commandes peuvent être soit des noms de fichiers (relatifs au répertoire courant), ou un chemin de fichier complet. Par exemple ls */usr/local/bin*

#### Manipulation de fichiers / de répertoires

Code	| Action
----- | -------
**touch** *filename*	| Créé un nouveau fichier, ou met à jour le timestamp du fichier si il existe déjà
**nano** *filename* | Lance un éditeur de texte dans le terminal pour modifier un fichier
**vim** *filename* | Lance l'éditeur de texte vim dans le terminal pour modifier un fichier
**rm** *filename*	| Supprimer un fichier
**rm -r** *dirname*	| Supprimer un répertoire
**cp** *filename new_filename* | Copier un fichier
**cp -r** *dirname new_name*	| Copier un répertoire
**mkdir** *new_dir_name*	| Créé un nouveau répertoire
**rmdir** *dirname*	| Supprime un répertoire seulement si il est vide
**mv** *filename new_name*	| Renomme un fichier, ou le déplace dans un autre répertoire

#### Voir les informations d'un fichier

Code	| Action
----- | -------
**cat** *filename* | Afficher le contenu d'un fichier
**cat** *filename* &#124; *more* | Afficher un fichier par pages. Appuyez sur la touche [q] pour quitter.
**vi** *filename* | Afficher un fichier. Appuyez sur la touche [q] pour quitter.
**head** *filename* | Afficher les premières lignes d'un fichier (utile pour les gros fichiers tels que les fichiers log)
**tail** *filename* | Afficher les dernières lignes d'un fichier
**tail -f** *filename* | Typically used on log files. Affiche les dernières lignes d'un fichier constamment mis à jour. Typiquement utilisé sur des fichiers log
**file** *filename* | Afficher le type du fichier (jpg, png, pdf, ...)

#### Commandes d'aide et de localisation

Code | Action
---- | -------
**type** *commamd*	| Montre si la commande est native au shell
**which** *command* |	Affiche le chemin complet d'une commande
**man** *command*	| Afficher la documentation d'une commande
**locate** *filename*	| Trouver un fichier par son nom


#### Archive, Compression

Code | Action
---- | -------
**zip -r** *new name.zip dirname* |	Zipper un répertoire
**unzip** *filename*	| Dézipper


#### Gestionnaire de tâches

Code | Action
---- | -------
**ps -ef**	| Voir les processus en cours
**kill** *idprocessus* | Quitter un processus via son id
**top**	| Afficher les processus en cours en temps direct. Appuyez sur la touche [q] pour quitter.

#### Sys Admin

Code | Action
---- | -------
**sudo** *command* | Exécuter une commande en temps que "root" (nom par défaut du compte administrateur)
**shutdown -r** *0*	| Redémarrer l'ordinateur sans délai (-P au lieu de -r pour l'éteindre)


### 05 - Scripts Shell

Les Script shell permettent d'exécuter plusieurs commandes dans un fichier.
*exemple de script*


### 06 - Conclusion

La plupart des idées et de l'interface des shells originaux persiste 35 ans plus tard, ce qui montre la qualité du travail des auteurs originaux. Dans une industrie en mouvement permanent, le shell a été amélioré, mais jamais vraiment changé. Et bien qu'il y ait eu des tentatives de créer des shells spécialisés, ce sont encore les dérivés du Bourne shell qui sont le plus utilisés aujourd'hui.

Pour ceux qui ont déjà eu l'occasion de taper des commandes dans divers systèmes d'exploitation, un des points qui demeure le plus frappant avec les shells unix est leur très faible verbosité et l'interaction limitée des commandes. C'est un choix conscient, le but étant qu'une commande ne retourne que les éléments demandés, sans fioritures, de manière à ce que sa sortie puisse être traitée par une autre commande sans devoir faire le ménage dans du texte inutile.

Par exemple, la commande wc -l retourne le nombre de lignes d'un fichier. Elle ne retourne qu'un nombre, au lieu de vous faire un texte du type "Le fichier xxxx contient yyy lignes" ce qui vous oligerait à traiter le texte si vous deviez utiliser le nombre dans un script.

Les shells fournissent malgré tout une panoplie importante de commandes de traitement de chaînes de caractères. La puissance de ces commandes permet d'écrire des scripts très sophistiqués avec assez peu de lignes de commande.
