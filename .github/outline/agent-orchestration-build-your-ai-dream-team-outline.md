# Exercise Outline: Agent Orchestration: Build Your AI Dream Team

## Exercise overview

- **Title**: Agent Orchestration: Build Your AI Dream Team
- **Repository name**: `agent-orchestration-build-your-ai-dream-team`
- **Audience**: Developers who have basic GitHub and GitHub Copilot familiarity and want to learn how to coordinate specialist agents from the terminal.
- **Experience level**: Intermediate
- **Estimated duration**: Less than one hour
- **Primary environment**: GitHub Codespaces
- **Primary interface**: GitHub Copilot CLI in the integrated terminal

## Summary

Learners use prebuilt custom agents in GitHub Copilot CLI to plan, design, build, validate, and hand off Mona's Project Pulse dashboard. The exercise focuses on using an Orchestrator to coordinate Planner, Designer, and Coder agents instead of having learners fill out agent definitions manually.

## Learning objectives

By the end of this exercise, learners will be able to:

1. Explain the responsibility of an Orchestrator agent in a multi-agent workflow.
1. Inspect prebuilt custom agent definitions in `.github/agents/`.
1. Identify model assignments for the exercise agents:
   - Orchestrator: Opus 5.5
   - Planner: Opus 5.5
   - Coder: GPT-5.5
   - Designer: Gemini 3.7 Flash
1. Use GitHub Copilot CLI in a Codespace terminal as the primary interface.
1. Ask the Orchestrator to involve the Planner before implementation.
1. Separate design work from coding work.
1. Build a small static dashboard with HTML, CSS, and JSON.
1. Validate the dashboard and write a final Orchestrator handoff.

## Prerequisites

- A GitHub account.
- Access to GitHub Codespaces.
- Access to GitHub Copilot and GitHub Copilot CLI.
- Basic familiarity with repositories, commits, and Markdown.
- Comfort working in an integrated terminal.

## What learners will build

Learners will use prebuilt agent definitions and create these outputs:

- `docs/agent-team.md`: summary of the custom agent team and their model assignments.
- `docs/project-pulse-plan.md`: Planner-informed implementation plan for Project Pulse.
- `app/index.html`: Project Pulse dashboard page.
- `app/styles.css`: dashboard styling.
- `app/project-data.json`: dashboard data.
- `.vscode/launch.json`: learner-created VS Code launch configuration for previewing the dashboard.
- `docs/final-handoff.md`: final Orchestrator validation and handoff.

## Codespaces and dev container setup

The repository includes:

- `.devcontainer/devcontainer.json`
- `.devcontainer/postCreate.sh`
- `.devcontainer/postStart.sh`
- `.vscode/tasks.json`

The dev container should:

- Install or verify GitHub Copilot CLI availability.
- Verify GitHub CLI availability.
- Open the terminal in the editor area after setup.
- Start GitHub Copilot CLI with `copilot --allow-all --enable-all-github-mcp-tools`.
- Configure terminal copy/paste ergonomics.
- Avoid requiring learners to install local desktop tools outside Codespaces.

## Story

Mona's team needs a lightweight **Project Pulse** dashboard that shows project names, owners, status, recent activity, priorities, and contributor-friendly summaries. The learner will use GitHub Copilot CLI and custom agents to orchestrate the work: Planner creates the plan, Designer guides the experience, Coder builds the static files, and Orchestrator validates and reports the final runnable dashboard.

## Step 1: Meet the agent team

### Theory

GitHub Copilot CLI can use custom agents stored in `.github/agents/`. In this exercise, those agents are already defined so the learner can focus on orchestration and use rather than authoring agent files.

### Activity

1. Open the exercise in Codespaces.
1. Use the terminal that opens in the editor area.
1. Start GitHub Copilot CLI with `copilot --allow-all --enable-all-github-mcp-tools` if it is not already running.
1. Ask Copilot CLI to inspect `.github/agents/`.
1. Update `docs/agent-team.md` with each agent, model, responsibility, source file, and how the team will build Project Pulse.
1. Ask Copilot CLI to stage, commit, and push the change from interactive mode.

### Action trigger

- Event: `push`
- Path filter: `docs/agent-team.md`

### Grading checks

- `docs/agent-team.md` exists.
- The file includes `Orchestrator`, `Planner`, `Coder`, and `Designer`.
- The file includes `Opus 5.5`, `GPT-5.5`, and `Gemini 3.7 Flash`.
- The file references `.github/agents/` and Project Pulse.

## Step 2: Plan Project Pulse

### Theory

The Orchestrator should ask the Planner for a practical plan before implementation. The plan should include file assignments, dependencies, design and coding ownership, and validation expectations.

