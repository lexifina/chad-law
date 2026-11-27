# Structure du dépôt / Repository layout

Les textes sont rangés par nature puis par année, en français (les noms que cherchent les juristes tchadiens). Un dossier
par texte, un fichier par article. Aucun dossier ne compte plus de 1 000 entrées.

Texts are filed by kind, then by year, with French names. One folder per text, one file per article. No folder holds
more than 1,000 entries.

```
constitution/                       Constitution du 29 décembre 2023 (préambule, un fichier par article et par titre)
codes/<code>/                       les codes : codes/code-penal/, codes/code-du-travail/, codes/code-minier/, ...
  art-001.md ... art-NNN.md         un fichier par article
  visas.md                          visas et préambule du texte qui adopte le code
  README.md                         source, date, couche texte, nombre d'articles
lois/<année>/<numéro>-<objet>/      lois et lois organiques (lois/1999/016-99-portant-.../)
ordonnances/<année>/<numéro>-<objet>/
decrets/<année>/<numéro>-<objet>/
arretes/<année>/<numéro>-<objet>/
decisions/<année>/<numéro>-<objet>/
traites-et-accords/<année>/<numéro>-<objet>/   conventions, accords, protocoles, avenants, traités, pactes
constitutions-anterieures/<année>/...   constitutions et actes fondamentaux antérieurs à celle de 2023
ohada/actes-uniformes/<année>/...      actes uniformes de l'OHADA (droit communautaire applicable au Tchad)
chartes/, resolutions/, deliberations/, reglements/, reglements-interieurs/, rectificatifs/, actes/   <année>/...
corpus.json                         la liste de tous les textes (td/national/acts)
```

- `<numéro>` reprend les groupes de chiffres du numéro officiel (`016/PR/99` donne `016-99`) ; `<objet>` est tiré de
  l'intitulé.
- Un texte dont aucun article n'a été repéré est un seul fichier, `texte-integral.md`.
- Un code adopté à nouveau (par exemple le Code minier de 1995 puis l'ordonnance de 2018) reste dans le même dossier
  `codes/<code>/` : la nouvelle version est un nouveau commit qui remplace les fichiers de l'ancienne.
- Les décrets et arrêtés de nomination, d'affectation ou de promotion, les décorations, grâces et ouvertures de session ne sont pas repris.
- Les textes de Légitchad portent le numéro que donne cette base (`05-006` pour la loi n° 006 de 2005).
- Les décisions de justice (OHADA) sont dans un dépôt séparé et privé.
