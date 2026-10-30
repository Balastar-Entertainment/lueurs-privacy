# Lueurs — Politique de confidentialité

Page publique de la politique de confidentialité de l'application Android
**Lueurs : concentration**, éditée par **Balastar Entertainments**.

## Contenu du dossier

| Fichier | Rôle |
|---------|------|
| `index.html` | La page elle-même. Autonome : aucune police, aucune ressource distante. Les **neuf langues** sont basculées par neuf boutons radio en CSS pur, donc la bascule fonctionne sans JavaScript. Un unique script inline, en fin de page, ne sert qu'à présélectionner la langue du navigateur quand elle est prise en charge ; sans lui, la page reste en français. |
| `.nojekyll` | Fichier vide, demandé par GitHub Pages pour servir les fichiers tels quels (sans traitement Jekyll). |

Empreinte de `index.html` : `61846313a8c5ff38354401c7e69e676b7586243c3111537ec6cd318467620fe3`
(87 344 octets, 9 langues) — version du 30 octobre 2026.

## Langues

| Code | Bouton | Origine du texte |
|------|--------|------------------|
| `fr` | Français | rédaction d'origine |
| `en` | English | rédaction d'origine |
| `es` `pt` `it` `de` `nl` `pl` `sv` | Español · Português · Italiano · Deutsch · Nederlands · Polski · Svenska | traduction intégrale du contenu d'origine (mêmes sections, mêmes tableaux, mêmes faits), 30 octobre 2026 |

La langue du navigateur est retenue si elle fait partie des neuf ; sinon la page
s'affiche en français.

Les libellés d'interface cités dans la page (Réglages, Vider mon ciel, Continuer,
les intentions…) reprennent les traductions réelles de l'application
(`lib/l10n/app_<langue>.arb`), pour que le texte corresponde à ce que l'utilisateur
voit à l'écran.

## Sauvegarde système Android

Depuis le **30 octobre 2026**, l'application **ne désactive plus** la sauvegarde
Android : le manifeste ne déclare ni `android:allowBackup` ni
`android:fullBackupContent`, la sauvegarde système reste donc **active par défaut**,
pour que la progression soit restaurable au changement de téléphone ou à la
réinstallation. La page le dit explicitement en section 2, dans les neuf langues,
et la section 3 le rappelle :

> si la sauvegarde système d'Android est activée sur votre appareil, le système peut
> inclure les données de l'application dans la sauvegarde rattachée à votre compte
> Google ; nous n'y avons aucun accès ; cela se désactive dans les réglages Android
> (Sauvegarde et restauration) ; en changeant de téléphone ou en réinstallant, la
> progression peut être restaurée par ce mécanisme.

Le même paragraphe figure dans `docs/store/politique-confidentialite.md` du dépôt.

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
  aucune ressource externe (87 344 octets, 1 328 lignes).
* Contrôle structurel : les neuf blocs de langue portent chacun 9 sections,
  2 tableaux (14 lignes), 6 puces, 17 paragraphes et 9 titres `h2` ; aucun marqueur
  d'une autre langue n'y apparaît.
* Bascule vérifiée dans un navigateur (**Edge headless**, captures d'écran) : avec
  `--lang=pl` la page s'affiche en polonais et le bouton « Polski » est mis en
  évidence, avec `--lang=de` en allemand et « Deutsch » mis en évidence.
* Sélection de la langue par défaut testée sur le **script réellement embarqué**
  (extrait de `index.html`, exécuté sous Node avec un navigateur simulé) : 9 cas,
  dont « aucune langue du navigateur prise en charge » → français.
* Paragraphes `fr` et `en` comparés à la version publiée précédente
  (`sha256 c9af2185…`, récupérée depuis la page en ligne) : **identiques hors deux
  passages** — le paragraphe « sauvegarde système Android » (section 2) et la seconde
  puce de la section 3, décrite ci-dessous.
* Section 3 « Suppression de ces données » reformulée dans les **neuf langues** :
  l'affirmation « personne n'en conserve de copie » est remplacée par la mention de la
  sauvegarde système Android — une copie peut y subsister, elle est rattachée au compte
  Google de l'utilisateur, qui la gère et peut la supprimer dans les réglages de son
  compte Google ou d'Android ; nous n'y avons aucun accès et n'en conservons aucune.
* E-mail de contact `loannsloan@gmail.com`, éditeur « Balastar Entertainments » et
  nom « Lueurs : concentration » présents dans les neuf langues.
* Contenu confronté au code de l'application (`lib/ads_config.dart`,
  `lib/consent_manager.dart`) et au manifeste fusionné du build release
  (`build/app/intermediates/merged_manifest/release/`).

Contact : loannsloan@gmail.com · Dernière mise à jour du texte : 30 octobre 2026.
