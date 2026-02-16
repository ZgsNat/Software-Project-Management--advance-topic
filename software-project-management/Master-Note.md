# Smart Driving School (SDS)

## Smart Booking & Allotment Management Sub-system

---

## 1. Project Context

### 1.1 Background

Smart Driving School (SDS) aims to modernise the driving skill training business in Vietnam by leveraging advanced technologies to improve learner experience, operational efficiency, and business scalability.

Due to the complexity of operations and increasing demand, SDS engages the project team as a consultant to analyse, design, and propose a suitable solution using an Agile approach.

### 1.2 Selected Objective

**Smart Booking & Allotment Management** has been selected as the focus objective for this project.

The sub-system addresses the challenges of:

* Managing learner driver bookings
* Allocating instructors efficiently
* Scheduling training sessions (1-hour sessions, maximum 3 learners)
* Forecasting training demand to optimise resources

---

## 2. Sub-system Definition

### 2.1 Sub-system Overview

The Smart Booking & Allotment Management sub-system is responsible for coordinating learner bookings, instructor availability, and session scheduling, supported by AI-driven demand forecasting at a conceptual level.

### 2.2 In-scope

* Booking and rescheduling of training sessions
* Instructor availability management
* Learner–instructor allotment logic
* Demand forecasting (conceptual design)
* Conflict detection and resolution
* Management-level reporting

### 2.3 Out-of-scope

* Payment processing
* Pricing algorithms
* Low-level AI/ML model implementation
* UI/UX design for mobile or web applications

---

## 3. Project Approach

### 3.1 Agile Suitability

An Agile approach is selected due to:

* Evolving requirements
* Need for incremental validation
* Stakeholder feedback through iterative deliverables

The project follows multiple sprints to gradually refine analysis, design, and testing artifacts.

### 3.2 Deliverables

The final assessment consists of:

1. A Jira project (backlog, sprint planning, task tracking)
2. A Confluence workspace (analysis, design, and testing documentation)

This repository supports the creation and organisation of those deliverables.

---

## 4. Sprint Structure Overview

### Sprint 0 – Initiation & Planning

**Purpose:** Define direction and feasibility

Key outcomes:

* Sub-system selection and justification
* Business values and stakeholders
* High-level requirements
* Agile suitability analysis
* Project Plan (Confluence template)

Reference folder:

```
02-sprint-0-initiation-planning/
```

---

### Sprint 1 – Analysis

**Purpose:** Understand the problem domain

Key outcomes:

* User stories
* Use case diagrams and specifications
* Domain model

Reference folder:

```
03-sprint-1-analysis/
```

---

### Sprint 2 – Design

**Purpose:** Define the system solution

Key outcomes:

* System architecture
* Sequence diagrams
* Data model
* Business rules

Reference folder:

```
04-sprint-2-design/
```

---

### Sprint 3 – Testing & Refinement

**Purpose:** Validate the proposed design

Key outcomes:

* Test strategy
* Test cases
* Traceability matrix
* Risk and issue analysis

Reference folder:

```
05-sprint-3-testing-refinement/
```

---

## 5. Repository Structure Guide

This repository is structured to reflect the project lifecycle rather than course materials.

Key folders:

* `00-project-overview/`: Problem statement, goals, and scope
* `01-subsystem-definition/`: Strategic decisions and assumptions
* `02–05`: Sprint-based artifacts
* `06-jira-confluence/`: Mapping between repository, Jira, and Confluence
* `07-meeting-mentor-prep/`: Mentor session preparation and feedback

---

## 6. Usage Guidelines for Team Members

* Start by reading this Master Note
* Review `00-project-overview/` and `01-subsystem-definition/` for context
* Work only within assigned sprint folders
* Ensure all artifacts are traceable to Jira issues and Confluence pages

---

## 7. Living Document Notice

This Master Note is a living document.
It will be updated as:

* Project understanding evolves
* Mentor feedback is received
* Sprint outcomes are refined

All team members are expected to align their work with this structure.
