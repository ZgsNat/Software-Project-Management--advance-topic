# Software Project Management — Folder Structure ✅

This document lists the repository layout and explains the purpose of each folder and markdown file. Use it as a quick reference for where to find and place artifacts for each sprint.

---

```
software-project-management/
├─ Master-Note.md            # Project overview and navigation
├─ Folder-Structure.md       # (this file) repo layout + descriptions
├─ 00-project-overview/
│  ├─ README.md              # Intro to project overview folder
│  ├─ problem-statement.md   # Problem description and context
│  ├─ business-goals.md      # Business objectives and success metrics
│  └─ scope-in-out.md        # In-scope and out-of-scope items
├─ 01-subsystem-definition/
│  ├─ subsystem-overview.md  # High-level sub-system description
│  ├─ stakeholders.md        # Stakeholder list, concerns, RACI info
│  ├─ business-values.md     # Business value proposition and KPIs
│  └─ assumptions-constraints.md # Project assumptions & constraints
├─ 02-sprint-0-initiation-planning/
│  ├─ sprint-0-objective.md  # Goals and deliverables for Sprint 0
│  ├─ requirements-analysis.md # Methods and initial requirement list
│  ├─ agile-suitability.md   # Why Agile is suitable and considerations
│  ├─ project-plan-outline.md# High-level plan, milestones, timeline
│  └─ references.md          # External sources and Confluence links
├─ 03-sprint-1-analysis/
│  ├─ user-stories.md        # Prioritised user stories + acceptance criteria
│  ├─ use-case-diagram.md    # Use case diagrams and actor mappings
│  ├─ use-case-specifications.md # Detailed use case flows and variants
│  ├─ domain-model.md        # Domain entities and relationships (UML)
│  └─ sprint-1-summary.md    # Sprint 1 outcomes and action items
├─ 04-sprint-2-design/
│  ├─ system-architecture.md # High-level architecture, components, diagrams
│  ├─ sequence-diagrams.md   # Interaction flows (PlantUML / images)
│  ├─ data-model.md          # ER diagrams, table definitions
│  ├─ business-rules.md      # Formalised business rules and constraints
│  └─ sprint-2-summary.md    # Sprint 2 outcomes and decisions
├─ 05-sprint-3-testing-refinement/
│  ├─ test-strategy.md       # Testing approach, environments, and scope
│  ├─ test-cases.md          # Test cases, steps, expected results
│  ├─ traceability-matrix.md # Map stories → tests → acceptance criteria
│  ├─ risks-issues.md        # Risk register and open issues
│  └─ sprint-3-summary.md    # Sprint 3 results and next steps
├─ 06-jira-confluence/
│  ├─ jira-structure.md      # Recommended Jira setup and workflows
│  ├─ sprint-backlog-mapping.md # Mapping repo artifacts to Jira items
│  └─ confluence-page-map.md # Confluence page templates and layout
└─ 07-meeting-mentor-prep/
   ├─ mentor-session-1.md    # Agenda, notes, feedback, actions
   ├─ mentor-session-2.md
   └─ mentor-session-3.md
```

---

Highlights & Usage Tips 🔧

- **Start** by reading `Master-Note.md` to get project context and navigation.  
- **Place** analysis/design/testing artifacts in the corresponding sprint folder.  
- **Keep** each file concise and include a `Status: Draft` and `TODO` section for visibility.  
- **Traceability:** update `traceability-matrix.md` when you add/modify user stories or test cases.

---

If you want, I can add templates for:  
- Acceptance criteria checklist,  
- Test case table,  
- Traceability matrix CSV/table — pick one and I’ll add it to the appropriate file. ✨
