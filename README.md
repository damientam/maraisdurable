# maraisdurable.com

Site de l'association **Marais Durable** (loi 1901), hébergé sur GitHub Pages.
Site statique : HTML et CSS uniquement, aucun build, aucune dépendance, aucun cookie.

## Arborescence

```
index.html              accueil (le marais + encart actualité)
le-marais.html          paysages, histoire, protections
faune-flore.html        faune et flore
actualites.html         actualités, dont le dossier éolien (chiffres, frise, fil des nouvelles)
petition.html           texte de la pétition et formulaire de signature  ┐
le-projet.html          le projet éolien, zones, calendrier              ├ rattachées à « Actualités »
nos-arguments.html      les sept arguments sourcés                       ┘
assets/img/             photos (Wikimedia Commons, crédits dans mentions-legales.html#credits) et logo.svg
agir.html               adhérer et agir
documents.html          publications et références
association.html        objet, bureau, méthode
mentions-legales.html
404.html
CNAME                   nom de domaine personnalisé
assets/css/style.css    feuille de style unique
documents/              PDF téléchargeables
```

## Mise en ligne (une seule fois)

1. Créer le dépôt `maraisdurable` sur le compte `damientam`, **public**.
2. Pousser le contenu de ce dossier à la racine de la branche `main`.
3. Dépôt → **Settings** → **Pages** → *Build and deployment* → Source : **Deploy from a branch**,
   branche `main`, dossier `/ (root)`. Enregistrer.
4. **Une fois le DNS configuré (voir plus bas)**, dans **Settings → Pages**, champ *Custom domain* :
   saisir `maraisdurable.com` (GitHub crée alors le fichier `CNAME`). Ne pas le faire avant :
   l'adresse `damientam.github.io/maraisdurable` redirigerait vers un domaine qui ne répond pas encore.
5. Cocher **Enforce HTTPS** une fois le certificat délivré (compter de quelques minutes à 24 h).

## Configuration DNS chez le registrar de maraisdurable.com

| Type | Nom | Valeur |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| AAAA | @ | 2606:50c0:8000::153 |
| AAAA | @ | 2606:50c0:8001::153 |
| AAAA | @ | 2606:50c0:8002::153 |
| AAAA | @ | 2606:50c0:8003::153 |
| CNAME | www | damientam.github.io. |

Vérifier ces adresses dans la documentation GitHub Pages avant de les saisir : elles changent
rarement, mais elles changent.

## Modifier une page

Tout est en HTML lisible. Pour corriger un texte : ouvrir le fichier sur github.com, cliquer sur
le crayon, modifier, enregistrer. Le site se met à jour en une à deux minutes.

L'en-tête et le pied de page sont recopiés dans chaque fichier (pas de gabarit). Une modification
de menu doit donc être reportée dans tous les fichiers HTML (douze à ce jour).

## Activer le formulaire de pétition

Le formulaire se trouve dans `petition.html`. Tant qu'il n'est pas configuré, il affiche un message
invitant à écrire par courriel : le site reste donc utilisable en l'état.

1. Créer un compte sur un service d'acheminement de formulaires. Le formulaire est écrit pour
   **Formspree** (`https://formspree.io`), mais tout service acceptant un `POST` de formulaire
   convient. Pour rester dans l'Union européenne, **Tally** ou **Framaforms** sont de bonnes
   alternatives — dans ce cas, remplacer l'attribut `action` par l'adresse fournie.
2. Créer un formulaire, récupérer son identifiant.
3. Dans `petition.html`, remplacer `VOTRE_IDENTIFIANT` par cet identifiant, dans la ligne :
   `action="https://formspree.io/f/VOTRE_IDENTIFIANT"`.
4. Envoyer une signature de test et vérifier la réception.
5. Indiquer le nom du prestataire et son pays d'hébergement dans `mentions-legales.html`, à la
   ligne « Sous-traitant technique » — c'est une obligation du RGPD.

Le champ caché `_gotcha` est un piège à robots : ne pas le supprimer. Le consentement est recueilli
par une case à cocher obligatoire, comme l'exige le RGPD ; ne pas la retirer non plus.

**Compteur de signatures.** Aucun compteur n'est affiché : un site statique ne peut pas en tenir un
sans service externe. Si vous y tenez, le plus simple est de mettre à jour à la main, une fois par
semaine, une phrase du type « 214 signatures au 12 octobre ». Un chiffre daté et exact vaut mieux
qu'un compteur automatique.

## Avant la mise en ligne — à faire

- [ ] Créer l'adresse `contact@maraisdurable.com` (ou remplacer partout par une adresse existante).
- [ ] Déposer les PDF dans `documents/` sous les noms attendus par `documents.html` :
      `tract-general.pdf`, `tract-la-laigne.pdf`, `lettre-conseil-municipal.pdf`,
      `lettre-prefet.pdf`.
- [ ] Compléter la date de la réunion publique dans `le-projet.html` et `index.html`.
- [ ] Vérifier le numéro de récépissé de déclaration en préfecture et l'ajouter aux mentions
      légales une fois connu.
- [ ] Configurer le formulaire de pétition (voir ci-dessus) et faire un envoi de test.
- [ ] Relire `nos-arguments.html` : c'est la page qui sera contestée, chaque chiffre doit être
      défendable.

## Notes

- Aucune image du promoteur n'est reproduite sur le site. Si vous souhaitez publier un extrait de
  ses diapositives, prenez un avis préalable : la reproduction d'un document d'entreprise, même à
  des fins critiques, n'est pas sans risque.
- Le site ne collecte rien : pas de formulaire, pas d'analytics, pas de cookie. C'est volontaire,
  cela simplifie les obligations RGPD et cela se dit dans les mentions légales.
