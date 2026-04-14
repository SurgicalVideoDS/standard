# Surgemes Relevance to Surgical Video Annotation Standard

## Purpose and Scope

This document clarifies the relevance of surgical gestures or **surgemes** to a modern **surgical video annotation standard** and to formal data‑dictionary deliverables. It consolidates conceptual background, comparative analysis, and normative guidance to support interoperable, video‑first annotation across procedures, platforms, and institutions.

## Background

*Surgemes* were originally proposed as fine‑grained action or motion primitives to support surgical robotics, skill assessment, and control abstraction [1]. Historically, these units were often parameterized, kinematics‑centric, and sometimes inferred (e.g., intent, control mode), making them powerful for robotics research but comparatively poorly suited to large‑scale, human‑annotated surgical video datasets [2,8].

In parallel, recent advances in **large‑scale self‑supervised surgical video foundation models** have demonstrated that robust spatiotemporal representation learning benefits from consistent exposure to **temporally localized, low‑level surgical actions**, including in settings where labels are limited [3]. This body of work reaffirms the conceptual value of atomic action structure while shifting requirements toward **video‑observable, annotation‑ready definitions**. In addition, contemporary surgical data‑science roadmaps emphasize operationally practical, scalable intra‑operative intelligence, favoring compact, compositional representations over heavy kinematic abstractions that are difficult to deploy in clinical contexts [7,8].

## Design Position

For a surgical video annotation standard, surgemes are best treated as a **conceptual ancestor** rather than a normative schema element. Their principal contribution is motivating the existence of a lowest‑level action layer. However, to be interoperable, scalable, and suitable for modern datasets and foundation models, that layer must be redefined as **atomic, directly observable, verb‑only actions**, grounded in video evidence and explicitly decoupled from platform‑specific control parameters or motion models [2,3,8].

## Short Comparison Table

**Classical Surgemes vs. Video‑Observable Atomic Actions**

|Dimension|Classical Surgemes|Video‑Observable Atomic Actions (Standard)|
|---|---|---|
|Original motivation|Robotics, skill modeling, control abstraction [1,2]|Dataset curation, benchmarking, foundation‑model training [3,4]|
|Primary signal|Robot kinematics, trajectories, forces|Operative video as sufficient evidence|
|Observability|Often partially inferred|Strictly directly observable on video|
|Granularity|Very fine‑grained, control‑level|Atomic yet visually coherent|
|Definition style|Parameterized (direction, velocity, frame)|Verb‑only, parameter‑free|
|Platform dependence|Frequently robot‑ or instrument‑specific|Procedure‑agnostic and vendor‑neutral|
|Annotation scalability|Limited|High across institutions and datasets [9]|
|Role today|Conceptual precursor|Canonical interface between video and workflow semantics|

## Normative Data‑Dictionary Note

### Relationship to Surgeme Literature

**Normative statement.** This data dictionary intentionally does **not** adopt classical surgeme definitions verbatim. While surgemes are acknowledged as foundational to action modeling in surgical robotics and skill analysis, their historical dependence on kinematic parameters, control abstractions, or inferred intent renders them unsuitable as primary entries in a video‑centric annotation standard [1,2,7].

**Design rationale.** All action entries in this standard are constrained to **atomic, directly observable, verb‑only surgical actions**. This constraint ensures annotation reproducibility, cross‑dataset interoperability, and compatibility with both large‑scale self‑supervised learning and real‑time or near‑real‑time inference pipelines [3,4,7,9].

**Interpretive guidance.** Surgeme concepts **MAY** be referenced as *conceptual antecedents* motivating the existence of a lowest‑level action hierarchy. However, dictionary entries **SHALL** be defined exclusively by what can be unambiguously observed in video, independent of procedure, surgical specialty, robotic platform, or control modality.

