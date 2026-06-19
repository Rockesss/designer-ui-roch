# Candidature UI Designer — daflon × roch

Page de candidature créative (démonstrateur) pour le poste d'**UI Designer freelance
chez Servier**, via Isalys Digital Lab. Reprend la direction artistique de
[daflon.fr](https://daflon.fr) et détourne ses composants pour présenter le profil de
Roch de Dinechin.

> ⚠️ Page **non officielle**, **non affiliée** à Servier ni à Daflon. Usage de démonstration.

## Structure
```
.
├── index.html          # tout le site (HTML + CSS + JS inline) — header + hero validés
├── img/                # tous les visuels (aucune image hors de ce dossier)
├── netlify.toml        # déploiement statique (publish = ".")
├── CLAUDE.md           # conventions projet
└── PROMPT_CLAUDE_CODE.md  # prompt de développement (sections restantes)
```

## Développer
Ouvre le dossier dans Claude Code et suis `PROMPT_CLAUDE_CODE.md`.

## Déployer sur Netlify
- **Drag & drop** : glisse le dossier sur https://app.netlify.com/drop
- **CLI** : `netlify deploy --prod` (à la racine du dossier)
