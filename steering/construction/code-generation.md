# Code Generation - Detailed Steps

## Overview
This stage generates code for each unit of work through two integrated parts:
- **Part 1 - Planning**: Create detailed code generation plan with explicit steps
- **Part 2 - Generation**: Execute approved plan to generate code, tests, and artifacts

## Prerequisites
- Unit Design Generation must be complete for the unit
- NFR Implementation (if executed) must be complete for the unit
- All unit design artifacts must be available
- Unit is ready for code generation

---

## CRITICAL: Code Placement Rules

**NEVER place generated code in `aidlc-docs/`** - This directory is ONLY for documentation.

### Brownfield Projects (Existing Codebase)
**MANDATORY**: Detect and follow existing project structure:
1. Scan workspace for existing source directories (`src/`, `lib/`, `app/`, package structures)
2. Identify language-specific patterns (Java packages, Python modules, etc.)
3. Place new/modified code in the SAME structure as existing code
4. Match existing naming conventions, directory depth, and organization
5. If modifying existing files, edit them in place - do NOT copy to aidlc-docs/

### Greenfield Projects (New Codebase)
**MANDATORY**: Create standard project structure based on language/framework:
- **Java/Maven**: `src/main/java/`, `src/test/java/`
- **Java/Gradle**: `src/main/java/`, `src/test/java/`
- **Python**: `src/`, `tests/` or root with package structure
- **JavaScript/Node**: `src/`, `lib/`, `test/`
- **TypeScript**: `src/`, `dist/`, `test/`
- **Go**: Package directories following Go conventions
- **Rust**: `src/`, `tests/`
- **C#/.NET**: `src/`, `tests/`
- **Infrastructure (CDK/Terraform)**: `infrastructure/`, `cdk/`, `terraform/`

### Validation Before Code Generation
**MANDATORY**: Before generating ANY code file:
1. Determine target directory by analyzing existing structure OR creating standard structure
2. Verify target path is NOT under `aidlc-docs/`
3. If path contains `aidlc-docs/`, STOP and recalculate correct path
4. Document target paths in code generation plan for user review

---

# PART 1: PLANNING

## Step 1: Detect Project Structure (MANDATORY)
- [ ] **Brownfield**: Scan workspace to identify existing source directories and patterns
- [ ] **Brownfield**: Document existing structure (e.g., "Java Maven project with src/main/java/com/example/")
- [ ] **Greenfield**: Determine language/framework and standard structure to create
- [ ] **CRITICAL**: Verify NO code will be placed in `aidlc-docs/` directory
- [ ] Document target code directories in the plan for user review

## Step 2: Analyze Unit Context
- [ ] Read unit design artifacts from Unit Design Generation
- [ ] Read unit story map to understand assigned stories
- [ ] Identify unit dependencies and interfaces
- [ ] Validate unit is ready for code generation

## Step 3: Create Detailed Unit Code Generation Plan
- [ ] Create explicit steps for unit generation:
  - Business Logic Generation
  - Business Logic Unit Testing
  - Business Logic Summary
  - API Layer Generation
  - API Layer Unit Testing
  - API Layer Summary
  - Repository Layer Generation
  - Repository Layer Unit Testing
  - Repository Layer Summary
  - Database Migration Scripts Generation (if data models exist)
  - Documentation Generation (API docs, README updates)
  - Deployment Artifacts Generation
- [ ] Number each step sequentially
- [ ] Include story mapping references for this unit
- [ ] Add checkboxes [ ] for each step

## Step 4: Include Unit Generation Context
- [ ] For this unit, include:
  - Stories implemented by this unit
  - Dependencies on other units/services
  - Expected interfaces and contracts
  - Database entities owned by this unit
  - Service boundaries and responsibilities

## Step 5: Create Unit Plan Document
- [ ] Save complete plan as `aidlc-docs/construction/plans/{unit-name}-code-generation-plan.md`
- [ ] Include step numbering (Step 1, Step 2, etc.)
- [ ] Include unit context and dependencies
- [ ] Include story traceability
- [ ] Ensure plan is executable step-by-step
- [ ] Emphasize that this plan is the single source of truth for Code Generation

## Step 6: Summarize Unit Plan
- [ ] Provide summary of the unit code generation plan to the user
- [ ] Highlight unit generation approach
- [ ] Explain step sequence and story coverage
- [ ] Note total number of steps and estimated scope

## Step 7: Log Approval Prompt
- [ ] Before asking for approval, log the prompt with timestamp in `aidlc-docs/audit.md`
- [ ] Include reference to the complete unit code generation plan
- [ ] Use ISO 8601 timestamp format

