# Green DiSC toolkit

A GitHub template that helps research groups gather, organise and review evidence for [Green DiSC](https://www.software.ac.uk/GreenDiSC), a Digital Sustainability Certification. It doesn't replace Green DiSC's own submission process; it keeps the evidence that goes into it up to date.

> **Status:** in development. It covers the Research Group track at Bronze tier. Criteria syncing, records, review cycles, starter guides and the evidence export are ready; optional guide publishing is planned.

## Quick start

For the Green DiSC representative, who sets the repository up:

1. Click **Use this template** to create your own repository (**private** if you will record locations or owners).
2. Follow [Setting up your repository](docs/setup.md): allow the toolkit's actions, choose your track in `config.yml` (this syncs the criteria), add people and name your representative below.
3. Start your first review: **Actions → Start Green DiSC review**, with the date the review should be done by. This creates the group record, a personal record for each member and everyone's check-in, as [GitHub issues](../../issues). See [Running reviews](docs/reviews.md).

Members don't need to read the docs: their [check-in](../../issues?q=is%3Aissue+is%3Aopen+label%3Acheck-in) and records say what to do.

## Your Green DiSC representative

> **To fill in:** your representative's name, how to contact them, and a link to their profile or role description. Update it when the representative changes.

- **Name:**
- **Contact:**
- **Profile or role description:**

## Who does what

**Members** (Write role) work through the check-in they get before each review:

- update their personal record (what they use, plus any shared items they look after, and their data cleanups), then comment `/save`;
- add anything new to the group record: computing systems, training, shared material and promotion;
- go over the [guides](guides/README.md), opening pull requests for changes and reviewing each other's.

**The Green DiSC representative** (Maintain role):

- sets up the repository and keeps the section above up to date;
- starts each review, and works through the representative's check-in, which includes reviewing and saving the group record;
- manages who's in the group: gives new members Write access (the next review creates their record), and when someone leaves, hands over their shared items, closes their record (which removes its rows from the data) and removes their access; see [When someone leaves](docs/records.md#when-someone-leaves).

## Documentation

- [Setting up your repository](docs/setup.md)
- [Recording evidence](docs/records.md): the records, which criteria each table is evidence for, and the data files
- [Running reviews](docs/reviews.md)
- [Submitting your evidence](docs/evidence.md): an optional export of the records for Green DiSC's auditors, without locations or names
- [Guides](guides/README.md): starter pages on e-waste and green computing tips, to fill in and publish
- [Keeping criteria in sync with Green DiSC](docs/criteria-sync.md)

## How it works

The workflows in `.github/workflows/` are thin wrappers around shared actions in [lochhh/actions](https://github.com/lochhh/actions/tree/greendisc-toolkit/greendisc_toolkit), pinned by commit SHA so that what runs can't change unnoticed. For now the pins are updated by hand; automatic update pull requests (Dependabot) will follow once the actions have tagged releases. The issue forms in `.github/ISSUE_TEMPLATE/` define the records, and the bot saves them to `data/`.

## Licence

The toolkit is released under the [BSD 3-Clause License](LICENSE).

The Green DiSC criteria are © Green DiSC, licensed [CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/), and not covered by this toolkit's licence. The toolkit doesn't include them; `criteria.yml` holds only IDs, titles and categories with a link to the [source](https://github.com/Cambridge-Sustainable-Computing-Lab/greenDiSC).
