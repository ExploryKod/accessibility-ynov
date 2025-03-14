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

## Les images et icones 

```
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Exemple de gestion des images</title>
    <style>
        .icon {
            display: inline-block;
            width: 32px;
            height: 32px;
            background-size: contain;
            background-repeat: no-repeat;
        }
        
        .home-icon {
            background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24'%3E%3Cpath fill='%23007bff' d='M3 9l9-7 9 7Z M5 19h14v-14H5v14Zm2-11a1 1 0 0 1 1-1h10a1 1 0 0 1 1 1v10a1 1 0 0 1-1 1H7a1 1 0 0 1-1-1v-10z'/%3E%3C/svg%3E");
        }
        
        figure {
            margin: 20px 0;
            padding: 10px;
            border: 1px solid #ddd;
        }
        
        img, svg {
            max-width: 100%;
            height: auto;
        }
    </style>
</head>
<body>
    <!-- Image avec alt descriptif -->
    <img src="https://via.placeholder.com/400x300" 
         alt="Paysage montagnard avec lac au soleil couchant" />

    <!-- SVG avec aria-label -->
    <svg width="50" height="50" aria-label="Logo de l'entreprise">
        <circle cx="25" cy="25" r="20" fill="#007bff"/>
        <text x="25" y="25" text-anchor="middle" dy=".35em" fill="white">E</text>
    </svg>

    <!-- Icône CSS avec aria-label -->
    <span class="icon home-icon" role="img" aria-label="Accueil"></span>

    <!-- Figure avec légende -->
    <figure>
        <img src="https://via.placeholder.com/400x300" 
             alt="Vue détaillée d'une fleur sauvage">
        <figcaption>
            Une belle fleur sauvage photographiée au printemps
        </figcaption>
    </figure>
</body>
</html>

