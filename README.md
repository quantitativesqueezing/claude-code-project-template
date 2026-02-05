# claude-code-project-template
The documentation stack you should write before touching any code. Six canonical docs that define your entire project, plus some files that keep AI aligned and persistent across sessions.


# The Documentation-First System

Documentation first, code second. Always do this.
Before you write a single line of code, you should write your project's canonical documentation markdown files.

AI coding tools execute tasks without structural guardrails. The absence of locked constraints and authoritative documentation causes AI to hallucinate requirements, make unauthorized architectural decisions, and produce code that solves problems you never articulated.

Here's the documentation stack you should write before touching any code. Six canonical docs that define your entire project, plus some files that keep AI aligned and persistent across sessions.

The Canonical Docs (your knowledge base):

1. PRD.md (Product Requirements Document) - The full spec. What you're building, who it's for, what features exist, what's in scope, and what's explicitly out of scope. User stories, success criteria, non-goals, and every feature with specific criteria. This is your contract. AI reads this and knows exactly what "done" looks like for you. Don't have this? You're not building an app. You're praying for one.

2. APP_FLOW.md - Every page and every user navigation path documented in plain English. What triggers each flow. Step-by-step sequences with decision points, what happens on success, what happens on error, and the screen inventory with routes. This prevents AI from guessing how users move through your app.

3. TECH_STACK.md - Every package, dependency, API, and tool locked to exact versions. No ambiguity. When AI sees "use React," it might pick any version. When it sees "Next.js 14.1.0, React 18.2.0, TypeScript 5.3.3," it builds exactly what you specified. This doc eliminates hallucinated dependencies and random tech choices.

4. FRONTEND_GUIDELINES.md - Your complete design system. Fonts, color palette with exact hex codes, spacing scale, layout rules, component styles, responsive breakpoints, and UI library preferences. Every visual decision locked down. AI references this for every component it creates. No more random colors or inconsistent spacing while you keep vibing.

5. BACKEND_STRUCTURE.md - Database schema with every table, column, type, and relationship defined. Authentication logic, API endpoint contracts, storage rules, and edge cases. If you're using Supabase, this doc contains the exact SQL structure. AI builds your backend against this blueprint, not against its own assumptions.

6. IMPLEMENTATION_PLAN.md - A step-by-step build sequence. 


Not "build the app." More like: step 1.1 initialize the project, step 1.2 install dependencies from TECH_STACK.md, step 1.3 create folder structure, step 2.1 build the navbar component per FRONTEND_GUIDELINES.md, and so on. 

The more steps, the less AI guesses. The less AI guesses, the fewer hallucinations.
These docs cross-reference each other. The PRD defines features, the APP FLOW defines how users experience them, the TECH STACK defines what builds them, the FRONTEND GUIDELINES define how they look, the BACKEND STRUCTURE defines how data works, and the IMPLEMENTATION PLAN defines the build order.
This is your knowledge base. 

AI will read these and have everything it needs.

The Two Session Files (your persistence layer):

CLAUDE.md - This is the file AI reads first, automatically, every session. It contains the rules, constraints, patterns, and context that every AI session must follow. Your tech stack summary, your file naming conventions. your component patterns, and your design system tokens. It's what's allowed and what's forbidden. Think of it as the AI's operating manual for your specific project. Claude Code can read this from the project root without you even asking.

progress.txt - This is the file everyone misses. This file tracks what's been done, what's in progress, and what's next. Every time you finish a feature, you update this file. Every time you start a new session, every time you open a new terminal window, every time you switch branches, AI reads this file first for contextual memory of your progress. Without it, every new session starts from zero context and a whole lot of fuckups along the way. With it, AI picks up exactly where you left off.

Here's why this matters: AI has no memory between sessions. When you close a terminal, open a new one, or start a new chat, everything is gone. Progress.txt is your external memory. It's the bridge between sessions.
Update it religiously. After every completed feature you implement, meticulously document what was built, what works, what's broken, what's next.


# The Interrogation System

Before you even write your documentation, make AI tear your idea apart.
This is the prompt that changes everything:
"Before writing any code, endlessly interrogate my idea in Planning mode only. Assume nothing. Ask questions until there's no assumptions left."
AI hallucinates when your clarity ends. So if you extend your clarity, you'll force AI to find the gaps in your thinking before it starts building on a broken foundation.
What AI should ask you:
Who is this for? What's the core action a user takes? What happens when they complete that action? What data needs to be saved? What data needs to be displayed? What happens on error? What happens on success? Does this need a login? Does this need a database? Does this need to work on mobile?
If you can't answer these questions, you're not ready to build. 

Go answer them first.
Here's what good interrogation looks like. 

Say you're building a recipe-sharing app:
Who is this for? Home cooks who want to save and share recipes. Core action? User creates a recipe with a title, ingredients list, steps, and a photo. What happens after? Recipe is saved to their profile and visible on a public feed. Data saved? Recipe title, ingredients (array), steps (array), photo URL, author ID, timestamp. Data displayed? Feed of recent recipes, individual recipe detail page, user's own recipe collection. Error states? Upload fails, missing required fields, unauthorized edit attempt. Login required? Yes, to create recipes. Browsing is public. Database? Yes, users table and recipes table with a foreign key relationship. Mobile? Yes, most users will add recipes from their phone while cooking.
Those answers aren't just answers. 

They're the raw material for your canonical markdown docs. 

The user description feeds your PRD. The data structure feeds your BACKEND STRUCTURE. The flows feed your APP FLOW. The mobile requirement feeds your FRONTEND GUIDELINES.
Once the interrogation is complete and you have clear answers to everything, use this second prompt:
"Based on our interrogation, generate my canonical documentation files: 
- PRD.md
- APP_FLOW.md
- TECH_STACK.md
- FRONTEND_GUIDELINES.md
- BACKEND_STRUCTURE.md
- IMPLEMENTATION_PLAN.md. 
Use the answers from our conversation as the source material. Be specific and exhaustive. No ambiguity."
AI will draft all docs from the interrogation output. You review them, correct anything vague, add anything missing, and lock them as your source of truth.
The sequence: 
Interrogation → Documentation → Code. 

And never, ever skip these steps.



Source: https://x.com/kloss_xyz/status/2018097344345223455
