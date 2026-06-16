# Maison Savary — Documentation technique

Cartographie interactive des automatisations et flux de données mis en place chez Maison Savary.

## Accès

- Page publiée : https://scalether-fr.github.io/maison-savary-doc-tech/
- Le détail métier (specs, configs, accès) reste dans les Google Docs du Drive Maison Savary, liés depuis chaque node.

## Édition

1. Cloner le repo
2. Modifier `index.html` (les nodes et edges sont en haut du `<script>`, sections `nodes = [...]` et `edges = [...]`)
3. `git commit` + `git push` → GitHub Pages redéploie automatiquement

## Structure d'un node

```js
{
  id: 'identifiant_unique',
  type: 'source' | 'script' | 'storage' | 'output',
  label: 'Nom affiché',
  desc: 'Sous-titre court',
  x: 80, y: 160,            // position canvas
  doc: 'https://docs.google.com/...', // optionnel : lien Google Doc
  meta: { 'Clé': 'Valeur', ... }
}
```

## Structure d'un edge

```js
{ from: 'id_source', to: 'id_cible', label: 'type de flux', style: 'dashed' }
```

`style: 'dashed'` est optionnel (par défaut trait plein).
