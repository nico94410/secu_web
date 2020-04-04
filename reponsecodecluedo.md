Exercice 1

- L'algorithme de chiffrement symétrique DES est aujourd'hui obsolète car plusieurs attaques ont été découvertes sur cet algorithme. Il faut lui préférer AES ou triple DES par exemple.
- Le module commands est déprécié, il est remplacé dans python3 par subprocess.
- La fonction de hachage MD5 est obsolète, elle a été cassée en 2004 et une collision complète a été découverte. Aujourd'hui, il faut lui préférer SHA-256 par exemple.
-  Utiliser le répertoire /tmp/ comme répertoire sécurisé est dangereux car l'OS vide régulièrement ce répertoire qui est censé contenir uniquement des fichiers temporaires. De plus, hard-coder le nom (en clair) du répertoire sécurisé rend d'éventuelles modifications plus compliquées.
- Aucun système d'authentification et d'autorisation n'est mis en place. Tout utilisateur accédant à /employee peut consulter et modifier les données "sécurisées".
- Il n'y a pas de gestion des erreurs par des try/except par exemple.
- La clé de chiffrement utilisée est la même pour tous les fichiers. Deplus, si quelqu'un à accès au code source de l'application, il peut récupérer la clé de chiffrement en calculant le md5 de "085ZMV..."
- La clé réellement utilisée pour le chiffrement n'utilise que les 8 premiers caractères de la clé "random" ce qui est court et vulnérable à une attaque par bruteforce.
- Les champs ssn et email sont des champs controlés par les utilisateurs. Il est donc a priori possible de remplacer n'importe quel fichier de n'importe quel utilisateur. En effet, si un premier utilisateur bienveillant met un fichier toto avec son addresse mail toto@titi.com le fichier sera enregistré dans /tmp/toto-toto@titi.com. Mais rien empèche un utilisateur malvaillant de donner les mêmes informations avec une data différente. Dans ce cas le fichier sera écrasé et les données originales perdues. Lorsque l'utilisateur légitime essayera de récupérer ses données, il récupérera à la place les données écrites par l'utilisateur malveillant.
- Les données peuvent également être ecrites dans n'importe quel dossier car si on donne un nom de fichier du style "../etc/" le fichier sera enregisté dans le dossier etc.
- Enfin, la faille de sécurité la plus grave est l'injection de shell code dans la fonction list_secure_data. En effet, le champs "ssn" est a priori controlé par l'utilisateur. Il est donc possible de mettre un point virgule puis n'importe quelle commande. L'utilisateur peut donc facilement créer une backdoor et faire tout ce qu'il veut.
