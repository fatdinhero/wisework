# WiseWork Project Build Guide

This document outlines the construction plan for implementing the WiseWork protocol, from Proof of Concept (PoC) to Minimum Viable Product (MVP). It provides a structured approach to development, including phases, milestones, module dependencies, and directory structure.

## 1. Development Phases & Technical Milestones

### Phase 1: Proof of Concept (PoC) - 8 Weeks

The PoC phase focuses on implementing core functionality to validate the key concepts of WiseWork.

| Milestone | Description | Timeline | Dependencies |
|-----------|-------------|----------|--------------|
| M1.1 | AI Validation Core | Weeks 1-2 | None |
| M1.2 | Proof of Contribution Module | Weeks 2-3 | M1.1 |
| M1.3 | Basic Reputation System | Weeks 3-4 | M1.2 |
| M1.4 | Simple Smart Contract | Weeks 3-4 | None (parallel) |
| M1.5 | API Layer | Weeks 4-5 | M1.1, M1.2 |
| M1.6 | Blockchain Anchoring | Weeks 5-6 | M1.2, M1.4 |
| M1.7 | Basic Frontend | Weeks 6-8 | M1.5 |
| M1.8 | PoC Integration & Testing | Week 8 | All above |

### Phase 2: Alpha Release - 8 Weeks

The Alpha phase expands on the PoC to create a more robust system with additional features.

| Milestone | Description | Timeline | Dependencies |
|-----------|-------------|----------|--------------|
| M2.1 | Enhanced Validation Pipeline | Weeks 9-10 | M1.1, M1.8 |
| M2.2 | Trust Graph Implementation | Weeks 9-11 | M1.3, M1.8 |
| M2.3 | Role Emergence Logic | Weeks 11-12 | M2.2 |
| M2.4 | Governance Contracts | Weeks 10-12 | M1.4, M1.6 |
| M2.5 | User Authentication | Weeks 10-11 | M1.7 |
| M2.6 | Enhanced Frontend | Weeks 12-14 | M2.3, M2.5 |
| M2.7 | GitHub Integration | Weeks 13-15 | M1.5, M2.5 |
| M2.8 | Alpha Testing & Refinement | Weeks 15-16 | All above |

### Phase 3: MVP Release - 8 Weeks

The MVP phase focuses on production readiness, performance, and security.

| Milestone | Description | Timeline | Dependencies |
|-----------|-------------|----------|--------------|
| M3.1 | Production Infrastructure | Weeks 17-18 | M2.8 |
| M3.2 | Security Audit & Fixes | Weeks 17-19 | M2.4, M2.8 |
| M3.3 | Performance Optimization | Weeks 19-20 | M2.1, M2.2, M2.6 |
| M3.4 | Documentation & Guides | Weeks 19-21 | All Phase 2 |
| M3.5 | Community Onboarding | Weeks 21-22 | M3.4 |
| M3.6 | Final Testing & QA | Weeks 22-23 | All above |
| M3.7 | Production Deployment | Week 24 | All above |

## 2. Modular Build Order

### Core Components (Build First)

1. **AI Validation Module**
   - Prerequisites: None
   - Outputs: Validation API, model integration

2. **Proof Storage System**
   - Prerequisites: AI Validation Module
   - Outputs: Data models, storage interfaces

3. **API Layer**
   - Prerequisites: AI Validation Module, Proof Storage System
   - Outputs: RESTful API endpoints

### Blockchain Components (Build in Parallel)

4. **Smart Contracts**
   - Prerequisites: None (can start in parallel with Core Components)
   - Outputs: Deployed testnet contracts

5. **Blockchain Integration**
   - Prerequisites: Proof Storage System, Smart Contracts
   - Outputs: Proof anchoring service

### Reputation Components (Build After Core)

6. **Reputation Calculator**
   - Prerequisites: Proof Storage System
   - Outputs: Reputation scoring service

7. **Trust Graph**
   - Prerequisites: Reputation Calculator
   - Outputs: Graph database integration, relationship mapping

8. **Role Emergence**
   - Prerequisites: Trust Graph, Reputation Calculator
   - Outputs: Role detection algorithms

### Frontend Components (Build After API)

9. **Authentication System**
   - Prerequisites: API Layer
   - Outputs: User authentication, profiles

