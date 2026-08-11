# Systems Mentor

Un skill d'IA qui t'apprend l'informatique **par premiers principes**, au lieu de te débiter des définitions.

Il ne répond pas à ta question. Il cherche le concept manquant en dessous, te le fait **prédire avant de révéler**, te fait ouvrir le capot sur de vrais outils (`tcpdump`, `strace`, `/proc`, `openssl`), et refuse de te flatter : un concept ne compte comme acquis que si tu peux **l'expliquer, le débugger et l'enseigner**.

Il garde une carte de ta compréhension qui grandit session après session.

---

## Pourquoi

Les agents écrivent le code. Le vrai métier remonte d'un cran : comprendre les systèmes qu'on déploie.

Un tuteur IA classique te caresse dans le sens du poil et gonfle ton niveau. Celui-ci fait l'inverse. Il est conçu pour **trouver tes trous et les combler**, pas pour te rassurer.

## Ce qu'il fait

| | |
|---|---|
| **Enseigne par systèmes** | Jamais "aujourd'hui, TCP". Toujours "ton navigateur vient de se connecter à ton API" → les concepts émergent du réel. |
| **Socratique** | Il te fait prédire, te laisse te tromper, puis explique pourquoi. |
| **Maîtrise active** | Familiarité ≠ compréhension. Le niveau se prouve, il ne se déclare pas. |
| **Mémoire long terme** | Un graphe de connaissance suit tes niveaux 0-5, tes prérequis et tes gaps dans le temps. |
| **Hands-on obligatoire** | Vrais paquets, vraies commandes, vrai code. Pas de jouet quand le réel est accessible. |
| **Sources de référence** | Doc officielle, RFC, POSIX, man pages. Pas de tuto bas de gamme. |

## Installation (Claude Code)

1. Copie `SKILL.md` dans `~/.claude/skills/mentor/SKILL.md` :
   ```bash
   mkdir -p ~/.claude/skills/mentor
   curl -o ~/.claude/skills/mentor/SKILL.md \
     https://raw.githubusercontent.com/moombba/systems-mentor/main/SKILL.md
   ```
2. Ouvre le fichier et **personnalise le bloc « Qui est l'apprenant »** avec ton profil (ton niveau, ce que tu connais au niveau API vs mécanisme, ce que tu veux comprendre en dessous).
3. Lance `/mentor`, ou pose une question système : *"comment marche X"*, *"pourquoi Y"*.

Le skill crée et maintient son dossier de travail dans `~/mentor/` (graphe de connaissance, journal, archives de cours).

> Compatible avec tout agent capable de lire un fichier de skill et d'exécuter des commandes shell locales. Adapte le chemin d'installation à ton outil.

## Comment ça marche

À chaque session, le mentor :

1. **Lit** ton graphe de connaissance pour savoir où tu en es.
2. **Enseigne en direct** dans le chat, une idée à la fois, en te faisant prédire avant de révéler.
3. **Te fait manipuler le réel** (une commande, une capture, une observation) pour ancrer le concept.
4. **Met à jour** ta maîtrise, ton journal, et archive le cours.

Un concept reste plafonné à "en cours" tant que tu ne l'as pas prouvé. Pas de niveau offert.

## Fichiers générés

```
~/mentor/
├── KNOWLEDGE_GRAPH.md   carte de ta compréhension (niveaux 0-5, prérequis, gaps)
├── LEARNING_LOG.md      journal chronologique des leçons
└── LESSONS/             archive du cours complet de chaque session
```

## Personnalisation

Le seul bloc à éditer est **« Qui est l'apprenant — À PERSONNALISER »** dans `SKILL.md`. Plus ton profil est précis, mieux le mentor calibre et évite de réexpliquer ce que tu sais déjà.

## Licence

MIT. Prends, utilise, modifie, partage.

---

Construit par **Quentin Claudet**. Je conçois et gouverne des systèmes IA agentiques en production, et je forme les équipes tech à faire pareil.
GitHub : [@moombba](https://github.com/moombba)
