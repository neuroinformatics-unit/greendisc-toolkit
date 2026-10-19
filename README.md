# Green DiSC toolkit

A GitHub template that helps research groups and teams gather, organise and review evidence for [Green DiSC](https://github.com/Cambridge-Sustainable-Computing-Lab/greenDiSC) (Green Digital Science Certification). It does not replace Green DiSC's own submission process; it keeps the evidence that goes into it up to date.

> **Status:** in development. Criteria syncing, personal and group records, review cycles and starter guides are ready; the public summary is not built yet.

## Quick start

1. Click **Use this template** to create your own repository (**private** if you will record locations or owners).
2. Follow [Setting up your repository](docs/setup.md): allow the toolkit's actions, fill in `config.yml` (your track; this syncs the criteria), add people and name your representative below.
3. Create the group record and ask each member to create theirs: **Issues → New issue**, then comment `/save`.
4. Start your first review: **Actions → Start Green DiSC review**, with the date of your review meeting. See [Running reviews](docs/reviews.md).

## Your Green DiSC representative

> **To fill in:** your representative's name, how to contact them, and a link to their profile or role description. Update it when the representative changes: it's evidence for `G1-B`.

- **Name:**
- **Contact:**
- **Profile or role description:**

## Who does what

**Members** (Write role):

- Keep your personal record up to date: what you use, plus any shared items you look after. Clean up your data directories regularly and log each cleanup. Comment `/save` when it's complete and up to date.
- Add to the group record: computing systems the group uses, training, shared material and promotion.
- Before each review, work through the check-in assigned to you, including reading the guides and suggesting changes as pull requests.

**The Green DiSC representative** (Maintain role):

- Sets up the repository, creates the group record and keeps the section above up to date.
- Reviews what members add to the group record, and saves it.
- Starts each review with the meeting date, and runs the meeting.
- Keeps the [guides](guides/README.md) up to date, reviewing members' suggestions, and updates the records of people who leave.

## Where the evidence lives

For the Research Group track, Bronze tier. Records are issues that the bot saves to `data/`; guides are pages to fill in and publish. Before each review, everyone gets a check-in to go over them.

| Criterion | Evidence | Where |
|---|---|---|
| `G1-B` Representative | Name and contact details; link to their profile or role description | *Your Green DiSC representative*, above |
| `G2-B` Induction | Induction material covering green computing | [guides/green-computing.md](guides/green-computing.md) |
| `G3-B` Resources shared | Rows with kind `shared resource` | Group record → `data/sharing.csv` |
| `G4-B` Dissemination | Rows with kind `promotion` | Group record → `data/sharing.csv` |
| `01-B` Hardware | All hardware rows | Personal records → `data/hardware.csv` |
| `02-B` Unused equipment | Hardware rows with status `unused` | Personal records → `data/hardware.csv` |
| `03-B` E-waste | Routes and policy | [guides/e-waste.md](guides/e-waste.md) |
| `DS1-B` Data resources | Dataset rows | Personal records → `data/data-resources.csv` |
| `DS2-B` Data cleaning | Cleanup rows | Personal records → `data/data-cleaning.csv` |
| `HPC1-B` Compute infrastructure | Systems the group uses | Group record → `data/compute.csv` |
| `HPC2-B` Pipelines | Pipeline rows | Personal records → `data/pipelines.csv` |
| `HPC3-B` Best practices | Training sessions; tips and materials | Group record → `data/training.csv`; [guides/green-computing.md](guides/green-computing.md) |

## Documentation

- [Setting up your repository](docs/setup.md)
- [Keeping criteria in sync with Green DiSC](docs/criteria-sync.md)
- [Recording evidence](docs/records.md)
- [Running reviews](docs/reviews.md)
- [Guides](guides/README.md): starter pages on e-waste and green computing tips, to fill in and publish

The shared logic lives in composite actions in [lochhh/actions](https://github.com/lochhh/actions/tree/greendisc-toolkit/greendisc_toolkit), which the workflows here reference by commit SHA.

## Licence

The toolkit is released under the [BSD 3-Clause License](LICENSE).

The Green DiSC criteria are © Green DiSC, licensed [CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/), and not covered by this toolkit's licence. The toolkit doesn't include them; `criteria.yml` holds only IDs, titles and categories with a link to the [source](https://github.com/Cambridge-Sustainable-Computing-Lab/greenDiSC).
