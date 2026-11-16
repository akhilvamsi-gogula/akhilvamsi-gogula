<div align="center">

# Akhil Vamsi Krishna Gogula

**Senior Software Quality Architect · AI & Test Automation Lead**

Bavaria, Germany · English: business fluent · German: B2 ([CEFR](https://www.coe.int/en/web/common-european-framework-reference-languages))

**Open to Software Quality Architect, QA Lead and AI Test Lead roles in Germany**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?logo=linkedin&logoColor=white)](https://linkedin.com/in/akhil-vamsi-krishna-gogula)
[![Live project](https://img.shields.io/badge/Live_project-Kanban_Board-000000?logo=vercel&logoColor=white)](https://kanban-board-seven-lilac.vercel.app/)

</div>

I design test architectures, quality strategies and release processes that let teams ship fast without losing control of risk. My background spans safety-critical and regulated products (medical devices under IEC 62304 / IEC 60601, industrial automation, automotive) as well as web, backend and AI-powered software. The methods carry across domains: risk-based testing, traceability, test automation at every layer, CI/CD quality gates and clear release decisions. Recently I have added LLM evaluation and AI quality engineering to that toolkit.

---

## Featured work

### [Kanban Board: full-stack AI app with production-grade testing](https://github.com/akhilvamsi-gogula/Kanban-board)
`Next.js 16` `FastAPI` `Postgres` `Groq` `pytest` `Vitest` `Playwright` `GitHub Actions` · [Live demo](https://kanban-board-seven-lilac.vercel.app/)

A multi-user Kanban app with an AI co-pilot that reads and edits boards and accepts file attachments. I built, tested and deployed it solo, using AI coding tools (Claude Code) under my own test strategy and review. Small in features, deliberate in quality:

- **Layered test strategy:** 134 backend tests against a real Postgres (no DB mocks), 75 frontend unit/component tests, 13 Playwright E2E scenarios across 4 device profiles (desktop, iPhone 13, Pixel 7, Galaxy S24 Ultra), a concurrent-user load check, and a manual real-device checklist.
- **Testing a non-deterministic AI feature:** deterministic contract tests in CI with faked model replies, plus a separate eval harness against the live model. The eval caught a real **prompt-injection defect** (an instruction hidden in an attached file renamed every column); fixed by prompt ordering and now guarded by a regression case.
- **Security and isolation:** ownership-scoped queries (foreign boards return 404, not 403), session and reset-token expiry, per-account AI rate limits, upload hardening (type spoofing, zip bombs, oversize bodies rejected before read).
- **Concurrency and performance:** 16 simultaneous saves stay consistent; a 25-user load run dropped from 21 s to 3.5 s after replacing a global lock with a connection pool, with per-user data isolation verified.
- **Defect log:** 11 real defects found by testing, each traced to the test that now guards it (real-touch drag on Android, out-of-order saves, mid-width layout cut-off, and more).

### [Production-Style LLM Evaluation with LangSmith](https://github.com/akhilvamsi-gogula/Production-Style-LLM-Evaluation-with-LangSmith)
`Python` `LangSmith` `Groq` `LLM-as-a-judge`

An evaluation pipeline for an LLM support assistant: versioned golden datasets with edge and adversarial cases, keyword-coverage checks for factual accuracy, an LLM-as-a-judge for tone and helpfulness, prompt-version comparison, and an automated **Go/No-Go release report** driven by score thresholds.

### [QuantizedQA: Steam web test automation](https://github.com/QuantizedQA/Quantized_QA_Steampowered_Web) · *Technical Lead*
`Playwright` `TypeScript` `GitHub Actions` `Jira`

A hobby QA project with a 5-person team spread across countries and time zones. I lead the team: running stand-ups, planning and assigning work on the Jira board, reviewing pull requests and maintaining the repository.

### Supporting repositories

| Repository | What it shows |
|---|---|
| [python-api-test-automation-framework](https://github.com/akhilvamsi-gogula/python-api-test-automation-framework) | Pytest + Requests against live REST APIs (GitHub, JSONPlaceholder): auth, CRUD, contract and negative tests, HTML and coverage reports in GitHub Actions |
| [playwright-tests](https://github.com/akhilvamsi-gogula/playwright-tests) | Playwright (JavaScript) UI and API specs with Page Object Model and role-based, accessibility-first locators |
| [langsmith-tracing-evaluation](https://github.com/akhilvamsi-gogula/langsmith-tracing-evaluation) | LangSmith tracing, exact-match / lenient / multi-metric evaluators, prompt A/B experiments |

---

## What I bring to a team

**Domains**
- *Safety-critical and regulated:* medical devices, industrial automation (PLC / TwinCAT), automotive.
- *Commercial software:* web applications, REST APIs and distributed backend services, AI / LLM products.

**Quality engineering and test strategy**
- Test strategies, test plans and test architectures from unit to system level, aligned to product risk.
- Risk-based testing, requirements-to-test traceability and audit-ready test evidence.
- Go/No-Go release assessments, quality gates in CI/CD, and quality metrics that teams act on.
- Defect triage and root-cause analysis workflows; mentoring engineers to stop recurring regressions at the source.
- Shift-left practices: testability reviews, static analysis and test coverage in the pull-request stage.

**Test automation and frameworks**
- Building maintainable automation frameworks for UI, API and integration testing (Python, TypeScript, JavaScript, C++).
- Non-functional testing: performance and load, concurrency, cross-device and cross-browser coverage.

**AI quality engineering**
- Validation of LLM-generated IEC 61131-3 PLC code with a Python/Pytest harness, simulating control-system behaviour via PyADS (TwinCAT).
- Evaluation design for LLM features: golden datasets, contract tests, live-model evals, prompt-injection cases.

**System and integration testing**
- ZeroMQ and REST integration tests across distributed services for a medical device manufacturer.
- GUI automation for Qt applications with Squish (PySide2), unit testing in C++ with Google Test.
- Hands-on security testing work on connected medical devices and automotive ECUs as part of project test scopes.

**Technical leadership**
- Leading a distributed, multi-time-zone team: planning, task assignment, code review and repository ownership.

---

## Tech stack

| Area | Tools |
|---|---|
| Languages | Python, TypeScript, JavaScript, C++ |
| Test automation | Pytest, Playwright, Vitest + Testing Library, Squish (Qt), Google Test, Requests |
| AI / LLM quality | LangSmith, LLM-as-a-judge, eval harnesses, Groq, prompt engineering |
| CI/CD and infrastructure | GitHub Actions, GitLab CI, Azure DevOps, Jenkins, Docker, Linux |
| Web and data | Next.js, React, FastAPI, Postgres |
| Standards | IEC 62304, IEC 60601, ISO 13485, IEC 61131-3 |
| Certification | ISTQB® Certified Tester: Testing with Generative AI (CT-GenAI) |

---

## How I work

1. **Test where the risk is.** Coverage numbers matter less than knowing which failure would hurt the user or the audit most, and testing that first.
2. **Real dependencies over mocks where it counts.** Databases, browsers and touch input behave differently from their fakes. Mocks belong at slow or non-deterministic boundaries, such as a live LLM.
3. **Non-deterministic systems still need deterministic gates.** Put the contract around the model in CI; evaluate the model itself separately, on purpose.
4. **A failing test should explain itself.** Flaky or unclear tests cost more trust than they buy. Every fixed defect gets a regression test.

---

<div align="center">

[LinkedIn](https://linkedin.com/in/akhil-vamsi-krishna-gogula)

</div>
