# Everyone's Prompt — Contribution Case Study

**Project:** 모두의 프롬프트 · SSAFY team project · July–August 2026  
**My role:** PM  
[Team repository](https://github.com/ddingorang/itsourprompt) · [Project site](https://lets.promptpractice.run/) · [LinkedIn](https://www.linkedin.com/in/sucheol-jang-244652361/)

## Problem

Junior developers need to express requirements precisely and verify AI-generated code. A plausible response is insufficient when an existing multi-file project has interfaces and state that must be preserved.

## My contribution

- Designed prompt-based Java coding challenges around partially completed projects that require investigation of multiple files.
- Specified normal, exceptional, and boundary behavior, preservation of state after failed operations, compatibility with existing interfaces, and limits on editable files.
- Defined evaluation criteria using public and hidden tests to make expected behavior assessable.

My contribution is requirements and evaluation design. The team repository lists separate owners for AI, backend, frontend, QA, and infrastructure; I do not claim sole implementation of those systems.

## Team system

The published README describes a React frontend, Spring Boot backend, PostgreSQL, RabbitMQ, Docker build/test workers, and OpenAI-based generation and feedback.

A user submits a prompt; the system checks it, generates code changes, and can compile and test the workspace in separate workers. Feedback reviews the user's prompt history. These are team-system capabilities, not claims that I implemented each component.

## Deliverables and evidence

- Java challenge specifications and acceptance criteria.
- Evaluation coverage for normal, error, and boundary cases.
- [Published team README](https://github.com/ddingorang/itsourprompt/blob/main/README.md): team role attribution, workflow, screenshots, and architecture.
- [API reference](https://github.com/ddingorang/itsourprompt/blob/main/docs/api.md) and [design decisions](https://github.com/ddingorang/itsourprompt/blob/main/docs/design-decisions.md): implementation context.

## Review and validation

This case study was checked against the published README and my documented project responsibilities. It does not claim a newly executed test pass, measured improvement in learning outcomes, production usage, or a performance benchmark.

The project site is linked from the team README; current service availability is not guaranteed by this document.
