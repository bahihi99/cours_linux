##### IBRAHIM BAHI
# Exercise Réseau

---
Q1: Avec quelle(s) commande(s) pouvez-vous vérifier le nom des interfaces réseau du système et l’adresse ip qui y es associée ?

A: `ip a`. La commande `ip` nous permet d'afficher des informations sur notre configuration réseau, on y rajoutant le parametre `a`, la commande nous affiche les noms des interfaces réseau et de leur addresse IP respective.

---

Q2: Avec quelle(s) commande(s) pouvez-vous vérifier la passerelle (gateway) de votre système ?

A: `ip route`. La commande `ip` nous permet d'afficher des informations sur notre configuration réseau, en y rajoutant le parametre `route`, on peut afficher la default gateway de notre réseau.

---

Q3: Quel fichier devez-vous modifier pour changer la configuration de vos interfaces réseau ? 

A: `/etc/network/interfaces`. le fichier `interfaces` qui se trouve dans `/etc/network`, est le fichier de configuration de nos interfaces réseaux, pour pouvoir modifier ce fichier il faut etre en `root`

---

Q4: Modifiez la configuration de votre interface réseau principale pour utiliser les paramètres fixe suivants :
  1. Adresse IP : l’adresse IP que vous aviez obtenu via DHCP.
  2. Masque de sous-réseau : le masque que vous aviez obtenu via DHCP.
  3. Passerelle par défaut : l’adresse IP que vous aviez obtenu via DHCP.
  4. Serveur de nom : utilisez l’adresse IP « 8.8.8.8 ».

A: Pour modifier la configuration IP et DNS de notre systeme il faudra modifier quelques fichiers, pour cela on utilise le programme `nano`:
  1. Pour modifier l'adresse IP donné via le DHCP en adresse IP statique nous devons modifier le fichier `/etc/network/interfaces`. 
    Une fois dans le fichier, on peut appercevoir plusieurs lignes, les lignes commençant par un `#` on peut les ignorer car ce ne sont que des commentaires.

```
    # The loopback network interface
    auto lo
    iface lo inet loopback
    
    # The primary network interface
    allow-hotplug enp1s0
    iface enp1s0 inet dhcp    <------
    # This is an autoconfigured IPv6 interface
    iface enp1s0 inet6 auto
```
  La ligne qui nous importe le plus est `iface enp1s0 inet dhcp`, cette ligne nous dis que l'interface `enp1s0` a son adresse ip donné par le DHCP, nous devons modifier cette ligne pour lui donner une adresse IP statique.

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
