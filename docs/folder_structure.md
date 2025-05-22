# WiseWork Repository Folder Structure

This document outlines the recommended folder structure for the WiseWork repository, designed to support modular development, clear separation of concerns, and scalability from PoC to MVP.

## Root Directory Structure

```
wisework/
├── ai-validation/             # AI validation pipeline
├── api/                       # API layer
├── blockchain/                # Blockchain integration
├── common/                    # Shared utilities
├── docs/                      # Documentation
├── frontend/                  # Web frontend
├── governance/                # Governance system
├── integrations/              # External integrations
├── proofs/                    # Proof of Contribution module
├── reputation/                # Reputation system
├── scripts/                   # Development and deployment scripts
├── tests/                     # End-to-end and integration tests
├── .github/                   # GitHub workflows and templates
├── .gitignore                 # Git ignore file
├── .env.example               # Example environment variables
├── docker-compose.yml         # Docker Compose configuration
├── package.json               # Node.js package configuration
├── pyproject.toml             # Python project configuration
├── README.md                  # Project overview
└── CONTRIBUTING.md            # Contribution guidelines
```

## Module Directory Structures

### AI Validation Module

```
ai-validation/
├── __init__.py                # Package initialization
├── config.py                  # Module configuration
├── models/                    # Model interfaces and wrappers
│   ├── __init__.py
│   ├── base.py                # Base model interface
│   ├── gpt.py                 # GPT model implementation
│   ├── llama.py               # Llama model implementation
│   └── factory.py             # Model factory
├── pipelines/                 # Validation pipelines
│   ├── __init__.py
│   ├── base.py                # Base pipeline
│   ├── contribution.py        # General contribution pipeline
│   ├── code.py                # Code contribution pipeline
│   └── thought.py             # Thought contribution pipeline
├── processors/                # Input/output processors
│   ├── __init__.py
│   ├── preprocessor.py        # Input preprocessing
│   ├── postprocessor.py       # Output postprocessing
│   └── context.py             # Context gathering
├── criteria/                  # Validation criteria
│   ├── __init__.py
│   ├── base.py                # Base criteria
│   ├── contribution.py        # General contribution criteria
│   ├── code.py                # Code contribution criteria
│   └── thought.py             # Thought contribution criteria
├── prompts/                   # Prompt templates
│   ├── __init__.py
│   ├── base.py                # Base prompt template
│   ├── validation.py          # Validation prompts
│   └── extraction.py          # Insight extraction prompts
└── tests/                     # Module tests
    ├── __init__.py
    ├── test_models.py
    ├── test_pipelines.py
    ├── test_processors.py
    └── test_criteria.py
```

### Proofs Module

```
proofs/
├── __init__.py                # Package initialization
├── config.py                  # Module configuration
├── models/                    # Proof data models
│   ├── __init__.py
│   ├── proof.py               # Proof model
│   ├── validation.py          # Validation result model
│   └── contributor.py         # Contributor reference model
├── repositories/              # Storage implementations
│   ├── __init__.py
│   ├── base.py                # Base repository interface
│   ├── mongodb.py             # MongoDB implementation
│   └── factory.py             # Repository factory
├── services/                  # Business logic
│   ├── __init__.py
│   ├── proof_service.py       # Proof service
│   ├── verification.py        # Verification service
│   └── factory.py             # Service factory
├── validators/                # Proof validation logic
│   ├── __init__.py
│   ├── base.py                # Base validator
│   ├── schema.py              # Schema validator
│   └── integrity.py           # Integrity validator
└── tests/                     # Module tests
    ├── __init__.py
    ├── test_models.py
    ├── test_repositories.py
    ├── test_services.py
    └── test_validators.py
```

### Blockchain Module

```
blockchain/
├── contracts/                 # Smart contracts
│   ├── WiseWorkProofRegistry.sol  # Proof registry contract
│   ├── ReputationOracle.sol       # Reputation oracle contract
│   └── Governance.sol             # Governance contract
├── scripts/                   # Deployment scripts
│   ├── deploy.js              # Deployment script
│   ├── verify.js              # Contract verification
│   └── setup.js               # Initial setup
├── tests/                     # Contract tests
│   ├── ProofRegistry.test.js  # Proof registry tests
│   ├── ReputationOracle.test.js  # Reputation oracle tests
│   └── Governance.test.js     # Governance tests
├── services/                  # Blockchain interaction services
│   ├── __init__.py
│   ├── anchoring.py           # Proof anchoring service
│   ├── verification.py        # Blockchain verification
│   └── transaction.py         # Transaction management
├── abis/                      # Contract ABIs
│   ├── WiseWorkProofRegistry.json
│   ├── ReputationOracle.json
│   └── Governance.json
├── hardhat.config.js          # Hardhat configuration
└── package.json               # Node.js package for contracts
```

