# Galaxy Morphology Classes – Data Dictionary

This document describes the meaning of each **Galaxy Zoo morphology probability** column
from the `training_solutions_rev1.csv` dataset.

Each `ClassX.Y` column stores a **probability (vote fraction)** between 0 and 1
representing how many human classifiers selected that answer.

- A value near **1.0** → feature is very likely present.
- A value near **0.0** → feature is very likely absent.

---

## In Brief
Global morphology: Class1

Edge-on: Class2

Spiral: Class4

Bar: Class3

Bulge prominence: Class5

Odd features / mergers / rings / dust lanes: Class8

Spiral arm tightness: Class10

Spiral arm count: Class11

---

## General

- **GalaxyID**  
  Unique integer identifier for each galaxy image.  
  The corresponding filename is typically `GalaxyID.jpg`.

- **sum_class1**  
  Sanity-check column: `Class1.1 + Class1.2 + Class1.3`.  
  Should be close to 1.0 for each galaxy.

---

## Class1 – Global Morphology

- **Class1.1** – Probability that the galaxy is **smooth / featureless**  
- **Class1.2** – Probability that the galaxy has **features or a disk**  
- **Class1.3** – Probability that the image is a **star or artifact**

These three capture the **top-level morphology**:  
smooth (often elliptical), disk/spiral, or non-galaxy.

---

## Class2 – Edge-on vs Not Edge-on

- **Class2.1** – Probability the galaxy is **edge-on**  
- **Class2.2** – Probability the galaxy is **not edge-on**

---

## Class3 – Bar Presence

- **Class3.1** – Probability the galaxy has a **bar**  
- **Class3.2** – Probability the galaxy has **no bar**

Bars are elongated structures across the galaxy center,
common in disk galaxies.

---

## Class4 – Spiral Structure

- **Class4.1** – Probability the galaxy is **spiral**  
- **Class4.2** – Probability the galaxy is **not spiral**

---

## Class5 – Bulge Prominence

- **Class5.1** – Probability the galaxy has **no prominent bulge**  
- **Class5.2** – Probability the galaxy’s bulge is **just noticeable**  
- **Class5.3** – Probability the galaxy’s bulge is **obvious**  
- **Class5.4** – Probability the galaxy’s bulge is **dominant**

Bulge prominence is an important indicator of
galaxy morphology and evolution.

---

## Class6 – Odd Features

- **Class6.1** – Probability the galaxy has **odd features**  
- **Class6.2** – Probability the galaxy has **no odd features**

“Odd” includes disturbances, tidal features, or other unusual structures.

---

## Class7 – Overall Shape (Roundness)

- **Class7.1** – Probability the galaxy is **completely round**  
- **Class7.2** – Probability the galaxy’s shape is **in-between** round and elongated  
- **Class7.3** – Probability the galaxy is **cigar-shaped** (highly elongated)

---

## Class8 – Detailed Odd / Special Features

- **Class8.1** – Probability the galaxy has a **ring**  
- **Class8.2** – Probability the galaxy has a **lens or arc**  
- **Class8.3** – Probability the galaxy is **disturbed**  
- **Class8.4** – Probability the galaxy is **irregular**  
- **Class8.5** – Probability the galaxy has **some other strange feature**  
- **Class8.6** – Probability the galaxy is **merging**  
- **Class8.7** – Probability the galaxy has a **dust lane**

These features are especially important for studying
galaxy interactions and mergers.

---

## Class9 – Bulge Shape

- **Class9.1** – Probability the galaxy’s bulge is **round**  
- **Class9.2** – Probability the galaxy’s bulge is **boxy**  
- **Class9.3** – Probability the galaxy has **no bulge**

---

## Class10 – Spiral Arm Tightness

- **Class10.1** – Probability that spiral arms are **tightly wound**  
- **Class10.2** – Probability that spiral arms are **moderately wound**  
- **Class10.3** – Probability that spiral arms are **loosely wound**

Spiral arm tightness is related to Hubble type (Sa, Sb, Sc).

---

## Class11 – Number of Spiral Arms

- **Class11.1** – Probability the galaxy has **one spiral arm**  
- **Class11.2** – Probability the galaxy has **two spiral arms**  
- **Class11.3** – Probability the galaxy has **three spiral arms**  
- **Class11.4** – Probability the galaxy has **four spiral arms**  
- **Class11.5** – Probability the galaxy has **more than four spiral arms**  
- **Class11.6** – Probability that the **number of spiral arms cannot be determined**

This information is useful for detailed morphology classification
and for studying spiral structure formation.
