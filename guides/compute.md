# Computing we use

The computing systems our group uses or could use, with what's known about their energy, so we can choose well and estimate the footprint of our work.

## Systems

> **To fill in:** one row per system: institutional clusters, cloud services, servers kept by the group, and shared lab workstations. Ask your research computing or IT team for the data centre details. Leave a cell as `unknown` rather than guessing, and delete the example rows.

| System | On-site or off-site | Provider | Region | PUE | Electricity | Hardware | Use it for |
|---|---|---|---|---|---|---|---|
| *Example:* institution HPC cluster | Off-site | *Institution* | *City* | *1.3* | *Grid, renewable tariff* | *CPU and GPU nodes* | *Large or long jobs* |
| *Example:* cloud provider | Off-site | *Company* | *Region name* | *1.1 (provider's figure)* | *Provider's renewable claim* | *Varies* | *Short bursts when the cluster is busy* |
| *Example:* group GPU server | On-site | *Our group* | *Building* | `unknown` | *Grid* | *2 GPUs* | *Interactive work, small tests* |

What the columns mean:

- **PUE (power usage effectiveness):** the data centre's total energy divided by the energy used by the computers themselves. 1.0 would be perfect; lower is better. Your computing team or provider usually knows it.
- **Electricity:** where the power comes from, such as the national grid, a renewable tariff or on-site solar.
- **Region:** where the data centre is. It matters because the carbon intensity of electricity varies by country and region.

Keep this page to what you'd publish. Leave out room numbers and anything that would help someone find a specific machine.

## Servers we run ourselves

> **To fill in:** if the group keeps its own servers, say why (for example: special hardware, data that can't leave the building, interactive work) and whether a shared facility could do the job instead. Delete this section if you have none.

## Choosing where to run

> **To fill in:** your group's rules of thumb, for example: test small jobs on the group server, run large ones on the cluster, and use the cloud only when the cluster can't do it.

To estimate the footprint of a job, use a calculator such as [Green Algorithms](https://calculator.green-algorithms.org/) with the PUE and region from the table above.

## Last checked

> **To fill in:** the date and who confirmed these details. Check at each review.
