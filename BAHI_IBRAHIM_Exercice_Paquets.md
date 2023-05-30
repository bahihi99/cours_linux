##### IBRAHIM BAHI
# Exercise Paquets


Q1: Avec quelle(s) commande(s) pouvez-vous vérifier si le paquet « htop » est bien installé sur votre système et quelle version est installée ?

A: `dpkg -s htop`. La commande `dpkg` permet de gérer les paquets. Quand on lui rajoute le paramètre `-s` et qu'on spécifie le programme qu'on souhaite, elle nous affiche le "status" (informations) du programme. On y trouve la version.

---

Q2: Avec quelle(s) commande(s) pouvez-vous vérifier quelle est la dernière version disponible du paquet « htop » dans les dépôts de votre distribution ?

A: `apt show htop`. La commande apt permet aussi de gérer les paquets. Quand on lui rajoute le paramètre `show` et qu'on spécifie le programme qu'on souhaite, elle nous affiche une liste des versions disponibles dans nos dépôts.

---

Q3: Avec quelle(s) commande(s) pouvez-vous installer la toute dernière version du paquet « htop » depuis les dépôts de votre distribution ?

A: `apt update && apt install htop`. La commande `apt` avec le paramètre `update` permet de mettre à jour notre dépôt. Ensuite, grâce au `&&`, on exécute la commande `apt install` directement après la fin de l'exécution de la mise à jour des dépôts. Si une nouvelle version est disponible, elle sera installée.

---

Q4: Avec quelle(s) commande(s) pouvez-vous vérifier quelles mises à jour sont disponibles ?

A: `apt list --upgradable`. La commande `apt list` permet de nous afficher une liste des programmes. On rajoute le paramètre `--upgradable` pour que le programme nous affiche uniquement les programmes qui ont des mises à jour disponibles.

---

Q5: Avec quelle(s) commande(s) pouvez-vous désinstaller le paquet « htop » ?
A: `apt remove htop`. La commande `apt` avec le paramètre `remove` permet de désinstaller un programme qu'on spécifie.

Q6: Avec quelle(s) commande(s) pouvez-vous vérifier si le paquet « iotop » est bien installé sur votre système et quelle version est installée ?

A: `yum info iotop`. La commande `yum` permet de gérer les paquets dans une distribution CentOS. Avec le paramètre `info`, on demande au programme de nous donner les infos du programme spécifié.

---

Q7: Avec quelle(s) commande(s) pouvez-vous vérifier quelle est la dernière version disponible du paquet « iotop » dans les dépôts de votre distribution ?

A: `yum list available iotop`. La commande yum avec les options `list available` affiche les versions disponibles d'un programme spécifié.

---

Q8: Avec quelle(s) commande(s) pouvez-vous installer la toute dernière version du paquet « iotop » depuis les dépôts de votre distribution ?

A: `yum install iotop`. La commande `yum`, avec l'option `install`, permet d'installer un programme qu'on spécifie.

---

Q9: Avec quelle(s) commande(s) pouvez-vous vérifier quelles mises à jour sont disponibles ?

A: `yum check-update`. La commande yum avec l'option `check-update` permet d'afficher les programmes qui ont des mises à jour disponibles.

---

Q10: Avec quelle(s) commande(s) pouvez-vous revenir à l'état dans lequel se trouvait le système avant l'installation de « iotop » ?
A: `yum history`. La commande yum avec le paramètre history permet d'afficher une liste des transactions effectuées par `yum`.
Ensuite, identifiez le numéro de transaction correspondant à l'installation de "iotop".
Utilisez la commande `yum history undo <numéro-de-transaction>`, en remplaçant `<numéro-de-transaction>` par le numéro que vous avez identifié précédemment.
Cette commande annulera la transaction spécifiée, supprimera le paquet "iotop" et restaurera l'état précédent du système.