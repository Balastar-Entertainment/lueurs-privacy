# Lueurs — Politique de confidentialité

Page publique (FR/EN) de la politique de confidentialité de l'application Android
**Lueurs : concentration**, éditée par **Balastar Entertainments**.

## Contenu du dossier

| Fichier | Rôle |
|---------|------|
| `index.html` | La page elle-même. Autonome : aucun script, aucune police ni ressource distante ; la bascule français/anglais est en CSS pur et fonctionne sans JavaScript. |
| `.nojekyll` | Fichier vide, demandé par GitHub Pages pour servir les fichiers tels quels (sans traitement Jekyll). |

## Publication (GitHub Pages)

1. Créer un dépôt **public** (par exemple `lueurs-confidentialite`).
2. **Add file → Upload files** et déposer `index.html` **et** `.nojekyll` à la racine.
3. Dépôt → **Settings → Pages** → *Deploy from a branch* → branche `main`, dossier
   `/ (root)` → **Save**.
4. Après une à deux minutes, la page est servie à l'adresse
   `https://<compte>.github.io/<depot>/`.

L'URL doit rester **publique et stable** : elle est déclarée dans la fiche Play
Store et Google la vérifie.

## Vérifications faites avant dépôt

* `python tools/check_html.py docs/store/site/index.html` → 0 erreur d'imbrication,
  aucun `<script>`, aucune ressource externe.
* E-mail de contact `loannsloan@gmail.com`, éditeur « Balastar Entertainments » et
  nom « Lueurs : concentration » présents en français et en anglais.
* Contenu confronté au code de l'application (`lib/ads_config.dart`,
  `lib/consent_manager.dart`) et au manifeste fusionné du build release
  (`build/app/intermediates/merged_manifests/release/`).

Contact : loannsloan@gmail.com · Dernière mise à jour du texte : 30 octobre 2026.
