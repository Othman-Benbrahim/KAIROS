# KAIROS — Intégration des skills

KAIROS orchestre quatre skills selon des interfaces précises.
Cette fiche spécifie, pour chaque skill, le moment d'invocation, les entrées
transmises, les sorties attendues, et les règles de délégation.

---

## NEXUS-ARCHÊ

**Rôle dans KAIROS** : vocabulaire structurel — photographie les états T0 et Trés.

### Invocations

| Phase | Moment | Entrée transmise | Sortie attendue |
|---|---|---|---|
| Phase 1 | T0 — état initial | Description de la situation initiale | Constellation 3 cartes + chaîne STÈLE |
| Phase 4 | Trés — état résolu | Description de l'état après transformation | Constellation 3 cartes + chaîne STÈLE |
| Réversibilité | Delta | Toutes les constellations T0 archivées | Tableau delta (persistance / dissolution / émergence) |

### Mode utilisé

Toujours **Mode 3** : Ce qui tient / Ce qui bouge / Ce qui manque.

### Protocole de rigueur (obligatoire à chaque invocation)

1. Ancrage observable : une observation concrète par carte
2. Test d'anti-résonance : qu'est-ce qui contredit chaque carte ?
3. Énoncé structurel de tension : la relation entre les 3 cartes en termes structurels

Aucun tirage NEXUS-ARCHÊ dans KAIROS n'est valide sans ces trois étapes.

### Critère de validité pour KAIROS

La résolution fermée est valide seulement si Trés ≠ T0 (au moins une carte différente).
Si la constellation Trés est identique à T0 → déplacement structurel nul → retour Phase 3.

### Ce que KAIROS ne fait pas

KAIROS n'utilise pas le Mode 1 ni le Mode 2 de NEXUS-ARCHÊ.
KAIROS n'invoque pas NEXUS-ARCHÊ pour des lectures symboliques libres — seulement
pour des instantanés d'état dans le protocole.

---

## LÉR-NARRATIF

**Rôle dans KAIROS** : grammaire sémantique — parse, transforme, ancre.

### Invocations

| Phase | Moment | Opérateurs actifs | Entrée | Sortie |
|---|---|---|---|---|
| Phase 2 | Parsing | `META` + `RESONE` | Récit brut | Phrase dominante + carte de tension |
| Phase 4A | Transformation | `TRANSDUIT` + `SIGNIFIE` | Résolution fermée candidate | Phrase réécrite + ancrage |
| Phase 4B | Bifurcation | `POLYLOGUE` | Deux branches candidates | POLYLOGUE ouvert, branches formulées |

### Mode auto-détecté

| Grain | Mode dominant |
|---|---|
| Long + personnel | A ou C |
| Moyen + collectif | B ou C |
| Ambigu | C — traiter A en premier |

### Contrainte absolue sur TRANSDUIT

La phrase réécrite ne falsifie pas la tension initiale.
Critère de test : la tension d'origine est reconnaissable dans la phrase réécrite,
mais n'a plus le même statut. Si ce test échoue → reformuler jusqu'à satisfaction.

### Ce que KAIROS ne fait pas

KAIROS n'invoque pas LÉR-NARRATIF pour des analyses stratégiques autonomes (Mode B pur)
en dehors du pipeline de résolution. Si un usage Mode B pur est souhaité → utiliser
LÉR-NARRATIF directement, pas via KAIROS.

KAIROS ne déclenche pas le Mode CRC-R interne de LÉR-NARRATIF — il utilise CRC-RÉCURSIF
directement pour la couche dynamique.

---

## CRC-RÉCURSIF

**Rôle dans KAIROS** : moteur de transformation + mémoire STÈLE inter-états.

### Invocation

| Phase | Entrée | Sortie |
|---|---|---|
| Phase 3 | Phrase dominante + carte de tension (Phase 2) | Cristallisation / Bifurcation / Suspension + signature STÈLE |

### Configuration selon le grain

**Grain moyen :**
- Étape 0B (démarrage neutre) sauf si journal fourni
- 3 à 5 cycles
- Seuil de cristallisation standard (≥ 80% / 2 cycles)
- Arrêt standard si cycles épuisés sans état stable

**Grain long :**
- Étape 0A si journal fourni (reconstruction depuis mémoire)
- Étape 0B si première session
- Variable (7 max par session)
- Seuil de cristallisation élevé (pattern stable sur N arcs, pas N cycles)
- Journal actif — entrée produite en fin de session