10. **Contribution UI**
    - Prerequisites: API Layer, Authentication System
    - Outputs: Contribution submission interface

11. **Profile & Reputation UI**
    - Prerequisites: Reputation Calculator, Role Emergence
    - Outputs: User profiles, reputation visualization

### Integration Components (Build Last)

12. **GitHub Integration**
    - Prerequisites: API Layer, Authentication System
    - Outputs: GitHub webhook, contribution extraction

13. **Governance System**
    - Prerequisites: Reputation Calculator, Blockchain Integration
    - Outputs: Voting interface, proposal system

## 3. Directory Structure & Module Responsibilities

```
wisework/
├── ai-validation/             # AI validation pipeline
│   ├── models/                # Model interfaces and wrappers
│   ├── pipelines/             # Validation pipelines for different contribution types
│   ├── processors/            # Input/output processors
│   └── criteria/              # Validation criteria definitions
│
├── api/                       # API layer
│   ├── routes/                # API endpoints
│   ├── middleware/            # API middleware
│   ├── schemas/               # API data models
│   └── services/              # Service interfaces
│
├── blockchain/                # Blockchain integration
│   ├── contracts/             # Smart contracts
│   ├── scripts/               # Deployment scripts
│   ├── tests/                 # Contract tests
│   └── services/              # Blockchain interaction services
│
├── proofs/                    # Proof of Contribution module
│   ├── models/                # Proof data models
│   ├── repositories/          # Storage implementations
│   ├── services/              # Business logic
│   └── validators/            # Proof validation logic
│
├── reputation/                # Reputation system
│   ├── calculator/            # Reputation calculation algorithms
│   ├── roles/                 # Role emergence logic
│   ├── trust-graph/           # Trust relationship mapping
│   └── anti-gaming/           # Anti-gaming measures
│
├── frontend/                  # Web frontend
│   ├── components/            # UI components
│   ├── pages/                 # Page definitions
│   ├── hooks/                 # Custom React hooks
│   ├── services/              # Frontend services
│   └── styles/                # CSS/styling
│
├── integrations/              # External integrations
│   ├── github/                # GitHub integration
│   ├── discord/               # Discord integration
│   ├── ipfs/                  # IPFS storage
│   └── lens/                  # Lens Protocol integration
│
├── governance/                # Governance system
│   ├── proposals/             # Proposal management
│   ├── voting/                # Voting mechanisms
│   ├── execution/             # Decision execution
│   └── dashboard/             # Governance UI
│
├── common/                    # Shared utilities
│   ├── utils/                 # Utility functions
│   ├── config/                # Configuration
│   ├── logging/               # Logging
│   └── errors/                # Error handling
│
├── docs/                      # Documentation
│   ├── api/                   # API documentation
│   ├── architecture/          # Architecture documentation
│   ├── contributing/          # Contribution guidelines
│   └── tutorials/             # Tutorials and guides
│
└── scripts/                   # Development and deployment scripts
```

### Module Responsibilities

#### AI Validation Module
- Integrate with AI models (GPT-4o, Llama)
- Process contributions for validation
- Apply validation criteria
- Extract insights and role signals

#### Proof Storage Module
- Define proof data structures
- Implement storage repositories
- Handle proof creation and retrieval
- Manage proof revisions

#### Blockchain Module
- Implement smart contracts
- Handle proof anchoring
- Manage blockchain interactions
- Verify proof integrity

#### Reputation Module
- Calculate reputation scores
- Detect role patterns
- Maintain trust relationships
- Implement anti-gaming measures

#### API Module
- Define API endpoints
- Handle request validation
- Coordinate between services
- Manage authentication and authorization

#### Frontend Module
- Implement user interfaces
- Handle state management
- Provide visualization components
- Manage user interactions

#### Integrations Module
- Connect with external platforms
- Process external contributions
- Sync data with external systems
- Provide integration interfaces

#### Governance Module
- Manage proposal lifecycle
- Implement voting mechanisms
- Record and execute decisions
- Provide governance dashboards

## 4. Dependencies & Implementation Order

### Critical Path Dependencies

```
AI Validation → Proof Storage → API Layer → Frontend
                    ↓
                Reputation → Role Emergence
                    ↓
Smart Contracts → Blockchain Integration → Governance
```

### Implementation Order (PoC Focus)