## Step 8: Wait for Explicit Approval
- [ ] Do not proceed until the user explicitly approves the unit code generation plan
- [ ] Approval must cover the entire plan and generation sequence
- [ ] If user requests changes, update the plan and repeat approval process

## Step 9: Record Approval Response
- [ ] Log the user's approval response with timestamp in `aidlc-docs/audit.md`
- [ ] Include the exact user response text
- [ ] Mark the approval status clearly

## Step 10: Update Progress
- [ ] Mark Code Planning complete in `aidlc-state.md`
- [ ] Update the "Current Status" section
- [ ] Prepare for transition to Code Generation

---

# PART 2: GENERATION

## Step 11: Load Unit Code Generation Plan
- [ ] Read the complete plan from `aidlc-docs/construction/plans/{unit-name}-code-generation-plan.md`
- [ ] Identify the next uncompleted step (first [ ] checkbox)
- [ ] Load the context for that step (unit, dependencies, stories)

## Step 12: Execute Current Step
- [ ] Perform exactly what the current step describes
- [ ] **CRITICAL**: Place code in detected project structure from Step 1 - NEVER in aidlc-docs/
- [ ] **Brownfield**: Match existing directory patterns, naming conventions, and organization
- [ ] **Greenfield**: Use standard structure for the language/framework
- [ ] Follow the unit's story requirements
- [ ] Respect dependencies and interfaces defined in the plan

## Step 13: Update Progress
- [ ] Mark the completed step as [x] in the unit code generation plan
- [ ] Mark associated unit stories as [x] when their generation is finished
- [ ] Update `aidlc-docs/aidlc-state.md` current status
- [ ] Save all generated artifacts

## Step 14: Continue or Complete Generation
- [ ] If more steps remain, return to Step 11
- [ ] If all steps complete, proceed to present completion message

## Step 15: Present Completion Message
- Present completion message in this structure:
     1. **Completion Announcement** (mandatory): Always start with this:

```markdown
# 💻 Code Generation Complete - [unit-name]
```

     2. **AI Summary** (optional): Provide structured bullet-point summary of code generation
        - Format: "Code generation has created [description]:"
        - List key code artifacts generated (bullet points)
        - List test coverage and documentation created
        - Mention deployment artifacts and configuration files
        - DO NOT include workflow instructions ("please review", "let me know", "proceed to next phase", "before we proceed")
        - Keep factual and content-focused
     3. **Formatted Workflow Message** (mandatory): Always end with this exact format:

```markdown
> **📋 <u>**REVIEW REQUIRED:**</u>**  
> Please examine the generated code in your project source directories



> **🚀 <u>**WHAT'S NEXT?**</u>**
>
> **You may:**
>
> 🔧 **Request Changes** - Ask for modifications to the generated code based on your review  
> ✅ **Continue to Next Stage** - Approve code generation and proceed to **[next-unit/Build & Test]**

---
```

## Step 16: Wait for Explicit Approval
- Do not proceed until the user explicitly approves the generated code
- Approval must be clear and unambiguous
- If user requests changes, update the code and repeat the approval process

## Step 17: Record Approval and Update Progress
- Log approval in audit.md with timestamp
- Record the user's approval response with timestamp
- Mark Code Generation stage as complete for this unit in aidlc-state.md

---

## Critical Rules

### Planning Phase Rules
- **DETECT PROJECT STRUCTURE FIRST**: Always identify existing code directories before planning
- **DOCUMENT TARGET PATHS**: Include specific code placement paths in the plan
- Create explicit, numbered steps for all generation activities
- Include story traceability in the plan
- Document unit context and dependencies
- Get explicit user approval before generation

### Generation Phase Rules
- **NEVER USE aidlc-docs/ FOR CODE**: This is a blocking error - code ONLY goes in project source directories
- **BROWNFIELD**: Match existing project structure exactly - same patterns, same conventions
- **GREENFIELD**: Create standard language/framework structure - never invent custom locations
- **NO HARDCODED LOGIC**: Only execute what's written in the unit plan
- **FOLLOW PLAN EXACTLY**: Do not deviate from the step sequence
- **UPDATE CHECKBOXES**: Mark [x] immediately after completing each step
- **STORY TRACEABILITY**: Mark unit stories [x] when functionality is implemented
- **RESPECT DEPENDENCIES**: Only implement when unit dependencies are satisfied

## Completion Criteria
- Complete unit code generation plan created and approved
- All steps in unit code generation plan marked [x]
- All unit stories implemented according to plan
- All code and tests generated (tests will be executed in Build & Test phase)
- Deployment artifacts generated
- Complete unit ready for build and verification
