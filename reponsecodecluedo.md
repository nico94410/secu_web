Exercice 1

- L'algorithme de chiffrement symétrique DES est aujourd'hui obsolète car plusieurs attaques ont été découvertes sur cet algorithme. Il faut lui préférer AES ou triple DES par exemple.
- Le module commands est déprécié, il est remplacé dans python3 par subprocess.
- La fonction de hachage MD5 est obsolète, elle a été cassée en 2004 et une collision complète a été découverte. Aujourd'hui, il faut lui préférer SHA-256 par exemple.
-  Utiliser le répertoire /tmp/ comme répertoire sécurisé est dangereux car l'OS vide régulièrement ce répertoire qui est censé contenir uniquement des fichiers temporaires. De plus, hard-coder le nom (en clair) du répertoire sécurisé rend d'éventuelles modifications plus compliquées.
- Aucun système d'authentification et d'autorisation n'est mis en place. Tout utilisateur accédant à /employee peut consulter et modifier les données "sécurisées".
- Il n'y a pas de gestion des erreurs par des try/except par exemple.
