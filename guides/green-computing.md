# Green computing tips

Practical ways to get the same research done with less computing, and so less energy and less waiting. Most of them also make your work faster and easier to reproduce.

## Before you run

- **Test small first.** Debug on a small subset of the data, or a short run, before launching the full job.
- **Ask for what you need.** Requesting more cores, memory or GPUs than a job uses leaves them idle, and they still draw power. Check what earlier runs actually used.
- **Estimate the footprint** of big jobs with a calculator such as [Green Algorithms](https://calculator.green-algorithms.org/), using the details on our [computing page](compute.md).
- **Pick the right system** for the job (see [Computing we use](compute.md)).

## While it runs

- **Checkpoint long jobs**, so a failure near the end doesn't mean starting again.
- **Watch the first minutes** of a big job and cancel it early if something is wrong.

## Avoid repeating work

- **Don't re-run what hasn't changed.** Save intermediate results and use tools that only redo the steps whose inputs changed (for example a workflow manager or caching).
- **Share results** within the group instead of each person computing the same thing.

## Code and data

- **Profile before optimising**: find where the time actually goes.
- **Use efficient libraries and data formats**: vectorised operations instead of loops, and compressed or binary formats for large data.
- **Clean up regularly.** Delete temporary files and outputs you no longer need; storing data also uses energy. Log each cleanup in your Green DiSC record.

## Our group's tips

> **To fill in:** tips specific to your group's tools and data, such as settings for your main pipelines, which datasets have smaller test versions, or how to request resources on your cluster.

## Learn more

> **To fill in:** links to your group's training sessions, slides or recordings, and to talks or courses you recommend. Log each session you run in the group record.

Measure and estimate:

- [Green Algorithms calculator](https://calculator.green-algorithms.org/): estimate the carbon footprint of a computation from its runtime, hardware and location.
- [GreenAlgorithms4HPC](https://github.com/GreenAlgorithms/GreenAlgorithms4HPC): the same estimate for jobs you've already run on a cluster, from its scheduler logs.
- [CodeCarbon](https://codecarbon.io/): a Python package that measures the emissions of your code as it runs.
- [Electricity Maps](https://www.electricitymaps.com/) and, in Great Britain, the [Carbon Intensity API](https://carbonintensity.org.uk/): how clean the electricity is by region and time, to help choose where and when to run.

Learn:

- [Green Algorithms](https://www.green-algorithms.org/): talks, guidance and tools for sustainable computational research.
- [GREENER principles for environmentally sustainable computational science](https://doi.org/10.1038/s43588-023-00461-y) (Lannelongue et al., *Nature Computational Science*, 2023): a framework for research groups and institutions.
- [Green Software Practitioner](https://learn.greensoftware.foundation/): a free short course from the [Green Software Foundation](https://greensoftware.foundation/).

Share and ask:

- [Green DiSC forum](https://forum.escs-community.org/c/green-disc/9): ask other groups, and share your own material (which also counts towards `G3-B`).
