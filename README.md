# Exposé sur l'accessibilité

## Les langues

La déclaration de la langue est essentielle pour l'accessibilité car elle permet aux lecteurs d'écran de :<br>
    - Utiliser le bon moteur de synthèse vocale <br>
    - Appliquer les règles linguistiques appropriées <br>
    - Faciliter la traduction automatique <br>
    
```
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Exemple de déclaration de langue</title>
</head>
<body>
    <h1>Bienvenue sur notre site</h1>
    <p>Ceci est un texte en français.</p>
</body>
</html>
```

Aussi, la langue peut être indiqué dans certains cas plus spécifiques si certains textes sont dans une autre langue que la langue générale du site. Elle s'indique dans le tag html. 

Exemple : 
`<a href="…" lang="fr" hreflang="fr">Version française</a>`

## Liens et bouton

La distinction entre lien et bouton est impérative. Voici un exemple :
```
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Exemple liens et boutons</title>
    <style>
        .button {
            display: inline-block;
            padding: 8px 16px;
            background-color: #007bff;
            color: white;
            text-decoration: none;
            border-radius: 4px;
        }
        
        /* Pour démontrer que les boutons ont une apparence native */
        button {
            margin-left: 10px;
        }
    </style>
</head>
<body>
    <!-- Navigation (utiliser des liens) -->
    <nav>
        <a href="/accueil">Accueil</a>
        <a href="/produits">Produits</a>
        <a href="/contact">Contact</a>
    </nav>

    <!-- Actions (utiliser des boutons) -->
    <div>
        <button onclick="alert('Formulaire soumis')">Soumettre le formulaire</button>
        <span class="button" role="button" tabindex="0" onclick="alert('Action effectuée')">Action rapide</span>
    </div>
</body>
</html>
```
