# 🚀 Sprint Plan: Initial Development Roadmap

📅 *Start Date:* March 26, 2025\
📅 *End Date:* April 11, 2025\
👥 *Team:* @youruser1, @youruser2

---

## 🎯 Overall Goal

Deliver the foundational components of the internal logistics system, establishing a reliable and traceable development workflow, project structure, and early implementation for core features. Each developer must complete *14 distinct features* throughout the project:

- *7 Functional Requirements (FReq)*
- *7 Non-Functional Requirements (NoFReq)*

Each requirement must include:

- Code implementation
- Traceable SRS documentation
- Unit tests (covered by CI)
- Peer review and validation

---

## 🗂 Planned Sprints

### ✅ Sprint 1: Planning & Setup (Mar 26–Mar 30)

🧱 Objective: Establish infrastructure, workflow, and planning documents.

- Define and validate coding standards (.clang-format)
- Setup repository with CMake, .gitignore, branching model, and GitHub protections
- Enable GPG-signed commits for both developers
- Create CI skeleton using GitHub Actions (build + static analysis + test stubs)
- Draft the Software Requirements Specification (SRS)
- Draw architecture, sequence, and component diagrams
- Prepare Dockerfile and basic conanfile.txt for later use
- Create initial GitHub Issues and Project Board workflow

---

### ⏳ Sprint 2: Protocol & Common Codebase (Mar 31–Apr 2)

📨 Objective: Define communication structure and shared logic layer.

- Design JSON message schema and delivery protocol
- Create protocol.c/.h for message serialization/deserialization
- Implement packet types, constants, and enums
- Write unit tests for message formatting and parsing
- Set up utils/, logger/, and config loader (default.json)
- Validate shared modules with CI and test coverage
- Ensure traceability for at least 4 requirements per developer (2 FReq + 2 NFR)

---

### ⏳ Sprint 3: Component Communication (Apr 3–Apr 8)

🔗 Objective: Implement basic server and client logic using the protocol.

- Bootstrap TCP-based communication using sockets (IPv4/IPv6)
- Server: Accept client connections, receive and parse messages
- Client: Connect, send simulated delivery requests, handle response
- Implement basic authentication (hostname-based)
- Simulate at least one full communication cycle: request → response → ack
- Begin linking requirements to features in the SRS and GitHub Issues
- Incorporate logistics routing logic (not network), simulating a network of interconnected nodes (graph/matrix) to simulate pathfinding between warehouses and hubs
- Simulate multiple simultaneous clients (1000+) using scripts/threads to validate scalability.

---

### ⏳ Sprint 4: Docs, CI, and Feature Finalization (Apr 9–Apr 11)

🧼 Objective: Complete documentation, polish, and finalize all deliverables.

- Add Doxygen-style comments to all headers and modules
- Finalize diagrams and update SRS with complete traceability
- Enforce clang-format, clang-tidy, valgrind, cppcheck in CI
- Ensure >90% test coverage and clean test results
- Complete minimum 14 features per dev (7 FReq + 7 NFR each)
- Write CHANGELOG.md, finalize README.md, and prepare release/1.0.0

---

## 🔗 Project Dependencies

These tasks must be completed early in Sprint 1:

- GPG-signed commits fully set up and verified on GitHub
- CI workflow runs basic build and formatting checks
- .clang-format, CMakeLists.txt, Dockerfile, and Conan bootstrap working
- Requirements spreadsheet and SRS draft underway
- GitHub Project board with issues per sprint and feature

---

## ✅ Definition of Done

- All four sprints have been split into GitHub Issues
- Project board reflects accurate task flow (Triage → Done)
- SRS is completed with traceability matrix, diagrams, and requirement ownership
- Each developer completes *7 FReq + 7 NoFReq*, linked to code and tests
- CI passes all checks (static analysis, tests, formatting)
- Final delivery includes documented codebase, validated features, and a tagged release (v1.0.0)

---

## 🧰 Tooling Stack

| Tool        | Purpose                                      |
| ----------- | -------------------------------------------- |
| CMake       | Project build system (Makefiles not allowed) |
| Conan       | Dependency manager for C/C++ libraries       |
| Docker      | Reproducible dev environment                 |
| GitHub CI   | Automated testing, formatting, analysis      |
| clang-tools | Linting, formatting, static analysis         |
| Doxygen     | Code documentation generation                |
| PlantUML    | Diagrams (architecture, sequence, flow)      |

---

📌 *Next step:* Create a new GitHub Issue for *Sprint 1*, divide it into tasks, and assign them with labels and ownership.
