# Agent team

I will use a four-agent custom team to build Mona's Project Pulse dashboard, with work orchestrated through GitHub Copilot CLI inside a Codespace.

## Agent roster

- Planner — Target model: Claude Opus 4.7 (copilot)
  - Responsibility: Research the repo, identify dependencies and edge cases, and produce a concrete implementation plan for the dashboard work.
  - Definition: `.github/agents/planner.agent.md`

- Orchestrator — Target model: Claude Opus 4.7 (copilot)
  - Responsibility: Break the plan into phases, assign file-scoped work to specialists, coordinate execution, and verify that the integrated result makes sense.
  - Definition: `.github/agents/orchestrator.agent.md`

- Coder — Target model: GPT-5.5 (copilot)
  - Responsibility: Implement the application logic, fix bugs, and make code changes within the file scope assigned by the Orchestrator, including support files for runnable app work when needed.
  - Definition: `.github/agents/coder.agent.md`

- Designer — Target model: Gemini 3.1 Pro (copilot)
  - Responsibility: Shape the dashboard UX, accessibility, information hierarchy, interaction flow, and visual polish to make the Project Pulse frontend feel like a real product experience.
  - Definition: `.github/agents/designer.agent.md`

## How this team works

The custom agents live in the repository's agent folder under `.github/agents/` and follow the GitHub Copilot custom-agent pattern. The Orchestrator delegates tasks to the Planner, Coder, and Designer, while the team uses Copilot CLI in a Codespace to coordinate the build and validation of Mona's Project Pulse dashboard.