### API Module

```
api/
├── __init__.py                # Package initialization
├── main.py                    # API entry point
├── config.py                  # API configuration
├── routes/                    # API endpoints
│   ├── __init__.py
│   ├── contributions.py       # Contribution endpoints
│   ├── proofs.py              # Proof endpoints
│   ├── reputation.py          # Reputation endpoints
│   └── auth.py                # Authentication endpoints
├── middleware/                # API middleware
│   ├── __init__.py
│   ├── auth.py                # Authentication middleware
│   ├── logging.py             # Logging middleware
│   └── error.py               # Error handling middleware
├── schemas/                   # API data models
│   ├── __init__.py
│   ├── contribution.py        # Contribution schemas
│   ├── proof.py               # Proof schemas
│   ├── reputation.py          # Reputation schemas
│   └── auth.py                # Authentication schemas
├── services/                  # Service interfaces
│   ├── __init__.py
│   ├── contribution.py        # Contribution service
│   ├── proof.py               # Proof service
│   ├── reputation.py          # Reputation service
│   └── auth.py                # Authentication service
└── tests/                     # API tests
    ├── __init__.py
    ├── test_contributions.py
    ├── test_proofs.py
    ├── test_reputation.py
    └── test_auth.py
```

### Reputation Module

```
reputation/
├── __init__.py                # Package initialization
├── config.py                  # Module configuration
├── calculator/                # Reputation calculation
│   ├── __init__.py
│   ├── base.py                # Base calculator
│   ├── weighted.py            # Weighted calculator
│   └── factory.py             # Calculator factory
├── roles/                     # Role emergence
│   ├── __init__.py
│   ├── detector.py            # Role detector
│   ├── signals.py             # Role signals
│   └── definitions.py         # Role definitions
├── trust-graph/               # Trust relationship mapping
│   ├── __init__.py
│   ├── graph.py               # Graph implementation
│   ├── relationships.py       # Relationship types
│   └── queries.py             # Graph queries
├── anti-gaming/               # Anti-gaming measures
│   ├── __init__.py
│   ├── detector.py            # Gaming detection
│   ├── mitigation.py          # Mitigation strategies
│   └── reporting.py           # Suspicious activity reporting
├── services/                  # Reputation services
│   ├── __init__.py
│   ├── reputation_service.py  # Main reputation service
│   ├── role_service.py        # Role service
│   └── factory.py             # Service factory
└── tests/                     # Module tests
    ├── __init__.py
    ├── test_calculator.py
    ├── test_roles.py
    ├── test_trust_graph.py
    └── test_anti_gaming.py
```

### Frontend Module

```
frontend/
├── public/                    # Static assets
│   ├── favicon.ico
│   ├── logo.svg
│   └── robots.txt
├── src/                       # Source code
│   ├── components/            # UI components
│   │   ├── common/            # Common components
│   │   ├── contribution/      # Contribution components
│   │   ├── proof/             # Proof components
│   │   ├── reputation/        # Reputation components
│   │   └── auth/              # Authentication components
│   ├── pages/                 # Page definitions
│   │   ├── index.tsx          # Home page
│   │   ├── contribute.tsx     # Contribution page
│   │   ├── proofs.tsx         # Proofs page
│   │   ├── profile.tsx        # Profile page
│   │   └── auth/              # Auth pages
│   ├── hooks/                 # Custom React hooks
│   │   ├── useAuth.ts         # Authentication hook
│   │   ├── useContribution.ts # Contribution hook
│   │   ├── useProof.ts        # Proof hook
│   │   └── useReputation.ts   # Reputation hook
│   ├── services/              # Frontend services
│   │   ├── api.ts             # API client
│   │   ├── auth.ts            # Auth service
│   │   ├── contribution.ts    # Contribution service
│   │   └── proof.ts           # Proof service
│   ├── styles/                # CSS/styling
│   │   ├── globals.css        # Global styles
│   │   └── components.css     # Component styles
│   ├── utils/                 # Utility functions
│   │   ├── formatting.ts      # Formatting utilities
│   │   ├── validation.ts      # Form validation
│   │   └── storage.ts         # Local storage
│   ├── types/                 # TypeScript types
│   │   ├── contribution.ts    # Contribution types
│   │   ├── proof.ts           # Proof types
│   │   └── reputation.ts      # Reputation types
│   ├── App.tsx                # Main app component
│   └── index.tsx              # Entry point
├── tests/                     # Frontend tests
│   ├── components/            # Component tests
│   ├── hooks/                 # Hook tests
│   └── services/              # Service tests
├── .eslintrc.js               # ESLint configuration
├── tailwind.config.js         # Tailwind CSS configuration
├── tsconfig.json              # TypeScript configuration
├── package.json               # Node.js package
└── README.md                  # Frontend documentation
```

