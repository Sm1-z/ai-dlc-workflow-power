# AI-DLC Workflow Power for Kiro

A comprehensive Kiro Power that implements the complete **AI-Driven Development Life Cycle (AI-DLC)** methodology developed by AWS. This Power provides an intelligent, adaptive software development workflow that adapts to your project's needs, maintains quality standards, and keeps you in control of the process.

## Overview

AI-DLC is a structured three-phase software development methodology:

- **🔵 INCEPTION PHASE**: Planning, requirements gathering, and architectural decisions
- **🟢 CONSTRUCTION PHASE**: Detailed design, implementation, and testing
- **🟡 OPERATIONS PHASE**: Deployment and monitoring (future expansion)

**Key Feature**: The workflow adapts to the work, not the other way around. AI-DLC intelligently determines which stages are needed based on your project's complexity and requirements.

## Installation

### Method 1: Direct Installation
1. Download or clone this repository
2. Copy the entire `ai-dlc-workflow` folder to your Kiro Powers directory:
   - **Kiro CLI**: `~/.kiro/powers/`
   - **Kiro IDE**: Use the Powers panel to install from local folder

### Method 2: From GitHub (Recommended)
1. In Kiro, open the Powers panel
2. Click "Install from URL"
3. Enter: `https://github.com/[your-username]/ai-dlc-workflow-power`
4. Click Install

## Quick Start

Once installed, using AI-DLC is simple:

1. **Activate the Power** in your Kiro environment
2. **Start any software development project** by saying:

```
"Using AI-DLC, [describe what you want to build]"
```

### Examples

```
"Using AI-DLC, I want to build a REST API for user management"
```

```
"Using AI-DLC, I want to add a notification system to my existing app"
```

```
"Using AI-DLC, I want to migrate my monolith to microservices"
```

## What Happens Next

When you start an AI-DLC workflow:

1. **AI-DLC automatically activates** and displays the welcome message
2. **Workspace analysis** - Determines if this is a new or existing project
3. **Requirements gathering** - Asks clarifying questions if needed
4. **Execution planning** - Shows which stages will run and why
5. **Your approval** - You review and approve the plan
6. **Workflow execution** - AI-DLC executes with checkpoints at each stage
7. **Deliverables** - You get working code with complete documentation

## Features

### ✅ Complete Official Implementation
- Contains the exact same workflow specification used by AI-DLC systems
- All 27 official rule files included in steering directory
- Maintains full compatibility with AWS AI-DLC methodology

### ✅ Adaptive Intelligence
- **Greenfield Projects**: Skips reverse engineering, focuses on requirements and design
- **Brownfield Projects**: Analyzes existing code, plans incremental changes
- **Simple Changes**: Streamlined workflow with minimal overhead
- **Complex Systems**: Full methodology with detailed planning and design

### ✅ Comprehensive Coverage
- **Requirements Analysis** with adaptive depth (minimal/standard/comprehensive)
- **User Stories** generation for complex requirements
- **Application Design** for component architecture
- **Code Generation** with detailed planning and implementation
- **Build and Test** instructions for comprehensive testing

### ✅ Quality Assurance
- **Audit Trail**: Complete logging of all decisions and user inputs
- **Content Validation**: Ensures all generated content meets quality standards
- **Progress Tracking**: Maintains state across interrupted sessions
- **User Control**: You approve each phase before proceeding

## Supported Workflows

### 1. New Greenfield Project
Perfect for starting fresh projects with no existing code.

### 2. Existing Codebase Enhancement
Analyzes your current system and plans incremental improvements.

### 3. Session Resumption
Automatically detects and resumes interrupted AI-DLC sessions.

### 4. Complex Multi-Component Systems
Breaks down large systems into manageable units of work.

## File Structure

AI-DLC creates organized documentation in your project:

```
aidlc-docs/
├── inception/                  # Planning and architecture
├── construction/               # Design and implementation
├── operations/                 # Future: deployment artifacts
├── aidlc-state.md             # Progress tracking
└── audit.md                   # Complete decision history
```

## Power Contents

This Power includes:

### Core Files
- **POWER.md** - Complete AI-DLC workflow specification
- **README.md** - This documentation

### Steering Files (27 official rule files)
- **common/** (10 files) - Core workflow rules and validation
- **inception/** (7 files) - Planning phase procedures
- **construction/** (6 files) - Implementation phase procedures
- **operations/** (1 file) - Future operations procedures

## Best Practices

### Starting Projects
- Always begin with "Using AI-DLC, ..." to activate the workflow
- Be specific about what you want to build
- Include context about existing systems or constraints

### During Execution
- Answer questions using the [Answer]: tag format with letter choices (A, B, C, D, E)
- Choose "E - Other" if provided options don't match your needs
- Review each phase carefully before approving
- Involve team members for architectural decisions

### Session Management
- AI-DLC automatically saves progress and can resume interrupted sessions
- Check `aidlc-state.md` to understand current progress
- Review `audit.md` for complete decision history

## Troubleshooting

### Workflow Not Activating
- Ensure you start with exactly: "Using AI-DLC, ..."
- Verify the Power is activated in Kiro
- Try restarting your AI assistant session

### Session Not Resuming
- Check if `aidlc-docs/aidlc-state.md` exists in your project
- If corrupted, AI-DLC can reconstruct state from existing artifacts

### Questions Not Appearing
- AI-DLC creates questions in dedicated files, never in chat
- Look for files ending in `-questions.md` in `aidlc-docs/` subdirectories

## Advanced Usage

### Accessing Rule Details
You can access any of the 27 official rule files using Kiro's `readSteering` action:

```
readSteering(powerName="ai-dlc-workflow", steeringFile="common/process-overview.md")
```

### Customization
- All rules and configurations are in the steering files
- Depth levels and execution criteria can be referenced from steering files
- No additional configuration required

## Requirements

- **Kiro CLI** (latest version) or **Kiro IDE**
- No additional dependencies required

## License

MIT-0 - Same as the original AWS AI-DLC methodology

## Resources

- **Official Blog**: [AI-Driven Development Life Cycle](https://aws.amazon.com/blogs/devops/ai-driven-development-life-cycle/)
- **Method Definition**: [AI-DLC Methodology Paper](https://prod.d13rzhkk8cj2z0.amplifyapp.com/)
- **Original Repository**: [aidlc-workflows](https://github.com/aws-samples/aidlc-workflows)
- **Kiro Documentation**: [Kiro Powers](https://kiro.dev/docs/powers/)

## Contributing

This Power implements the official AWS AI-DLC methodology. For methodology improvements, please refer to the [original AWS repository](https://github.com/aws-samples/aidlc-workflows).

For Power-specific issues or improvements:
1. Fork this repository
2. Create a feature branch
3. Submit a pull request

## Support

- **Kiro Support**: [Kiro Documentation](https://kiro.dev/docs/)
- **AI-DLC Methodology**: [AWS AI-DLC Resources](https://aws.amazon.com/blogs/devops/ai-driven-development-life-cycle/)

---

**Built with ❤️ for the Kiro community**

Transform your software development process with the power of adaptive, intelligent workflows.