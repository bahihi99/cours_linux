##### IBRAHIM BAHI
# Exercise FHS & Commands
Q1: Avec quelle commande pouvez-vous affichez le dossier dans lequel vous vous trouvez ?

A: `pwd` affiche le répertoire courant.

---

Q2: Avec quelle commande pouvez-vous vous déplacer dans le dossier
« /tmp » ?

A: `cd /tmp` permet de changer le répertoire courant à ´tmp´.

---

Q3: Avec quelle commande pouvez-vous vous déplacer dans le dossier parent
de « /tmp » ?

A: `cd ..` permet de changer le répertoire courant dans le dossier parent si on se trouve dans `/tmp`. Si on ne se trouve pas dans le dossier `/tmp` on peut utiliser la commande `cd /tmp/..` .

---

Q4: Avec quelle commande pouvez-vous retourner dans votre dossier initial,
sans préciser le nom du dossier ?

A: `cd` permet de retourner dans le répertoire initial de l'utilisateur.

---

Q5: Avec quelle commande pouvez-vous créer le fichier « /tmp/lin-fhs-01.txt » contenant la phrase « ceci est un fichier texte » ?

A: `echo ceci est un fichier texte > /tmp/lin-fhs-01.txt` `echo` affiche du texte mais on dirige le contenu dans le fichier `/tmp/lin-fhs-01.txt`.

---

Q6: Avec quelle commande pouvez-vous copier et renommer le fichier
« /etc/passwd » en « /tmp/new-passwd » ?

A: `cp /etc/passwd /tmp/new-passwd` copie le fichier source `/etc/passwd` en un nouveau fichier destination `/tmp/new-passwd`.

---

Q7: Avec quelle commande pouvez-vous copier le fichier « /etc/group » et le fichier « /etc/passwd » dans le dossier courant ? Le dossier courant est déterminé avec la réponse à la question 1.

A: `cp /etc/group /etc/passwd .` on copie les fichiers `/etc/group` et `/etc/passwd` dans le répertoire courant via `.`(qui désigne le répertoire courant).

---

Q8: Avec quelle commande pouvez-vous lister les fichiers présents dans le dossier « /var/log » ?

A: `ls /var/log` permet de lister les fichier et dossies dans le repertoire mis en parametre.

---

Q9: Avec quelle commande pouvez-vous lister tous les fichiers, même les fichiers cachées, dans votre répertoire utilisateur ? Le répertoire utilisateur est le répertoire courant lors de votre connexion au shell.

A: `ls -a /home/debianvm` la commande `ls` permet de lister les fichier et dossiers dans le répertoire `/home/debianvm` qui est le répertoire utilisateur de l'utilisateur `debianvm`; on rajoute le paramètre `-a` qui nous permet de voir tout les fichiers et dossiers cachés.

---

Q10: Avec quelle commande pouvez-vous créer un fichier caché ?

A: `echo > .filename` on dirige la réponse de la commande `echo` (dans ce cas rien) dans le fichier `/tmp/lin-fhs-01.txt`

---

Q11: Avec quelle commande pouvez-vous afficher le manuel de la commande « cat » ?

A: `man cat` la commande `man` permet d'afficher le manuel d'une commande (dans ce cas `cat`).

---

Q12: Avec quelle commande pouvez-vous créer un répertoire nommé « /tmp/lin-fhs-dir » ?

A: `mkdir /tmp/lin-fhs-dir` la commande `mkdir` permet de créer un repertoire qu'on spécifie.

---

Q13: Avec quelle commande pouvez-vous déplacer le fichier « /tmp/lin-fhs-01.txt » dans le dossier «/tmp/lin-fhs-dir » ?

A: `mv /tmp/lin-fhs-01.txt /tmp/lin-fhs-dir` la commande `mv` permet de deplacer un fichier spéficié à un autre repertoire spécifié.

---

Q14: Avec quelle commande pouvez-vous supprimer le dossier « /tmp/lin-fhs-dir » et le fichier qu’il contient ?

A: `rm -r /tmp/lin-fhs-dir` la commande `rm` permet de supprimer un fichier spécifié mais dans ce cas on souhaite supprimer un dossier et son contenu donc on rajoute le parametre `-r` qui permet de supprimer les fichier et le dossier de façon recursive

---

Q15: Avec quelle commande pouvez-vous afficher les cinq premières lignes du fichier « /etc/passwd » ?

A: `head -n 5 /etc/passwd` la commande `head` nous permet d'afficer le début d'un fichier, dans ce cas grace au drapeau `-n` avec comme valeur 5 nous permet d'afficher les 5 premieres lignes.


---

Q16: Avec quelle commande pouvez-vous afficher les trois dernières lignes du fichier « /etc/passwd » ?

A: `tail -n 3 /etc/passwd` la commande `tail` nous permet d'afficer la fin d'un fichier, dans ce cas grace au drapeau `-n` avec comme valeur 3 nous permet d'afficher les 3 dernieres lignes.

---

Q17: Avec quelle commande pouvez-vous afficher la ligne contenant « root » dans le fichier « /etc/passwd » ?

A: `cat /etc/passwd | grep root` la commande `cat` permet de lire les donnés dans `/etc/passwd` et grace au pipe (`|`) on peut passer le résulstat a la commande `grep` qui elle va chercher dans le résultat de `cat` la chaine de charactere demandée.

---

Q18: Avec quelle commande peut-on rediriger la sortie de la commande « date » dans un fichier « /tmp/date.txt » ?

A: `date > /tmp/date.txt` la commande `date` renvois comme données la date actuelle et grace a l'operateur `>` on redirige le résultat dans un fichier texte `/tmp/date.txt`

---

Q19: Avec quelle commande pouvez-vous trouver l’emplacement de la commande « cat » ?

A: `whereis cat` la commande `whereis` permet d'afficher le repertoire d'une commande et de son manuel.

---

Q20: Avec quelle commande pouvez-vous afficher l’historique de commande

A: `history` permet d'afficher l'historique des commandes utilisés.
