# IMPLEMENTATION_SPEC

Source: task_pdf.pdf (repository root)

This document extracts the actionable implementation requirements and turns them into a concrete implementation plan. Where the PDF is ambiguous or requires external inputs (datasets, CognoDB account), TODOs are listed in docs/Questions.md.

1. Project summary (interpreted from PDF)
- Objective: Build a working application that uses CognoDB Cloud for data storage and queries, demonstrating data ingestion, query examples, an interactive UI, and documentation as required by the assignment brief.
- Deliverables (high-level): working application (backend + frontend), ingestion scripts, example queries, documentation (setup, architecture, submission), and any deployment artifacts or demo (per the PDF).

2. Chosen defaults for implementation (if you prefer other choices, update Questions.md)
- Stack: Node.js (18+) + Express backend; React frontend (Vite); Docker + docker-compose for local dev; GitHub Actions for CI.
- Language: JavaScript/TypeScript (initial implementation in JavaScript; convert to TypeScript if requested).

3. Use-case selection
- The PDF includes a "Choose your use case" section. No explicit dataset was found in the repo. Default approach: implement a single, self-contained use case that demonstrates ingestion, query complexity, and UI/UX. Proposed default use case: a simple analytics dataset (e.g., ecommerce orders or movies dataset) that supports filtering, aggregation, and free-text search. If you want a different use case from the PDF, add it in docs/Questions.md.

4. Requirements checklist (scoped from the PDF headings)
- Ingest: ingestion script to upload CSV -> CognoDB Cloud (or local fallback) with idempotency.
- Data model: a schema for the chosen dataset with mapping/transform rules.
- Query examples: a curated set of example queries (stored in docs/example_queries.md).
- Backend: API endpoints for health, ingest, run query, and list example queries.
- Frontend: pages for Home, Data Explorer (form-based), Query Console (raw query editor), Visualizations (chart for at least one aggregation), Submission page.
- Tests: unit tests for backend modules, integration tests (mock CognoDB), and one E2E smoke test.
- Docs: IMPLEMENTATION_SPEC.md, COGNODB_SETUP.md, architecture.md, submission.md, and a Questions.md for ambiguous items.
- CI: GitHub Actions that run tests and basic lints/build.
- Deployment: docker-compose for local dev; optional cloud deployment instructions (Vercel/Netlify for frontend, Docker host for backend) and CognoDB Cloud steps.

5. CognoDB integration (design & env variables)
- Environment variables (placeholders):
  - COGNODB_API_KEY
  - COGNODB_PROJECT_ID
  - COGNODB_ENDPOINT (if applicable; default to https://api.cognodb.example)
- Behavior: ingestion scripts should attempt to call CognoDB REST API if COGNODB_API_KEY is present; otherwise fall back to writing data to data/local_sample.json and printing the REST payloads as dry-run output.
- Mocking: backend must support MOCK_COGNODB=true to simulate responses for CI/e2e without real credentials.

6. Milestones & branches
- milestone/00-readme-and-spec: this specification and questions (current branch).
- milestone/01-scaffold: initial scaffold with backend/ frontend/ infra/ data/ docs/ and basic Dockerfiles.
- milestone/02-data: dataset selection, data samples, and ingestion script.
- milestone/03-backend: implement API and CognoDB client, unit tests.
- milestone/04-frontend: implement UI and e2e smoke test.
- milestone/05-deploy: docker-compose production-ready instructions, CognoDB setup doc, CI workflow.
- milestone/06-deliverables: final docs, screenshots/video script, submission.md checklist.

7. Acceptance criteria (per milestone)
- Each milestone must include a short README and automated tests where applicable.
- Ingestion script must be idempotent and support dry-run.
- Example query path must return deterministic results against the sample dataset or mocked CognoDB client.
- Final repo must include documentation that exactly matches the deliverables requested by the assignment PDF.

8. Next actions (what Copilot agent will do next)
- Create docs/IMPLEMENTATION_SPEC.md (this file) and docs/Questions.md (list of clarifying questions).
- After your confirmation, scaffold milestone/01-scaffold (skeleton backend, frontend and infra).

9. Open questions and TODOs
- See docs/Questions.md which enumerates the specific clarifications needed from the instructor or repo owner (dataset choice, CognoDB access, required deliverable formats, and any constraints the PDF imposes that aren't explicit in the repo).


---

Document created automatically from repository task_pdf.pdf inspection. When you are ready I will:
- push this file (done),
- then scaffold the codebase on milestone/01-scaffold (create skeleton backend, frontend, dockerfiles) on request.
