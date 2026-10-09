# Green DiSC toolkit

A GitHub template that helps research groups and teams gather, organise and review evidence for [Green DiSC](https://github.com/Cambridge-Sustainable-Computing-Lab/greenDiSC) (Green Digital Science Certification). It does not replace Green DiSC's own submission process; it keeps the evidence that goes into it up to date.

> **Status:** in development. Criteria syncing and hardware records work so far.

## Quick start

1. Click **Use this template** to create your own repository. Make it **private** if you will record inventory details such as locations or owners.
2. Edit [`config.yml`](config.yml) and set your `track` (`RG` Research Group, `CT` Central Team or `RCI` Research Computing Infrastructure).
3. Enable **Settings → Actions → General → Allow GitHub Actions to create and approve pull requests**.
4. Run the **Sync Green DiSC criteria** workflow from the **Actions** tab and merge the pull request it opens. This creates `criteria.yml`.
5. Ask each member to create their record: **Issues → New issue → My Green DiSC record**, then comment `/save`.

## Documentation

- [Keeping criteria in sync with Green DiSC](docs/criteria-sync.md)
- [Recording evidence](docs/records.md)

The shared logic lives in composite actions in [lochhh/actions](https://github.com/lochhh/actions/tree/greendisc-toolkit/greendisc_toolkit), which the workflows here reference by commit SHA.

## Licence

The toolkit is released under the [BSD 3-Clause License](LICENSE).

The Green DiSC criteria are © Green DiSC, licensed [CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/), and not covered by this toolkit's licence. The toolkit doesn't include them; `criteria.yml` holds only IDs, titles and categories with a link to the [source](https://github.com/Cambridge-Sustainable-Computing-Lab/greenDiSC).
