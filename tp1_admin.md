William Dubosq
Baptiste Jurand
4ETI

# Compte-rendu TP1 Administration système

## Exercice 2

### Manuel

1. which renvoie le chemin des fichiers qui seraient exécutés dans l'environnement courant si ses arguments avaient été donnés comme commandes dans un interpréteur de commandes strictement conforme à POSIX.

2. Pour faire une recherche de terme dans le terminal, on utilise la commande suivante :

	>*/mon_terme, par exemple /option*

3. Pour quitter le manuel, on utilise la touche *q* du clavier.

4. La section 6 du manuel décrit des jeux et petits programmes disponibles dans le système.

Pour trouver cette section, nous avons utilisé la commande *man 6 intro*.

### Navigation dans l’arborescence des fichiers

1. Pour se placer dans le dossier var/log, on utilise la commande : *cd . ./. ./var/log*

2.  Pour remonter dans l'arborescence, on utilise la commande : *cd . .*

3. Pour retourner dans le dossier personnel, on utilise la commande : *. ./. ./home*.

4. Pour revenir au dossier *var* sans utiliser de chemin, on utilise la commande suivante : *cd /var*

5. La permission ne nous est pas accordée.

6. La commande *sudo* ne fonctionne pas avec la commande *cd*.

7. Pour créer l'arborescence demandée, on tape les commandes suivantes suivantes dans cet ordre :

	>*cd . ./. ./home
	
	>sudo mkdir dossier1
	
	>cd dossier1
	
	>sudo touch fichier1
	
	>cd . .
	
	>sudo mkdir dossier2
	
	>cd dossier2
	
	>sudo mkdir dossier2.1
	
	>sudo mkdir dossier2.2
	
	>cd dossier2.2
	
	>sudo touch fichier2
	
	>sudo touch fichier3*

8. On ne peut pas supprimer *fichier1* car celui-ci n'est pas directement dans le dossier dans lequel on se trouve. On ne peut pas non plus supprimer *dossier1*, car c'est un *directory* et non un fichier.

9. Pour supprimer un dossier, il faut utiliser la commande *rmdir*.

10. Ici, cette commande ne fonctionne pas car *dossier2* n'est pas vide.

11. Pour supprimer un dossier et son contenu, on utilise l'option *-r*. Donc pour supprimer *dossier2* et son contenu, on exécute la commande suivante :

	>*sudo rm -r dossier2*.

### Commandes importantes

1. Il s'agit de la commande *date*. La commande *time* sert à connaître le temps d'exécution d'une commande.

2. La commande *ls* permet d'afficher les fichiers contenus dans un répertoire.

	La commande *la* permet d'afficher les fichiers cachés (commençant par un point).

3.

4. La commande *ll* permet d'afficher l'intégralité des fichiers, y compris les fichiers cachés. Elle ne possède pas d'entrée dans le manuel car il s'agit d'un raccourci de la commande :

	> *ls -alF* (cf. alias).

5. La commande à utiliser pour voir le contenu du dossier *bin* est la suivante :

	> *ls /bin*

6.  La commande *ls . .* affiche l'ensemble des répertoires parents du dossier dans lequel on se trouve.

7. Il s'agit de la commande *pwd*.

8. On obtient un fichier texte *plop* dans le répertoire courant, avec écrit *yo* une fois dedans.

9. On obtient un fichier texte *plop* dans le répertoire courant, avec écrit *yo* deux fois dedans.

	On en déduit que l'utilisation d'un seul chevron (>) écrase et ajoute du texte. L'utilisation de deux chevrons ajoute simplement le texte dans le fichier avec un retour à la ligne.

10. La commande *file* permet de déterminer le type d'un fichier ou d'un dossier. Par exemple, pour *plop*, il s'agit d'un *ASCII text*, pour *fichier1* d'un *empty*, pour *dossier1* d'un *directory*.

11. On remarque qu'en modifiant *toto*, on modifie également *titi*. En revanche, lorsque l'on supprime *toto*, cela ne supprime pas *titi* et son contenu reste inchangé.

12. Lorsqu'on modifie l'un des documents, l'autre s'actualise automatiquement. Contrairement à la question précédente, lorsqu'on supprime *titi*, *tutu* ne pointe plus vers rien. Le lien symbolique est cassé (*broken symbolic link to titi*).

13. Pour arrêter le défilement, il faut taper *CTRL + S*, et *CTRL + Q* pour reprendre le défilement.

14. Nous réalisons la commande suivante afin d'afficher les 5 premières lignes de *syslog* :

	> *head -5 /var/log/syslog*

	Pour afficher les 15 dernières lignes de *syslog* :

	> *tail -15 /var/log/syslog*

	Pour afficher les lignes entre 10 et 20 de *syslog* :

	> *head -n 10 /var/log/syslog | tail -n 20*

15. Cette commande *dmesg* | *less* (*display message*) permet d'afficher la mémoire tampon de message du noyau.

16. Le fichier *passwd* contient toutes les informations relatives aux logins et mots de passe des comptes d'utilisateurs.

	Pour afficher la page du manuel de passwd, il suffit de taper :

	> *man passwd*

17. Pour afficher uniquement la colonne triée par ordre alphabétique inverse, il faut utiliser la commande :

	> *sort +0 -r /etc/passwd*

18. Pour connaître le nombre d'utilisateurs, on utlise la commande suivante :

	> *wc -l /etc/passwd*

	Cette commande nous indique 31 utilisateurs.

19. Pour connaître le nombre des pages contenant le mot-clé *conversion*, on utilise la commande suivante :

	> *man -k conversion*

	On obtient 4 lignes de résultats, on en déduit que 4 pages de manuel contiennent le mot *conversion*.

20. La commande suivante permet de trouver les fichiers dont le nom est *passwd* sur l'ordinateur :

	> *find / -name passwd*

21. Pour que la liste des fichiers trouvés soit enregistrée dans le fichier~/list_passwd_files.txtet que les erreurs soient redirigées vers le fichier spécial/dev/null, on utilise la commande suivante :

	> *find / -name passwd > ~/list_passwd_files.txt 2>> /dev/null*

22. En utilisant la commande suivante :

	> *grep -ll*

	on voit que ll est défini dans *grep [OPTION]... PATTERNS[FILE]...*

23. On installe d'abord la commande *locate* avec la commande suivante :

	> *apt install mlocate*

	On peut ensuite chercher le chemin vers le fichier avec la commande suivante :

	> *locate history.log*

	On obtient alors le chemin */var/log/apt/history.log*

24. Rien ne s'affiche lorsqu'on fait la commande *locate fichier_a_trouver*, alors que nous avions créé le fichier précédemment.

## Exercice 4

3. L’invite de commande passe en effet en couleur. La partie *rootoor@serveur* est verte, *~* devient bleue et *:$* blanche.

4. Il faut changer une séquence dans .bashrc. Pour cela on exécute la commande suivante :

	> *nano .bashrc*

	Puis on recherche dans le fichier les lignes commençant pas *P1=*.

	Enfin on rajoute la ligne :

	> * \[\e[31m\A\e[0m-\[\033[1;92m]\u@\h\[\033[00m\]*

	On a ainsi l’heure en rouge, rootoor@serveur en vert clair et le chemin en bleu.
