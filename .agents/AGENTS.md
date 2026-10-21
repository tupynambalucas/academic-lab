<context-hierarchy>
  <parent src="../AGENTS.md" type="global-rules" />
  <system-instruction>
    AGENT: If you have not read "../AGENTS.md" in this session, stop now and read it using your
    file-reading tools before proceeding. Global constraints are mandatory.
  </system-instruction>
</context-hierarchy>

# Agents and Automation Context

This document serves as the bounded context router (Layer 2) for the .agents/ workspace.

## Purpose

This directory manages all AI agent behaviors, skills, and user-driven execution plans for Academic Lab.

## Workspaces

- [skills/](./skills/): Contains all custom agent skills formatted according to skill-expert guidelines.
- [plans/](./plans/): Directory dedicated to study and execution plans authored by the user.

## Guidelines

- Agents MUST strictly follow the directives in skills/ when performing tasks.
- The plans/ directory is the primary source of truth for upcoming study goals and academic milestones.
- Agents MUST read config/src/project.config.ts to retrieve technical study variables.
- Agents MUST read LEARNING_CONTEXT.md in the root to grasp the user's current subjective goals.
