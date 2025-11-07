<div align="center">
    <img src="./media/FrenchPOC-LOGOS-General-EXE-1_FP-Picto Fd Bleu.png"/>
    <h1>🔧 Hardware Spec Kit</h1>
    <h3><em>Build high-quality hardware products faster.</em></h3>
</div>

<p align="center">
    <strong>An open source toolkit for hardware teams implementing Spec-Driven Development for hardware products and prototypes - spanning mechanical, electrical, and embedded systems.</strong>
</p>

<p align="center">
    <a href="https://github.com/LeFrenchPOC/hardware-spec-kit/actions/workflows/release.yml"><img src="https://github.com/LeFrenchPOC/hardware-spec-kit/actions/workflows/release.yml/badge.svg" alt="Release"/></a>
    <a href="https://github.com/LeFrenchPOC/hardware-spec-kit/stargazers"><img src="https://img.shields.io/github/stars/LeFrenchPOC/hardware-spec-kit?style=social" alt="GitHub stars"/></a>
    <a href="https://github.com/LeFrenchPOC/hardware-spec-kit/blob/main/LICENSE"><img src="https://img.shields.io/github/license/LeFrenchPOC/hardware-spec-kit" alt="License"/></a>
</p>

---

## Table of Contents

- [🤔 What is Spec-Driven Hardware Development?](#-what-is-spec-driven-hardware-development)
- [⚡ Get Started](#-get-started)
- [📽️ Video Overview](#️-video-overview)
- [🤖 Supported AI Agents](#-supported-ai-agents)
- [🔧 Specify CLI Reference](#-specify-cli-reference)
- [📚 Core Philosophy](#-core-philosophy)
- [🌟 Development Phases](#-development-phases)
- [🎯 Experimental Goals](#-experimental-goals)
- [🔧 Prerequisites](#-prerequisites)
- [📖 Learn More](#-learn-more)
- [📋 Detailed Process](#-detailed-process)
- [🔍 Troubleshooting](#-troubleshooting)
- [👥 Maintainers](#-maintainers)
- [💬 Support](#-support)
- [🙏 Acknowledgements](#-acknowledgements)
- [📄 License](#-license)

## 🤔 What is Spec-Driven Hardware Development?

Spec-Driven Development **flips the script** on traditional hardware development. For decades, CAD files and schematics have been king — specifications were just scaffolding we built and discarded once the "real work" of design began. Spec-Driven Hardware Development changes this: **specifications become executable**, directly generating working hardware designs, embedded code, and manufacturing documentation rather than just guiding them.

### Why Hardware Needs Spec-Driven Development

Hardware development is inherently complex, involving multiple disciplines:
- **Mechanical Design**: Enclosures, mounting systems, thermal management
- **Electrical Engineering**: Schematics, PCB layout, power distribution
- **Embedded Systems**: Firmware, drivers, communication protocols
- **Manufacturing**: Assembly procedures, testing protocols, quality control

Traditional approaches treat specs as throw-away documentation. Spec-Driven Hardware Development makes specifications the **living source of truth** that drives design decisions, validates implementations, and ensures all subsystems work together.

## ⚡ Get Started

### 1. Install Specify CLI

Choose your preferred installation method:

#### Option 1: Persistent Installation (Recommended)

Install once and use everywhere:

```bash
uv tool install specify-cli --from git+https://github.com/LeFrenchPOC/hardware-spec-kit.git
```

Then use the tool directly:

```bash
specify init <PROJECT_NAME>
specify check
```

To upgrade specify run:

```bash
uv tool install specify-cli --force --from git+https://github.com/LeFrenchPOC/hardware-spec-kit.git
```

#### Option 2: One-time Usage

Run directly without installing:

```bash
uvx --from git+https://github.com/LeFrenchPOC/hardware-spec-kit.git specify init <PROJECT_NAME>
```

### 2. Establish project principles

Use the **`/constitution`** command to create your project's governing principles and development guidelines that will guide all subsequent hardware development across mechanical, electrical, and embedded domains.

### 3. Create functional specifications

Use the **`/specify`** command to document:
- Product requirements and user scenarios
- Mechanical constraints and form factor requirements
- Electrical specifications and power budgets  
- Embedded system functionality and interfaces
- Manufacturing and testing requirements

### 4. Generate implementation plan

Use the **`/plan`** command to create a detailed implementation plan covering:
- CAD tool selection and mechanical design approach
- PCB design tools and electrical architecture
- Firmware development environment and embedded architecture
- Component selection and sourcing strategy
- Testing and validation procedures

### 5. Break down into tasks

Use the **`/tasks`** command to generate an actionable task breakdown organized by engineering discipline and hardware subsystem.

### 6. Implement

Use the **`/implement`** command to guide implementation across all hardware domains while maintaining traceability to specifications.

## 📽️ Video Overview

*Coming soon: Video walkthrough of Hardware Spec Kit for hardware product development*

> **Note**: This is a fork of [github/spec-kit](https://github.com/github/spec-kit) adapted specifically for hardware development workflows.

## 🤖 Supported AI Agents

| Agent                                                     | Support | Notes                                             |
|-----------------------------------------------------------|---------|---------------------------------------------------|
| [Claude Code](https://www.anthropic.com/claude-code)      | ✅ |                                                   |
| [GitHub Copilot](https://code.visualstudio.com/)          | ✅ |                                                   |
| [Gemini CLI](https://github.com/google-gemini/gemini-cli) | ✅ |                                                   |
| [Cursor](https://cursor.sh/)                              | ✅ |                                                   |
| [Qwen Code](https://github.com/QwenLM/qwen-code)          | ✅ |                                                   |
| [opencode](https://opencode.ai/)                          | ✅ |                                                   |
| [Windsurf](https://windsurf.com/)                         | ✅ |                                                   |
| [Kilo Code](https://github.com/Kilo-Org/kilocode)         | ✅ |                                                   |
| [Auggie CLI](https://docs.augmentcode.com/cli/overview)   | ✅ |                                                   |
| [CodeBuddy CLI](https://www.codebuddy.ai/cli)             | ✅ |                                                   |
| [Roo Code](https://roocode.com/)                          | ✅ |                                                   |
| [Codex CLI](https://github.com/openai/codex)              | ✅ |                                                   |
| [Amazon Q Developer CLI](https://aws.amazon.com/developer/learning/q-developer-cli/) | ⚠️ | Amazon Q Developer CLI [does not support](https://github.com/aws/amazon-q-developer-cli/issues/3064) custom arguments for slash commands. |
| [Amp](https://ampcode.com/) | ✅ | |

## 🔧 Specify CLI Reference

### Commands

| Command     | Description                                                    |
|-------------|----------------------------------------------------------------|
| `init`      | Initialize a new Hardware Specify project from the latest template      |
| `check`     | Check for installed tools (`git`, AI agents, CAD tools) |

### `specify init` Arguments & Options

| Argument/Option        | Type     | Description                                                                  |
|------------------------|----------|------------------------------------------------------------------------------|
| `<project-name>`       | Argument | Name for your new hardware project directory (optional if using `--here`, or use `.` for current directory) |
| `--ai`                 | Option   | AI assistant to use: `claude`, `gemini`, `copilot`, `cursor-agent`, `qwen`, `opencode`, `codex`, `windsurf`, `kilocode`, `auggie`, `roo`, `codebuddy`, `amp`, or `q` |
| `--script`             | Option   | Script variant to use: `sh` (bash/zsh) or `ps` (PowerShell)                 |
| `--ignore-agent-tools` | Flag     | Skip checks for AI agent tools like Claude Code                             |
| `--no-git`             | Flag     | Skip git repository initialization                                          |
| `--force`              | Flag     | Merge template files into non-empty directory without confirmation |
| `--here`               | Flag     | Initialize in the current directory (equivalent to `.`)                     |
| `--debug`              | Flag     | Enable debug output for troubleshooting                                     |
| `--github-token`       | Option   | GitHub personal access token for API requests (helps with rate limiting)    |

### Examples

```bash
# Basic hardware project initialization
specify init my-hardware-project

# Initialize with specific AI assistant
specify init my-hardware-project --ai claude

# Initialize with Cursor support
specify init my-hardware-project --ai cursor-agent

# Initialize with PowerShell scripts (Windows/cross-platform)
specify init my-hardware-project --ai copilot --script ps

# Initialize in current directory
specify init . --ai copilot
# or use the --here flag
specify init --here --ai copilot

# Force merge into current (non-empty) directory without confirmation
specify init . --force --ai copilot
# or 
specify init --here --force --ai copilot

# Skip git initialization
specify init my-hardware-project --ai gemini --no-git

# Enable debug output for troubleshooting
specify init my-hardware-project --ai claude --debug

# Use GitHub token for API requests (helpful for corporate environments)
specify init my-hardware-project --ai claude --github-token ghp_your_token_here

# Check system requirements
specify check
```

### Available Slash Commands

After running `specify init`, your AI coding agent will have access to these slash commands for structured hardware development:

#### Core Commands

- **`/constitution`** - Define project principles, design constraints, and quality standards specific to hardware development
- **`/specify`** - Create comprehensive hardware product specifications covering mechanical, electrical, and embedded requirements
- **`/plan`** - Generate detailed implementation plans with tool selection, design approach, and validation procedures
- **`/tasks`** - Break down work into actionable tasks organized by discipline and subsystem
- **`/implement`** - Execute implementation following the structured task breakdown

#### Optional Commands

- **`/clarify`** - Validate and refine specifications before planning
- **`/analyze`** - Perform deep analysis of specifications and designs
- **`/checklist`** - Generate requirement validation checklists for hardware verification

## 📚 Core Philosophy

Hardware Spec Kit adapts software engineering best practices to the unique challenges of hardware development:

1. **Specifications First**: Define complete mechanical, electrical, and embedded requirements before any CAD work
2. **Multi-Discipline Integration**: Ensure mechanical, electrical, and embedded systems are designed as integrated wholes
3. **Design for Test**: Build testability into hardware from the start - mechanical fit checks, electrical validation, firmware testing
4. **Iterative Refinement**: Start with high-level architecture, progressively refine through detailed design
5. **Documentation as Code**: Keep specifications, schematics, and firmware docs in sync with actual designs
6. **Manufacturing-Aware**: Consider assembly, testing, and manufacturing constraints throughout the design process

## 🌟 Development Phases

| Phase | Focus | Key Activities |
|-------|-------|----------------|
| **0-to-1 Development** ("Greenfield") | Generate from scratch | <ul><li>Start with high-level hardware requirements</li><li>Generate specifications for mechanical, electrical, embedded</li><li>Plan implementation across disciplines</li><li>Build production-ready hardware</li></ul> |
| **Creative Exploration** | Parallel implementations | <ul><li>Explore diverse mechanical approaches</li><li>Compare different electrical architectures</li><li>Experiment with embedded platforms</li></ul> |
| **Iterative Enhancement** ("Brownfield") | Product evolution | <ul><li>Add features to existing hardware</li><li>Modernize legacy designs</li><li>Adapt manufacturing processes</li></ul> |

## 🎯 Experimental Goals

Hardware Spec Kit aims to:

- **Reduce design iterations**: Get it right the first time through comprehensive specifications
- **Improve cross-discipline communication**: Bridge mechanical, electrical, and embedded teams
- **Accelerate prototyping**: Clear specs lead to faster, more focused prototyping
- **Minimize late-stage changes**: Catch design issues during spec review, not after PCB fab
- **Enable parallel development**: Well-defined interfaces allow teams to work independently
- **Maintain design traceability**: Link every component and line of code back to requirements

## 🔧 Prerequisites

- **Linux/macOS/Windows**
- [Supported](#-supported-ai-agents) AI coding agent
- [uv](https://docs.astral.sh/uv/) for package management
- [Python 3.11+](https://www.python.org/downloads/)
- [Git](https://git-scm.com/downloads)
- **Optional CAD Tools**: Fusion360, KiCAD, or your preferred mechanical/electrical design tools

If you encounter issues with an agent, please open an issue so we can refine the integration.

## 📖 Learn More

- **[Complete Spec-Driven Development Methodology](./spec-driven.md)** - Deep dive into the full process adapted for hardware
- **[Detailed Walkthrough](#-detailed-process)** - Step-by-step hardware implementation guide

---

## 📋 Detailed Process

<details>
<summary>Click to expand the detailed step-by-step walkthrough for hardware projects</summary>

You can use the Specify CLI to bootstrap your hardware project, which will bring in the required artifacts in your environment. Run:

```bash
specify init <project_name>
```

Or initialize in the current directory:

```bash
specify init .
# or use the --here flag
specify init --here
# Skip confirmation when the directory already has files
specify init . --force
# or
specify init --here --force
```

![Specify CLI bootstrapping a new hardware project in the terminal](./media/specify_cli.gif)

You will be prompted to select the AI agent you are using. You can also proactively specify it directly in the terminal:

```bash
specify init <project_name> --ai claude
specify init <project_name> --ai gemini
specify init <project_name> --ai copilot

# Or in current directory:
specify init . --ai claude
specify init . --ai codex

# or use --here flag
specify init --here --ai claude
specify init --here --ai copilot
```

The CLI will check if you have your selected AI agent installed. If you do not, or you prefer to get the templates without checking for the right tools, use `--ignore-agent-tools` with your command:

```bash
specify init <project_name> --ai claude --ignore-agent-tools
```

### **STEP 1:** Establish project principles

The first step is to establish the guiding principles for your hardware project. This is done using the `/constitution` command with your AI agent.

The constitution defines:
- Design principles and constraints specific to your hardware
- Quality standards for mechanical, electrical, and embedded work
- Testing requirements and validation procedures
- Tool choices and workflows (CAD, PCB design, firmware development)
- Manufacturing and assembly considerations

Example prompt for a hardware project:

```text
We're building an IoT environmental sensor device. Key requirements:
- Mechanical: IP67 rated enclosure, wall-mountable, 100x80x40mm max
- Electrical: Battery powered (2x AA), <50μA sleep current, I2C sensors
- Embedded: ESP32-C3, MicroPython firmware, MQTT over WiFi
- Manufacturing: Injection molded enclosure, PCBA by external CM
- Testing: Environmental chamber testing, EMC compliance required
```

### **STEP 2:** Create hardware specifications

Use the `/specify` command to create detailed functional specifications. For hardware, you'll want to specify:

```text
Create specs for an environmental monitoring device with:
- Temperature range: -40°C to +85°C, ±0.5°C accuracy
- Humidity: 0-100% RH, ±3% accuracy
- Pressure: 300-1100 hPa
- Battery life: 2 years on 2x AA batteries with 5-minute reporting interval
- Connectivity: WiFi 2.4GHz, MQTT to cloud platform
- Enclosure: IP67, UV-resistant plastic, wall-mountable
- User interface: RGB LED status indicator, magnetic reed switch for config mode
```

The output will be a structured specification document covering:
- Functional requirements (what the device must do)
- Performance requirements (accuracy, battery life, response time)
- Physical requirements (dimensions, weight, environmental ratings)
- Interface requirements (sensors, connectivity, user interaction)
- Compliance requirements (EMC, safety, environmental)

### **STEP 3:** Functional specification clarification (required before planning)

Before generating the implementation plan, use `/clarify` to validate and refine your specifications:

```text
/clarify
```

This ensures:
- No ambiguous requirements
- All interfaces clearly defined
- Conflicting requirements identified and resolved
- Missing specifications highlighted

### **STEP 4:** Generate a hardware implementation plan

Now specify your technical approach. For hardware, this includes tool selection and design strategy:

```text
We'll implement this using:
- Mechanical: Fusion360 for enclosure design, 3D print prototypes, injection molding for production
- Electrical: KiCAD for schematic and PCB, 4-layer board, Espressif devkit for prototyping
- Embedded: ESP-IDF with Arduino framework, OTA firmware updates, low-power state machine
- Sensors: Sensirion SHT40 (temp/humidity), Bosch BMP388 (pressure), I2C bus
- Testing: Environmental chamber validation, current profiling, RF testing
```

The output will include:
- Component selection and bill of materials
- Mechanical design approach and CAD file structure
- Electrical architecture and PCB stackup
- Firmware architecture and module breakdown
- Testing and validation procedures
- Manufacturing and assembly plan

Your directory tree will include:

```text
.
├── memory
│   └── constitution.md
├── scripts
│   ├── bash/
│   │   ├── check-prerequisites.sh
│   │   ├── common.sh
│   │   ├── create-new-feature.sh
│   │   └── update-agent-context.sh
│   └── powershell/
│       ├── check-prerequisites.ps1
│       ├── common.ps1
│       ├── create-new-feature.ps1
│       └── update-agent-context.ps1
├── specs
│   └── 001-iot-sensor
│       ├── spec.md
│       ├── plan.md
│       ├── data-model.md        # Component interfaces and data structures
│       ├── contracts/           # API specs, I2C command sets
│       └── research.md          # Technology decisions and trade-offs
└── templates
    ├── plan-template.md
    ├── spec-template.md
    └── tasks-template.md
```

### **STEP 5:** Review and validate the plan

Review the generated plan to ensure:
- Correct components selected (check availability, lifecycle status)
- Realistic power budget and battery life calculations
- Feasible mechanical design (moldability, assembly)
- Appropriate firmware complexity for timeline
- Complete testing coverage

You can ask your AI agent to refine specific sections or validate technical decisions.

### **STEP 6:** Generate task breakdown

Use `/tasks` to create an actionable task list organized by engineering discipline:

```text
/tasks
```

This will generate a structured task breakdown:
- **Phase 1: Design & Specification** - Detailed requirements, interface definitions
- **Phase 2: Mechanical Design** - Enclosure CAD, 3D printed prototypes
- **Phase 3: Electrical Design** - Schematic capture, PCB layout, power analysis
- **Phase 4: Firmware Development** - Driver development, application logic, power management
- **Phase 5: Integration** - Hardware/firmware integration, system testing
- **Phase 6: Validation** - Environmental testing, compliance testing, field trials

### **STEP 7:** Implementation

Once ready, use the `/implement` command to execute your hardware development:

```text
/implement
```

The AI agent will guide you through:
- Creating CAD models and generating manufacturing files
- Designing schematics and PCB layouts
- Writing and testing firmware modules
- Documenting assembly procedures
- Defining test protocols and validation criteria

> [!IMPORTANT]
> Hardware implementation requires appropriate tools installed (Fusion360, KiCAD, ESP-IDF, etc.) and access to prototyping resources (3D printer, PCB fab, components).

Monitor your progress, validate designs at each milestone, and iterate based on test results. Your AI agent can help debug issues, suggest design improvements, and maintain documentation throughout the process.

</details>

---

## 🔍 Troubleshooting

### Common Issues

**Issue: "No template found for AI assistant"**

Make sure you have a valid GitHub release with hardware template assets. See [RELEASE_FIX_GUIDE.md](./RELEASE_FIX_GUIDE.md) for details.

**Issue: AI commands not showing up**

Verify that the command files exist in the correct location for your AI agent:
- Claude: `.claude/commands/`
- Copilot: `.github/prompts/`
- Gemini: `.gemini/commands/`

**Issue: Script execution fails**

Ensure you have the required tools installed and permissions set correctly:

```bash
# Make scripts executable
chmod +x .specify/scripts/bash/*.sh

# For PowerShell users on Linux/macOS
pwsh .specify/scripts/powershell/script-name.ps1
```

### Getting Help

1. Check existing [Issues](https://github.com/LeFrenchPOC/hardware-spec-kit/issues)
2. Review [CONTRIBUTING.md](./CONTRIBUTING.md) for development setup
3. Open a new issue with details about your environment and the problem

## 👥 Maintainers

This hardware fork is maintained by:
- **[@FrenchPOC](https://github.com/LeFrenchPOC)** - Hardware adaptation and maintenance

Original Spec Kit by:
- **[@github](https://github.com/github)** - Original Spec Kit framework

## 💬 Support

Need help? Have questions about hardware-specific workflows?

- 📝 [Open an issue](https://github.com/LeFrenchPOC/hardware-spec-kit/issues)
- 💬 [Discussions](https://github.com/LeFrenchPOC/hardware-spec-kit/discussions)
- 📖 [Documentation](./docs/)
- �� [Upstream Spec Kit](https://github.com/github/spec-kit)

## 🙏 Acknowledgements

This project is a fork of [github/spec-kit](https://github.com/github/spec-kit), adapted specifically for hardware development workflows. We're grateful to the original maintainers and contributors for creating the foundation that makes this hardware-focused toolkit possible.

Special thanks to:
- The Spec Kit team at GitHub for the original framework
- All contributors to the upstream spec-kit project
- The hardware development community for feedback and testing

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

---

<div align="center">
    <p><strong>Built with ❤️ for hardware teams everywhere</strong></p>
    <p><em>Bringing software engineering best practices to mechanical, electrical, and embedded development</em></p>
</div>
