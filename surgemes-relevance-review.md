# Surgemes Relevance to Surgical Video Annotation Standard

## Purpose and Scope

This document clarifies the relevance of **surgemes** to a modern **surgical video annotation standard** and to formal data‑dictionary deliverables. It consolidates conceptual background, comparative analysis, and normative guidance to support interoperable, video‑first annotation across procedures, platforms, and institutions.

## Background

*Surgemes* were originally proposed as fine‑grained action or motion primitives to support surgical robotics, skill assessment, and control abstraction [1,2]. Historically, these units were often parameterized, kinematics‑centric, and sometimes inferred (e.g., intent, control mode), making them powerful for robotics research but comparatively poorly suited to large‑scale, human‑annotated surgical video datasets [3,4].

In parallel, recent advances in **large‑scale self‑supervised surgical video foundation models** have demonstrated that robust spatiotemporal representation learning benefits from consistent exposure to **temporally localized, low‑level surgical actions**, even when labels are sparse or weak [5,6]. This body of work reaffirms the conceptual value of atomic action structure while shifting requirements toward **video‑observable, annotation‑ready definitions**. In addition, contemporary surgical data‑science roadmaps emphasize **time‑critical, low‑latency intra‑operative intelligence**, favoring compact, compositional representations over heavy kinematic abstractions that are difficult to deploy in real‑time clinical contexts [7].

## Design Position

For a surgical video annotation standard, surgemes are best treated as a **conceptual ancestor** rather than a normative schema element. Their principal contribution is motivating the existence of a lowest‑level action layer. However, to be interoperable, scalable, and suitable for modern datasets and foundation models, that layer must be redefined as **atomic, directly observable, verb‑only actions**, grounded in video evidence and explicitly decoupled from platform‑specific control parameters or motion models [3,5,8].

## Short Comparison Table

**Classical Surgemes vs. Video‑Observable Atomic Actions**

|Dimension|Classical Surgemes|Video‑Observable Atomic Actions (Standard)|
|---|---|---|
|Original motivation|Robotics, skill modeling, control abstraction [1,2]|Dataset curation, benchmarking, foundation‑model training [5,6,9]|
|Primary signal|Robot kinematics, trajectories, forces|Operative video as sufficient evidence|
|Observability|Often partially inferred|Strictly directly observable on video|
|Granularity|Very fine‑grained, control‑level|Atomic yet visually coherent|
|Definition style|Parameterized (direction, velocity, frame)|Verb‑only, parameter‑free|
|Platform dependence|Frequently robot‑ or instrument‑specific|Procedure‑agnostic and vendor‑neutral|
|Annotation scalability|Limited|High across institutions and datasets [9]|
|Role today|Conceptual precursor|Canonical interface between video and workflow semantics|

## Normative Data‑Dictionary Note

### Relationship to Surgeme Literature

**Normative statement.** This data dictionary intentionally does **not** adopt classical surgeme definitions verbatim. While surgemes are acknowledged as foundational to action modeling in surgical robotics and skill analysis, their historical dependence on kinematic parameters, control abstractions, or inferred intent renders them unsuitable as primary entries in a video‑centric annotation standard [3,4,7].

**Design rationale.** All action entries in this standard are constrained to **atomic, directly observable, verb‑only surgical actions**. This constraint ensures annotation reproducibility, cross‑dataset interoperability, and compatibility with both large‑scale self‑supervised learning and real‑time or near‑real‑time inference pipelines [5–7,9].

**Interpretive guidance.** Surgeme concepts **MAY** be referenced as *conceptual antecedents* motivating the existence of a lowest‑level action hierarchy. However, dictionary entries **SHALL** be defined exclusively by what can be unambiguously observed in video, independent of procedure, surgical specialty, robotic platform, or control modality.

**Out of scope.** Mappings between these atomic action labels and robot‑specific or kinematic surgeme representations **MAY** be defined in downstream ontologies or application‑specific models, but such mappings are **explicitly out of scope** for this data‑dictionary specification.

## Implications for Standards and AI

By reframing surgeme‑level granularity into **video‑observable atomic actions**, the proposed standard aligns with contemporary trends in surgical foundation models, dataset benchmarking, and time‑critical surgical data science [5–7,9]. The resulting vocabulary functions as a stable semantic interface between raw video, learned spatiotemporal representations, and higher‑level workflow or decision‑support layers—preserving the conceptual spirit of surgemes while meeting the practical and operational requirements of modern surgical video annotation.

## Summary

- Surgemes remain conceptually relevant but are **not** adopted verbatim.
- A surgical video annotation standard requires **observable, verb‑only atomic actions**.
- This design maximizes interoperability, scalability, and compatibility with current and future surgical AI systems.

---

## References

2. Reiley CE, Hager GD. Task versus subtask surgical skill evaluation of robotic minimally invasive surgery. *Med Image Comput Comput Assist Interv*. 2009;12(Pt 1):435–442. -- this work  evaluating surgical skills on da vinci platform based on surgemes for the 1st time (to their knowledge). tasks (suturing, actions nowadays), surgemes (needle pulling), and lower element dexeme where defined here. 
3. Jannin P, Despinoy F, Bouget D, et al. Surgical process modelling: A review. *Int J Comput Assist Radiol Surg*. 2020;15(6):959–987.
4. Timoh KN, Huaulme A, Cleary K, et al. A systematic review of annotation for surgical process model analysis based on video. *Surg Endosc*. 2023;37(6):4298–4314.
5. Yang S, Zhou F, Mayer L, et al. Large‑scale self‑supervised video foundation model for intelligent surgery. *npj Digit Med*. 2026;9:220.
6. Li Y, Yang X, Xu D, et al. A comparative study in surgical AI: Datasets, foundation models, and barriers to Med‑AGI. *arXiv*. 2026. arXiv:2603.27341.

8. Meireles OR, Rosman G, Altieri MS, et al. SAGES consensus recommendations on an annotation framework for surgical video. *Surg Endosc*. 2021;35(9):4928–4940.