1. **Week 1-2: Core Validation**
   - Set up development environment
   - Implement basic validation with GPT-4o
   - Create validation criteria definitions
   - Build simple validation pipeline

2. **Week 2-3: Proof Storage**
   - Define proof data models
   - Implement MongoDB repository
   - Create proof service layer
   - Build proof creation workflow

3. **Week 3-4: Basic Reputation & Smart Contracts**
   - Implement simple reputation calculator
   - Create basic smart contract for proof registry
   - Deploy contract to testnet
   - Implement contract interaction service

4. **Week 4-5: API Layer**
   - Define API routes and schemas
   - Implement contribution endpoints
   - Create proof retrieval endpoints
   - Add basic authentication

5. **Week 5-6: Blockchain Anchoring**
   - Implement proof anchoring service
   - Create verification endpoints
   - Connect proof creation to anchoring
   - Build transaction monitoring

6. **Week 6-8: Frontend & Integration**
   - Create contribution submission UI
   - Build proof visualization components
   - Implement user profiles
   - Integrate all components
   - Conduct end-to-end testing

## 5. Technical Stack & Dependencies

### Backend
- **Language:** Python 3.11+
- **Framework:** FastAPI
- **Database:** MongoDB, Neo4j (for Trust Graph)
- **AI:** OpenAI API (GPT-4o), Hugging Face Transformers
- **Caching:** Redis

### Blockchain
- **Network:** Optimism (testnet for PoC)
- **Smart Contracts:** Solidity 0.8.17+
- **Development:** Hardhat, ethers.js
- **Storage:** IPFS via web3.storage

### Frontend
- **Framework:** Next.js
- **UI:** Tailwind CSS, Headless UI
- **State:** Zustand, React Query
- **Visualization:** D3.js, Recharts

### DevOps
- **Containerization:** Docker, Docker Compose
- **CI/CD:** GitHub Actions
- **Monitoring:** Prometheus, Grafana
- **Hosting:** Railway (PoC), AWS/GCP (MVP)

## 6. Getting Started for Developers

### Prerequisites
- Python 3.11+
- Node.js 18+
- Docker and Docker Compose
- MongoDB (local or Atlas)
- OpenAI API key (for development)

### Setup Steps

1. **Clone the repository:**
   ```bash
   git clone https://github.com/fatdinhero/wisework.git
   cd wisework
   ```

2. **Set up Python environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   # or
   .\venv\Scripts\activate  # Windows
   pip install -r requirements.txt
   pip install -r requirements-dev.txt
   ```

3. **Set up environment variables:**
   ```bash
   cp .env.example .env
   # Edit .env with your API keys and configuration
   ```

4. **Start services with Docker:**
   ```bash
   docker-compose up -d
   ```

5. **Run database migrations:**
   ```bash
   python src/db/init_db.py
   ```

6. **Start the development server:**
   ```bash
   uvicorn src.main:app --reload
   ```

7. **Run frontend development server:**
   ```bash
   cd frontend
   npm install
   npm run dev
   ```

### Development Workflow

1. **Create a feature branch:**
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Implement your changes following the module structure**

3. **Run tests:**
   ```bash
   pytest
   ```

4. **Submit a pull request**

## 7. Testing Strategy

### Unit Testing
- Test individual components in isolation
- Use pytest for backend, Vitest for frontend
- Aim for 80%+ coverage

### Integration Testing
- Test interactions between components
- Focus on API endpoints and service interactions
- Use pytest with test database

### Contract Testing
- Test smart contracts with Hardhat
- Ensure 100% coverage for contracts
- Test gas optimization

### End-to-End Testing
- Test complete workflows
- Use Playwright for browser testing
- Focus on critical user journeys

## 8. Documentation Requirements

Each module should include:

1. **README.md** - Overview and setup instructions
2. **API documentation** - Endpoints, parameters, responses
3. **Architecture documentation** - Component design and interactions
4. **Usage examples** - Code snippets and tutorials

## 9. Contribution Guidelines

See [CONTRIBUTING.md](../.github/CONTRIBUTING.md) for detailed guidelines on:

- Code style and formatting
- Pull request process
- Issue reporting
- Review process
- Documentation requirements

---

This build guide is a living document and will be updated as the project evolves. For questions or clarifications, please open an issue on GitHub.
