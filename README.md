# Green DiSC toolkit

A GitHub template that helps research groups and teams gather, organise and review evidence for [Green DiSC](https://github.com/Cambridge-Sustainable-Computing-Lab/greenDiSC) (Green Digital Science Certification). It does not replace Green DiSC's own submission process; it keeps the evidence that goes into it up to date.

> **Status:** in development. Criteria syncing, personal and group records, and starter guides are ready; review cycles and the public summary are not built yet.

## Quick start

1. Click **Use this template** to create your own repository (**private** if you will record locations or owners).
2. Follow [Setting up your repository](docs/setup.md): allow the toolkit's actions, set your track in `config.yml` (which syncs the criteria) and add people.
3. Create the group record and ask each member to create theirs: **Issues → New issue**, then comment `/save`.

## Where the evidence lives

For the Research Group track, Bronze tier. Records are issues that the bot saves to `data/`; guides are pages to fill in and publish.

| Criterion | Evidence | Where |
|---|---|---|
| `G1-B` Representative | Link to their profile or role description | Comment on the criterion's review issue |
| `G2-B` Induction | Induction material covering green computing | [guides/green-computing.md](guides/green-computing.md), linked on the review issue |
| `G3-B` Resources shared | Rows with kind `shared resource` | Group record → `data/sharing.csv` |
| `G4-B` Dissemination | Rows with kind `promotion` | Group record → `data/sharing.csv` |
| `01-B` Hardware | All hardware rows | Personal records → `data/hardware.csv` |
| `02-B` Unused equipment | Hardware rows with status `unused` | Personal records → `data/hardware.csv` |
| `03-B` E-waste | Routes and policy | [guides/e-waste.md](guides/e-waste.md) |
| `DS1-B` Data resources | Dataset rows | Personal records → `data/data-resources.csv` |
| `DS2-B` Data cleaning | Cleanup rows | Personal and group records → `data/data-cleaning.csv` |
| `HPC1-B` Compute infrastructure | Systems table | [guides/compute.md](guides/compute.md) |
| `HPC2-B` Pipelines | Pipeline rows | Personal records → `data/pipelines.csv` |
| `HPC3-B` Best practices | Training sessions; tips and materials | Group record → `data/training.csv`; [guides/green-computing.md](guides/green-computing.md) |

## Documentation

- [Setting up your repository](docs/setup.md)
- [Keeping criteria in sync with Green DiSC](docs/criteria-sync.md)
- [Recording evidence](docs/records.md)
- [Guides](guides/README.md): starter pages on e-waste, the computing you use and green computing tips, to fill in and publish

The shared logic lives in composite actions in [lochhh/actions](https://github.com/lochhh/actions/tree/greendisc-toolkit/greendisc_toolkit), which the workflows here reference by commit SHA.

## Licence

The toolkit is released under the [BSD 3-Clause License](LICENSE).

The Green DiSC criteria are © Green DiSC, licensed [CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/), and not covered by this toolkit's licence. The toolkit doesn't include them; `criteria.yml` holds only IDs, titles and categories with a link to the [source](https://github.com/Cambridge-Sustainable-Computing-Lab/greenDiSC).
