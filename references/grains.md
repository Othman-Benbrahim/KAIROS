# KAIROS — Grains narratifs

Le grain détermine la profondeur opératoire du modèle, les seuils des cycles
CRC-R, l'activation du journal STÈLE, et le rôle de Miroir Intégral.

---

## GRAIN MOYEN — Arc narratif

### Définition

Un segment narratif avec un début identifiable, une crise, et une clôture possible.
L'arc a une durée délimitée — de quelques semaines à quelques mois, rarement plus.

**Exemples :**
- Un chapitre ou un acte dans un récit fictionnel
- Un projet avec ses phases de lancement, friction, résolution
- Une phase relationnelle (rencontre, rupture, réconciliation)
- Un épisode professionnel (conflit, décision, transition)
- Un arc de scénario dans un jeu ou une stratégie collective

### Spécifications opératoires

| Paramètre | Valeur |
|---|---|
| **Durée narrative** | Quelques semaines à quelques mois |
| **NEXUS-ARCHÊ** | Tirage Mode 3 à chaque nœud d'arc (entrée, crise, sortie) |
| **CRC-R cycles** | 3 à 5 par segment |
| **Seuil cristallisation** | Standard — ≥ 80% stabilité sur 2 cycles |
| **Journal actif** | Non par défaut (sauf si demandé ou session > 1) |
| **LÉR-NARRATIF** | Mode B dominant, ou C (hybride) |
| **Miroir Intégral** | Optionnel — sur demande ou signal fort de transformation |
| **Mémoire STÈLE** | T0_arc → Tcrise_arc → Trés_arc |
| **Session** | Généralement mono-session |

### Signaux de détection (grain moyen)

- L'utilisateur décrit un épisode avec un cadre temporel visible
- La tension a un déclencheur identifiable (événement, date, décision)
- La question posée est "comment ça se résout ?" plutôt que "pourquoi ça revient ?"
- Le récit a des acteurs clairement définis et des enjeux délimités

### Structure d'un arc moyen dans KAIROS

```
T0_arc ──→ Nœud de crise ──→ Trés_arc
              │
         [CRC-R 3-5 cycles]
```

Si l'arc contient plusieurs nœuds de crise visibles, KAIROS les traite
séquentiellement : chaque Trés intermédiaire devient le T0 du sous-arc suivant.

---

## GRAIN LONG — Cycle de vie

### Définition

Un récit qui traverse plusieurs arcs, porte des motifs récurrents, touche à
l'identité, à la trajectoire de vie, ou à une dynamique collective structurante.
La durée est en années, parfois en décennies.

**Exemples :**
- Un motif relationnel qui revient à travers différentes personnes
- Une trajectoire professionnelle avec ses phases de construction, crise, bifurcation
- Un récit identitaire ("je suis quelqu'un qui...") en cours de transformation
- Une dynamique institutionnelle ou collective sur le long terme
- Un cycle familial transgénérationnel

### Spécifications opératoires

| Paramètre | Valeur |
|---|---|
| **Durée narrative** | Années à décennies |
| **NEXUS-ARCHÊ** | Tirage aux transitions majeures + delta inter-T0 |
| **CRC-R cycles** | Variable — 7 max par session, plusieurs sessions |
| **Seuil cristallisation** | Élevé — pattern stable sur N arcs, pas juste N cycles |
| **Journal actif** | Oui — obligatoire, colonne vertébrale mémorielle |
| **LÉR-NARRATIF** | Mode A dominant, ou C (hybride) |
| **Miroir Intégral** | Activé par défaut |
| **Mémoire STÈLE** | Généalogie T0¹ → Trés¹ → T0² → Trés²... |
| **Session** | Multi-sessions — le journal assure la continuité |

### Signaux de détection (grain long)

- "ça revient toujours", "c'est un motif", "c'est ma façon d'être"
- La tension n'a pas de déclencheur unique — elle traverse plusieurs épisodes
- La question posée touche à l'identité, pas juste à la situation
- Le récit implique des schémas (Schema Therapy) ou des parts (IFS)
- L'utilisateur fait référence à "avant" et "maintenant" sur une longue durée

### Structure d'un cycle de vie dans KAIROS

```
T0¹ ──[KAIROS session 1]──→ Trés¹ [◊]
                               │
                          [journal STÈLE]
                               │
T0² ──[KAIROS session 2]──→ Trés² [◊ ou ↻]
                               │
                              ...
```

Chaque session lit le journal avant de commencer (CRC-R Étape 0A).
Les attracteurs hérités des sessions précédentes sont actifs dès le départ.

### Delta structurel inter-T0

En grain long, KAIROS peut comparer les constellations NEXUS-ARCHÊ de tous
les T0 pour mesurer le déplacement réel sur toute la trajectoire :

```
T0¹ : [CONTRAINTE ⊘, POLARITÉ ⥀, INCERTITUDE Ø]
T0² : [CONTRAINTE ⊘, TRANSFORMATION ∿, INCERTITUDE Ø]
T0³ : [ÉMERGENCE ⊙, TRANSFORMATION ∿, RÉCIPROCITÉ ⊗]
```

→ CONTRAINTE a persisté pendant deux arcs avant de céder.
→ TRANSFORMATION est apparue en T0² et maintenue en T0³ — elle s'est stabilisée.
→ ÉMERGENCE en T0³ était absente des deux premiers T0 — elle est nouvelle.

Ce delta mesure le voyage réel du récit sur toute sa durée.

---

## Élévation de grain en cours de session

Il est possible de commencer en grain moyen et d'élever vers le grain long
si les cycles CRC-R révèlent un motif de fond.

**Signaux d'élévation :**
- CRC-R produit les mêmes attracteurs qu'une session précédente
- La phrase dominante ressemble à une formulation déjà rencontrée
- NEXUS-ARCHÊ identifie les mêmes structures que lors d'un tirage antérieur
- L'utilisateur reconnaît spontanément "c'est encore ça"

**Protocole d'élévation :**
1. Marquer l'arc moyen en cours comme Trés_arc intermédiaire
2. L'archiver dans le journal
3. Repartir sur le récit avec le grain long activé
4. Le T0 du grain long intègre l'arc moyen comme premier nœud documenté

---

## Tableau récapitulatif

| | Grain moyen | Grain long |
|---|---|---|
| **Arc** | 1 arc délimité | Plusieurs arcs, trajectoire |
| **Durée** | Semaines — mois | Années — décennies |
| **CRC-R** | 3-5 cycles / session | Variable, multi-sessions |
| **Cristallisation** | Standard | Élevée |
| **Journal STÈLE** | Optionnel | Obligatoire |
| **LÉR mode** | B ou C | A ou C |
| **Miroir Intégral** | Optionnel | Par défaut |
| **Mémoire** | T0 → Tcrise → Trés | Généalogie T0ⁿ |
| **Sessions** | 1 (généralement) | N sessions |
