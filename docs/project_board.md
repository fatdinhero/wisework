# GitHub Project Board Template for WiseWork

This document provides a template for setting up a GitHub Project Board to track the development of WiseWork from PoC to MVP. The board is organized into columns representing different stages of work, with issues assigned to each column based on priority and dependencies.

## Board Structure

```
+---------------+---------------+---------------+---------------+---------------+
|    Backlog    | Ready for Dev |  In Progress  |  For Review   |     Done      |
+---------------+---------------+---------------+---------------+---------------+
| Future issues | Prioritized   | Currently     | Completed but | Completed and |
| and features  | and ready to  | being worked  | needs review  | accepted      |
| not yet       | be picked up  | on by team    | and testing   | tasks         |
| prioritized   | by developers | members       |               |               |
+---------------+---------------+---------------+---------------+---------------+
```

## Board Columns

### 1. Backlog
Issues that have been identified but are not yet ready for development or are planned for future phases.

### 2. Ready for Dev
Issues that are fully specified, prioritized, and ready to be picked up by developers. All dependencies are resolved.

### 3. In Progress
Issues currently being worked on by team members. Each issue should have an assignee.

### 4. For Review
Completed issues that need code review, testing, or other forms of verification before being considered done.

### 5. Done
Issues that have been completed, reviewed, and accepted.

## Initial Board Setup for PoC Phase

Below is the recommended initial setup for the project board, focusing on the PoC phase. Issues are referenced by their numbers from the GitHub Project Issue List.

### Backlog

Issues planned for Alpha or MVP phases, or lower priority PoC issues:

```json
[
  {
    "issue_number": 9,
    "title": "Implement proof revision tracking",
    "labels": ["backend"],
    "milestone": "PoC",
    "priority": "Low"
  },
  {
    "issue_number": 12,
    "title": "Deploy smart contracts to testnet",
    "labels": ["blockchain", "devops"],
    "milestone": "PoC",
    "priority": "Medium"
  },
  {
    "issue_number": 15,
    "title": "Implement reputation API endpoints",
    "labels": ["backend", "api"],
    "milestone": "PoC",
    "priority": "Medium"
  },
  {
    "issue_number": 16,
    "title": "Add API authentication and authorization",
    "labels": ["backend", "api", "security"],
    "milestone": "PoC",
    "priority": "Medium"
  },
  {
    "issue_number": 19,
    "title": "Implement anti-gaming measures",
    "labels": ["backend", "reputation", "security"],
    "milestone": "PoC",
    "priority": "Low"
  },
  {
    "issue_number": 21,
    "title": "Implement proof visualization components",
    "labels": ["frontend"],
    "milestone": "PoC",
    "priority": "Medium"
  },
  {
    "issue_number": 22,
    "title": "Build user profile and reputation UI",
    "labels": ["frontend"],
    "milestone": "PoC",
    "priority": "Medium"
  },
  {
    "issue_number": 23,
    "title": "Implement authentication UI",
    "labels": ["frontend", "security"],
    "milestone": "PoC",
    "priority": "Medium"
  },
  {
    "issue_number": 24,
    "title": "Set up end-to-end testing framework",
    "labels": ["testing", "devops"],
    "milestone": "PoC",
    "priority": "Medium"
  },
  {
    "issue_number": 25,
    "title": "Implement GitHub integration for code contributions",
    "labels": ["integration", "backend"],
    "milestone": "Alpha",
    "priority": "High"
  },
  {
    "issue_number": 27,
    "title": "Implement continuous integration with GitHub Actions",
    "labels": ["devops", "testing"],
    "milestone": "PoC",
    "priority": "Medium"
  },
  {
    "issue_number": 28,
    "title": "Create API documentation",
    "labels": ["documentation", "api"],
    "milestone": "PoC",
    "priority": "Medium"
  },
  {
    "issue_number": 30,
    "title": "Create user documentation",
    "labels": ["documentation"],
    "milestone": "Alpha",
    "priority": "Medium"
  }
]
```

### Ready for Dev

First priority issues to start the PoC development:

```json
[
  {
    "issue_number": 1,
    "title": "Set up AI validation pipeline architecture",
    "labels": ["ai", "architecture", "backend", "high-priority"],
    "milestone": "PoC",
    "priority": "High",
    "notes": "Foundation for validation module, should be started first"
  },
  {
    "issue_number": 6,
    "title": "Define proof data models",
    "labels": ["backend", "data-models", "high-priority"],
    "milestone": "PoC",
    "priority": "High",
    "notes": "Foundation for proof module, can be started in parallel with #1"
  },
  {
    "issue_number": 10,
    "title": "Implement WiseWorkProofRegistry smart contract",
    "labels": ["blockchain", "smart-contracts", "high-priority"],
    "milestone": "PoC",
    "priority": "High",
    "notes": "Foundation for blockchain integration, can be started in parallel"
  },
  {
    "issue_number": 26,
    "title": "Create Docker development environment",
    "labels": ["devops", "documentation"],
    "milestone": "PoC",
    "priority": "High",
    "notes": "Needed for consistent development environment"
  },
  {
    "issue_number": 29,
    "title": "Write developer onboarding guide",
    "labels": ["documentation", "high-priority"],
    "milestone": "PoC",
    "priority": "High",
    "notes": "Critical for new developer onboarding"
  }
]
```

