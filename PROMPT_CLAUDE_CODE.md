# Prompt Claude Code — Candidature UI Designer « façon daflon.fr »

Copie-colle ce prompt dans Claude Code, à la racine du dossier `candidature-roch-daflon/`
(qui contient déjà `index.html`, `img/`, `netlify.toml`, `CLAUDE.md`).

---

## 0. Mission

Tu développes une **page de candidature unique** qui **imite la direction artistique du
site daflon.fr** (Servier) et **détourne ses composants** pour présenter **Roch de Dinechin**
comme candidat au poste d'**UI Designer freelance chez Servier**, via Isalys Digital Lab.
C'est un **démonstrateur** : l'objet lui-même prouve la compétence (concevoir une interface
dans l'identité d'une marque). Cible finale : déploiement **Netlify**.

Méthode : **français, tutoiement, itératif, une section à la fois, QA visuelle (captures
desktop + mobile) avant de passer à la suivante.** Édits chirurgicaux, jamais de régénération
globale. Tu ne touches pas au header/hero déjà validés sauf demande explicite.

---

## 1. Ce que tu reçois (base validée)

- `index.html` : contient un **header + hero VALIDÉS** (ne pas les casser). Le marqueur
  `<!-- SECTIONS À CONSTRUIRE ICI -->` indique où ajouter la suite. Les tokens CSS, le kit
  de titre de section (`.sec-title` + `.wave-rule`) et le composant `.pill` sont déjà définis.
- `img/` : tous les visuels. Rôles :
  | Fichier | Usage |
  |---|---|
  | `roch-portrait.jpg` | photo (hero ✅ + section Profil) |
  | `phone-fact-cutout.png` | téléphone FACT détouré (hero ✅) |
  | `mockup-fact-accueil.jpg`, `mockup-fact-livreurl.jpg`, `envato-labs-image-edit.png` | expérience **FACT / MBC** |
  | `Laptop-02.jpg`, `Computer-Screen-Mockup--_3_.jpg`, `Bridor---mockup---form.jpg` | expérience **Bridor** |
  | `Mobile-kefaire-1-Accueil.jpg`, `Mobile-kefaire-crit-3.jpg`, `Mobile-kefaire-1-Reco-1.jpg` | projet **Kefaire** |
  | `image-roch.jpg` | original (au cas où un recadrage est à refaire) |
  | `phone-kefaire-cutout.png` | écran Kefaire détouré (dispo si besoin) |

Si tu dois préparer un nouvel asset (détourage, recadrage), fais-le en Python
(`rembg` + `Pillow`) et écris le résultat dans `img/`.

---

## 2. Direction artistique (tokens exacts, extraits du vrai daflon.fr)

**Palette** (déjà en variables CSS dans `index.html`) :
- `--navy:#1D2340` — texte, logo, fond du hero, illustrations
- `--teal:#46BBD4` — CTA pilule, accents, dots ; hover `--teal-d:#34A6BF`
- `--lavender:#E7EFFF` — fonds de section alternés, cartes
- `--gold:#FFCF24` — **la vague signature** sous les titres + badges de catégorie
- `--white:#FFFFFF`, `--line:#CFD8E9`, `--ink-soft:#4A5170`

**Typo** : **Barlow** (Google Fonts, déjà chargée), 400/500/600/700. H2 ≈ 38px/700,
H3 ≈ 18px/700, body 16px/400. *Caveat* uniquement pour le micro-accent manuscrit (déjà au hero).

**Composants signature à respecter partout :**
- **CTA = pilule** : `.pill` (fond teal, texte navy, radius 52px). Variante secondaire possible
  (contour navy sur fond clair) si besoin de hiérarchie.
- **Vague jaune** (`.wave-rule`) **sous chaque titre de section** (titre `.sec-title` centré).
- **Cartes lavande** : fond `--lavender`, grand border-radius (~24px), illustration/visuel
  qui **déborde en haut** de la carte, titre navy.
- **Sections info alternées** : fond blanc / fond lavande en alternance ; image d'un côté,
  texte + CTA de l'autre, sens inversé une section sur deux.
- **Carte « projet »** (= carte « article » daflon) : visuel en haut (coins arrondis),
  **badge catégorie jaune** (pilule, texte navy), titre navy, CTA pilule teal en bas.
- Header sticky, ombre douce au scroll (déjà en place).

---

## 3. Garde-fous HONNÊTETÉ (non négociable — appliquer à chaque texte)

