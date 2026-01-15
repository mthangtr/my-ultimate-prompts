<div align="center">

# 🎯 My Ultimate Prompts

**A curated collection of professional AI prompts and skills for software development, documentation, and learning**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Markdown](https://img.shields.io/badge/Markdown-000000?style=flat&logo=markdown&logoColor=white)](https://www.markdownguide.org/)
[![AI Prompts](https://img.shields.io/badge/AI-Prompts-blue)](https://github.com)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

</div>

---

## 📑 Table of Contents

- [Introduction](#-introduction)
- [Features](#-features)
- [Project Structure](#-project-structure)
- [Documentation Prompts](#-documentation-prompts)
- [AI Skills](#-ai-skills)
- [Learning Prompts](#-learning-prompts)
- [Usage](#-usage)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🌟 Introduction

**My Ultimate Prompts** is a comprehensive repository of battle-tested AI prompts and skill definitions designed for software engineers, product managers, technical writers, and learners. This collection transforms how you interact with AI assistants by providing structured, professional prompts that generate high-quality outputs for documentation, code analysis, learning materials, and more.

Whether you're generating a BRD, debugging complex issues, or creating a learning outline, these prompts ensure consistency, completeness, and professional standards across all AI-generated content.

---

## ✅ Features

✅ **8 Professional Documentation Generators** - BRD, PRD, SRS, TDD, Product Concepts, and README templates  
✅ **9 Specialized AI Skills** - Code review, debugging, database optimization, diagram creation, and more  
✅ **Learning Framework** - Structured outline generator for deep technical learning  
✅ **Bilingual Support** - English and Vietnamese (tiếng Việt) prompts  
✅ **AI-Optimized Format** - Markdown-based, structured for consistent AI interpretation  
✅ **Production-Ready** - Used in real software projects and product development  
✅ **Extensible** - Easy to customize and adapt to your specific needs  
✅ **Best Practices** - Incorporates industry standards and proven methodologies  

---

## 🛠 Tech Stack

![Markdown](https://img.shields.io/badge/Markdown-000000?style=for-the-badge&logo=markdown&logoColor=white)
![AI](https://img.shields.io/badge/AI_Prompts-412991?style=for-the-badge&logo=openai&logoColor=white)
![Documentation](https://img.shields.io/badge/Documentation-4285F4?style=for-the-badge&logo=googledocs&logoColor=white)

**Primary Format**: Markdown  
**Target Platforms**: GitHub Copilot, Claude, ChatGPT, and other LLM assistants  
**Use Cases**: Software development, product management, technical writing, learning

---

## 📂 Project Structure

```
my-ultimate-prompts/
│
├── documentations/              # Business & Technical Documentation Generators
│   ├── brd-generator-prompt.md             # Business Requirements Document
│   ├── business-model-definition-prompt.md # Business Model Canvas
│   ├── prd-generator-prompt.md             # Product Requirements Document
│   ├── srs-generator-prompt.md             # Software Requirements Specification
│   ├── tdd-generator-prompt.md             # Technical Design Document
│   ├── product-concept-prompt.md           # Product Concept Canvas
│   ├── product-idea-requirements-spec.md   # Product Idea & Requirements
│   └── readme-generator.md                 # README.md Generator
│
├── skills/                      # AI Assistant Skill Definitions
│   ├── analyzing-business/      # Business analysis & market research
│   ├── code-simplifier/         # Code refactoring & cleanup
│   ├── debugging-issues/        # Error diagnosis & troubleshooting
│   ├── diagram-maker/           # Mermaid diagram generation
│   ├── docs-write/              # Technical documentation writing
│   ├── frontend-design/         # UI/UX design guidance
│   ├── optimizing-database/     # Database performance optimization
│   ├── reviewing-code/          # Code review & quality assurance
│   └── strategizing-product/    # Product strategy & roadmap planning
│
└── learning/                    # Learning & Education Resources
    ├── prompts/
    │   └── learning-outline-generator.md   # Structured learning framework
    └── outputs/
        └── reactjs-interview-outline.md    # Example: ReactJS learning outline
```

---

## 📝 Documentation Prompts

### Business Documents
- **BRD (Business Requirements Document)**: Strategic business case, financials, stakeholder analysis
- **Business Model Canvas**: Revenue streams, value propositions, customer segments
- **Product Concept**: Product metaphor, pillars, signature interactions using 5 Whys technique

### Product Documents
- **PRD (Product Requirements Document)**: Feature specifications, user stories, acceptance criteria
- **Product Idea & Requirements Spec**: Initial product ideation and high-level requirements

### Technical Documents
- **SRS (Software Requirements Specification)**: Functional/non-functional requirements, Gherkin scenarios
- **TDD (Technical Design Document)**: Architecture, database design, API contracts, folder structure
- **README Generator**: Professional GitHub README with badges, structure, usage examples

---

## 🎯 AI Skills

### Development Skills
- **`code-simplifier`**: Refactor code for clarity, consistency, and maintainability
- **`debugging-issues`**: Root cause analysis, stack trace interpretation, error resolution
- **`reviewing-code`**: Code quality assessment, security checks, best practices enforcement
- **`diagram-maker`**: State machine diagrams using Mermaid for comprehensive code path mapping

### Architecture Skills
- **`optimizing-database`**: Query optimization, indexing strategies, performance tuning
- **`frontend-design`**: UI/UX guidance, component design, accessibility standards

### Strategy Skills
- **`strategizing-product`**: Market analysis, feature prioritization, competitive positioning
- **`analyzing-business`**: Business model evaluation, market sizing (TAM/SAM/SOM)
- **`docs-write`**: Technical documentation, API docs, user guides

---

## 🎓 Learning Prompts

### Learning Outline Generator
Generates structured, hierarchical learning plans optimized for note-taking in tools like Notion:

- **Customizable depth**: Overview, Detailed, or Deep-dive levels
- **Personalized**: Adapts to current skill level and learning goals
- **Systematic**: Progressive structure from fundamentals to advanced topics
- **Practical**: Keywords, core questions, and actionable topics for self-research

**Example Output**: See [`reactjs-interview-outline.md`](learning/outputs/reactjs-interview-outline.md) for a comprehensive ReactJS learning plan.

---

## 🚀 Usage

### Using Documentation Prompts

1. **Choose your prompt**: Navigate to [`documentations/`](documentations/) and select the appropriate generator
2. **Fill in the input section**: Replace placeholders with your project details
3. **Submit to AI**: Copy the entire prompt with your inputs to your AI assistant
4. **Receive structured output**: Get a professionally formatted document following industry standards

**Example: Generate a PRD**
```markdown
1. Open documentations/prd-generator-prompt.md
2. Replace [Project Name], [Status], [Stakeholders], etc. with your data
3. Copy the entire content
4. Paste into ChatGPT, Claude, or GitHub Copilot Chat
5. Review and refine the generated PRD
```

### Using AI Skills

**For AI Agent Configuration** (GitHub Copilot, Claude, etc.):
1. Navigate to the [`skills/`](skills/) directory
2. Each `SKILL.md` contains a frontmatter declaration:
   ```yaml
   ---
   name: code-simplifier
   description: Simplifies and refines code for clarity...
   ---
   ```
3. Configure your AI agent to recognize these skills
4. Trigger skills via commands like "simplify this code" or "debug this error"

**Manual Usage**:
1. Read the skill documentation to understand its purpose
2. Apply the methodologies manually in your code reviews or development process
3. Use as reference for best practices and structured thinking

### Using Learning Prompts

1. Open [`learning/prompts/learning-outline-generator.md`](learning/prompts/learning-outline-generator.md)
2. Fill in:
   - **Topic**: What you want to learn (e.g., "Microservices Architecture")
   - **Current Level**: Beginner, Intermediate, or Expert
   - **Goal**: Why you're learning (e.g., "Pass system design interview")
   - **Detail Level**: Overview, Detailed, or Deep-dive
3. Submit to AI assistant
4. Receive a structured outline ready for Notion or your note-taking tool

---

## 📦 Installation

This is a documentation repository, so no installation is required. Simply clone and use:

```bash
# Clone the repository
git clone https://github.com/yourusername/my-ultimate-prompts.git

# Navigate to the directory
cd my-ultimate-prompts

# Browse prompts in your favorite editor
code .
```

---

## 🤝 Contributing

Contributions are welcome! Whether you have new prompts, improvements to existing ones, or bug fixes:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-prompt`)
3. **Commit** your changes (`git commit -m 'Add amazing prompt for X'`)
4. **Push** to the branch (`git push origin feature/amazing-prompt`)
5. **Open** a Pull Request

### Contribution Guidelines
- Follow existing Markdown structure and formatting
- Include clear frontmatter for skills (name, description)
- Test prompts with at least one AI assistant before submitting
- Add examples or sample outputs when applicable
- Update this README if adding new categories

---

## 🙏 Acknowledgments

- Inspired by best practices from top product management and software engineering teams
- Structured for optimal AI assistant interpretation and output quality
- Built with experience from real-world software projects and product development
- Community feedback and contributions

---

<div align="center">

**⭐ Star this repo if you find it useful! ⭐**

Made with ❤️ for developers, PMs, and lifelong learners

</div>
