---
icon: lucide/git-graph
---

# Version Control

## Overview

This guide is going to outline how you are to use Version Control in The Dancer with Diversion.

Before you do anything, you need to ensure you have the Diversion Desktop add installed and the Diversion Plugin working inside Unreal Engine.

These guidelines are mandatory and if you don't follow them your pull request is going to get rejected until it is fixed. 

## Main Branches

The Game will have two primary branches at all times.

| Branch | Purpose                                                                            |
| ------ | ---------------------------------------------------------------------------------- |
| `Main` | Stable branch containing the latest release of the game                            |
| `Dev`  | Main development branch. All new features, fixes and content are merged into here. |

**Rules:**

- Never commit directly to Main or Dev.
- All development work must take place on a separate branch.
- Main should always remain in a stable, working state.
- Dev is the starting point for all normal development.

### Branch Workflow

- `Main`
    - `Dev`
        - `feature/player-movement`
        - `fix/character-collision`
        - `content/forest-environment`
        - `refactor/interaction-system`

I will make it so I am the only one able to touch main or dev. 

## Development Branches

All new branches extending from Dev must follow this format: `BranchType/ShortDescription`
Use lowercase and kebab-case for branch names, anything else will be denied.

### Branch Naming

These names should cover everything you would need, if you feel something is missing let me know, but if it is not on here it won't be accepted.

| Branch Type | Purpose                                | Example                         |
| ----------- | -------------------------------------- | ------------------------------- |
| `feature/`  | New gameplay features or functionality | `feature/player-movement`       |
| `fix/`      | Bug fixes and corrections              | `fix/character-collision`       |
| `content/`  | New or modified game assets            | `content/forest-environment`    |
| `refactor/` | Improving existing code or systems     | `refactor/interaction-system`   |
| `docs/`     | Documentation changes                  | `docs/asset-naming-guide`       |
| `chore/`    | General maintenance and configuration  | `chore/update-project-settings` |
| `test/`     | Experimental changes and testing       | `test/new-movement-system`      |

**Rules:**

- Always create development branches from the latest Dev.
- Use the appropriate branch type.
- Keep names short and descriptive.
- Do not use spaces or special characters.
- Delete branches once they have been successfully merged and are no longer needed.

### Diversion Usage

**Creating a Branch in Diversion:**

1. Switch to the Dev branch.
2. Ensure your workspace is up to date.
3. Open the branch dropdown and select New Branch.
4. Enter your branch name using the naming convention above.
5. Confirm that the branch is being created from Dev.

Diversion will switch you to the newly created branch automatically.

## Working and Committing

Commits need proper names too which might take you some time to get used to.
It is a pain in the ass to update an entire backlog of poorly named commits so take this seriously. 
I won't be super strict on the specific content of a commit for the first month, but if you are bundling multiple different tasks into a single broadly named commit after new years your pull request is going to be denied. 

You might think this is dumb and annoying at first, but when we hit a game breaking issue and need to find the exact source of the problem.
Doing this properly is the difference between spending hours / days searching through months of work from 4 different people versus taking a couple minutes to scan through the commit history. 

**Before committing:**

- Make sure you are working on the correct branch.
- Only include changes relevant to the task.
- Ensure your changes are functioning as expected.
- Write a meaningful commit message.

### Commit Naming Conventions

| Type       | Purpose                       | Example                                               |
| ---------- | ----------------------------- | ----------------------------------------------------- |
| `feat`     | New functionality             | `feat(character): add player sprinting`               |
| `fix`      | Bug fixes                     | `fix(level): correct vine collision`                  |
| `content`  | New or modified game content  | `content(environment): add forest environment assets` |
| `refactor` | Code improvements             | `refactor(gameplay): simplify interaction logic`      |
| `docs`     | Documentation changes         | `docs(guide): add asset naming guide`                 |
| `chore`    | Maintenance and configuration | `chore(settings): update project settings`            |

**Rules:**

- Use lowercase for commit types and descriptions.
- Keep messages clear and concise.
- Describe what the commit changes.
- Avoid vague messages such as changes, update, stuff or fixed things.
- Keep commits focused on logical changes.

## Reviews and Merging

All Pull Requests will be reviewed and merged by me after review.

I will leave you feedback like this if needed: [Pull Request Review](pr_review.md)

Use Diversion's Reviews feature to submit changes for review.

**When creating a Review:**

- Select Dev as the base branch.
- Select your development branch as the branch being reviewed.
- Provide a meaningful title and description.
- Assign the relevant team members as reviewers.
Once approved, the changes can be merged into Dev.

**Rules:**

- Do not merge unfinished or untested work.
- Address requested changes before merging.
- Ensure the relevant reviewers have approved the changes.
- Delete your development branch once merged and no longer needed.

### Merging into Main

Main should only receive changes from Dev through an approved release Review.

Do not merge individual feature branches directly into Main.

### Hotfixes

Hotfixes are urgent fixes required for the stable version of the game, we will hopefully never have to do them but in case we do:

Hotfix branches must be created from Main.

Example: `hotfix/game-crash-on-startup`

Once complete, the hotfix must be reviewed and merged into both Main and Dev to ensure the fix is present in ongoing development.

## Final Notes

Following these conventions is mandatory for all contributors.

Branches and commits should be named consistently so that the project history remains organised and easy to understand.

Changes that do not follow these guidelines **will be rejected** during review and must be corrected before being merged.

> Last Updated: Seán Burke - 21st November 2026