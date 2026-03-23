**Surgical video data standard**
**v0.9.1** 

# Change log

- Mar 19, 2026: initial version (for collaborators; e.g., AWS team) *italic font indicates content to be expanded later or comments to colaborators*

# Introduction

Video annotation standard in the field of Robotic Assisted Surgery (RAS) aims to facilitate progress in the field.

## Terms describing surgical activity

This section defines the semantic levels used to describe surgical activity. 

A **Phase** is a high-level, temporally contiguous segment describing the overall stage of operative progression (macro workflow). Phases are designed to be broadly applicable and interpretable.

A **Step** is a procedure-specific milestone required to complete a given operation (e.g., identify cystic duct in laparoscopic cholecystectomy). 

A **Task** is a goal-oriented functional activity that may recur across procedures (e.g., control bleeding, expose target anatomy). 

An **Action** is an atomic, directly observable, verb-only maneuver (e.g., cut, grasp, retract). Actions are high-frequency and form the foundation for computational learning.

### How they relate

Surgical procedures can be understood as a compositional process like assembling a structure from reusable building blocks:

- **Actions** are the atomic building blocks (directly observable maneuvers).
- Sequences of **Actions** form **Tasks** (goal-oriented functional activities).
- Tasks aggregate into procedure-specific **Steps** (milestones of a particular operation).
- Steps combine into higher-level **Phases** (macro progression of surgery).

# Schema

## General principles

Timestamp is a key organizing principle for annotation. At least one timestamp is required (start_time). If an interval is annotated, the end_time is also included.
Annotations

## Description

*non-programmer description of schema will be added here later*

# Technical implementation

To test implementation, standard is implemented using JSON and JSON schema. Other technical implementations are possible and may be included in future versions. 

*AWS team can further experiment with YAML, XML schema or other implementations*
*For implementation format, also it is possible to be inspired how it is solved by HL7 FHIR*

## Implementation phases

The standard assumes a gradual icrease in complexity and a gradual implementation in phases. Note that term phase in implementation is distinct from phase defined above.

PHASE 1:
milestones
	1. access
	2. surgical objectives
	3. closure

action - cut, grasp, retract, suture, staple, cauterize, clip

idle-ness in video

PHASE 2:
mechanism for defining and/or restricting the permissible values used in annotation

PHASE 3:
task boundaries
procedure basic metadata

PHASE 4:
general anatomy (linked to action)

PHASE 5:
tool use (anotate which tool is used by surgeon)

PHASE 6:
type of surgery 

PHASE 7:
annotation of tissue on which the tool interacts on

# What is out of scope

- complex terminology considerations (to avoid the risk that such discussion will delay consensus for using the standard and delay the standard's adoption)
- frame annotations (annotate what is visible in a given video frame). Only relevant items for the surgery are of importance. A relevant related information is in Segmentation section of the page at [https://www.cvschallenge.org/the-challenge-2](https://www.cvschallenge.org/the-challenge-2)
- any anotation of surgical skill assesment

