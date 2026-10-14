# Green DiSC toolkit

A GitHub template that helps research groups and teams gather, organise and review evidence for [Green DiSC](https://github.com/Cambridge-Sustainable-Computing-Lab/greenDiSC) (Green Digital Science Certification). It does not replace Green DiSC's own submission process; it keeps the evidence that goes into it up to date.

> **Status:** in development. Criteria syncing and hardware records work so far.

## Quick start

1. Click **Use this template** to create your own repository (**private** if you will record locations or owners).
2. Follow [Setting up your repository](docs/setup.md): allow the toolkit's actions, set your track in `config.yml` (which syncs the criteria) and add people.
3. Create the group record and ask each member to create theirs: **Issues → New issue**, then comment `/save`.

## Documentation

- [Setting up your repository](docs/setup.md)
- [Keeping criteria in sync with Green DiSC](docs/criteria-sync.md)
- [Recording evidence](docs/records.md)

The shared logic lives in composite actions in [lochhh/actions](https://github.com/lochhh/actions/tree/greendisc-toolkit/greendisc_toolkit), which the workflows here reference by commit SHA.

## Licence

The toolkit is released under the [BSD 3-Clause License](LICENSE).

The Green DiSC criteria are © Green DiSC, licensed [CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/), and not covered by this toolkit's licence. The toolkit doesn't include them; `criteria.yml` holds only IDs, titles and categories with a link to the [source](https://github.com/Cambridge-Sustainable-Computing-Lab/greenDiSC).
