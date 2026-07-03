# Journal de navigation — Bavaria 37 (PWA)

Application web installable pour saisir en mer les mesures (vitesse, AWS, AWA)
et la configuration voile, avec stockage local robuste (IndexedDB) et export Excel/CSV.

## Fichiers

- `index.html` — l'application
- `sw.js` — service worker (fonctionnement hors-ligne)
- `manifest.json` — déclaration PWA (installation sur l'écran d'accueil)
- `icon-192.png`, `icon-512.png` — icônes

**Important : garder tous les fichiers dans le même dossier, à la racine.**

## Déploiement sur GitHub Pages (≈ 5 min)

1. Sur github.com, crée un nouveau dépôt (par ex. `journal-nav`), public.
2. Bouton **Add file → Upload files** : dépose les 5 fichiers (sans sous-dossier).
   Valide avec **Commit changes**.
3. Onglet **Settings → Pages**.
4. Section **Build and deployment**, source **Deploy from a branch**.
   Choisis la branche `main` et le dossier `/ (root)`. **Save**.
5. Patiente ~1 min, recharge la page Settings → Pages : une URL apparaît,
   du type `https://<ton-pseudo>.github.io/journal-nav/`.
6. Ouvre cette URL **dans Chrome sur le téléphone**.
7. Menu Chrome (⋮) → **Ajouter à l'écran d'accueil** / **Installer l'application**.
   L'icône bateau apparaît ; l'appli s'ouvre en plein écran, fonctionne hors-ligne,
   et conserve l'historique de façon fiable.

## Mise à jour ultérieure

Si je te fournis une nouvelle version, ré-uploade les fichiers modifiés sur GitHub.
Le numéro `CACHE_VERSION` dans `sw.js` doit être incrémenté à chaque changement
pour que le téléphone recharge la nouvelle version (sinon l'ancienne reste en cache).

## Sauvegarde des données

Les saisies sont stockées dans le téléphone (IndexedDB + copie de secours).
Exporte régulièrement en Excel ou CSV pour conserver une sauvegarde hors de l'appareil.