- **Bridor = CDD**, jamais CDI.
- **Diplômes : nom + établissement uniquement, JAMAIS de dates.**
- **Séniorité = 4 ans.** La fiche demande 6 ; on ne ment pas. On s'appuie sur les ancrages
  réels (50+ maquettes, DA multi-marques, 18 mois de prod IA, refonte BO+Front).
- **Profil = UI + PO**, mais la fiche veut un **UI pur** : mets en avant l'UI / interface /
  brand / design system ; garde le PO en **second plan** (collaboration avec les PO, pilotage
  produit en appui). Ne revendique pas la conception du parcours client comme cœur de métier.
- **RGAA = « bonnes pratiques d'accessibilité courantes » + « montée en compétences sur le
  référentiel complet ».** JAMAIS d'expertise/certification RGAA revendiquée.
- **Ton** : phrases courtes, factuelles, verbes d'action. **Pas de superlatif** (« expert »,
  « passionné », « parfaitement »), **pas de langage qui sonne IA**, pas d'emoji décoratif,
  pas de « n'hésitez pas à me contacter ». Vouvoiement quand on s'adresse au lecteur.
- **Aucun chiffre inventé.** Chiffres validés autorisés uniquement : **+120 %** (téléchargements
  catalogue), **+117 %** (formulaires soumis), **+131 %** (trafic SEO France), **50+** maquettes
  Figma, **5** langues, **350+** produits, **~350** œuvres/concours (Netspring),
  **8** projets clients en freelance, **18 mois** de production IA, **4 ans** d'expérience.
  En cas de doute : ne pas chiffrer.

---

## 4. Précautions marque / pharma

- **Disclaimer fort et visible dans le footer** : page de candidature créative,
  **non officielle, non affiliée à Servier ni à Daflon**, à usage de démonstration.
- **Ne reproduis pas** les visuels, illustrations, photos ou textes médicaux/réglementaires
  de daflon.fr. On réutilise le **langage visuel** (palette, mise en page, vague, composants),
  **pas** les contenus protégés. **Aucune allégation santé**, aucune mention de médicament.
- Le wordmark `roch®` est **recréé** (texte Barlow 800 + ®), il ne réutilise aucun asset daflon.

---

## 5. Structure + contenu, section par section

Ordre des sections (après le hero) :
**3 piliers → Profil → Expériences (FACT, Bridor) → Projet (Kefaire) → Compétences → Contact → Footer.**

### 5.1 — Section « 3 piliers » (cartes lavande + vague jaune)
Titre : **« Trois piliers pour ce poste »** + vague jaune.
Trois cartes lavande, chacune avec une **illustration SVG navy line-art recréée** (style daflon :
trait épais, monochrome navy) qui déborde en haut de la carte, un titre H3 navy et 2–3 lignes.

1. **Design systems multi-marques**
   Composants, variants, auto-layout, bibliothèques partagées et handoff. Déclinaison du ton
   visuel marque par marque : 8 projets clients menés en parallèle en freelance, plus un
   environnement industriel multilingue (Bridor, 5 langues).
   *Illustration : grille de composants / blocs imbriqués.*

2. **Accessibilité & qualité de production**
   Bonnes pratiques courantes intégrées dès la conception : contraste, hiérarchie sémantique,
   navigation clavier, alternatives textuelles. Montée en compétences en cours sur le
   référentiel RGAA complet. *(Honnête — ne pas survendre.)*
   *Illustration : œil / cible de contraste / coche.*

3. **IA appliquée au design**
   Claude Code en pratique quotidienne depuis 18 mois pour produire interfaces et composants,
   prompt engineering pour générer des variations, veille active sur Figma AI.
   *Illustration : curseur + étincelles (sparkles).*

### 5.2 — Section « Profil » (`id="profil"`)
Bloc avec **photo** (`roch-portrait.jpg`) + texte de positionnement. Titre **« Le profil »** + vague jaune.
- Accroche factuelle (≈ 3 lignes) : UI Designer & Product Owner, 4 ans d'expérience, du
  back-office au front, en environnement industriel et multi-marques. Production design
  accélérée par l'IA.
- **Formation** (sans dates) : *Master Expert en Stratégie Digitale — Digital Campus Rennes* ;
  *Licence de Droit — Université Rennes 1.*
- **Langues** : Français natif · Anglais professionnel C1 (TOEIC 865) · Allemand notions.
  *(Présente ça proprement, p.ex. en petites étiquettes / liste sobre.)*

