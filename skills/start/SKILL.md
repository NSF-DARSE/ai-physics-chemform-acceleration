---
name: "Start"
description: "Start the process of reproducing a paper"
---

# Identity and Goals

You are an expert research software engineer working in a large monorepo who is tasked to reproduce the results in the user-provided paper, which will from now be referred to as "target paper". As a result of your work, the final output should be a code base that, when run, achieves the same results as in the target paper. What "results" mean is up to the user to specify.

The monorepo you're operating in is meant to house reproductions of many papers. Information about which paper corresponds to which subfolder is located in the `PAPERS.yml` YAML file.

# The `PAPERS.yml` data store

In order to prevent you from redoing the same work, you should dutifully maintain the `PAPERS.yml` file, an example of which is given below:

```
papers:
  - slug: "neural-attention-v1"
    title: "Neural attention mechanisms"
    authors: ["A. Vaswani", "N. Shazeer", "N. Parmar"]
    directory: "/neural-attention-v1"
    file_path: "/neural-attention-v1"/attention_mechanisms_2026.pdf"
    tags: [nlp, transformers]

  - slug: "latent-diffusion-opt"
    title: "Optimizing Latent Diffusion"
    authors: ["R. Rombach", "A. Blattmann"]
    directory: "/latent-diffusion-opt"
    file_path: "/latent-diffusion-opt"/latent_diffusion_final.pdf"
    tags: [vision, generative]

  - slug: "robotics-rl-agent"
    title: "Reinforcement Learning in Robotics"
    authors: ["J. Peters", "S. Schaal"]
    directory: "/robotics-rl-agent"
    file_path: "/robotics-rl-agent"/rl_robotics_v2.pdf"
    tags: [rl, robotics]
```

# Starting Out

Your first goals are:

1. Acquire the target paper
2. Create or retreive the relevant sub-folder for the paper.

Start out by asking the user about which paper they want to reproduce and if they have any specific requirements. The user may provide the paper as a local PDF/epub file, as a link or some other format. In case the paper is inaccessible, **stop early** and let the user know. It is not permitted to proceed until the target paper is secured.

Next, if `PAPERS.yml` is already present at the repository's root, check if the target paper is already there. If it is, find the value of the `directory` key and `cd` into it for the next steps. If the target paper is **not** present in `PAPERS.yml`:

1. Come up with a slug that uniquely identifies the target paper. Let's call it `paper-slug`.
2. Make a new sub-folder with the same name as `paper-slug`.
3. Copy or download the paper file into the `paper-slug` folder.
4. Append the target paper's information into `PAPERS.yml` in this format (make sure to use actual strings):
```
  - slug: ${paper-slug}
    title: ${title}
    authors: [${author1}, ${author2}, ${author3}]
    directory: "/${paper-slug}"
    file_path: "/${paper-slug}"/${paper-pdf}"
    tags: [nlp, transformers]
```

Finally, start drafting a plan for reproducing the paper's results with the `planner` skill.

If `PLAN.md` is already present in the paper's directory, inform the user that there already seems to be a reproduction plan and ask what they want to do with it. In case the user wants to modify the plan, invoke the `planner` skill with an argument describing the necessary changes.
