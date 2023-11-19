# Cofundable's architecture decision records (ADRs)

This repository stores a copy of all of Cofundable's architecture decision records, so that they can be managed, searched, and discovered in one place.

## About ADRs

### Why do we need to document architecture decisions?

Developing software involves making lots of decisions. Documenting these decisions and their outcomes achieves several important goals:

1. **Communication and collaboration:** It helps facilitate communication among team members and stakeholders and creates share a common understanding of Cofundable's architecture, components, and history.
2. **Decision Transparency:** It provides greater insight into the choices made throughout the project, helping team members and stakeholders understand the factors considered, alternatives evaluated, and the trade-offs involved in the decision-making process.
3. **Risk Management:** It also helps manage risk by encouraging project stakeholders to assess the potential impact of architectural changes, identify dependencies, and evaluate the consequences of modifying specific components.
4. **Improved Maintainability and Adaptability:** Good documentation enables future maintainers to modify or extend the codebase in a consistent and coherent manner, reducing the risk of introducing unintended side effects or architectural drift.
6. **Onboarding and Knowledge Transfer:** When new team members join a project, documentation also serves as a valuable resource for onboarding. It provides insights into the design choices, patterns, and best practices employed in the codebase.

### What constitutes an architecture decision?

Almost all of engineering and code development involves making choices, so how do you know when a particular choices rises to the level of an architecture decision and requires an ADR?

> An Architectural Decision (AD) is a software design choice that addresses a functional or non-functional requirement that is architecturally significant.
>
> Source: [ADR GitHub Organization](adr)

Another way to recognize when making a decision related to your project constitutes an architecture decision is to ask yourself three questions about that decision:

1. Does this decision affect the structure, direction, or outcome of the project?
2. Would someone unfamiliar with the project ask me to explain why I made this decision?
3. Were there other viable alternatives I could have chosen?

If you answer "Yes" to at least one of these questions, then you've likely just made an architectural decision, and you should create an ADR to explain why you made that choice. Other contributors (and your future self) will thank you for it.

### Examples of architecture decisions

While architecture decisions come in all shapes and sizes, some common examples include:

- Setting up the repository's main file structure
- Selecting a critical library, tool, or platform
- Adopting a certain analytical framework or algorithm
- Choosing _not_ to build a particular feature

### ADR process

When an architectural decision needs to be recorded, please use the following steps:

1. [Create a new ADR ticket in GitHub](https://github.com/cofundable/decisions/issues/new/choose)
2. Identify the approvers for this decision, i.e. individuals or groups who must sign off on the decision before the ADR can be merged (ideally this happens before work starts on the ADR)
3. Draft an ADR in a branch named after the ticket, then open a Pull Request (PR)
   - Use the `{YYYY-MM-DD}-{description}.md` naming convention and copy the [template](./template.md) into the [adr](./adr/) directory (name the file with the date it was created, which may differ from the date the decision was made, PR was merged, or file was last modified)
   - The ADR should use the status "Active"
   - If this decision replaces an existing ADR, update its status to indicate the reason (e.g. `"Superseded By [xxx](yyyymmdd-xxx.md)"`)
4. Invite the approvers to review the PR and provide feedback or approve the decision
5. Once the approvers have signed off on the decision, merge the PR into the `main` branch
6. Create any follow-up tickets that are needed to implement the decision outlined in the ADR (if necessary)

### Acknowledgements and Further Reading

- [ADR GitHub Organization](adr)
- [Joel Parker Henderson's ADR repo](joel)
- [GitHub Blog - Why Write ADRs](github)

[adr]: https://adr.github.io/
[joel]: https://github.com/joelparkerhenderson/architecture-decision-record#what-is-an-architecture-decision-record
[github]: https://github.blog/2020-08-13-why-write-adrs/

## Maintainers

- [@widal001](https://github.com/widal001)