### Integrations Module

```
integrations/
├── __init__.py                # Package initialization
├── config.py                  # Integrations configuration
├── github/                    # GitHub integration
│   ├── __init__.py
│   ├── webhook_handler.py     # Webhook handler
│   ├── service.py             # GitHub service
│   └── tests/                 # GitHub integration tests
├── discord/                   # Discord integration
│   ├── bot.js                 # Discord bot
│   ├── commands/              # Bot commands
│   ├── events/                # Event handlers
│   └── tests/                 # Discord integration tests
├── ipfs/                      # IPFS storage
│   ├── __init__.py
│   ├── storage.py             # IPFS storage service
│   └── tests/                 # IPFS integration tests
├── lens/                      # Lens Protocol integration
│   ├── client.ts              # Lens client
│   ├── profile.ts             # Profile integration
│   └── tests/                 # Lens integration tests
└── factory.py                 # Integration factory
```

### Governance Module

```
governance/
├── __init__.py                # Package initialization
├── config.py                  # Governance configuration
├── proposals/                 # Proposal management
│   ├── __init__.py
│   ├── models.py              # Proposal models
│   ├── service.py             # Proposal service
│   └── repository.py          # Proposal repository
├── voting/                    # Voting mechanisms
│   ├── __init__.py
│   ├── quadratic.py           # Quadratic voting
│   ├── reputation.py          # Reputation-weighted voting
│   └── role_based.py          # Role-based voting
├── execution/                 # Decision execution
│   ├── __init__.py
│   ├── executor.py            # Decision executor
│   ├── recorder.py            # Decision recorder
│   └── tracker.py             # Execution tracker
├── dashboard/                 # Governance UI
│   ├── components/            # Dashboard components
│   ├── pages/                 # Dashboard pages
│   └── hooks/                 # Dashboard hooks
├── services/                  # Governance services
│   ├── __init__.py
│   ├── governance_service.py  # Main governance service
│   └── factory.py             # Service factory
└── tests/                     # Governance tests
    ├── __init__.py
    ├── test_proposals.py
    ├── test_voting.py
    └── test_execution.py
```

### Common Module

```
common/
├── __init__.py                # Package initialization
├── utils/                     # Utility functions
│   ├── __init__.py
│   ├── formatting.py          # Formatting utilities
│   ├── validation.py          # Validation utilities
│   └── hashing.py             # Hashing utilities
├── config/                    # Configuration
│   ├── __init__.py
│   ├── settings.py            # Settings management
│   ├── environment.py         # Environment variables
│   └── defaults.py            # Default configurations
├── logging/                   # Logging
│   ├── __init__.py
│   ├── logger.py              # Logger setup
│   └── handlers.py            # Log handlers
├── errors/                    # Error handling
│   ├── __init__.py
│   ├── exceptions.py          # Custom exceptions
│   └── handlers.py            # Error handlers
└── tests/                     # Common tests
    ├── __init__.py
    ├── test_utils.py
    ├── test_config.py
    └── test_logging.py
```

### Documentation Module

```
docs/
├── README.md                  # Documentation overview
├── BUILD.md                   # Build guide
├── ARCHITECTURE.md            # Architecture documentation
├── api/                       # API documentation
│   ├── README.md              # API overview
│   ├── contributions.md       # Contribution endpoints
│   ├── proofs.md              # Proof endpoints
│   └── reputation.md          # Reputation endpoints
├── architecture/              # Architecture documentation
│   ├── README.md              # Architecture overview
│   ├── validation.md          # Validation architecture
│   ├── proofs.md              # Proof architecture
│   └── reputation.md          # Reputation architecture
├── contributing/              # Contribution guidelines
│   ├── README.md              # Contributing overview
│   ├── code-of-conduct.md     # Code of conduct
│   ├── development.md         # Development workflow
│   └── testing.md             # Testing guidelines
├── tutorials/                 # Tutorials and guides
│   ├── README.md              # Tutorials overview
│   ├── quickstart.md          # Quickstart guide
│   ├── contribution.md        # Contribution tutorial
│   └── validation.md          # Validation tutorial
└── assets/                    # Documentation assets
    ├── images/                # Images
    └── diagrams/              # Architecture diagrams
```

### Scripts Module

