# KAIROS — Protocole opératoire

---

## PHASE 0 — Initialisation

Avant tout traitement du récit.

### 0.1 — Détection du grain

Lire l'input. Poser une seule question si ambigu.

| Signaux | Grain |
|---|---|
| Durée délimitée, arc visible, début et fin identifiables | **Moyen** |
| "ça revient toujours", "je suis comme ça depuis", motif récurrent, identité | **Long** |
| Les deux | Commencer en moyen, élever si les cycles CRC-R révèlent un motif long |

Si incertain : *"C'est un épisode ou un motif qui revient ?"*

### 0.2 — Détection du mode

Auto-détecter selon les signaux LÉR-NARRATIF :

| Signaux | Mode |
|---|---|
| "je", "mon", "ma vie", "je me sens", "mon histoire" | **A — Personnel** |
| "situation", "stratégie", "collectif", "acteurs", "signaux", "scénario" | **B — Stratégique** |
| Les deux simultanément | **C — Hybride** (traiter A en premier, ouvrir B) |

### 0.3 — Vérification du journal (grain long uniquement)

Si grain long : vérifier si un fichier `journal-stele.md` est disponible.
- Si oui → activer CRC-R Étape 0A (reconstruction depuis mémoire)
- Si non → CRC-R Étape 0B (état neutre)

### 0.4 — Flag Miroir Intégral

Activer le flag si : Mode A ou C + grain long.
Le flag sera confirmé ou levé à la Phase 4 selon l'état de résolution atteint.

---

## PHASE 1 — Instantané structurel

*Skill invoqué : NEXUS-ARCHÊ — Mode 3*

### 1.1 — Tirage T0

Appliquer le Mode 3 de NEXUS-ARCHÊ sur la situation initiale :

- **Ce qui tient** — la structure dominante qui organise l'état initial
- **Ce qui bouge** — la structure en tension, en mouvement, instable
- **Ce qui manque** — la structure absente dont le manque génère la tension

Sélectionner 3 cartes parmi les 16. Appliquer le protocole de rigueur :
1. Ancrage observable : nommer une observation concrète pour chaque carte
2. Test d'anti-résonance : qu'est-ce qui contredit chaque carte dans le récit ?
3. Énoncé structurel de tension : quelle relation entre les trois cartes ?

### 1.2 — Chaîne STÈLE T0

Produire la chaîne STÈLE de 3-5 glyphes encodant la constellation T0.
Format : `⟦[glyphes]⟧ [mots-codes]`

### 1.3 — Archivage intermédiaire