### In Progress

Initial issues that would be in progress at the start of development:

```json
[
  {
    "issue_number": 2,
    "title": "Implement GPT-4o validation strategy",
    "labels": ["ai", "backend", "high-priority"],
    "milestone": "PoC",
    "priority": "High",
    "assignee": "ai-lead",
    "notes": "Core validation implementation"
  },
  {
    "issue_number": 7,
    "title": "Implement proof repository interface and MongoDB implementation",
    "labels": ["backend", "database", "high-priority"],
    "milestone": "PoC",
    "priority": "High",
    "assignee": "backend-lead",
    "notes": "Storage implementation for proofs"
  }
]
```

### For Review

Empty at project start, but would contain completed issues awaiting review:

```json
[]
```

### Done

Empty at project start, but would contain completed and accepted issues:

```json
[]
```

## PoC Development Flow

The following sequence shows how issues should flow through the board during PoC development:

### Week 1-2: Core Validation

1. Move #1 (AI validation pipeline architecture) and #2 (GPT-4o validation strategy) to In Progress
2. Move #3 (Validation criteria) and #4 (Contribution preprocessing) to Ready for Dev
3. As #1 completes, move to For Review, then Done
4. Start #3 and #4, moving them to In Progress
5. As they complete, move to For Review, then Done

### Week 2-3: Proof Storage

1. Move #6 (Proof data models) and #7 (Proof repository) to In Progress
2. Move #8 (Proof service layer) to Ready for Dev
3. As #6 and #7 complete, move to For Review, then Done
4. Start #8, moving it to In Progress
5. As it completes, move to For Review, then Done

### Week 3-4: Basic Reputation & Smart Contracts

1. Move #10 (WiseWorkProofRegistry contract) to In Progress
2. Move #17 (Basic reputation calculator) and #18 (Simple mock reputation system) to Ready for Dev
3. As #10 completes, move to For Review, then Done
4. Start #17 and #18, moving them to In Progress
5. As they complete, move to For Review, then Done

### Week 4-5: API Layer

1. Move #13 (Contribution API endpoints) and #14 (Proof API endpoints) to Ready for Dev, then In Progress
2. As they complete, move to For Review, then Done

### Week 5-6: Blockchain Anchoring

1. Move #11 (Blockchain service for proof anchoring) to Ready for Dev, then In Progress
2. As it completes, move to For Review, then Done

### Week 6-8: Frontend & Integration

1. Move #20 (Contribution submission UI) to Ready for Dev, then In Progress
2. Move #31 (PoC Integration) to Ready for Dev
3. As #20 completes, move to For Review, then Done
4. Start #31, moving it to In Progress
5. Move #32 (PoC Testing) and #33 (PoC Documentation) to Ready for Dev
6. As #31 completes, move to For Review, then Done
7. Start #32 and #33, moving them to In Progress
8. As they complete, move to For Review, then Done

## Automation Rules

GitHub Projects supports automation rules. The following rules are recommended:

1. **New Issues**: Automatically add new issues to the Backlog column
2. **Assigned Issues**: When an issue is assigned, move it to In Progress
3. **Pull Requests**: When a PR is linked to an issue, move the issue to For Review
4. **Merged PRs**: When a PR is merged, move the linked issue to Done

## Labels for Filtering

The board should use the following labels for filtering:

- **Priority**: `high-priority`, `medium-priority`, `low-priority`
- **Type**: `backend`, `frontend`, `blockchain`, `ai`, `devops`, `documentation`, `testing`
- **Milestone**: `PoC`, `Alpha`, `MVP`
- **Status**: `blocked`, `needs-discussion`, `ready-for-review`

## Views

Create the following saved views:

1. **PoC Focus**: Filter to show only `PoC` milestone issues
2. **High Priority**: Filter to show only `high-priority` issues
3. **By Module**: Group issues by type labels
4. **Blocked Issues**: Filter to show only `blocked` status issues

## Using This Template

To implement this project board in GitHub:

1. Create a new Project (beta) in your repository
2. Set up the columns as described above
3. Add the automation rules
4. Create the labels and apply them to issues
5. Create the saved views
6. Import or create the issues
7. Assign issues to the appropriate columns

This board structure provides visibility into the development process and helps manage the flow of work from backlog to completion, with a focus on the PoC phase and the critical path for development.

> Licensed under CC BY 4.0
