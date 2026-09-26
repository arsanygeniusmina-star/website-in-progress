# THE WEBSITE IN PROGRESS

## WIP Brain

The editor contains a custom autonomous website-building intelligence layer called **WIP Brain**.

It does not use Ollama and does not require a cloud AI API key. The language-model inference runs in the browser through WebGPU/WebLLM, while the agent architecture around the model is custom to this repository.

### Autonomous loop

Every user request can flow through:

1. Understand the conversation and current site.
2. Plan concrete website changes.
3. Execute structured build operations.
4. Persist project memory.
5. Run deterministic validation.
6. Run a separate AI senior-QA pass.
7. Apply targeted repairs.
8. Return to the same project for the next request.

### Maximum brain

The browser AI now ranks supported models and attempts the strongest compatible option first. The current WebLLM configuration includes Hermes-3 Llama 3.1 8B variants, including a q4f32 variant and a q4f16 variant. WebLLM's official configuration also identifies the Hermes-3 Llama 3.1 8B models as supporting function calling.

Because an 8B browser model can require several GB of GPU memory, WIP Brain automatically falls back to smaller supported models if the strongest candidate cannot load.

### What “strongest model in the world” means here

This repository can realistically become an extremely strong **specialized website-building agent**, but it is not truthful to claim that a small web application has trained a new frontier-scale general-purpose foundation model from zero. Frontier pretraining requires enormous datasets, accelerator clusters, evaluation infrastructure and research.

The strategy in this project is instead:

**strong compatible base model + custom agent architecture + persistent project memory + structured website tools + deterministic validation + AI critique + self-repair**

That architecture is what lets the product behave like an autonomous website engineer rather than a keyword command parser.

## Example conversation

“Build me a premium portfolio for a 3D designer.”

“Make it darker and more cinematic.”

“Add a Work page.”

“Give the hero a huge title and an animated visual.”

“Add a contact section.”

“Make the navigation open the Work page.”

“Now make mobile feel intentionally designed.”

WIP Brain keeps the website and the important conversation context available for every request.

## Requirements

- Modern Chromium-based browser with WebGPU.
- Internet access for the first model download.
- Enough GPU memory for at least one compatible model.
- Model assets are cached by the browser after download.


### v3 builder engine

The engine now exports functional input and textarea controls, supports duplication and z-order operations, stores site metadata, and validates page navigation references and semantic section organization.


## v4 quality engine

The project now carries image source/alt metadata and accessible labels, a reusable design-system state, adaptive model ranking, and stronger deterministic QA including overlap detection and accessibility checks before the AI repair pass.
