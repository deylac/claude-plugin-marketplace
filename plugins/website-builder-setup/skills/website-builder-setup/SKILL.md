---
name: website-builder-setup
description: |
  Install the full AI website builder stack: UI/UX Pro Max, Framer Motion animations,
  and 21st.dev components. One skill, three tools, zero coding experience needed.
  Triggers: website builder, setup site, installer UI UX, 21st dev, magic MCP,
  configurer design, stack web, creer site web, website setup, builder setup,
  install design tools, setup components, web design stack.
allowed-tools: Bash
---

# Website Builder Setup

Orchestration skill to install and configure the complete AI website builder stack in Claude Code.

## What Gets Installed

| Tool | Purpose | Installation |
|------|---------|-------------|
| **UI/UX Pro Max** | Design intelligence (67 UI styles, 161 color palettes, 57 font pairings, 99 UX guidelines) | Automatic via `claude skill add` |
| **21st.dev Magic MCP** | High-quality AI-generated UI components directly in Claude Code | Requires user's personal API key |

## Workflow

Follow these steps **sequentially**. Do not skip steps.

### Step 0: Check Prerequisites

Run these checks before anything else:

1. Check if UI/UX Pro Max skill is already installed:
   ```bash
   claude skill list 2>/dev/null | grep -i "ui-ux-pro-max" || echo "UI_UX_NOT_INSTALLED"
   ```

2. Check if Magic MCP server is already configured:
   ```bash
   claude mcp list 2>/dev/null | grep -i "magic" || echo "MAGIC_NOT_INSTALLED"
   ```

3. Check that npx is available:
   ```bash
   which npx || echo "NPX_NOT_FOUND"
   ```

**If npx is not found:** Stop and tell the user to install Node.js from https://nodejs.org before continuing.

**If both tools are already installed:** Show the summary table from Step 3 and congratulate the user. Offer to verify everything works.

### Step 1: Install UI/UX Pro Max Skill

**If NOT already installed:**

1. Tell the user:
   > Installing UI/UX Pro Max — a comprehensive design intelligence skill with 67 UI styles, 161 color palettes, 57 font pairings, and much more...

2. Run the installation:
   ```bash
   claude skill add https://github.com/nextlevelbuilder/ui-ux-pro-max-skill.git
   ```

3. Verify success:
   ```bash
   claude skill list 2>/dev/null | grep -i "ui-ux-pro-max"
   ```

4. If successful: confirm to the user and move to Step 2.
5. If failed: show the error, suggest checking internet connection, and offer to retry.

**If already installed:**
   > UI/UX Pro Max is already installed. Moving to the next step.

### Step 2: Configure 21st.dev Magic MCP Server

**IMPORTANT: This step requires the user to manually get their personal API key.**

**If NOT already configured:**

1. Explain clearly what the user needs to do:

   > **Action required from you:**
   >
   > The 21st.dev Magic MCP server needs a personal API key. I cannot get it automatically — you need to retrieve it yourself.
   >
   > **Steps:**
   > 1. Open your browser and go to: https://21st.dev/magic-chat?mcp_section=true
   > 2. Create an account on 21st.dev if you don't have one yet
   > 3. Once logged in, you will see your personal API key on the page
   > 4. Copy the API key
   > 5. Come back here and paste it when I ask
   >
   > The API key is free and tied to your 21st.dev account.

2. Ask the user to provide their API key:
   > Please paste your 21st.dev API key here:

3. **Wait for the user's response.** Do NOT proceed until the key is provided.

4. Once the user provides their API key, run (replacing `USER_API_KEY` with the actual key):
   ```bash
   claude mcp add magic --scope user --env API_KEY="USER_API_KEY" -- npx -y @21st-dev/magic@latest
   ```

5. Verify success:
   ```bash
   claude mcp list 2>/dev/null | grep -i "magic"
   ```

6. If successful:
   > 21st.dev Magic MCP server configured successfully. You now have access to high-quality UI components directly in Claude Code.

7. If failed: show the error and suggest:
   - Verify the API key is correct
   - Check that npx works: `npx -y @21st-dev/magic@latest --help`
   - Try again with a fresh API key from the website

**If already configured:**
   > 21st.dev Magic MCP server is already configured. If you want to update your API key, let me know.

### Step 3: Final Summary

Display a summary table:

> **Setup complete!**
>
> | Component | Status |
> |-----------|--------|
> | UI/UX Pro Max Skill | [Installed / Failed] |
> | 21st.dev Magic MCP | [Configured / Failed] |
>
> **What you can do now:**
> - Ask Claude to design a landing page with a specific style
> - Use 67+ UI styles (glassmorphism, neobrutalism, minimalism, etc.)
> - Generate high-quality UI components with 21st.dev Magic
> - Combine design intelligence + components for professional websites
>
> **Try it:** Ask me to "Create a modern landing page for [your project]"

## Error Handling

- **`claude` not available:** Tell the user Claude Code must be installed and accessible from the command line
- **`npx` not available:** Suggest installing Node.js from https://nodejs.org
- **Invalid or empty API key:** Ask politely again without running the command
- **Network errors:** Suggest checking internet connection and retrying

## Security Rules

- The API key is PERSONAL — never hardcode it or suggest a default value
- Do NOT attempt to automate 21st.dev account creation
- Do NOT attempt to scrape the API key from the browser
- Use `--scope user` so the MCP config stays local to the user
- Never log or store the API key beyond the installation command