```
scripts/
├── setup.sh                   # Development environment setup
├── db/                        # Database scripts
│   ├── init_db.py             # Database initialization
│   ├── migrations/            # Database migrations
│   └── seed.py                # Seed data
├── dev/                       # Development scripts
│   ├── start.sh               # Start development servers
│   ├── test.sh                # Run tests
│   └── lint.sh                # Run linters
├── deploy/                    # Deployment scripts
│   ├── deploy.sh              # Deployment script
│   ├── rollback.sh            # Rollback script
│   └── monitor.sh             # Monitoring script
└── ci/                        # CI/CD scripts
    ├── build.sh               # Build script
    ├── test.sh                # Test script
    └── deploy.sh              # CI deployment script
```

### Tests Module

```
tests/
├── __init__.py                # Package initialization
├── conftest.py                # Test configuration
├── fixtures/                  # Test fixtures
│   ├── __init__.py
│   ├── contributions.py       # Contribution fixtures
│   ├── proofs.py              # Proof fixtures
│   └── users.py               # User fixtures
├── integration/               # Integration tests
│   ├── __init__.py
│   ├── test_validation.py     # Validation integration
│   ├── test_proofs.py         # Proofs integration
│   └── test_reputation.py     # Reputation integration
├── e2e/                       # End-to-end tests
│   ├── __init__.py
│   ├── test_contribution.py   # Contribution workflow
│   ├── test_verification.py   # Verification workflow
│   └── test_governance.py     # Governance workflow
└── performance/               # Performance tests
    ├── __init__.py
    ├── test_validation.py     # Validation performance
    ├── test_api.py            # API performance
    └── test_blockchain.py     # Blockchain performance
```

### GitHub Workflows

```
.github/
├── ISSUE_TEMPLATE/            # Issue templates
│   ├── bug_report.md          # Bug report template
│   ├── feature_request.md     # Feature request template
│   └── config.yml             # Template configuration
├── PULL_REQUEST_TEMPLATE/     # PR templates
│   └── pull_request_template.md  # PR template
└── workflows/                 # GitHub Actions
    ├── test.yml               # Test workflow
    ├── lint.yml               # Linting workflow
    ├── build.yml              # Build workflow
    └── deploy.yml             # Deployment workflow
```

## Purpose of Each Folder

### Core Modules

- **ai-validation/**: Contains all AI-powered validation logic, including model integrations, validation pipelines, and criteria definitions. This is the core innovation of WiseWork.

- **proofs/**: Implements the Proof of Contribution module, including data models, storage, and verification. This is the foundation of the system's trust mechanism.

- **blockchain/**: Handles all blockchain interactions, including smart contracts, proof anchoring, and verification. This provides the immutable record of contributions.

- **reputation/**: Implements the reputation system, including calculation, role emergence, and trust graph. This enables the governance and role-based features.

### Infrastructure Modules

- **api/**: Provides the RESTful API layer for all services, handling requests, validation, and responses. This is the primary interface for frontend and integrations.

- **common/**: Contains shared utilities, configuration, logging, and error handling used across all modules. This promotes code reuse and consistency.

- **scripts/**: Provides development, deployment, and maintenance scripts. This simplifies common operations and ensures consistency.

- **tests/**: Contains integration, end-to-end, and performance tests that span multiple modules. This ensures system-wide quality.

### User Interface Modules

- **frontend/**: Implements the web user interface, including components, pages, and services. This is the primary user interaction point.

- **governance/**: Contains governance-specific features, including proposals, voting, and decision execution. This enables community governance.

### Integration Modules

- **integrations/**: Implements integrations with external systems like GitHub, Discord, IPFS, and Lens Protocol. This extends the system's reach.

### Documentation and Configuration

- **docs/**: Contains all project documentation, including architecture, API, tutorials, and contribution guidelines. This enables developer onboarding.

- **.github/**: Provides GitHub-specific configuration, including issue templates, PR templates, and workflows. This streamlines the development process.

## Module Dependencies

```
ai-validation <---- proofs <---- reputation <---- governance
                      |             ^
                      v             |
                   blockchain ------+
                      |
                      v
common <----------- api <----------- frontend
                      ^
                      |
                  integrations
```

## Implementation Priority

For the PoC phase, focus on these directories first:

1. **ai-validation/**: Core validation logic
2. **proofs/**: Proof of Contribution module
3. **blockchain/**: Basic smart contracts
4. **api/**: Essential API endpoints
5. **frontend/**: Minimal user interface

## Scalability Considerations

This structure is designed to scale from PoC to MVP and beyond:

- **Modularity**: Each module has clear boundaries and responsibilities
- **Testability**: Each module has its own tests directory
- **Extensibility**: New validation strategies, proof types, or integrations can be added without changing existing code
- **Maintainability**: Common code is extracted to shared modules
- **Documentation**: Each module includes its own documentation

The structure follows the principle of "separation of concerns" and allows for independent development of different modules by different teams.
