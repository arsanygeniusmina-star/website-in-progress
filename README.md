# THE WEBSITE IN PROGRESS

A conversational AI website builder with a real in-browser language model.

## What changed

The project no longer uses Ollama or a fake keyword-command AI. The new intelligence layer runs the language model directly in the browser through WebGPU and WebLLM, while the website-building logic, website state, planner contract, operation executor, history, renderer, and interaction system are custom code in this project.

The browser model is downloaded once and cached locally after the first run. WebLLM supports in-browser inference and OpenAI-style chat completion APIs; its current prebuilt model list includes low-resource Llama 3.2 1B/3B variants. WebGPU availability depends on the browser/device.

## Agent loop

1. Read the conversation memory.
2. Inspect the current website state.
3. Understand the latest request.
4. Produce a multi-step build plan as structured operations.
5. Execute the operations against the live website state.
6. Validate the resulting structure in code.
7. Render the updated site.
8. Keep the result in memory for the next request.

## Example conversation

- “Build me a portfolio for a 3D designer.”
- “Make it much darker and more cinematic.”
- “Add a Work page with three projects.”
- “Give the hero a huge title and an animated circle.”
- “Add a contact section at the bottom.”
- “Make the navigation open the Work page.”
- “Now simplify the typography and give everything more breathing room.”

No Ollama installation or cloud API key is required for the browser AI path.

## Requirements

- A modern Chromium-based browser with WebGPU enabled/supporting the device.
- Internet access on first model load so the browser can download model assets.
- Enough GPU memory for the selected model. The app prefers a low-resource 3B Llama 3.2 model and can fall back to a 1B model.

## Important limitation

This is a custom AI agent system, not a new frontier-scale language model trained from random initialization. Training a model comparable to ChatGPT from scratch requires a very large training corpus and substantial compute. This project instead builds the website-builder intelligence, agent loop, memory, tools, and renderer from scratch while running an open model locally in the browser.
