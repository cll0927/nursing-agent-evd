# EVD# EVD Position and Leveling Safety Agent Skill

## 1. Overview

This repository contains a prototype nursing Agent Skill for identifying potential safety risks related to external ventricular drain (EVD) positioning and leveling.

The Skill is designed to transform relevant nursing safety knowledge into a structured, checkable workflow that an AI agent can follow.

The focus is not autonomous clinical decision-making, but information organization, risk identification, safety reminders, and human verification.

## 2. Clinical Scenario

External ventricular drainage requires accurate positioning and leveling of the drainage system relative to the prescribed anatomical reference point.

Patient repositioning or movement of the drainage system may change the relative height between the reference point and the drainage system.

This Skill focuses on:

- Patient position
- EVD reference point
- Prescribed EVD level
- Current drainage system position
- Re-leveling after repositioning
- Drainage changes
- Relevant neurological warning information

## 3. Agent Goal

The Agent should be able to:

1. Identify whether an EVD is present.
2. Identify the patient's current position.
3. Detect recent patient repositioning.
4. Identify the prescribed reference point when documented.
5. Identify the prescribed EVD level when documented.
6. Assess whether current leveling has been confirmed.
7. Identify potential leveling problems.
8. Identify missing or contradictory information.
9. Classify the potential safety risk.
10. Generate a structured safety reminder.
11. Determine whether bedside human verification is required.

## 4. Input

The Skill may use the following information:

### Patient

- Current body position
- Recent repositioning
- Neurological observations
- New or changing symptoms

### EVD

- Presence of EVD
- Prescribed EVD level
- Reference point
- Current drainage system position
- Recent movement of the system

### Leveling information

- Whether leveling has been confirmed
- Whether re-leveling occurred after repositioning
- Whether the current position corresponds to the prescribed configuration

### Clinical information

- Drainage amount or trend
- Sudden drainage changes
- New neurological symptoms
- Other documented warning signs

If the prescribed level or reference point is unavailable, the Agent must not infer or invent it.

## 5. Core Safety Concept

The effective drainage relationship of an EVD depends on the relative height between the drainage system and the prescribed anatomical reference point.

Therefore, a patient position change or movement of the drainage system should trigger reassessment of the leveling status.

The exact reference point and prescribed level must be determined from the applicable clinical order, institutional protocol, or device-specific procedure.

## 6. Core Workflow

The Skill follows a structured workflow:

Confirm EVD
↓
Current patient position
↓
Recent repositioning?
↓
Identify reference point
↓
Identify prescribed EVD level
↓
Assess current leveling
↓
Assess system movement
↓
Assess drainage / neurological warnings
↓
Risk classification
↓
Human verification

The workflow is intended to support consistent and reproducible safety assessment.

## 7. Risk Categories

The Agent classifies the available information into four categories:

### No identified leveling risk

No relevant EVD position or leveling abnormality is identified from the available information.

### Potential leveling risk

A possible problem involving patient repositioning, system movement, or leveling status is identified.

### Urgent human verification required

The available information suggests a potentially significant EVD-related safety concern or concerning neurological change.

### Insufficient information

Important information required for assessment is unavailable or contradictory.

## 8. Output

The Agent produces a structured assessment containing:

- EVD presence
- Current patient position
- Recent repositioning
- Reference point
- Prescribed EVD level
- Current leveling status
- Recent system movement
- Drainage change
- Neurological warning information
- Risk classification
- Reason for classification
- Human verification requirement

This structure makes the Agent's output easier to inspect and evaluate.

## 9. Safety Boundaries

This Skill is a decision-support component.

The Agent must not independently:

- Determine or change the prescribed EVD level
- Raise or lower the drainage system
- Clamp or unclamp the EVD
- Open or close the EVD system
- Diagnose hydrocephalus
- Diagnose intracranial hypertension
- Diagnose overdrainage or underdrainage
- Modify physician orders

When a potential high-risk situation is identified, the Agent should prompt qualified healthcare professionals to perform bedside assessment.

## 10. Human Oversight

The Agent is responsible for:

- Organizing information
- Detecting potential position-related risks
- Identifying possible leveling problems
- Explaining why a risk was identified
- Identifying missing information
- Prompting human verification

Qualified healthcare professionals remain responsible for bedside assessment and clinical decisions.

## 11. Intended Use

This Skill is intended for:

- Nursing informatics research
- Nursing education
- Clinical simulation
- Prototype nursing Agents
- Human-AI collaboration research
- Structured clinical reasoning research

It is not intended to function as an independent clinical decision-making system.

## 12. Repository Structure

nursing-agent-evd-safety/
│
├── README.md
└── SKILL.md

## 13. Version

Version: v1.0

Status: Prototype

This repository is intended for research and educational development.
