# Second Brain Template

Un système de second cerveau personnel, propulsé par Claude Code et Obsidian.

Inspiré du concept de LLM Knowledge Base d'Andrej Karpathy — au lieu d'utiliser l'IA pour écrire du code, on l'utilise pour construire et maintenir une base de connaissance personnelle qui grandit avec toi.

---

## Le principe

Tu consommes du contenu (vidéos, articles, podcasts, notes) → tu déposes dans `raw/` → Claude compile, connecte, et construit ton wiki automatiquement.

Au fil du temps, le wiki révèle des connexions entre tes idées que toi-même tu ne voyais pas encore.

---

## Ce qu'il te faut

- [Claude Code](https://claude.ai/download) — l'agent IA qui maintient le wiki
- [Obsidian](https://obsidian.md) — pour visualiser et naviguer dans le vault

---

## Installation

**1. Clone ce repo**
```bash
git clone https://github.com/yodapalma/second-brain-template.git mon-wiki
```

**2. Ouvre Obsidian**
- "Open folder as vault" → sélectionne le dossier `mon-wiki/`
- Active le Graph View dans le panneau gauche

**3. Adapte le schema**
Ouvre `schema.md` et remplace les domaines génériques par les tiens :
- `[domaine-1]/`, `[domaine-2]/`... → tes vrais centres d'intérêt
- Crée les dossiers correspondants dans `raw/` et `wiki/`

**4. Ouvre Claude Code**
- Pointe sur le dossier `mon-wiki/`
- Lance ta première session :
> *"Lis le schema.md et confirme que tu as compris ta mission"*

---

## Structure du vault

```
mon-wiki/
├── schema.md          ← le cerveau du système (à adapter)
├── index.md           ← catalogue auto-maintenu
├── log.md             ← historique des opérations
│
├── raw/               ← tu déposes ici
│   ├── brut/          ← quand tu sais pas où mettre → ici
│   ├── reflexions/    ← tes pensées personnelles
│   ├── projets/
│   └── [tes domaines]/
│
├── wiki/              ← Claude compile ici
│   ├── _liens/        ← connexions inter-domaines
│   └── [tes domaines]/
│
├── projets/           ← un dossier par projet actif
├── journal/           ← quotidien + bilans
│   ├── quotidien/
│   └── bilans/
└── archive/           ← tout ce qui est traité ou terminé
```

---

## Les commandes du quotidien

| Commande | Ce que ça fait |
|---|---|
| `ingest raw/[fichier]` | Compile une source dans le wiki |
| `ingest raw/brut/` | Trie et compile les pensées en vrac |
| `query : [question]` | Pose une question à ton wiki |
| `journal — [ce que t'as fait]` | Écrit dans le journal du jour |
| `bilan [projet]` | Résume l'avancée d'un projet |
| `lint` | Audit complet du wiki |
| `archive [projet]` | Archive un projet terminé |

---

## Au quotidien

| Moment | Action |
|---|---|
| Tu tombes sur quelque chose | Copie dans `raw/` → `ingest` |
| Tu sais pas où mettre | `raw/brut/` → Claude trie |
| T'as une pensée personnelle | `raw/reflexions/` |
| Fin de journée | `journal —` |
| 1x par semaine | `lint` |

---

## Ce que Claude fait automatiquement

- Crée les pages wiki avec date de création et date de mise à jour
- Ajoute des backlinks entre toutes les pages liées
- Crée des pages dans `_liens/` quand une idée connecte plusieurs domaines
- Déplace les sources traitées dans `archive/`
- Met à jour `index.md` et `log.md` à chaque opération
- Propose un nouveau dossier si 3+ sources émergent sur un thème non couvert

---

Made with 🤍 by [@yodapalma](https://github.com/yodapalma)
