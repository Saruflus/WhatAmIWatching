# WhatAmIWatching
Search infos about your Movies and Shows (with poster and disk art)

Par [Sulfuras](https://github.com/Saruflus)

Un outil web (page unique) pour rechercher films/séries, récupérer les métadonnées (OMDb), l’art du disque (fanart.tv) et exporter un PDF avec les mêmes infos. Interface bilingue (FR par défaut, EN dispo), avec autocomplétion, affichage du disque et export PDF (affiche + disque).

## Prérequis
- Navigateur moderne (aucune installation supplémentaire).
- Clés API valides :
  - OMDb
  - fanart.tv

## Configuration
1. Ouvrez `config.js`.
2. Remplacez les valeurs de `FANART_KEY` et `OMDB_KEY` par vos propres clés si nécessaire.
   ```js
   window.MOV_CONFIG = {
     FANART_KEY: 'votre_cle_fanart',
     OMDB_KEY: 'votre_cle_omdb'
   };
   ```

## Utilisation
1. Ouvrez `index.html` dans votre navigateur (double-clique ou servez-le via un petit serveur statique).
2. Choisissez la langue (FR/EN) depuis le sélecteur.
3. Saisissez un titre (ex. “Dune”, “Succession”) et lancez la recherche (les recherches FR passent par une traduction du titre pour interroger l’API).
4. L’affiche, les infos détaillées, l’art du disque (fanart.tv) et le bouton PDF apparaissent.
5. Cliquez sur « Télécharger le PDF » pour générer un PDF A4 (fond blanc) incluant l’affiche et l’art du disque centré en bas.

## Fichiers principaux
- `index.html` — Interface principale et logique côté client.
- `config.js` — Clés API (à personnaliser).
- `README.md` — Ce guide.

## Notes
- L’autocomplétion utilise iTunes (sans clé).
- Pour la traduction du synopsis en français (et des titres lors d’une recherche FR), un appel léger à l’API MyMemory est effectué; si cela échoue, le texte reste en anglais.
- Le fanart.tv est accédé avec repli CORS via `corsproxy.io` pour les images et les métadonnées si nécessaire.
