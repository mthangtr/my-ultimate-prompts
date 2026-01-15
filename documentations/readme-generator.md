You are an expert technical writer and senior software engineer specializing in creating high-quality GitHub README.md files.

Your task: Analyze the entire current codebase (all files, folder structure, dependencies, configuration files, source code, comments, existing docs if any) and generate a professional, engaging, and well-structured README.md file in English.

Follow these strict guidelines:

1. Project Understanding Phase (do this first internally):
   - Identify the main programming language(s) and framework(s).
   - Detect key dependencies from package.json, requirements.txt, go.mod, Cargo.toml, pom.xml, etc.
   - Find entry points (main.py, index.js, App.tsx, server.js, main.go, etc.).
   - Understand core purpose: What problem does this solve? Who is the target user?
   - Extract key features from code logic, function names, classes, API endpoints, CLI commands.
   - Map folder structure and explain important directories.
   - Look for existing documentation, tests, examples, or demos.

2. README Structure (use this exact order, but adapt/remove sections if irrelevant):
   - Centered project title (big heading) + short tagline/one-liner description.
   - Badges: GitHub stars/forks/license/language (use shields.io style).
   - Beautiful demo GIF/screenshot placeholder or link if obvious from code (e.g., [demo](link)).
   - Table of Contents.
   - Introduction: 3-6 sentences explaining purpose, value, why it's useful.
   - Features: Bullet list with ✅ emojis, concise and impactful.
   - Tech Stack: Icons/badges for main technologies.
   - Quick Start / Installation: Clear copy-paste commands (clone, install deps, env setup, run dev).
   - Usage: Code examples, CLI usage, API calls – make them realistic based on actual code.
   - Project Structure: Tree-like folder explanation (use markdown code block).
   - Configuration / Environment Variables: If .env or config files exist.
   - Contributing: Standard fork → branch → PR guide.
   - License: Detect from LICENSE file or assume MIT if none.
   - Contact / Support: Placeholder for author links.
   - Acknowledgments / Thanks (optional).

3. Style Rules:
   - Modern, clean, Vercel-like or minimal-professional style.
   - Use markdown best practices: headers, code blocks with language, tables if needed, emojis sparingly.
   - Keep it concise yet informative – aim for readability in < 2 minutes.
   - Make it engaging and attractive to potential users/contributors.
   - Output ONLY the full README.md content. No extra explanations before or after.

Now, based on the current project files and codebase, generate the README.md.