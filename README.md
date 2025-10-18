# rcm-agent-claude

The `rcm-agent-claude` project is a specialized collection of Anthropic Claude AI agents designed to automate and enhance the creation of compelling, high-quality property listings. It streamlines the process from initial content generation to final, optimized, and publication-ready descriptions suitable for major booking platforms like Booking.com and Airbnb.

## Key Features

*   **Automated Content Generation**: Utilizes a `content-creator-agent` to craft engaging and persuasive property descriptions and unique selling points, drawing in potential guests with vivid storytelling and benefit-driven narratives.
*   **Multi-Stage Content Refinement**: Employs an `optimizing-editor-agent` for meticulous review and optimization, ensuring grammar, clarity, conciseness, tone consistency, legal compliance (common knowledge), and strict adherence to specific platform requirements and audience expectations.
*   **Professional Prose Enhancement**: Includes a `prose-editor` agent designed for general professional editing of written content, focusing on improving clarity, correctness, and conciseness while meticulously preserving the author's original voice and intent.
*   **Platform-Optimized Output**: Generates final listings that are not only grammatically perfect and engaging but also strategically tailored for effective performance on international booking platforms, as demonstrated by the `BOOKING-FINAL.txt` example.

## Tech Stack

This project primarily leverages Anthropic's Claude AI, with the agents specifically utilizing the `sonnet` model for advanced natural language processing, content generation, and sophisticated editing capabilities. Agent definitions and their operational guidelines are structured in Markdown format.

## Getting Started

To utilize these agents, you would typically interact with them within an Anthropic Claude environment or through an orchestration layer that integrates with the Claude API. Each agent is defined by its specific capabilities, purpose, and guiding principles, as detailed in their respective Markdown files located within the `.claude/agents` directory.

You can invoke these agents based on their `name` to perform their designated tasks:

*   **`content-creator-agent`**: For generating initial drafts of property descriptions and unique selling points.
*   **`optimizing-editor-agent`**: For the final polish and platform-specific optimization of property listings.
*   **`prose-editor`**: For general professional editing of any written content, focusing on clarity, correctness, and conciseness.

An example of a final output, refined by these agents, can be seen in `BOOKING-FINAL.txt`.