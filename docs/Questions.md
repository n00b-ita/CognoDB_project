# Questions / Clarifications (generated from task_pdf.pdf)

This file lists items that require input from you or the assignment owner before we can fully implement the project.

1) Use case selection
- The PDF's "Choose your use case" section lists options. Please confirm which use case to implement, or explicitly allow me to pick a default (proposed default: ecommerce analytics or movies dataset).

2) Dataset
- Provide the dataset(s) to use, or confirm I should pick a public dataset (CSV) that matches the selected use case. If you provide a dataset, please upload it to the repo under data/ or share a download link.

3) CognoDB Cloud access
- Provide COGNODB_API_KEY and COGNODB_PROJECT_ID if you want the agent to run ingestion and integration tests against a live CognoDB Cloud instance. If not available, confirm that local/mock integration is acceptable for CI and demonstration.

4) Deployment requirements
- Does the assignment require a public deployment (URL) running on CognoDB Cloud or is a local deployment + recorded demo acceptable?

5) Deliverable format
- The PDF mentions deliverables and "what a strong submission looks like". Confirm if the deliverables must include: (a) a recorded demo video, (b) a PDF report, (c) source code only, (d) live deployed URL, or (e) all of the above.

6) Time/resource constraints
- Any limits on dataset size, API usage quotas, or runtime limits I should follow.

7) Preferred stack
- I proposed Node.js + Express + React. If you prefer Python (FastAPI) or another stack, say so now.

8) Evaluation specifics
- If there are specific evaluation rubrics (performance, model accuracy, query latency thresholds) not captured in the PDF, provide them.


Once these are answered I will proceed to scaffold milestone/01-scaffold and implement the skeleton. If you prefer I can choose reasonable defaults and proceed without answers, noting each assumption in the spec.
