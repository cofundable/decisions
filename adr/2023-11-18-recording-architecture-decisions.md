---

status: active
last_modified: 2023-11-18
related_issue: null
replaced_by: null
deciders:
  - "@widal001"
tags:
  - "decision-records"
  - "docs"
  - "knowledge-management"

---

# Recording Architecture Decisions

- **Status:** Active
- **Last Modified:** 2023-06-26
- **Related Issue:** [#34](https://github.com/HHS/simpler-grants-gov/issues/34)
- **Deciders:** Lucas Brown, Aaron Couch, Billy Daly
- **Tags:** ADRs

## Overview

### Problem Statement

Important decisions about the structure of a codebase, the tools or platforms adopted, and the scope or vision of a product are made all throughout a project's lifecycle. Often these decisions are made and changed blindly with little record of why that decision was made, making it difficult for other collaborators and even the original decision makers to understand the justification behind that decision in the future.

_What is the best way to document key architectural decisions made within the project so that future contributors can understand the justification for those decisions?_

### Decision Drivers
<!-- RECOMMENDED -->

- **Explicit:** Important decisions about the project architecture should be clear and unambiguous
- **Documented:** There should be a written record describing which decisions are made
- **Discoverable:** Decision records should be centrally located and easy to discover or search
- **Accessible:** Decision records should be accessible to non-technical audiences
- **Portable:** The decision records should be able to travel with the code when it's forked, cloned, etc.
- **Maintainable:** The system we adopt should be easy to maintain or amend as needed.

### Options Considered

- Architecture decision records (ADRs) in a central repository
- ADRs in a `docs/adr/` folder in the repository that the decision is relevant to
- Comments and docstrings in the code itself
- Articles in the public docs

### Decision Outcome
<!-- REQUIRED -->

**ADRs in a central repository**

Decisions will be documented using Architecture Decision Records (ADRs) as described by [Joel Parker Henderson](joel) and the [ADR GitHub organization](https://adr.github.io/). The template for this project's ADRs will be adapted from the [MADR template](adrs). These ADRs will be stored in the `adr/` folder of this repository.

**NOTE:** We may want to revisit this decision to reconsider storing them in the public docs once the docs are set up. Ideally ADRs could be drafted/edited and visible in the public docs (or another website) but also synced with the repo -- some wiki solutions provide this option.

#### Positive Consequences
<!-- OPTIONAL -->

- ADRs will be stored in a centralized location, making them easier to search and discover
- ADRs can be managed with a workflow based on issues and pull requests
- Changes to ADRs will be listed in the project's commit history
- If, in the future, we wanted to display the ADRs in a more user-friendly format, we could easily render them as a simple static site hosted on GitHub pages

#### Negative Consequences
<!-- OPTIONAL -->

- Certain urgent decisions may take longer to finalize if they need to be documented and agreed upon, slowing down the process of finalizing key decisions with the project
- Unless regularly maintained and complied with, it could be easy for the ADRs to become out of sync with the actual decisions made about the architecture
- ADRs will be separate from the code that they are describing
- Non-technical users may have a more challenging time creating and editing ADRs if they are not familiar with Markdown or GitHub

## Evaluation
<!-- OPTIONAL -->

### Comparison matrix

**Matrix legend**

- ✅ Condition is fully satisfied
- 🟡 Condition is partially met or unclear
- ❌ Condition is not met

| Criteria            | Central ADR Repo | ADRs per repo | Docstrings | Public docs |
| ------------------- | :--------------: | :-----------: | :--------: | :---------: |
| Explicit            |        ✅        |      ✅       |     ✅     |     ✅      |
| Publicly Documented |        ✅        |      ✅       |     ✅     |     ✅      |
| Accessible          |        🟡        |      🟡       |     ❌     |     ✅      |
| Discoverable        |        ✅        |      ❌       |     ❌     |     ✅      |
| Portable            |        🟡        |      ✅       |     ✅     |     🟡      |
| Maintainable        |        ✅        |      ❌       |     ❌     |     🟡      |

### ADRs in the code repos

Using the ADR framework but storing ADRs in the code repository that they're describing.

- **Pro**
  - ADRs live closer to the code that they pertain to
  - ADRs travel with the code when it's forked, cloned, etc.
  - ADRs can be version controlled in the same codebase
- **Cons**
  - Not very accessible to non-technical audiences
  - Not centralized and difficult to search for, especially with multiple microservices
  - Harder to see the sequential evolution of decisions than in a centralized repo
  - Harder to maintain with a microservices-based architecture

### Comments and Docstrings

Recording decisions as docstrings and comments in the code itself.

- **Pro**
  - Decisions live alongside the code that implements them
  - Docstrings travel with the code when it's forked, cloned, etc.
  - Changes to docstrings and comments are part of the commit history
- **Cons**
  - Very inaccessible to non-technical audiences
  - Least centralized and hardest to search for
  - Nearly impossible to see the sequential evolution of decisions
  - Record of history will be lost if a repo is archived

### Public docs

Documenting decisions as pages or articles in Cofundable's public.

- **Pro**
  - Decisions recorded in the public docs will be easy to discover and search
  - Public docs will be more accessible to users than markdown stored in GitHub
- **Cons**
  - Changes to the public docs aren't easily integrated into a PR and Issue workflow
  - Depending on the public docs platform we choose it may be hard to automate the maintenance and indexing of ADRs

## Links <!-- OPTIONAL -->

- [ADR GitHub Organization](adr)
- [Joel Parker Henderson's ADR repo](joel)
- [GitHub Blog - Why Write ADRs](github)

[adr]: https://adr.github.io/
[joel]: https://github.com/joelparkerhenderson/architecture-decision-record#what-is-an-architecture-decision-record
[madr]: https://adr.github.io/madr/#the-template
[github]: https://github.blog/2020-08-13-why-write-adrs/
