# Mes fiches films

Mon carnet de cinéma personnel : tous les films que j'ai vus et notés sur 5, enrichis de leurs informations (réalisateur, acteurs, durée, budget, recettes, note IMDb, thèmes, synopsis), avec une interface pour les retrouver.

## Contenu

| Fichier | Rôle |
|---|---|
| `index.html` | L'interface de recherche, en style Art déco |
| `films.json` | La liste des films notés, un film par ligne |

## L'interface

- **Recherche** par titre français ou titre original, avec suggestions pendant la frappe (accents, majuscules et articles ignorés).
- **Film déjà noté** : fiche complète avec ma note, le synopsis, les infos du film, ses thèmes, et une section « Dans la même veine » qui propose des films proches de ma liste.
- **Film pas encore noté** : quand la page est ouverte dans Claude, elle prépare la fiche du film et prédit la note que je lui mettrais d'après mes goûts. Cette fonction n'est pas disponible en dehors de Claude.

## Format des données

`films.json` est un tableau de films. Chaque film est une liste de 14 valeurs, dans cet ordre :

1. Titre
2. Ma note (sur 5, par demi-points)
3. Genre
4. Réalisateur
5. Acteurs principaux
6. Année
7. Durée (minutes)
8. Pays
9. Budget (dollars)
10. Recettes mondiales (dollars)
11. Note IMDb (sur 10)
12. Thèmes
13. Remarques
14. Synopsis

Les valeurs inconnues sont à `null`. Beaucoup de chiffres (budget, recettes, note IMDb) ont été renseignés de mémoire et ne sont pas revérifiés : c'est indiqué dans la colonne Remarques.

## Voir la page en local

Le fichier `index.html` charge `films.json` : il faut donc le servir depuis un petit serveur plutôt que l'ouvrir directement.

```bash
python3 -m http.server 8000
```

Puis ouvrir http://localhost:8000.

Le site peut aussi être publié avec GitHub Pages (Settings → Pages → branche `main`).
