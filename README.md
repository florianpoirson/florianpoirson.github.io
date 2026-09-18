# severinewilliams.com

Site vitrine de Dr Séverine Williams — formation linguistique et interculturelle.
Site statique, sans dépendance ni étape de compilation. Hébergement prévu : GitHub Pages.

## Contenu du dépôt

| Fichier | Rôle |
|---|---|
| `index.html` | Version française, servie sur `/` |
| `en/index.html` | Version anglaise, servie sur `/en/` |
| `assets/severine-williams.jpg` | Portrait, également utilisé comme image de partage |
| `404.html` | Page d'erreur, reprise automatiquement par GitHub Pages |
| `CNAME` | Domaine personnalisé — **ne pas supprimer** |
| `robots.txt` | Autorise l'indexation, déclare le plan de site |
| `sitemap.xml` | Déclare les deux URL et leurs équivalences de langue |
| `.nojekyll` | Désactive le traitement Jekyll de GitHub |

Chaque page contient un bloc de données structurées JSON-LD (schema.org) qui décrit
Séverine Williams, ses diplômes, ses distinctions, ses formations et ses sources publiques.
C'est ce bloc que lisent en priorité les moteurs de recherche et les moteurs IA.
**Les deux pages partagent les mêmes identifiants `@id`**, afin que les moteurs considèrent
qu'il s'agit d'une seule et même personne décrite en deux langues.

## Mise en ligne

1. Créer un dépôt **public** sur GitHub, par exemple `severinewilliams.com`.
   GitHub Pages ne fonctionne sur les dépôts privés qu'avec un compte payant.
2. Téléverser le contenu de ce dossier **à la racine** du dépôt (pas dans un sous-dossier).
   Via l'interface web : *Add file* → *Upload files* → glisser tous les fichiers.
3. *Settings* → *Pages* → **Source : Deploy from a branch** → branche `main`, dossier `/ (root)` → *Save*.
4. Toujours dans *Settings* → *Pages*, champ **Custom domain** : saisir `www.severinewilliams.com`,
   puis *Save*. Le fichier `CNAME` doit rester présent.
5. Attendre la vérification du domaine, puis cocher **Enforce HTTPS**.
   Le certificat met de quelques minutes à une heure à être délivré.

## Configuration DNS

Chez le registrar du domaine `severinewilliams.com` :

**Sous-domaine www** — un enregistrement `CNAME` :

    www    CNAME    <votre-identifiant-github>.github.io.

**Domaine nu** (pour que `severinewilliams.com` redirige vers `www`) — quatre enregistrements `A` :

    @    A    185.199.108.153
    @    A    185.199.109.153
    @    A    185.199.110.153
    @    A    185.199.111.153

Et, si le registrar accepte l'IPv6, quatre enregistrements `AAAA` :

    @    AAAA    2606:50c0:8000::153
    @    AAAA    2606:50c0:8001::153
    @    AAAA    2606:50c0:8002::153
    @    AAAA    2606:50c0:8003::153

Ces adresses sont celles publiées par GitHub ; **les vérifier dans la documentation
GitHub Pages avant de les saisir**, elles ont déjà changé par le passé.
La propagation DNS prend de quelques minutes à 48 heures.

## Après la mise en ligne

- Déclarer le site dans **Google Search Console** et **Bing Webmaster Tools**,
  puis y soumettre `https://www.severinewilliams.com/sitemap.xml`.
  Bing alimente une partie des moteurs IA, il ne faut pas l'oublier.
- Vérifier le balisage sur `https://validator.schema.org/` et
  `https://search.google.com/test/rich-results`.
- Ajouter l'adresse du site sur les deux profils LinkedIn : c'est le lien entrant
  le plus utile pour rattacher le site à l'identité professionnelle de Séverine.

## Points à compléter avant toute mise en ligne publique

Les emplacements concernés apparaissent **en rouge** dans le pied de page des deux pages
(chercher `class="todo"` dans le code) :

- forme juridique, SIREN/SIRET, numéro de TVA, adresse du siège ;
- hébergeur : raison sociale, adresse et téléphone.
  Pour GitHub Pages : *GitHub, Inc., 88 Colin P. Kelly Jr. Street, San Francisco, CA 94107, États-Unis* ;
- numéro de déclaration d'activité de prestataire de formation —
  **si l'activité n'est pas déclarée, supprimer entièrement le paragraphe** plutôt que le laisser vide ;
- médiateur de la consommation : l'adhésion est obligatoire dès qu'il y a des clients particuliers ;
- modalités de paiement et délai d'annulation dans les conditions générales ;
- liste des sous-traitants techniques dans la politique de confidentialité.

Deux liens sont volontairement absents faute de source vérifiée : les arrêtés d'admission
à l'agrégation et au CAPES. Les ajouter depuis Légifrance ou le Bulletin officiel,
dans la section « Parcours », au même format que les autres sources.

## Modifier le site

Les deux pages sont autonomes : toute correction de fond doit être reportée
dans `index.html` **et** dans `en/index.html`, y compris dans le bloc JSON-LD.

## Formulaire de contact

Le formulaire ouvre le logiciel de messagerie du visiteur avec un message pré-rempli.
C'est suffisant pour démarrer, mais cela convertit mal : de nombreux visiteurs,
sur mobile notamment, n'ont pas de client mail configuré.
Pour un envoi direct, créer un compte sur un service comme Formspree ou Web3Forms
et remplacer le gestionnaire `submit` en bas de page par l'action du formulaire fournie
par le service. Aucune autre modification n'est nécessaire.
