---
name: kairos
version: 1.0
description: >
  KAIROS est un modèle de résolution d'histoires à quatre couches. Il traite les
  récits de grain moyen (arcs narratifs) et long (cycles de vie) en articulant
  NEXUS-ARCHÊ (structure), CRC-RÉCURSIF (dynamique), LÉR-NARRATIF (sémantique)
  et MIROIR-INTÉGRAL (sujet, optionnel). Produit trois états : résolution fermée,
  résolution ouverte (bifurcation), suspension narrative. Toute résolution fermée
  est réversible — elle devient le T0 d'un nouveau cycle. Le format de sortie
  (bloc structuré / narration / les deux) est choisi par le lecteur après que la
  résolution a émergé. Activer dès qu'un récit — personnel, collectif, fictionnel
  ou stratégique — cherche sa résolution, qu'un arc narratif demande une clôture,
  qu'un cycle de vie veut être relu, ou que l'utilisateur veut savoir où une
  histoire peut aller. Mots-clés déclencheurs : "résolution", "dénouement",
  "comment ça se termine", "arc narratif", "cycle de vie", "histoire qui tourne
  en rond", "je veux clore", "je cherche une issue", "où va ce récit",
  "traitement narratif", "résoudre cette histoire", "KAIROS".
---

# KAIROS — Modèle de Résolution d'Histoires

> *Le moment qualitativement juste — non une position sur une timeline,*
> *mais un état structurel atteint.*

KAIROS traite un récit jusqu'à sa résolution en articulant quatre couches
opératoires. Il ne prescrit pas la forme de la résolution — il détecte l'état
où le récit peut légitimement s'arrêter, bifurquer, ou signaler qu'il manque
de matière.

---

## POSITION DANS L'ÉCOSYSTÈME

KAIROS est un **orchestrateur** — il ne remplace aucun des skills qu'il invoque.
Il leur délègue des fonctions précises et agrège leurs sorties en une résolution
cohérente.

Articulations directes :
- **NEXUS-ARCHÊ** — vocabulaire structurel, instantanés T0 et T_résolution
- **CRC-RÉCURSIF** — moteur de transformation, gestion de la récursion, STÈLE
- **LÉR-NARRATIF** — grammaire sémantique, parsing, ancrage performatif
- **MIROIR-INTÉGRAL** — validation de la transformation du sujet (conditionnel)

KAIROS ne fait pas appel au skill STÈLE standalone. Il utilise le modèle STÈLE
interne à CRC-RÉCURSIF, plus élaboré pour les compressions inter-états.

---

## DÉPENDANCES

| Skill | Rôle | Activation |
|---|---|---|
| `nexus-arche` | Structure invariante des états narratifs | Phases 1, 4, réversibilité |
| `ler-narratif` | Parsing sémantique, transformation, ancrage | Phases 2, 4 |
| `crc-recursif` | Moteur de transformation + mémoire STÈLE | Phase 3 |
| `miroir-integral` | Validation transformation sujet | Phase 5, conditionnel |

---

## PARAMÈTRES DU MODÈLE

| Paramètre | Valeur |
|---|---|
| **Grain** | Moyen (arc narratif) / Long (cycle de vie) |
| **États de résolution** | Fermée · Ouverte · Suspension |
| **Réversibilité** | Oui — toute résolution fermée est un T0 possible |
| **Format de sortie** | Au choix du lecteur après point de chute |
| **Mémoire** | STÈLE CRC-R, journal inter-sessions, généalogie T0ⁿ |

---

## PHASES DU PROTOCOLE

Protocole complet : `references/protocole-kairos.md`

