1. Pourquoi l'application Android ne se connecte pas directement a MongoDB ?
Pour la securite, sinon il faut mettre les identifiants de la base dans l'application. L'API sert
d'intermediaire : elle verifie les donnees et controle l'acces, et plusieurs clients peuvent utiliser la
meme API.
2. Quelle est la difference entre req.body, req.params et req.query ?
req.body : les donnees envoyees en JSON dans un POST ou PUT, par exemple { "nom": "Ben
Salah", "prenom": "Ali" }
req.params : la partie variable de l'URL, par exemple /api/patients/:id donne req.params.id
req.query : les filtres apres le ?, par exemple /api/patients?statut=Actif donne req.query.statut
3. Pourquoi repondre 404 et non 400 quand l'id ne correspond a aucun patient ?
400 c'est quand la requete est mal formee (id invalide comme "abc"). Ici l'id est valide mais le patient
n'existe pas, donc c'est 404 (introuvable).
4. Que se passe-t-il si on oublie app.use(express.json()) ?
Le JSON n'est pas lu donc req.body est undefined. Le POST donne une erreur de validation meme si
on a envoye les donnees.
5. Pourquoi l'emulateur utilise 10.0.2.2 au lieu de localhost ?
Pour l'emulateur, localhost c'est lui-meme et pas le PC. 10.0.2.2 est l'adresse qui renvoie vers le
localhost du PC ou tourne le serveur.
6. A quoi sert await ? Quelle notion de Kotlin lui correspond ?
await attend le resultat d'une operation longue (comme une requete MongoDB) sans bloquer le
serveur. En Kotlin ca correspond aux fonctions suspend et aux coroutines.
