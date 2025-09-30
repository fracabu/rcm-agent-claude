# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is an agent configuration repository for Claude Code, containing custom agent definitions for content creation and editing workflows. There is no executable code or build system—the repository exists solely to define specialized agents.

## Custom Agents

This repository defines three specialized agents located in `.claude/agents/`:

### 1. prose-editor
**Model**: Sonnet
**Purpose**: Professional editing agent that improves clarity, correctness, and conciseness while preserving the author's voice.

**When to use**: When content needs professional editing for publication quality, documentation refinement, or business communication.

**Workflow**:
- Reads content holistically to understand voice and intent
- Makes systematic passes for mechanics, clarity, conciseness, and consistency
- Provides edited version with "Editor's Notes" explaining changes
- Preserves author's voice while ruthlessly cutting unnecessary words

### 2. content-creator-agent
**Model**: Sonnet
**Color**: Blue
**Purpose**: Master wordsmith for crafting engaging, persuasive content tailored to specific platforms and audiences.

**Key capabilities**:
- Creates compelling narratives that draw audiences in
- Generates unique selling points (USPs) - typically 5 concise bullet points
- Integrates research insights about target audiences and best practices
- Maintains consistent tone while adhering to length constraints

**Guiding principles**:
- Evoke desire and excitement
- Prioritize clarity and conciseness
- Focus on audience experience and benefits

### 3. optimizing-editor-agent
**Model**: Sonnet
**Color**: Pink
**Purpose**: Meticulous final-pass editor ensuring output is flawless, legally compliant, and platform-ready.

**Responsibilities**:
- Scrutinizes grammar, clarity, conciseness, and tone consistency
- Verifies platform and audience alignment
- Performs common-sense checks for misleading or problematic statements
- Ensures format adherence and immediate usability

**Key difference from prose-editor**: This agent focuses on optimization, compliance, and platform-specific requirements rather than general prose improvement.

## Agent Interaction Pattern

These agents are designed to work in sequence:
1. **content-creator-agent** generates initial content with storytelling and USPs
2. **prose-editor** refines the prose for quality, clarity, and voice preservation
3. **optimizing-editor-agent** performs final optimization, compliance checks, and platform-specific formatting

**Example workflow visible in repository**:
- `booking-listing-description.txt`: Raw output from content-creator-agent (620 words)
- `BOOKING-FINAL.txt`: Final output after prose-editor and optimizing-editor passes (448 words, publication-ready)

This demonstrates the multi-agent pipeline reducing content from 620→448 words while improving quality.

## File Structure

```
.claude/
└── agents/
    ├── content-creator-agent.md
    ├── optimizing-editor-agent.md
    └── prose-editor.md
```

Each agent file contains YAML frontmatter with metadata (name, description, model, color) followed by detailed instructions for the agent's behavior.

## Working with Content

When editing content in this repository:
- Sample `.txt` files demonstrate agent output at different pipeline stages
- These are reference examples, not production code
- The agents themselves (`.claude/agents/*.md`) define the behavior used by Claude Code's Task tool
- DO NOT modify agent definitions unless explicitly requested
- Focus on improving specific content pieces when asked, using the agents as guides for quality standards