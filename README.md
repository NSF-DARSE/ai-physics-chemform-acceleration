# Case Study: Accelerating Chemical Formulation Discovery With ML/AI

## Overview

Domain experts in chemical manufacturing greatly benefit from cutting edge chemical formulation research that uses machine learning. However, given time and energy constraints and the experts not also specializing in machine learning, reproducing the results shown in publications is rendered virtually inaccessible. To address this problem, we're leveraging the power of modern large vision-language models to plan and execute a paper reproduction pipeline that can guide the domain expert through every step of understanding the data processing, training and evaluation of the models. To do that, we've developed a plugin for Claude Code which can be used by domain experts to accelerate their paper analysis and reproduction workflow.

## Getting Started

1. Launch Claude Code in a directory where you want your paper reproduction results to be at.
2. Run the following command to clone and add this plugin:
```
/plugin marketplace add https://github.com/NSF-DARSE/ai-physics-chemform-acceleration.git
```
3. In Claude Code, use this command to get started: `/Start`
   1. The full name of the skill being invoked is `/chempaper2code:start`, which you should see when you run the command.
4. Follow the instructions.

## Repository Structure

We follow the standard Claude Code plugin structure which can be seen [here](https://code.claude.com/docs/en/plugins#plugin-structure-overview). The `docs` directory includes an optional Sphinx documentation scaffold.

## Contributing

All changes must go through pull requests.