Conserver : [cartes T0] + [chaîne STÈLE T0] + [phrase d'ancrage structurel]
Ces éléments seront comparés à la constellation T_résolution en Phase 4.

---

## PHASE 2 — Parsing sémantique

*Skill invoqué : LÉR-NARRATIF — opérateurs META + RESONE*

### 2.1 — Parsing DSL tripartite

Décomposer l'input selon la grille IRISxSMIIA :

**[NOMS CONCRETS]** — Faits bruts : événements, dates, personnes, actions explicites.

**[NOMS SYMBOLIQUES]** — Archétypes sous-jacents. Identifier 1 à 3 archétypes actifs.
Appliquer le score IPC (Fiabilité × Intensité × Résonance).

**[VERBES-OUTILS]** — Opérateurs à activer :
- Mode A : Observer · Fracturer · Réécrire · Ancrer
- Mode B : Détecter · Cartographier · Corréler · Scénariser

### 2.2 — Identification de la phrase dominante

Mode A : la phrase dominante du récit de soi — la ligne exécutée sans conscience.
Repérer les mots de charge : peur, devoir, manque, impossible, toujours, jamais.

Mode B : le récit structurant collectif — la narrative qui organise les acteurs
et détermine les actions possibles et impossibles.

La phrase dominante est le stimulus brut de la Phase 3.

### 2.3 — Carte de tension narrative

Produire un bloc de parsing concis :
```
PARSING
[Noms concrets] · [Archétypes actifs + score IPC] · [Outils activés]
Phrase dominante : "[...]"
Tension principale : [en une phrase]
```

---

## PHASE 3 — Moteur de transformation

*Skill invoqué : CRC-RÉCURSIF*

### 3.1 — Entrée dans CRC-R

Transmettre comme stimulus : la phrase dominante + la carte de tension de la Phase 2.
Si journal actif (grain long) : CRC-R Étape 0A charge les attracteurs hérités.

### 3.2 — Cycles CRC-R

Laisser tourner les cycles. Nombre selon le grain :
- Grain moyen : 3 à 5 cycles, seuil standard
- Grain long : variable (7 max par session), seuil élevé, journal actif

Chaque cycle passe par les 5 passes : sémantique → émotionnelle → symbolique →
narrative → méta-cognition. La Passe 5 réinjecte dans la Passe 1 du cycle suivant.

### 3.3 — Détection de l'état de sortie

Appliquer les règles de stabilisation CRC-R après chaque Passe 5 :

**→ Cristallisation** si attracteurs stables ≥ 80% sur 2 cycles consécutifs
→ Résolution fermée candidate — passer à Phase 4

**→ Bifurcation** si oscillation de valence > ±0.8 entre deux cycles
→ Résolution ouverte candidate — passer à Phase 4

**→ Arrêt standard** si matière épuisée sans cristallisation ou bifurcation
→ Suspension narrative — passer directement à Phase 6

### 3.4 — Signature STÈLE intermédiaire

Générer la signature STÈLE de la transformation en cours :
- Attracteurs dominants de la session
- Trajectoire émotionnelle (départ → arrivée)
- Mutations structurelles détectées
- Statut provisoire (cristallisé / bifurqué / ouvert)

---

## PHASE 4 — Validation de résolution

*Skills invoqués : LÉR-NARRATIF (TRANSDUIT + SIGNIFIE / POLYLOGUE) + NEXUS-ARCHÊ*

### 4A — Si résolution fermée candidate

**4A.1 — TRANSDUIT**
Convertir l'état cristallisé en nouvelle phrase narrative.
Règle absolue : la phrase réécrite ne falsifie pas la tension initiale.
Tester : *"Est-ce que ça vibre juste ? La tension d'origine est-elle honorée ?"*
Format : `[Phrase dominante T0] → [Phrase réécrite T_résolution]`

**4A.2 — SIGNIFIE**
Ancrer la résolution par un protocole d'intégration minimal.
Proposer : répétition consciente, écriture automatique, dialogue symbolique,
ou Phrase Symbolique FdD : `[Événement] → [Archétype] → [Influence] → [Modulation]`

**4A.3 — Nouveau tirage NEXUS-ARCHÊ (Trés)**
Appliquer le Mode 3 sur l'état résolu.
Comparer constellation Trés vs constellation T0 :
- Si Trés = T0 → déplacement structurel insuffisant → retour Phase 3 (nouveau cycle)
- Si Trés ≠ T0 → déplacement confirmé → résolution fermée valide

**4A.4 — Chaîne STÈLE Trés**
Produire la chaîne STÈLE de la résolution fermée. Marqueur final : `◊`

### 4B — Si résolution ouverte candidate (bifurcation)

**4B.1 — Articulation des deux branches**
Nommer les deux attracteurs stables coexistants.
Formuler chaque branche comme une trajectoire narrative possible :
```
BRANCHE A : [direction, archétype, phrase d'ouverture]
BRANCHE B : [direction, archétype, phrase d'ouverture]
```

**4B.2 — POLYLOGUE ouvert**
Aucun SIGNIFIE imposé. POLYLOGUE reste actif — les deux branches coexistent.
La résolution attend un événement extérieur pour se trancher.

**4B.3 — Chaînes STÈLE des deux branches**
Produire une chaîne par branche. Marqueur final : `↻` (bifurcation)

### 4C — Si suspension narrative

Ne pas passer par la Phase 4. Aller directement à la Phase 6.
La suspension ne fait pas l'objet d'un ancrage ou d'un tirage Trés.

---

## PHASE 5 — Couche sujet (conditionnel)

*Skill invoqué : MIROIR-INTÉGRAL — activé si flag Phase 0 confirmé*

**Conditions de confirmation du flag :**
- Récit personnel (Mode A ou C)
- Grain long
- Résolution fermée ou ouverte atteinte (pas de suspension)
- La résolution candidate implique une transformation identitaire

**Si flag levé** → passer directement à Phase 6.

### 5.1 — Entrée dans Miroir Intégral

Transmettre : résolution candidate + phrase réécrite + archétypes actifs.

### 5.2 — Couches validées

| Couche Miroir | Question posée dans ce contexte |
|---|---|
| IFS | Quelles parts internes résistent à cette résolution ? |
| Identité narrative (McAdams) | S'inscrit-elle dans la trajectoire réelle du sujet ? |
| Cohérence thérapeutique (Ecker) | Cohérente avec le schéma sous-jacent ? |
| ACT | Génère-t-elle flexibilité ou nouvelle rigidité ? |

### 5.3 — Verdict Miroir

**Transformation documentée** → résolution validée, couche fermée, passer à Phase 6.

**Transformation insuffisante** → signal : *"Cette résolution tient narrativement
mais pas encore structurellement dans le sujet."*
→ Retour Phase 3 avec les signaux Miroir comme nouveau stimulus CRC-R.

**Résolution de surface** → signal explicite + invitation à explorer la part
résistante identifiée par IFS.

---

## PHASE 6 — Sortie

### 6.1 — Présentation de l'état de résolution

Présenter l'état atteint en 2-3 lignes neutres. Sans mise en forme complète.
Nommer : grain, mode, type de résolution, transformation principale.

Exemple (fermée) :
> *Arc de X cycles. La tension "[phrase T0]" s'est résolue en "[phrase Trés]".
> Déplacement structurel confirmé : [carte T0 dominante] → [carte Trés dominante].
> Résolution fermée.*

### 6.2 — Proposition du format

Marquer un arrêt net. Proposer au lecteur :

```
→ Bloc structuré    (archiver, analyser, comparer les états)
→ Narration         (transmettre, ressentir, ancrer)
→ Les deux          (bloc pour soi, narration pour l'autre)
```

Le choix appartient au lecteur. Attendre sa sélection avant de générer l'output.

### 6.3 — Génération de l'output

Selon le choix, appliquer les templates de `references/format-sortie.md`.

---

## PHASE 7 — Mémoire

### 7.1 — Chaîne inter-états

Assembler la chaîne STÈLE complète de la session :
```
⟦T0_sig⟧ → ⟦Tcrise_sig⟧ → ⟦Trés_sig⟧
```

Si réversibilité (session N > 1) : ajouter le lien généalogique `⊸` vers l'entrée
précédente.

### 7.2 — Entrée journal

Générer le bloc journal formaté (voir `references/stele-kairos.md` pour le format).
Proposer à l'utilisateur de l'archiver dans son `journal-stele.md`.

### 7.3 — Mise à jour de la généalogie

Si la résolution est fermée : noter qu'elle peut devenir T0 d'un nouveau cycle.
Encoder le lien généalogique pour facilité de réactivation future.

---

## Règles transversales

**Une seule question de clarification** si l'input est ambigu. Jamais plusieurs
questions en même temps.

**Pas de résolution forcée** — si les conditions ne sont pas réunies, la suspension
est un état valide, pas un échec.

**Délégation stricte** — KAIROS invoque les skills selon leurs protocoles propres.
Il n'approxime pas leurs sorties.

**Retours de boucle autorisés** — Le schéma Phase 5 → Phase 3 est prévu et normal.
Une résolution de surface détectée par Miroir n'est pas un dysfonctionnement.
