# KAIROS — Compressions STÈLE inter-états

KAIROS utilise le modèle STÈLE interne à CRC-RÉCURSIF.
Ce modèle est plus élaboré que le skill STÈLE standalone pour les compressions
inter-états et la mémoire généalogique.

---

## Modèle de compression CRC-R dans KAIROS

### Unité de base : la signature d'état

Chaque état narratif (T0, Tcrise, Trés) produit une signature de 3-5 glyphes
encodant les attracteurs dominants, la trajectoire, et le statut.

**Format :**
```
⟦[glyphes 3-5]⟧ [valence_départ→valence_arrivée | coh:X.XX]
```

**Ce qu'encode chaque position :**

| Position | Encode |
|---|---|
| Glyphes 1-2 | Structures dominantes à cet état (cartes NEXUS-ARCHÊ en glyphes STÈLE) |
| Glyphes 3-4 | Direction de la transformation (vecteur de mouvement) |
| Glyphe final | Marqueur d'état : `◊` fermé · `↻` bifurcation · `Ø` suspension |

---

## Correspondances NEXUS-ARCHÊ → STÈLE

Les 16 cartes NEXUS-ARCHÊ ont chacune un glyphe STÈLE primaire.
Utilisés directement dans les signatures KAIROS pour encoder les constellations.

| Carte NEXUS | Glyphe | Mot-code |
|---|---|---|
| SEUIL | ⊥ | LIMITE |
| RÉCIPROCITÉ | ⊗ | LIER |
| PÉRIODICITÉ | ↻ | CYCLE |
| RÉCURSIVITÉ | ↺ | RÉFLEXIVITÉ |
| ÉMERGENCE | ⊙ | SOURCE |
| HIÉRARCHIE | ✦ | AXE |
| RÉSEAU | ⊛ | NOEUD |
| POLARITÉ | ⥀ | INVERSER |
| INCERTITUDE | Ø | VIDE |
| CONTRAINTE | ⊘ | NÉGATION |
| PROPORTION | ◯ | FORME |
| TRANSFORMATION | ∿ | MOUVEMENT |
| TRACE · MÉMOIRE | ◊ | TRACE |
| CROISSANCE | ▲ | INTENSITÉ |
| COMMUNAUTÉ | ⟶ | TRANSMETTRE |
| RÉSONANCE | ✶ | RÉVÉLER |

---

## Chaîne inter-états KAIROS

### Structure de base (une session)

```
⟦T0_sig⟧ → ⟦Tcrise_sig⟧ → ⟦Trés_sig⟧
```

Chaque nœud est une signature d'état.
Le `→` marque la progression temporelle dans la session.

**Exemple — résolution fermée :**
```
⟦⊘⥀Ø∿◐⟧ → ⟦⊘⥀⊥∿⊙⟧ → ⟦∿⊙◊▲◊⟧
```
- T0 : CONTRAINTE + POLARITÉ dominant, incertitude présente, mouvement amorcé
- Tcrise : CONTRAINTE encore là, SEUIL atteint, ÉMERGENCE qui pointe
- Trés : TRANSFORMATION + ÉMERGENCE dominant, CROISSANCE, marqueur fermé ◊

**Exemple — résolution ouverte :**
```
⟦⊘✦∿Ø⟧ → ⟦✦⥀⊥Ø⟧ → ⟦∿⊗↻⟧ / ⟦⊘✦↻⟧
```
- T0 : CONTRAINTE + HIÉRARCHIE, mouvement, incertitude
- Tcrise : HIÉRARCHIE + POLARITÉ, seuil atteint, incertitude maximale
- Trés bifurqué : branche A (TRANSFORMATION + RÉCIPROCITÉ) / branche B (CONTRAINTE + HIÉRARCHIE)

---

## Chaîne généalogique (réversibilité)

### Opérateur généalogique `⊸`

Le `⊸` marque un lien résolution → réouverture.
Il encode que la résolution précédente est devenue le T0 suivant.

