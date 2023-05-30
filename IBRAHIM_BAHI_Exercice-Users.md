##### IBRAHIM BAHI
# Exercise Permissions

---
Q1: Avec quelle commande pouvez-vous vérifier les permissions du fichier « /etc/passwd » ?

A: `ls -l /etc/passwd`. la commande `ls` permet d'afficher les elements d'un dossier, quand on lui rajoute l'option `-l` et qu'on précise un fichier il nous affiche ses permissions.

---

Q2: Avec quelle commande pouvez-vous ajouter les droits d’écriture pour le groupe propriétaire du fichier « /etc/passwd » ?

A: `chmod g+w /etc/passwd`. `chmod` permet de changer les permissions d'un fichier. Dans ce cas avec l'option `g+w` on dit de rajouter (grace au `+`) la permission d'écrire (`w`) dans le groupe propriétaire (`g`).

---

Q3: Avec quelle commande pouvez-vous définir les droits de lecture, écriture et exécution à tout utilisateur du système, y compris l’utilisateur et le groupe propriétaire, pour le fichier « /etc/passwd » ? 

A: `chmod 777 /etc/passwd`. `chmod` permet de changer les permissions d'un fichier. Avec l'option `777` on précise a la commande qu'on souhaite donner tout les droits a tout les utilisateurs du systeme. Le 1er chiffre determine l'utilisateur, le 2eme le groupe et le 3eme les autres. Dans ce cas on met comme valeur 7 car on veut lui donner toutes les permissions (4 pour lecture + 2 pour l'écriture + 1 pour l'execution)

---

Q4: Avec quelle commande pouvez-vous retirer les droits d’exécution pour tous les utilisateurs du système, y compris l’utilisateur et le groupe propriétaire, pour le fichier « /etc/passwd » ? 

A: `chmod 000 /etc/passwd`. `chmod` permet de changer les permissions d'un fichier. Avec l'option `000` on précise a la commande qu'on souhaite donner aucune permission a tout les utilisateurs du systeme. Le 1er chiffre determine l'utilisateur, le 2eme le groupe et le 3eme les autres. Dans ce cas on met comme valeur 0 car on veut lui donner aucune permission (0 pour lecture + 0 pour l'écriture + 0 pour l'execution)

---

Q5: Avec quelle commande pouvez-vous retirer les droits d’écriture à tous les utilisateurs du système, sauf à l’utilisateur propriétaire, pour le fichier « /etc/passwd » ?


A: `chmod go-rwx /etc/passwd`. `chmod` permet de changer les permissions d'un fichier. Dans ce cas avec l'option `go-rwx` on dit de supprimier (grace au `-`) les permissions écrire (`w`), lire (`r`) et executer (`x`) dans le groupe propriétaire (`g`) et les autres (`o`).

---

Q6: Avec quelle commande pouvez-vous changer les propriétés du fichier « /etc/passwd » pour que votre groupe primaire en soit le groupe propriétaire ?


A: `chown :debianvm /etc/passwd` la commande `chown` nous permet de modifier le propriétaire et groupe du fichier. Dans ce cas on modifie le groupe d'un fichier grace a l'option `:debianvm` (les `:` précisent que on souhaite changer le groupe et `debienvm` est le groupe souhaité)
---

Q7: Avec quelle commande pouvez-vous changer les propriétés de tous les fichiers sous « /etc »  pour qu’ils appartiennent à votre utilisateur ?

A: `chown -R debian /etc` nous permet de modifier l'utilisateur propriétaire du fichier. Avec l'option `-R` on dit a la commande de parcourir tout les fichiers du dossier `/etc`.

---

Q8: Considérons un fichier « /tmp/test.txt » qui est accessible en écriture par tous les utilisateurs du système. Avec quelle commande pouvez-vous vous assurer que seul le propriétaire du fichier soit capable de le supprimer, sans retirer les droits d’écritures aux autres utilisateurs ?


A: `chmod +t /tmp/test.txt`. `chmod` permet de changer les permissions d'un fichier. En rajoutant l'option `+t` on rajoute un "sticky bit", quand le propriétaire du fichier le rajoute, personne peut supprimer ce fichier sauf son propriétaire.

---

Q9:  Avec quelle commande pouvez-vous vous assurer qu’un simple utilisateur puisse exécuter le binaire « /usr/bin/stat » en endossant l’identité de l’utilisateur qui en est propriétaire ?

A: `chmod u+s /usr/bin/stat`. `chmod` permet de changer les permissions d'un fichier. Dans ce cas nous sommes connectés tant que propriétaire du fichier. On rajoute la permission `s` ce qui permet d'executer le fichier avec les permission du propriétaire.

---

Q10: Considérons que le dossier /tmp/temp-dir appartient au groupe « teams ». Avec quelle commande pouvez-vous vous assurer que tous les fichiers créés dans ce dossier appartiendront bien à ce groupe et pas au groupe primaire de l’utilisateur qui a créé le fichier ?

A: `chmod g+s /tmp/temp-dir`. `chmod` permet de changer les permissions d'un fichier. Dans ce cas nous sommes connectés tant que propriétaire du dossier. On rajoute la permission `s` dans les permissions de groupe pour que tout nouveau fichier crée par peu importe l'utilisateur, aie comme propriétaire le groupe du do