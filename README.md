# markdown-pretty-app
Vibe coding experiment — A responsive markdown editor web app with live preview, version control, AI assistance, and sharing capabilities. This project combines approaches from [My LLM codegen workflow atm](https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/) and the Maven course [AI Prototyping for Product Managers](https://maven.com/tech-for-product/ai-prototyping-for-product-managers).

**DEVELOPMENT STATUS:** In progress

![Handsketch of app overview](https://michellepace.github.io/markdown-pretty-app/images/00-handsketch-START.jpg)

![Github cover image from Hone page wireframe screenshot](https://michellepace.github.io/markdown-pretty-app/images/github-cover.jpg)

## Development Workflow

### Step 1: Create Product Specification (`spec.md`)
---
Used Claude 3.7 Sonnet with extended thinking mode in an iterative Q&A approach.

- Prompt: [prompt-make-spec.md](/prompts/01-make-app-spec/prompt-make-spec.md)
- Output: [spec.md](/spec.md)

**Notes:**
1. *Idea in prompt — can be FAR less detailed, I knew what I wanted*
2. *Iterative process — after Q&A, prompt for changes and/or manually edit artefact*
3. *Save spec in app project — use to guide later step-by-step development. Update for accuracy/completion*

### Step 2: Create Simplified Specification (`spec-simple.md`)
---
Created a more focused version to facilitate initial app creation.

- Prompt: [prompt-make-spec-simple.md](/prompts/01-make-app-spec/prompt-make-spec-simple.md) + slimmed version of [spec.md](/spec.md)
- Output: [spec-simple.md](/spec-simple.md)

**Notes:**
1. *Adaptations needed — [Bolt](https://bolt.new/) works with this spec as-is; [Replit](https://replit.com/ai) has PostgreSQL (no need for [Supabase](https://supabase.com/)) but still uses [Clerk](https://clerk.com/) for auth; [v0](https://v0.dev/) requires Next.js adjustments.*

### Step 3: Generate Wireframes
---
Created HTML wireframes with Claude to visualise the app over spending limited credits in vibe coding tools.

- Prompt: [prompt-make-wireframes.md](/prompts/02-make-wireframes/prompt-make-wireframes.md) + [spec-simple.md](/spec-simple.md)
- This was an iterative process; see screenshots in [/images](/images/)
- Output: See wireframes in [/wireframes-html](/wireframes-html/)

| Wireframe | Claude.ai Chat | View wireframe | View wireframe code |
|-----------|-----------|----------------|-----------|
| Home Page | [Screenshot](https://michellepace.github.io/markdown-pretty-app/images/1-home-page.jpg) | [View visually](https://michellepace.github.io/markdown-pretty-app/wireframes-html/1-home-page.html) | [1-home-page.html](/wireframes-html/1-home-page.html) |
| Dashboard | [Screenshot](https://michellepace.github.io/markdown-pretty-app/images/2-dashboard-page.jpg) | [View visually](https://michellepace.github.io/markdown-pretty-app/wireframes-html/2-dashboard-page.html) | [2-dashboard-page.html](/wireframes-html/2-dashboard-page.html) |
| Markdown Editor | [Screenshot](https://michellepace.github.io/markdown-pretty-app/images/3-markdown-editor.jpg) | [View visually](https://michellepace.github.io/markdown-pretty-app/wireframes-html/3-markdown-editor.html) | [3-markdown-editor.html](/wireframes-html/3-markdown-editor.html) |
| Markdown Editor v2 | [Screenshot](https://michellepace.github.io/markdown-pretty-app/images/3-markdown-editor-v2.jpg) | [View visually](https://michellepace.github.io/markdown-pretty-app/wireframes-html/3-markdown-editor-v2.html) | [3-markdown-editor-v2.html](/wireframes-html/3-markdown-editor-v2.html) |
| Version Compare Modal | [Screenshot](https://michellepace.github.io/markdown-pretty-app/images/4-version-compare-modal.jpg) | [View visually](https://michellepace.github.io/markdown-pretty-app/wireframes-html/4-version-compare-modal.html) | [4-version-compare-modal.html](/wireframes-html/4-version-compare-modal.html) |
| Version Compare Modal v2 | [Screenshot](https://michellepace.github.io/markdown-pretty-app/images/4-version-compare-modal-v2.jpg) | [View visually](https://michellepace.github.io/markdown-pretty-app/wireframes-html/4-version-compare-modal-v2.html) | [4-version-compare-modal-v2.html](/wireframes-html/4-version-compare-modal-v2.html) |

**Notes:**
1. *Ask for html wireframe — Claude creates better wireframes in this format*
2. *Attach to creation prompt — screenshot will suffice, html file more directive*
3. *One wireframe — is enough to establish the design foundation*
4. *Others optional — provide agent with wireframes as features are built, but unnecessary and may detract from vibe tool's initial design interpretation*

### Step 4: Refactor Primary Wireframe
---
Selected and optimised the home page wireframe to establish design standards (Tailwind good practice).

> Note: STILL TO BE COMPLETED as of 14th April 2025

1. Created refactoring goals with Grok3 and Tailwind documentation: [refactor-goal-tailwind-best-practice.md](/prompts/03-refactor-wireframe-home-page/refactor-goal-tailwind-best-practice.md)
2. Prompt: [prompt-make-refactor-plan.md](/prompts/03-refactor-wireframe-home-page/prompt-make-refactor-plan.md)
3. Initial output: [response-refactor-plan.md](/prompts/03-refactor-wireframe-home-page/response-refactor-plan.md)
4. Grok executed refactor plan, manual browser testing after each step
5. Final result: [1-home-page.html](/wireframes-html/1-home-page.html) (reduced from 400 to ~150 lines)

Notes:
1. *Rationale for refactoring — Both Replit and Bolt tend to generate suboptimal UI code that is hardcoded and difficult to maintain. The goal was to provide a wireframe demonstrative of "Tailwind good practices" that will *hopefully* steer app generation.*
2. *A better v0 approach for later — use [v0](https://v0.dev/) to create UI (strongly adheres to Tailwind good practices and also uses [shadcn/ui](https://ui.shadcn.com/) components), then bring that into Bolt or Replit.*

### Step 5: Create App in Vibe Coding Tool
---
To be completed

### Step 6: Integrate Full Specification
---
To be completed

## General Vibe Notes
To be completed