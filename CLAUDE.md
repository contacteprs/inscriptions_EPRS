# EPRS Football — Inscriptions 2026/2027

Formulaire d'inscription en ligne pour les jeunes du club **EPRS (Entente Petit-Réderching Siersthal)**, Moselle, Grand Est.

**Responsable projet :** Guillaume Sumann — Coordinateur des jeunes EPRS  
**Contact :** guillaume.sumann@gmail.com — 06 76 93 73 28

---

## Stack technique

- HTML / CSS / JS vanilla (pas de framework)
- Hébergement : **GitHub Pages** (dépôt public)
- Collecte des données : **Google Forms** (migration depuis Formspree, limité en soumissions)
- Email de confirmation : **EmailJS** (service `service_p7jxxvn`, template `8mwemee`)
- Webhook automation : **Make.com** (`https://hook.eu1.make.com/dtwh31l3g7g8pzktlhuamv94acnvhrkv`)

---

## Fichiers

| Fichier | Rôle |
|---|---|
| `index.html` | Formulaire 4 étapes (Joueur → Contact → Démarches → Droit à l'image) |
| `style.css` | Design mobile-first, couleurs EPRS |
| `script.js` | Logique formulaire, validation, catégories, soumission |
| `confirmation.html` | Page affichée après envoi réussi |
| `images/` | logo.png, hero.jpg, hero2.jpg |

---

## Charte graphique

| Élément | Valeur |
|---|---|
| Bleu EPRS | `#1a3a6b` |
| Rouge EPRS | `#c0392b` |
| Fond | `#f8f7f4` |
| Titres | Oswald |
| Corps | Lato |

---

## Catégories saison 2026/2027

| Année de naissance | Catégorie | Mutation |
|---|---|---|
| 2021 ou 2020 | U7 | Non |
| 2019 ou 2018 | U9 | Non |
| 2017 ou 2016 | U11 | Non |
| 2015 ou 2014 | U13 | Oui — limite 15 juillet 2026 |
| 2013 ou 2012 | U15 | Oui — limite 15 juillet 2026 |
| 2011 | U16 | Oui — limite 15 juillet 2026 |
| 2010 | U17 | Oui — limite 15 juillet 2026 |
| 2009 et avant | Senior | Oui — limite 15 juillet 2026 |

**Règle annuelle :** chaque saison, ajouter 1 an à chaque fourchette de naissance.

---

## Éducateurs (script.js — constante `EDUCATEURS`)

| Catégorie | Nom | Téléphone |
|---|---|---|
| U7 | Guillaume Sumann | 06 76 93 73 28 |
| U9 | Claude Behr | 06 88 24 40 29 |
| U11 | Gilles Steiner | 06 70 34 85 80 |
| U13 | Maxime Collet | 06 10 37 36 66 |
| U15 | Benjamin Neu | 07 71 94 85 72 |
| U16 | Mickael D'anna | 06 32 08 37 68 |
| U17 | Lucas Homer | 07 71 66 77 69 |
| Senior | Alexandre Neu | 07 70 70 79 96 |

> À mettre à jour chaque saison ou dès qu'un éducateur change.

---

## Intégration Google Forms (en cours de migration)

Le formulaire HTML soumet ses données vers Google Forms via `fetch` en mode `no-cors`.  
Les champs HTML sont mappés sur les `entry.XXXXXXXXX` du Google Form.

**À compléter quand l'URL et les entry IDs sont disponibles :**
- URL de soumission : `https://docs.google.com/forms/d/e/XXXXXXXX/formResponse`
- Mapping champs ↔ entry IDs : à documenter ici

---

## Checklist mise à jour annuelle

- [ ] `index.html` : titre, texte hero, bannières, année footer
- [ ] `script.js` : table `CATEGORIES` (+1 an), dates min/max, éducateurs
- [ ] `confirmation.html` : année footer
- [ ] Google Forms : objet email auto-réponse, date limite mutation, coordonnées éducateurs
- [ ] `images/` : photos si nouvelles équipes

---

## Déploiement GitHub Pages

```bash
git add index.html style.css script.js confirmation.html
git commit -m "feat: mise à jour saison XXXX/XXXX"
git push origin main
# Disponible sur : https://TON_USERNAME.github.io/eprs-inscription/
```
