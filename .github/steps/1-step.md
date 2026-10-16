## Step 1: Meet the agent team

Welcome to **Agent Orchestration: Build Your AI Dream Team**! :robot:

Mona's team needs a small **Project Pulse** dashboard. You will use GitHub Copilot CLI to coordinate a prebuilt team of custom agents that can plan, design, code, and validate the dashboard.

### What is the goal?

The goal is not to write every file with one prompt. The goal is to practice orchestration:

- The **Orchestrator** coordinates the request.
- The **Planner** creates implementation phases and file ownership.
- The **Designer** guides the dashboard experience.
- The **Coder** implements the static app files.

The custom agent definitions are already available in `.github/agents/`. Your first task is to inspect that team and document how you will use it.

### :keyboard: Activity: Open the Codespace and start Copilot CLI

1. Right-click the button below to open the **Create Codespace** page in a new tab.

   [![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/{{full_repo_name}}?quickstart=1)

2. Confirm the **Repository** field is your copy of the exercise, then select **Create Codespace**.

   - ✅ Your copy: `/{{full_repo_name}}`
   - ❌ Original: `/skills/agent-orchestration-build-your-ai-dream-team`

3. Wait for the Codespace to finish loading.

4. The Codespace opens a terminal in the editor area and starts GitHub Copilot CLI with broad exercise permissions.

> [!NOTE]
> If you are not already in the Copilot CLI interactive mode, run this command.

   ```bash
   copilot --allow-all --enable-all-github-mcp-tools
   ```

5. If prompted, use `/login` to authenticate.

> [!NOTE]
> Copy and paste should work in the Codespace terminal with standard browser shortcuts. You can also select text to copy it automatically, then right-click in the terminal to paste. If multiline input is awkward, run `/terminal-setup` inside Copilot CLI.

### :keyboard: Activity: Inspect the custom agents

1. Ask Copilot CLI to inspect the agent definitions:

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Inspect .github/agents/ and summarize the custom agent team I will use to build
   > Mona's Project Pulse dashboard.
   >
   > Update the replace text in `docs/agent-team.md`.
   > ```

1. Update `docs/agent-team.md` with:

   - Orchestrator, Planner, Coder, and Designer.
   - The model assigned to each agent.
   - The responsibility of each agent.
   - The `.github/agents/` file for each agent.
   - How the team will work together to build Project Pulse.

1. Save the file.

1. Ask Copilot CLI to stage, commit, and push your work. Copy and paste this prompt into the Copilot CLI interactive mode:

   > ![Static Badge](https://img.shields.io/badge/-Prompt-text?style=social&logo=github%20copilot)
   >
   > ```prompt
   > Stage docs/agent-team.md.
   >
   > Commit it with the message "Document the Project Pulse agent team".
   >
   > Push the commit.
   > ```

1. Mona will check your work and post the next lesson.

<details>
<summary>Having trouble? 🤷</summary><br/>

- Make sure you updated `docs/agent-team.md`.
- Make sure the file references `.github/agents/`.
- Make sure the file includes all four agent names.
- Make sure the file uses the updated models: Opus 5.5, GPT-5.5, and Gemini 3.7 Flash.
- Make sure you pushed your commit.

</details>