### STÈLE CRC-R (usage exclusif dans KAIROS)

KAIROS utilise le modèle STÈLE **interne à CRC-R**, plus élaboré que le skill
STÈLE standalone.

Le skill STÈLE standalone n'est **pas** invoqué par KAIROS.

Le modèle STÈLE de CRC-R gère :
- La compression des états T0, Tcrise, Trés
- La signature de session (8-12 glyphes)
- Les marqueurs d'état (`◊` `↻` `Ø`)
- L'opérateur généalogique `⊸`
- La lecture des entrées passées du journal

Spécifications complètes : `references/stele-kairos.md`

### Ce que KAIROS ne fait pas

KAIROS ne modifie pas les règles internes de CRC-R (seuils, passes, règles de
récursion). Il configure les paramètres d'entrée et lit les sorties.

---

## MIROIR-INTÉGRAL

**Rôle dans KAIROS** : validation de la transformation du sujet — couche conditionnelle.

### Conditions d'activation

Toutes ces conditions doivent être réunies :
- Récit personnel (Mode A ou C)
- Grain long
- Résolution fermée ou ouverte atteinte (pas de suspension)
- La résolution candidate implique une transformation identitaire lisible

Si l'une des conditions manque → couche non activée, session continue sans elle.

### Invocation

| Entrée transmise | Sortie attendue |
|---|---|
| Résolution candidate + phrase réécrite + archétypes actifs | Verdict transformation (documentée / insuffisante / surface) |

### Couches Miroir invoquées dans ce contexte

KAIROS n'invoque pas l'intégralité du protocole Miroir Intégral (6 couches complètes).
Il cible les quatre couches les plus pertinentes pour valider une résolution :

| Couche | Question posée | Pertinence pour KAIROS |
|---|---|---|
| IFS (Schwartz) | Quelles parts internes résistent à cette résolution ? | Détecter les résistances cachées |
| Identité narrative (McAdams) | S'inscrit-elle dans la trajectoire identitaire réelle ? | Cohérence avec le récit de soi |
| Cohérence thérapeutique (Ecker) | Cohérente avec le schéma sous-jacent ? | Transformation ou adaptation de surface ? |
| ACT (Hayes) | Flexibilité ou nouvelle rigidité ? | La résolution est-elle durable ? |

### Verdicts et conséquences

| Verdict | Signification | Action KAIROS |
|---|---|---|
| Transformation documentée | La résolution correspond à un changement réel du sujet | Validation — passer à Phase 6 |
| Transformation insuffisante | Le changement n'a pas encore pénétré les couches profondes | Retour Phase 3 avec signal Miroir comme stimulus |
| Résolution de surface | Narrativement cohérente mais pas structurellement ancrée | Signal explicite + exploration de la part résistante |

### Ce que KAIROS ne fait pas

KAIROS n'invoque pas Miroir Intégral pour des analyses introspectives générales.
Il l'utilise exclusivement comme validateur final de résolution dans les conditions
définies ci-dessus.

---

## Tableau synthétique

| Skill | Phases | Opérateurs / Modes | Conditionnel ? |
|---|---|---|---|
| NEXUS-ARCHÊ | 1, 4, réversibilité | Mode 3 uniquement | Non |
| LÉR-NARRATIF | 2, 4 | META, RESONE, TRANSDUIT, SIGNIFIE, POLYLOGUE | Non |
| CRC-RÉCURSIF | 3, 7 | Cycles 3-7, STÈLE interne | Non |
| MIROIR-INTÉGRAL | 5 | IFS, McAdams, Ecker, ACT | Oui |

---

## Skills hors protocole core

Ces skills peuvent enrichir une session KAIROS mais ne font pas partie
du protocole obligatoire.

| Skill | Quand l'utiliser |
|---|---|
| **FRACTALES DU DESTIN** | Lecture symbolique complémentaire en début de session (Mode B) |
| **OSINT-INTEL** | Validation de scénarios en résolution ouverte (branches stratégiques) |
| **SUPERFORECASTING** | Scoring des branches d'une résolution ouverte à valeur prédictive |
| **STÈLE** (standalone) | Ne pas utiliser — remplacé par STÈLE CRC-R interne |
| **TCAI / TCAI-V2** | Hors scope KAIROS — registre médiumnique distinct |