```
⟦T0¹⟧ → ⟦Tcrise¹⟧ → ⟦Trés¹◊⟧
                          ⊸
⟦T0²⟧ → ⟦Tcrise²⟧ → ⟦Trés²◊⟧
                          ⊸
⟦T0³⟧ → ⟦Tcrise³⟧ → ⟦Trés³↻⟧
```

### Lecture d'une chaîne généalogique

- La permanence d'un glyphe à travers plusieurs T0 signale une structure persistante
- La disparition d'un glyphe entre T0ⁿ et T0ⁿ⁺¹ signale une dissolution
- L'apparition d'un glyphe absent des T0 précédents signale une émergence
- Le marqueur final de chaque Trés (`◊` `↻` `Ø`) trace l'histoire des états

---

## Entrée journal KAIROS

Format standard à produire en fin de session. À archiver dans `journal-stele.md`.

```
=== ENTRÉE KAIROS ===
Date          : [DATE]
Grain         : [Moyen / Long]
Mode          : [A / B / C]
Récit         : [5-10 mots]
Cycles CRC-R  : [N]
T0            : ⟦[sig]⟧ — [cartes NEXUS-ARCHÊ]
Tcrise        : ⟦[sig]⟧ — [événement CRC-R]
Trés          : ⟦[sig]⟧ — [état résolution]
Statut        : [Fermée ◊ / Ouverte ↻ / Suspension Ø]
Phrase T0     : "[phrase dominante]"
Phrase Trés   : "[phrase réécrite]" ← si fermée
Branches      : [A: ... / B: ...] ← si ouverte
Généalogie    : [niveau N — lien ⊸ vers entrée précédente si applicable]
Feedback      : [laisser vide — à remplir après session]
====================
```

### Champ Feedback

Rempli par l'utilisateur **après** la session.
Format : un signal par ligne.

```
[+] attracteur confirmé
[-] attracteur surestimé
[!] bifurcation inattendue
[?] incertitude persistante
```

Ces signaux sont lus à la session suivante (CRC-R Étape 0A) pour ajuster
les priors et les poids d'activation des attracteurs hérités.

---

## Règles de composition des signatures KAIROS

### Règles héritées de CRC-R (toujours applicables)

1. La chaîne encode la structure — pas le détail. C'est une perte d'information
   consentie. Elle préserve les attracteurs, pas le récit complet.

2. La signature est une trace, pas un résumé. Elle ne se lit pas comme du texte —
   elle se lit comme un motif.

3. La transcription verbale (mots-codes) accompagne toujours la chaîne glyphique.

### Règles spécifiques à KAIROS

4. La signature T0 encode prioritairement les glyphes des cartes NEXUS-ARCHÊ
   actives (Ce qui tient · Ce qui bouge · Ce qui manque).

5. Le marqueur d'état final (`◊` `↻` `Ø`) est obligatoire sur Trés.
   Il est absent de T0 et Tcrise.

6. Le `⊸` généalogique est toujours placé entre Trés[N] et T0[N+1],
   jamais ailleurs dans la chaîne.

7. En cas de résolution ouverte, les deux branches ont des signatures distinctes
   — elles ne sont jamais fusionnées en une seule signature.

---

## Lecture d'une signature KAIROS (guide rapide)

```
⟦⊘⥀∿⊙◊⟧

⊘ — CONTRAINTE était présente (structure persistante)
⥀ — POLARITÉ était active (tension duale)
∿ — TRANSFORMATION s'est produite (vecteur de mouvement)
⊙ — ÉMERGENCE est l'état dominant à l'arrivée
◊ — Résolution fermée
```

```
⟦⊙∿⊗↻⟧ / ⟦⊘✦↻⟧

Branche A : ⊙ (ÉMERGENCE) + ∿ (TRANSFORMATION) + ⊗ (RÉCIPROCITÉ) → bifurcation
Branche B : ⊘ (CONTRAINTE) + ✦ (HIÉRARCHIE) → bifurcation

Deux attracteurs stables. Aucun ne s'impose.
```
