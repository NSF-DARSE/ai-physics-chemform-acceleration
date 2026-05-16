# Case Study: Accelerating Chemical Formulation Discovery With ML/AI

## Overview

Domain experts in chemical manufacturing greatly benefit from cutting edge chemical formulation research that uses machine learning. However, given time and energy constraints and the experts not also specializing in machine learning, reproducing the results shown in publications is rendered virtually inaccessible. To address this problem, we're leveraging the power of modern large vision-language models to plan and execute a paper reproduction pipeline that can guide the domain expert through every step of understanding the data processing, training and evaluation of the models. To do that, we've developed a plugin for Claude Code which can be used by domain experts to accelerate their paper analysis and reproduction workflow.

## Getting Started

1. Ensure that you have [Claude Code](https://claude.ai/code) installed and running.
2. Launch Claude Code in a directory where you want your paper reproduction results to be at.
3. Run the following command to clone and add this plugin:
```
/plugin marketplace add https://github.com/NSF-DARSE/ai-physics-chemform-acceleration.git
```
4. In Claude Code, use this command to get started: `/Start`
   1. The full name of the skill being invoked is `/chempaper2code:start`, which you should see when you run the command.
5. Follow the instructions.

## Workflow Overview

Using this plugin, the domain expert can go through the following steps:

1. Provide information about the target paper, which figures/tables to reproduce and what the technical requirements or constraints are.
2. Read through the model's generated plan for reproduction and validation and provide feedback.
3. Observe Claude Code invoking multiple sub-agents that implement the plan.
4. Participate in validating the code's correctness.

One important thing to know here is that we're not relying on the models to do everything. We encourage the user to be an active participant in the process and to use this tool to learn, not offload work.

## File Structure

This plugin works best if it's continuously used in the same exact folder. As a part of the first stages of the process, we initialize a `PAPERS.yml` file, which is meant to be a plain text repository of all the papers that were processed so far. Each paper lives in its own subdirectory, where the paper itself and the source code of reproduction tasks are also present.

Your directory could look like this:

```
~/Documents/Papers/
├── PAPERS.yml
├── zhang-coating-ml-2025
│   ├── Containerfile
│   ├── data
│   ├── models
│   ├── outputs
│   │   ├── figure1.pdf
│   │   ├── figure2.pdf
│   ├── PLAN.md
│   ├── README.md
│   ├── reports
│   │   ├── evaluation-report-1.md
│   │   ├── evaluation-report-2.md
│   ├── requirements.txt
│   ├── scripts
│   │   ├── 01_download_data.py
│   │   ├── 02_preprocess.py
│   │   ├── 03_train_gp.py
│   │   ├── 04_compute_pdp.py
│   │   ├── 05_plot_figure1.py
│   │   ├── 06_train_gp_hiding.py
│   │   ├── 07_plot_figure2.py
│   └── zhang-coating.pdf
```

With more time and usage of this tool, one can build a large repository of papers and reproduced results, which can be synthesized in novel and creative ways. Currently, we don't provide a specified skill for synthesis, but Claude models are generally very amenable to clearly worded instructions, so you can try to do this yourself.

## Repository Structure

We follow the standard Claude Code plugin structure which can be seen [here](https://code.claude.com/docs/en/plugins#plugin-structure-overview):

- `.claude-plugin` contains metadata about the Claude Code plugin.
- `agents` includes descriptions for sub-agents, which are expected to run with their own context, independent of what the user typed earlier in the conversation.
- `skills` includes descriptions for skills, which are system instructions for the Claude models that let us specify the model's identity, purpose and its toolset.
- `docs` includes an optional Sphinx documentation scaffold.

## Contributing

All changes must go through pull requests.
