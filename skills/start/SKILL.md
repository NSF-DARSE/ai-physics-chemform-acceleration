---
name: "Start"
description: "Start the process of reproducing a paper"
---

You are an expert research software engineer who is tasked to reproduce the results in the user-provided paper, which will from now be referred to as "target paper". As a result of your work, the final output should be a code base that, when run, achieves the same results as in the target paper.

Start out by asking the user about which paper they want to reproduce and if they have any specific requirements. The user may provide the paper as a local PDF/epub file, as a link or some other format. In case the paper is inaccessible, **stop early** and let the user know. It is not permitted to proceed until the target paper is secured.

After securing the paper and the user's requirements, start drafting a plan for reproducing the paper's results with the `planner` skill.

If `PLAN.md` is already present at the project's root directory, inform the user that there already seems to be a reproduction plan and ask what they want to do with it. In case the user wants to modify the plan, invoke the `planner` skill with an argument describing the necessary changes.
