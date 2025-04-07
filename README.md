# Loop for VSCODE
Loop is a highly customizable AI coding assistant, specifically designed to streamline complex, multi-file development workflows.

- [Features](#features)
- [Code Generation](#code-generation)
- [Rewind](#rewind)
- [Model Configuration](#model-configuration)
- [System Prompts](#system-prompts)
- [Context Management](#context-management)

## Features
- **Iterative Refinement (Rewind):** Easily undo the last interaction (prompt and response) to refine your request, adjust settings, or change the context without losing your place.
- **Flexible Prompting:** Utilize any compatible AI model, define custom system prompts, and precisely control the context sent to the model.

![Wingman process preview](https://raw.githubusercontent.com/Signal-Loop/Loop-public/refs/heads/main/Pages/Media/WingmanProcessMini.png)

## Code Generation
Loop empowers you to generate new code or modify existing files based on your prompts. Following a generation request, Loop presents a clear overview of proposed changes:
- **Preview:** Review newly created files before adding them to your project.
- **Diff View:** Examine modifications to existing files line-by-line.
- **Selective Acceptance:** Accept or reject changes on a per-file basis.
- **Bulk Operations:** Accept all proposed changes with a single action.

![Extracted Files Preview](https://raw.githubusercontent.com/Signal-Loop/Loop-public/refs/heads/main/Pages/Media/ExtractedFiles.png)

## Rewind
If the AI's response doesn't meet your expectations, the Rewind feature allows for **efficient iteration** by:
- Restoring the last prompt in the input field, ready for editing.
- Removing the last prompt and its corresponding AI response from the chat history.
- Discarding changes that are not accepted.
This enables you to quickly:
- **Modify the prompt** for clarity or specificity.
- **Experiment with different AI models** or adjust their parameters.
- **Switch to a different system prompt** tailored to the task.
- **Add or remove files from the context** to guide the AI.

![Rewind Preview](https://raw.githubusercontent.com/Signal-Loop/Loop-public/refs/heads/main/Pages/Media/Rewind.png)

Important note: Rewind feature does not undo accepted changes. Use source control for this scenario.

## Model Configuration
Loop offers robust model management capabilities:
- **Multiple Model Definitions:** Configure settings for various AI models. You can define the same base model multiple times with different parameters (like temperature, stop words, topP, max output tokens) to tailor its behavior for specific use cases (e.g., "Creative Coder" with high temperature, "Strict Code Reviewer" with low temperature and specific stop words).
- **Provider Flexibility:** Integrate with popular providers like Groq, Together.ai, and others supporting standard APIs.
- **Local Model Support:** Connect to local models running via services like LM Studio.
- **On-the-Fly Switching:** Change the active AI model configuration between prompts as needed.

Supported APIs currently include:
- OpenAI API
- Google Generative AI (Gemini) API

### Configuration:
- Command: 'Loop: Select Model'
- To add new model, modify configuration 'Loop: Models' in ```user``` configuration ```json``` file

![Model Configuration Preview](https://raw.githubusercontent.com/Signal-Loop/Loop-public/refs/heads/main/Pages/Media/ModelConfiguration.png)

## System Prompts
Define and manage multiple system prompts to tailor the AI's behavior for specific tasks, languages, or frameworks.
- **Multiple Profiles:** Create and save distinct system prompts (e.g., "Python Expert," "React Component Generator," "Documentation Writer").  
![System Prompts Preview](https://raw.githubusercontent.com/Signal-Loop/Loop-public/refs/heads/main/Pages/Media/SystemPromptSelectList.png)
- **Easy Switching:** Select the most appropriate system prompt for your current task at any time.  
![System Prompts Preview](https://raw.githubusercontent.com/Signal-Loop/Loop-public/refs/heads/main/Pages/Media/SystemPromptSelectButton.png)
- **Template System:** Enhance reusability and modularity by creating system prompt templates. Reference other prompts as "building blocks" to construct complex instructions efficiently. Leverage community resources like Cursor.directory or awesome-cursorrules for inspiration.  
![System Prompts Preview](https://raw.githubusercontent.com/Signal-Loop/Loop-public/refs/heads/main/Pages/Media/SystemPromptTemplate.png)

### Configuration:
- Command: 'Loop: Select System Prompt'
- Command: 'Loop: Create System Prompt'

Created System Prompts are in workpace folder .loop/SystemPrompts'.

## Context Management
Provide the AI with relevant project context for accurate code generation and modification.
- **File Inclusion:** Add specific files to the context window to serve as references or targets for modification.
- **Exclusion Option:** Temporarily exclude files from the context without removing them entirely. Easily re-include them later.
- **In-Prompt File References:** Type `#` within the prompt input to trigger a file selection dialog. Selecting a file automatically adds it to the context and inserts its path into your prompt, allowing for direct instructions regarding specific files within your workspace.

![Context Management Preview](https://raw.githubusercontent.com/Signal-Loop/Loop-public/refs/heads/main/Pages/Media/Context.png)
