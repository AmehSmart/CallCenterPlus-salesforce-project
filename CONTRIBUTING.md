# Contributing to CallCenterPlus (CCP) Salesforce Project

## Branches

- `main` — Production-ready code. Only updated via merges from `dev`. Never push directly.
- `dev` — The primary working and integration branch. All feature branches start from here and merge back into here.
- Feature branches: `feature/CCP-<Issue-Number>-short-description`
  - Example: `feature/CCP-12-agent-console-lwc`
  - Example: `feature/CCP-45-case-routing-trigger`

## Workflow

1. Pull the latest `dev` (`git pull origin dev`).
2. Create your branch from `dev`: `git checkout -b feature/CCP-XXX-your-feature-name`.
3. Commit your work with clear, descriptive messages (e.g., `"Add CCP_CaseRoutingService and test classes"`).
4. Push your branch and open a Pull Request (PR) into `dev`.
5. Get **at least 1 peer review/approval** from the collaborator team before merging.
6. Delete your branch after it's successfully merged.

## Code Review & Salesforce Standards

- **Naming Conventions:** All custom Apex classes, triggers, and objects must follow the `CCP_` prefix standard (e.g., `CCP_CaseController`, `ccpCallTimer`).
- **Test Coverage:** All Apex classes must meet or exceed Salesforce's minimum code coverage requirement (target 85%+ for new `CCP_` components).
- **Peer Review:** Ensure debug logs (`System.debug`) are cleaned up and your code passes linting before requesting review.

## Environment & Secrets Handling

- **Never commit real credentials, SFDX auth files, security tokens, or environment secrets.**
- Keep sensitive configuration files excluded via `.gitignore` (`.sfdx/`, `.sf/`, `local.json`, `.env`).
- Request sandbox or developer scratch org credentials from the project lead if you do not have them.

## Adding New Components & Directories

- Add new Lightning Web Components or Apex classes inside `force-app/main/default/` structure only when you are actively building them.
- Re-use existing shared components or utility classes across the project where possible instead of duplicating logic.
