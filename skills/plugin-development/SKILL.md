---
name: plugin-development
description: Guide for designing, scaffolding, securing, and documenting Antigravity plugins.
---

# Antigravity Plugin Development Workflow

This skill outlines the standard lifecycle for developing plugins for the Google Antigravity CLI (`agy`). It leverages the superpowers and ponytail skill sets to ensure robustness, simplicity, and correctness. Follow these five structured phases.

## Phase 1: Planning, Discussion, and Brainstorming

1. **Invoke Brainstorming**: Before beginning implementation, invoke the `superpowers:brainstorming` skill. Draft the initial specification and secure user approval.
2. **Apply Ponytail Scoping (YAGNI)**: Assess if the plugin or feature needs to exist at all. Explore if standard library tools, native platform capabilities, or existing commands can solve the problem. Aim to design the simplest solution that works.
3. **Architecture Mapping & Interface Design**: Refer to the `api-and-interface-design` skill to design clean boundaries. Map the directory structure (`commands/`, `skills/`, `agents/`, `hooks/`) and manifests (`plugin.json`, `plugin.yaml`).
4. **Context Retrieval**: Consult project conventions in `GEMINI.md` and `antigravity-guide` to align with established standards.

## Phase 2: Research and Prototyping

1. **API & CLI Testing**: Execute exploratory commands or query API endpoints to understand parameter schemas and format responses.
2. **MCP & Environment Verification**: Inspect Model Context Protocol (MCP) tool definitions and environment dependencies.

## Phase 3: Scaffolding and Implementation

1. **Bedrock Initialisation**: Run `npx @isonnymichael/bedrock init --tool antigravity` to bootstrap standard rules, workflows, and guardrails, then follow the generated instructions.
2. **Implementation Planning**: Invoke the `superpowers:writing-plans` skill to write a detailed, task-by-task plan stored in the plans directory.
3. **Execution & Test-Driven Development (TDD)**: Execute the plan using `superpowers:subagent-driven-development` or `superpowers:executing-plans`. For each task, adhere to `superpowers:test-driven-development` (write failing test, verify failure, implement code, verify success).
4. **Obsolescence & Simplicity (Ponytail Mode)**: Maintain a lean implementation. Avoid unrequested abstractions and third-party dependencies. Mark deliberate simplifications using ponytail comments highlighting limits and upgrade paths.
5. **Observability**: Integrate structured logging and telemetry using the `observability-and-instrumentation` skill to make future debugging straightforward.

## Phase 4: Security Hardening and Over-Engineering Review

1. **Threat Modelling & Input Validation**: Follow the `security-and-hardening` skill. Model injection vectors, filesystem operations, and sub-process execution.
2. **Injection Prevention**: Never format shell command strings directly with user input. Use parameter arrays or temporary script files.
3. **Secrets Safeguards**: Ensure credentials, private keys, and absolute machine-specific paths are never committed.
4. **Over-Engineering Review**: Run `ponytail-review` to audit changes. Identify and remove redundant abstractions, dead code, or unnecessary dependencies.

## Phase 5: Verification, Quality Review, and Documentation

1. **Rigorous Verification**: Invoke `superpowers:verification-before-completion`. Execute all tests and validation commands to verify correctness before claiming success.
2. **Quality Review**: Employ the `code-review-and-quality` skill (or dispatch the `code-reviewer` subagent) to review structure, readability, and performance.
3. **Documentation**: Write a detailed `README.md` covering prerequisites, command definitions, usage examples, and configuration options. Add code comments explaining non-obvious architecture or error handlers.