**Out of scope.** Mappings between these atomic action labels and robot‑specific or kinematic surgeme representations **MAY** be defined in downstream ontologies or application‑specific models, but such mappings are **explicitly out of scope** for this data‑dictionary specification.

## Implications for Standards and AI

By reframing surgeme‑level granularity into **video‑observable atomic actions**, the proposed standard aligns with contemporary trends in surgical foundation models, dataset benchmarking, and time‑critical surgical data science [3,4,7,9]. The resulting vocabulary functions as a stable semantic interface between raw video, learned spatiotemporal representations, and higher‑level workflow or decision‑support layers—preserving the conceptual spirit of surgemes while meeting the practical and operational requirements of modern surgical video annotation.

## Summary

- Surgemes remain conceptually relevant but are **not** adopted verbatim.
- A surgical video annotation standard requires **observable, verb‑only atomic actions**.
- This design maximizes interoperability, scalability, and compatibility with current and future surgical AI systems.

---

## References

1. Reiley CE, Hager GD. Task versus subtask surgical skill evaluation of robotic minimally invasive surgery. *Med Image Comput Comput Assist Interv*. 2009;12(Pt 1):435-442. DOI: [10.1007/978-3-642-04268-3_54](https://link.springer.com/chapter/10.1007/978-3-642-04268-3_54#Abs1).
2. Timoh KN, Huaulme A, Cleary K, et al. A systematic review of annotation for surgical process model analysis based on video. *Surg Endosc*. 2023;37(6):4298-4314. DOI: [10.1007/s00464-023-10041-w](https://pmc.ncbi.nlm.nih.gov/articles/PMC10282964/).
3. Yang S, Zhou F, Mayer L, et al. Large-scale self-supervised video foundation model for intelligent surgery. *npj Digit Med*. 2026;9:220. DOI: [10.1038/s41746-026-02403-0](https://www.nature.com/articles/s41746-026-02403-0).
4. Ye Z, Zhou R, Deng Z, et al. A comprehensive video dataset for surgical laparoscopic action analysis. *Sci Data*. 2025;12:862. DOI: [10.1038/s41597-025-05093-7](https://www.nature.com/articles/s41597-025-05093-7).
5. Timoh KN, Galuret S, et al. International expert consensus-driven surgical process model for robot-assisted hysterectomy: Delphi study results. *Surgical Endoscopy*. 2026;40(1):541-552. DOI: [10.1007/s00464-025-12339-3](https://link.springer.com/article/10.1007/s00464-025-12339-3).
6. SAGES Surgical Video Annotation Standards Industry Data Standard Working Group. SAIIL (SAGES) Surgical Video Annotation Standards Industry Data Standard Working Group. Internal working document. Source: [Local file](../../02. Resources + Publications/SAIIL (SAGES) Surgical Video Annotation Standards Industry Data Standard Working Group (Ozanan Meireles' original ).docx).
7. Mlambo B, Shields M, Bach S, et al. A standardized temporal segmentation framework and annotation resource library in robotic surgery. *Mayo Clin Proc Digit Health*. 2025;3(4):100257. DOI: [10.1016/j.mcpdig.2025.100257](../../02. Resources + Publications/Intuitive_2025 Standardized Framework for Robotic Surgery.pdf).
8. Eckhoff JA, Rosman G, Altieri MS, et al. SAGES consensus recommendations on surgical video data use, structure, and exploration (for research in artificial intelligence, clinical quality improvement, and surgical education). *Surg Endosc*. 2023;37:8690-8707. DOI: [10.1007/s00464-023-10288-3](../../02. Resources + Publications/SAGES consensus recommendations on surgical video data use et al.pdf).
9. Alapatt D, Eckhoff J, Lyu Z, et al. The SAGES Critical View of Safety Challenge: A global benchmark for AI-assisted surgical quality assessment. *arXiv*. 2025. Source: [arXiv:2509.17100](../../02. Resources + Publications/SAGES critical view_AI assisted surgical quality assessment.pdf).
