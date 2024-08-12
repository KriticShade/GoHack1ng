# Permissions Linux

Sur Linux et les systèmes d'exploitation de type UNIX, les permissions sont un mécanisme qui détermine qui peut accéder à un fichier ou un dossier, ainsi que la manière dont ils peuvent interagir avec celui-ci. Les permissions sont attribuées à trois catégories d'utilisateurs : le propriétaire du fichier, le groupe auquel appartient le fichier, et les autres utilisateurs.

### Types de Permissions

Il existe trois types de permissions de base :

* **Lecture (r)** : Permet de lire le contenu d'un fichier ou de lister les fichiers d'un répertoire.
* **Écriture (w)** : Permet de modifier un fichier ou d'ajouter/supprimer des fichiers dans un répertoire.
* **Exécution (x)** : Permet d'exécuter un fichier comme un programme ou d'accéder à un répertoire.

### Affichage des Permissions

Pour voir les permissions d'un fichier ou d'un répertoire, vous pouvez utiliser la commande `ls -l` dans le terminal. Cela affichera une sortie comme celle-ci :

```bash
-rwxr-xr-- 1 utilisateur groupe 4096 jan 28 12:34 exemple.txt
```

Ici, `-rwxr-xr--` représente les permissions, `utilisateur` est le nom du propriétaire, `groupe` est le nom du groupe, et `4096` est la taille du fichier.

### Structure des Permissions

La chaîne de permissions peut être décomposée comme suit :

* Le premier caractère indique le type d'objet : un `-` pour un fichier, `d` pour un répertoire.
* Les trois caractères suivants (`rwx` dans cet exemple) définissent les permissions du propriétaire.
* Les trois caractères suivants après cela (`r-x`) définissent les permissions du groupe.
* Les trois derniers caractères (`r--`) définissent les permissions pour les autres utilisateurs.

### Modification des Permissions

Pour modifier les permissions d'un fichier ou d'un répertoire, vous pouvez utiliser la commande `chmod`. Voici quelques exemples :

* `chmod u+w fichier` : Ajoute la permission d'écriture au propriétaire du fichier.
* `chmod g-r fichier` : Retire la permission de lecture au groupe.
* `chmod o+x fichier` : Ajoute la permission d'exécution aux autres utilisateurs.

### Propriété des Fichiers

Les commandes `chown` et `chgrp` permettent de changer respectivement le propriétaire et le groupe d'un fichier ou d'un répertoire.

* `chown utilisateur fichier` : Change le propriétaire du fichier.
* `chgrp groupe fichier` : Change le groupe du fichier.

### Permissions Spéciales

Il existe également des permissions spéciales :

* **SUID (Set User ID)** : Si défini sur un exécutable, l'utilisateur qui exécute le fichier le fait avec les permissions du propriétaire du fichier.
* **SGID (Set Group ID)** : Similaire au SUID, mais applique les permissions du groupe du fichier.
* **Sticky Bit** : Utilisé principalement sur les répertoires pour indiquer que seuls le propriétaire du fichier et le superutilisateur (root) peuvent supprimer le fichier dans le répertoire, même si d'autres ont des permissions d'écriture sur le répertoire.

Ces concepts forment la base de la gestion des permissions sur les systèmes Linux et UNIX, permettant un contrôle détaillé de l'accès aux fichiers et aux répertoires.