### 5.3 — Expérience #1 (section alternée image+texte+CTA) — `id="experiences"`
**Mobility by Colas / Aximum (Groupe Colas)** — UI Designer & Product Owner — Décembre 2025 → Mai 2026.
Visuels : `mockup-fact-accueil.jpg`, `mockup-fact-livreurl.jpg`, `envato-labs-image-edit.png`
(galerie ou empilement façon daflon). Badge/eyebrow : « Expérience · Mobility by Colas ».
Contenu (UI d'abord, PO en appui) :
- Refonte UI complète du plugin métier **FACT** — **Back-Office** (admin) et **Front-end**
  (terrain) : nouvelle hiérarchie visuelle, charte, composants Figma, écrans haute fidélité,
  prototype interactif.
- **Système de design tokens** (couleurs, typo, espacements) + bibliothèque de composants
  Figma exploitable par l'équipe dev.
- **Production IA-assistée** (vibe coding avec Claude Code) : maquettes Figma → composants
  React et HTML/CSS opérationnels, cycle design-to-prod accéléré.
- Dashboard interne de remontée des erreurs pour des équipes terrain non techniques.
- *(En appui)* spécification fonctionnelle, animation des sprints (2 semaines), recette Squash TM.
CTA : **« Voir le projet »** (ouvre le popup contact, ou ancre interne — pas de lien externe inventé).

### 5.4 — Expérience #2 (section alternée, sens inversé)
**Bridor (Groupe Le Duff) — CDD** — Chef de projets digitaux & Conception UI — Août 2022 → Septembre 2024.
Visuels : `Laptop-02.jpg` (catalogue), `Computer-Screen-Mockup--_3_.jpg` (e-commerce),
`Bridor---mockup---form.jpg` (formulaire). Badge/eyebrow : « Expérience · Bridor — CDD ».
Contenu :
- **50+ maquettes Figma** sur le portefeuille digital : pages produits, formulaires, parcours,
  écrans back-office, prototypage avant validation des directions métier.
- **Refonte du Catalogue Digital** (PDF généré dynamiquement depuis SAP) : conception graphique,
  choix typographiques pour 5 langues, déclinaison de la charte Bridor → **+120 % de téléchargements**.
- **Pilotage du site Bridor.com** sous SAP Commerce / Hybris (5 langues, 350+ produits) :
  conception des écrans, briefs visuels pour l'éditeur, recette → **+117 % de formulaires soumis**,
  **+131 % de trafic SEO France**.
- Outils internes pour les équipes commerciales internationales (supports multilingues).
CTA : **« Voir le projet »** (même règle que ci-dessus).

> (Le stage Bridor — Mars→Août 2022 — peut être évoqué en une ligne de timeline, ou omis. Au choix, sobre.)

### 5.5 — Section « Projet » (`id="projet"`) — Kefaire
**Une seule** carte/section projet (on ne met pas les projets sans visuels). Titre **« Un projet en vedette »** + vague jaune.
**Kefaire — Progressive Web App de découverte d'activités à Paris.**
Badge catégorie jaune : « Progressive Web App · Projet personnel ».
Visuels (les 3 écrans, façon trio mobile ou mini-galerie) : `Mobile-kefaire-1-Accueil.jpg`,
`Mobile-kefaire-crit-3.jpg`, `Mobile-kefaire-1-Reco-1.jpg`.
Texte : conception produit complète (design system, écrans, prototype Figma), développement
IA-assisté avec Claude Code, déployée en production.
CTA : **« Voir le projet »** (ancre/popup — pas d'URL inventée ; si Roch fournit le lien réel, l'utiliser).

### 5.6 — Section « Compétences & outils »
Présentation sobre (étiquettes / petites colonnes), pas de barres de niveau bidon. Catégories :
- **Design** : Figma (composants, variants, auto-layout, prototypage), Adobe Creative Cloud, Whimsical.
- **IA design** : Claude Code (prod UI quotidienne, 18 mois), prompt engineering, veille Figma AI.
- **Dev & intégration** : HTML/CSS/JS, React, Vite, Tailwind CSS, Supabase, WordPress, Git/GitHub.
- **Collaboration & gestion de projet** : Azure DevOps, Jira, Confluence, Squash TM, Notion, Slack.
- **Web & analytics** : GA4, Google Search Console, GSAP, ChartJS.

### 5.7 — Section « Contact » (`id="contact"`) — détourne le localisateur de pharmacie
Titre **« Prenons rendez-vous »** + vague jaune. Le bloc « recherche pharmacie » de daflon
devient un **bloc contact** sur fond lavande :
- Disponibilité : **dès le 24 août 2026**, Paris (présentiel partiel).
- Boutons : **Email** (`mailto:`) et **LinkedIn**. *(Demande à Roch l'adresse e-mail et l'URL
  LinkedIn exactes avant de les câbler ; ne les invente pas — mets des `data-*` à compléter
  si tu ne les as pas.)*
- Ce bloc et le bouton header « Prenons rendez-vous » **ouvrent le même popup** (voir §6).

### 5.8 — Footer (façon Servier)
Colonnes de liens (rendus **inertes** — `preventDefault`), wordmark `roch®`, contact, et surtout :
- **Disclaimer visible** : « Page de candidature créative, non officielle et non affiliée à
  Servier ni à Daflon. Réalisée à des fins de démonstration. »
- Mention « Conçu et développé par Roch de Dinechin · 2026 ».

---

## 6. Popup « Prenons rendez-vous » (réutilisable)

- Overlay + carte centrée ; contenu : court texte + bouton **Email (mailto)** + bouton **LinkedIn**.
- Fermeture par **X**, **clic sur l'overlay**, **touche Échap**. Focus piégé dans le popup quand ouvert,
  focus rendu au déclencheur à la fermeture. `aria-modal="true"`, `role="dialog"`.
- Tous les déclencheurs portent `data-open-contact` (déjà utilisé par le header).
- **Placer le markup du popup avant la balise `<script>`** finale.

---

## 7. Contraintes techniques

- **Un seul `index.html`**, vanilla, **sans build**. CSS et JS **inline**.
- **Images dans `/img`** ; **0 data-URI**, **0 orphelin** (chaque `src` ↔ un fichier ; chaque
  fichier utilisé). Les illustrations des piliers et la vague sont du **SVG inline** (autorisé,
  ce n'est pas un data-URI).
- **Mobile-first, zéro scroll horizontal.** Attention aux éléments larges / `transform` :
  clipper avec `overflow:hidden` sur le conteneur. Tester **360 / 390 / 414 / 768 px**
  (`scrollWidth === clientWidth`).
- **Navigation interne** : smooth-scroll JS sur `a[href^="#"]` (déjà en place — étends-le aux
  nouvelles ancres) ; liens factices **inertes** ; `scroll-margin-top` sur les sections cibles
  pour compenser le header sticky.
- **Accessibilité (clé du poste)** : `header`/`nav`/`main`/`section`/`footer` sémantiques,
  `alt` descriptif partout, `:focus-visible` visible, contrastes **AA**, `prefers-reduced-motion`
  respecté (déjà sur le hero — applique aux nouvelles animations), navigation clavier complète,
  hiérarchie de titres correcte (un seul `h1`, puis `h2`/`h3`).
- **Menu mobile** : le burger du header (déjà présent, `id="burger"`) doit ouvrir/fermer un
  menu de navigation accessible (à implémenter : `aria-expanded`, fermeture clavier).
- Reveals au scroll discrets (IntersectionObserver, classe `.rv` → `.in`), désactivés en
  `prefers-reduced-motion`. **Pas de surenchère d'animation** (ça fait « IA-généré »).

---

## 8. Workflow QA (à chaque section)

1. Construire la section, puis **capturer desktop (1440) ET mobile (390)** via Playwright/Chromium.
2. **Révéler les reveals avant capture** (forcer `.rv→.in`), pour voir le rendu final.
3. Vérifier `scrollWidth === clientWidth` aux 4 largeurs ; corriger tout débordement.
4. Vérifier l'intégrité images : chaque `src` pointe vers un fichier de `img/`, aucun orphelin,
   aucun data-URI.
5. Montrer la capture, valider, **puis** passer à la section suivante. Édits chirurgicaux.

Avant livraison finale : passe complète (overflow, focus clavier, contraste, `alt`,
`prefers-reduced-motion`, 0 lien factice actif, 0 data-URI).

---

## 9. Déploiement Netlify

`netlify.toml` est déjà prêt (`publish = "."`).
- **Le plus simple** : glisser le dossier sur https://app.netlify.com/drop.
- **CLI** : `npm i -g netlify-cli` puis, à la racine : `netlify deploy --prod`.
- Après déploiement : ré-ouvrir l'URL en mobile réel, revérifier overflow + focus + popup.

---

## 10. Démarre maintenant

1. Confirme en une phrase ta compréhension + l'ordre des sections.
2. Demande à Roch les **infos contact manquantes** (email, URL LinkedIn) — ne les invente pas.
3. Construis la **section « 3 piliers »** d'abord (illustrations SVG navy comprises), QA desktop
   + mobile, montre, valide — puis enchaîne section par section dans l'ordre du §5.