```
PHASE 0 — Initialisation
  Détection du grain · Détection du mode · Vérification journal si grain long

PHASE 1 — Instantané structurel [NEXUS-ARCHÊ]
  Tirage Mode 3 sur situation initiale → Constellation T0 + chaîne STÈLE

PHASE 2 — Parsing sémantique [LÉR-NARRATIF]
  DSL tripartite · META + RESONE → phrase dominante · carte de tension

PHASE 3 — Moteur de transformation [CRC-RÉCURSIF]
  N cycles (3–5 grain moyen / variable grain long)
  → Cristallisation / Bifurcation / Suspension

PHASE 4 — Validation de résolution [LÉR-NARRATIF + NEXUS-ARCHÊ]
  TRANSDUIT + SIGNIFIE si fermée · POLYLOGUE ouvert si bifurcation
  Nouveau tirage NEXUS-ARCHÊ → constellation T_résolution

PHASE 5 — Couche sujet [MIROIR-INTÉGRAL] ← conditionnel
  Activé si : récit personnel + grain long
  Validation 6 couches : transformation réelle du sujet

PHASE 6 — Sortie
  Présentation de l'état de résolution
  Proposition du format au lecteur → Bloc / Narration / Les deux

PHASE 7 — Mémoire [CRC-R STÈLE]
  Chaîne inter-états T0 → Tcrise → Trés
  Entrée journal · Mise à jour généalogie
```

---

## CRITÈRES DE RÉSOLUTION VALIDE

Une résolution est valide selon son type :

**Fermée** — les trois conditions doivent être remplies :
1. CRC-R cristallisé (≥ 80% stabilité sur 2 cycles consécutifs)
2. Constellation T_résolution ≠ constellation T0 (déplacement structurel réel)
3. La transformation ne falsifie pas la tension initiale (contrôle LÉR)

**Ouverte** — la bifurcation est l'état lui-même :
1. CRC-R en bifurcation (oscillation > ±0.8 entre deux cycles)
2. Deux attracteurs stables coexistent sans résolution par l'un sur l'autre
3. Les deux branches sont narrativement cohérentes

**Suspension** — le récit signale son incomplétude :
1. Cycles CRC-R insuffisants OU matière narrative épuisée avant cristallisation
2. Aucune sortie forcée — état encodé en attente

---

## RÉVERSIBILITÉ

Toute résolution fermée peut être rouverte.
La chaîne STÈLE de la résolution précédente devient l'état hérité du nouveau cycle.
NEXUS-ARCHÊ mesure le delta structurel entre T0¹ et T0ⁿ.

Mécanisme complet : `references/reversibilite.md`

---

## FORMAT DE SORTIE

Le format n'est pas prescrit par le modèle. Il est proposé au lecteur après
que l'état de résolution a été déterminé et présenté en 2-3 lignes neutres.

```
→ Bloc structuré    (archiver, analyser, comparer)
→ Narration         (transmettre, ressentir, clore)
→ Les deux          (bloc pour soi, narration pour l'autre)
```

Templates et règles : `references/format-sortie.md`

---

## FICHIERS DE RÉFÉRENCE

| Fichier | Lire quand |
|---|---|
| `references/architecture.md` | Vue d'ensemble des 4 couches et de leurs interactions |
| `references/protocole-kairos.md` | Toujours — détail opératoire des 7 phases |
| `references/etats-resolution.md` | Phase 4 — critères et spécification des 3 états |
| `references/grains.md` | Phase 0 — détection et spécification des deux grains |
| `references/reversibilite.md` | Quand un récit est rouvert sur une résolution précédente |
| `references/integration-skills.md` | Interface entre KAIROS et chaque skill délégué |
| `references/format-sortie.md` | Phase 6 — templates et règles de formatage |
| `references/stele-kairos.md` | Phase 7 — compressions inter-états et encodage généalogique |
| `references/exemples.md` | Deux tirages annotés complets + un exemple rejeté commenté |

---

## PRINCIPES OPÉRATOIRES

**Délégation stricte** — KAIROS orchestre, il n'implémente pas. Chaque skill
délégué est invoqué selon son protocole propre. KAIROS ne court-circuite pas
les protocoles internes des skills.

**Résolution émergente** — Le modèle ne cherche pas une résolution, il détecte
quand les conditions d'une résolution sont réunies. La cristallisation n'est pas
forcée — elle arrive ou n'arrive pas.

**Intégrité de la tension initiale** — Une résolution qui falsifie la tension
d'origine n'est pas valide. Le contrôle LÉR (TRANSDUIT sans falsification) est
non négociable.

**Réversibilité assumée** — Aucune résolution n'est définitive. La stabilité
est locale. Le modèle traite cette réversibilité comme une propriété structurelle,
non comme un échec de résolution.

**Agentivité du lecteur** — Le format de sortie appartient au lecteur. KAIROS
produit l'état de résolution ; la mise en forme est un acte distinct qui dépend
de l'usage que le lecteur fera de sa résolution.
