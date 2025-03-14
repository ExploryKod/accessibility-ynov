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

Il existe des labels alternatifs pour les liens et boutons à n'utiliser que si on ne peux faire autrement. Les labels alternatifs sont essentiels pour les éléments interactifs qui ne sont pas suffisamment descriptifs :

```
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Exemple de labels alternatifs</title>
    <style>
        .button {
            display: inline-block;
            padding: 8px 16px;
            background-color: #007bff;
            color: white;
            text-decoration: none;
            border-radius: 4px;
        }
        
        /* Pour masquer visuellement le texte tout en le gardant accessible */
        .sr-only {
            position: absolute;
            width: 1px;
            height: 1px;
            padding: 0;
            margin: -1px;
            overflow: hidden;
            clip: rect(0, 0, 0, 0);
            border: 0;
        }
    </style>
</head>
<body>
    <!-- Lien avec icône et aria-label -->
    <a href="/panier" aria-label="Accéder au panier d'achat">
        🛒 Panier (3 articles)
    </a>

    <!-- Bouton avec aria-label -->
    <button aria-label="Fermer cette fenêtre">
        ×
    </button>

    <!-- Lien avec titre explicatif -->
    <a href="/mentions-legales" title="Voir les conditions générales d'utilisation">
        Mentions légales
    </a>
</body>
</html>
```



