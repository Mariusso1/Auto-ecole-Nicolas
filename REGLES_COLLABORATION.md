================================================================================
RÈGLES DE COLLABORATION - PROJET AUTO-ÉCOLE NICOLAS
Version : 1.0 | Date : 2026
================================================================================

================================================================================
RÈGLE 1 : COMMANDES CMD
================================================================================
→ Je ne exécuterai JAMAIS de commande dans le terminal sans vous demander au préalable
→ Chaque commande sera soumise pour validation avant exécution

================================================================================
RÈGLE 2 : FICHIERS (CRÉATION/MODIFICATION)
================================================================================
→ Je demanderai systématiquement votre AVANT de créer ou modifier un fichier
→ Chaque modification sera soumise pour validation avant application

================================================================================
RÈGLE 3 : BONNES PRATIQUES DE DÉVELOPPEMENT
================================================================================

--- 3.1 FRONT-END (HTML, CSS, JS) ---
• Sémantique HTML : Utiliser les balises appropriées (<main>, <nav>, <article>, 
  <button> au lieu de <div>) pour l'accessibilité (SEO et lecteurs d'écran)
• Performance des Images : Utiliser des formats modernes (WebP/Avif) et 
  l'attribut loading="lazy" pour les images hors écran
• Mobile-First : Concevoir les styles pour les petits écrans d'abord, puis 
  utiliser les @media queries pour les écrans plus larges
• DRY (Don't Repeat Yourself) : Créer des composants réutilisables pour éviter 
  la duplication de code
• Gestion d'état : Ne JAMAIS stocker d'informations sensibles (mots de passe, 
  clés secrètes) dans le LocalStorage ou la mémoire JS

--- 3.2 BACK-END (Logique & API) ---
• Validation des entrées : Ne JAMAIS faire confiance aux données provenant du 
  client. Valider le type, la longueur et le format (Regex) de chaque champ
• Codes de statut HTTP : Utiliser les bons codes (200 OK, 201 Created, 
  400 Bad Request, 401 Unauthorized, 404 Not Found, 500 Internal Server Error)
• Statelessness : Préférer les API REST sans état. Utiliser des JWT (JSON Web 
  Tokens) ou des sessions sécurisées pour l'authentification
• Logs & Monitoring : Enregistrer les erreurs (sans logger de données sensibles) 
  pour pouvoir déboguer rapidement en production


--- 3.3 SQL & BASES DE DONNÉES ---
• Requêtes Préparées : Utiliser systématiquement des paramètres (bind parameters) 
  pour éviter les injections SQL
• Normalisation : Éviter la redondance des données en structurant les tables 
  (1NF, 2NF, 3NF)
• Indexation : Créer des index sur les colonnes souvent utilisées dans les 
  clauses WHERE pour accélérer les recherches (avec parcimonie)
• Principe du moindre privilège : L'utilisateur SQL de l'application ne doit 
  pas avoir les droits "ROOT" ou "DROP TABLE". Lui donner uniquement 
  SELECT, INSERT, UPDATE, DELETE
• Sauvegardes : Automatiser des backups réguliers et tester la restauration

--- 3.4 CYBERSÉCURITÉ ---
• HTTPS Partout : Utiliser des certificats SSL/TLS pour chiffrer les données 
  en transit
• En-têtes de sécurité (HSTS, CSP) : Implémenter une Content Security Policy 
  (CSP) pour bloquer l'exécution de scripts non autorisés (XSS)
• Hachage des mots de passe : Ne JAMAIS enregistrer de mots de passe en clair. 
  Utiliser des algorithmes robustes comme Argon2 ou Bcrypt (avec un sel/salt)
• Gestion des Cookies : Utiliser les flags 'HttpOnly' (interdit l'accès JS), 
  'Secure' (uniquement via HTTPS) et 'SameSite=Strict' (protection CSRF)
• Rate Limiting : Limiter le nombre de requêtes par IP pour éviter les 
  attaques par force brute (Brute Force) ou par déni de service (DoS)

--- 3.5 ERREURS SIMPLES À ÉVITER (Checklist) ---
[ ] ERREUR : Pousser le dossier 'node_modules' ou les fichiers '.env' sur GitHub
    → CORRECTIF : Utiliser un fichier .gitignore
[ ] ERREUR : Utiliser 'admin'/'admin' ou des mots de passe faibles
    → CORRECTIF : Utiliser un gestionnaire de mots de passe et des secrets 
                  complexes dès le développement
[ ] ERREUR : Exposer des clés API de services tiers dans le code JavaScript
    → CORRECTIF : Faire transiter l'appel par le serveur (Backend Proxy)
[ ] ERREUR : Afficher des messages d'erreur détaillés en production
    → CORRECTIF : Afficher un message générique à l'utilisateur et logger 
                  l'erreur détaillée sur le serveur
[ ] ERREUR : Oublier de mettre à jour les dépendances (bibliothèques)
    → CORRECTIF : Utiliser des outils comme 'npm audit' ou Snyk pour 
                  surveiller les vulnérabilités

================================================================================
FIN DU DOCUMENT
================================================================================
