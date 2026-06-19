# CLAUDE.md — Candidature créative UI Designer (daflon × roch)

## Nature du projet
Page web de candidature unique qui **imite la direction artistique du site daflon.fr**
(Servier) et en détourne les composants pour présenter Roch de Dinechin comme candidat
au poste d'**UI Designer freelance chez Servier (via Isalys Digital Lab)**.
C'est un **démonstrateur** : l'objet prouve la compétence (savoir concevoir une interface
dans l'identité d'une marque).

## Règles non négociables
- **Un seul fichier `index.html`**, vanilla HTML/CSS/JS, **sans framework ni build**. CSS et JS inline.
- **Images dans `/img`** uniquement. **Zéro data-URI**, zéro image orpheline, chaque `src` ↔ un fichier réel.
- **Mobile-first, zéro scroll horizontal** (tester 360 / 390 / 414 / 768 px : `scrollWidth === clientWidth`).
- **Accessibilité soignée** (c'est la compétence vendue) : landmarks sémantiques, `alt` partout,
  `:focus-visible`, contrastes AA, `prefers-reduced-motion`, navigation clavier complète.
  ⚠️ Ne JAMAIS prétendre à une certification/expertise RGAA. La page est *soignée*, pas *certifiée*.
- **Contenu honnête** (voir PROMPT_CLAUDE_CODE.md, section « Garde-fous ») : Bridor = CDD,
  diplômes sans dates, 4 ans de séniorité (pas 6), pas de superlatif, pas de ton « IA »,
  pas de « n'hésitez pas », seuls les chiffres validés.
- **Précautions marque/pharma** : ne pas reproduire les visuels/textes médicaux de daflon.fr.
  On réutilise le **langage visuel** (palette, mise en page, vague, composants), pas les contenus protégés.
  Aucune allégation santé. **Disclaimer fort et visible dans le footer**.

## Workflow QA (à chaque section)
1. Construire la section dans `index.html`.
2. Capturer en desktop (1440) ET mobile (390) via Playwright/Chromium.
3. Révéler les animations avant capture (`.rv → .in`) ; vérifier l'overflow horizontal.
4. Vérifier que chaque image référencée existe dans `/img` (0 orphelin, 0 data-URI).
5. Itérer **section par section** ; édits chirurgicaux, pas de régénération globale.

## Déploiement
- `netlify.toml` est déjà configuré (`publish = "."`).
- Drag & drop du dossier sur app.netlify.com, **ou** `netlify deploy --prod`.

## État actuel
- ✅ `index.html` contient un **header + hero VALIDÉS** (ne pas les casser).
- ⏳ Sections suivantes à construire (voir PROMPT_CLAUDE_CODE.md).