### Activity

1. Read `.github/project-pulse-brief.md`.
1. Use `/agent` to select the Orchestrator.
1. Ask the Orchestrator: `Ask the Planner to create an implementation plan for the Project Pulse dashboard. Save the plan in docs/project-pulse-plan.md.`
1. Create `docs/project-pulse-plan.md`.
1. Ensure the plan references `app/index.html`, `app/styles.css`, `app/project-data.json`, `.vscode/launch.json`, Designer responsibilities, Coder responsibilities, dependencies, parallel work decisions, and validation.
1. Ask Copilot CLI to stage, commit, and push the change from interactive mode.

### Action trigger

- Event: `push`
- Path filter: `docs/project-pulse-plan.md`

### Grading checks

- `docs/project-pulse-plan.md` exists.
- The file includes Project Pulse, Designer, Coder, all three app files, `.vscode/launch.json`, dependencies, parallel work, and validation.

## Step 3: Build Project Pulse

### Theory

The Orchestrator coordinates the build by assigning experience decisions to Designer and implementation to Coder. The learner produces a small static app rather than only documenting the plan.

### Activity

1. Use `/agent` to select the Orchestrator.
1. Ask the Orchestrator to delegate design and coding work based on `docs/project-pulse-plan.md`.
1. Create `app/index.html`, `app/styles.css`, `app/project-data.json`, and `.vscode/launch.json`.
1. Ensure the dashboard title, polished project-card UI, JSON data, and launch preview are connected.
1. Configure `.vscode/launch.json` to serve from `app/` and open `index.html` instead of a directory listing.
1. Run **Run Project Pulse Dashboard** from `.vscode/launch.json`.
1. Ask Copilot CLI to stage, commit, and push the change from interactive mode.

### Action trigger

- Event: `push`
- Path filters: `app/**` and `.vscode/launch.json`

### Grading checks

- `app/index.html`, `app/styles.css`, and `app/project-data.json` exist.
- `app/index.html` includes Project Pulse and references `styles.css` and `project-data.json`.
- `app/index.html` renders project cards with status, recent activity, and priority.
- `app/styles.css` includes `.dashboard`, `.project-card`, `border-radius`, and `box-shadow`.
- `app/project-data.json` parses as JSON and includes `projects`, `owner`, `status`, `recentActivity`, and `priority`.
- `.vscode/launch.json` exists and includes **Run Project Pulse Dashboard** and `index.html`.

## Step 4: Validate and hand off

### Theory

The Orchestrator closes the loop by validating the final app and summarizing what each specialist contributed.

### Activity

1. Use `/agent` to select the Orchestrator.
1. Ask the Orchestrator to review `docs/agent-team.md`, `docs/project-pulse-plan.md`, the `app/` files, and `.vscode/launch.json`.
1. Create `docs/final-handoff.md`.
1. Include the participating agents, final result, app files, launch configuration, validation notes, and next steps or limitations.
1. Ask Copilot CLI to stage, commit, and push the change from interactive mode.

### Action trigger

- Event: `push`
- Path filter: `docs/final-handoff.md`

### Grading checks

- `docs/final-handoff.md` exists.
- The file includes Project Pulse, all four agent names, all three app files, validation, and final result or handoff language.
- The file references `.vscode/launch.json` and **Run Project Pulse Dashboard**.

## Review content

The review step should recap that learners:

- Used GitHub Copilot CLI in Codespaces.
- Inspected prebuilt custom agents.
- Used an Orchestrator to involve Planner, Designer, and Coder.
- Created an implementation plan.
- Built and previewed a small static dashboard.
- Validated the result and wrote a final handoff.

## References

- GitHub Copilot CLI documentation: https://docs.github.com/copilot/concepts/agents/about-copilot-cli
- GitHub Copilot CLI help topics: `/agent`, `/model`, `/tasks`, `/fleet`, `/terminal-setup`, `/init`, `/skills`, and `/mcp`.
- Source multi-agent gist: https://gist.github.com/burkeholland/0e68481f96e94bbb98134fa6efd00436#file-three-agent-md
- GitHub Codespaces dev containers: https://docs.github.com/en/codespaces/setting-up-your-project-for-codespaces/introduction-to-dev-containers
- Dev Container JSON reference: https://containers.dev/implementors/json_reference/
- GitHub Actions events that trigger workflows: https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows

## Bootstrap notes

- Keep `.github/agents/` prebuilt so learners use agents rather than authoring them.
- Do not commit learner output files that match Step 1-4 path filters.
- `postCreate.sh` should create only the Step 1 starter file, `docs/agent-team.md`.
- Later steps should create their output files as the learner reaches them.
