# Green DiSC toolkit

A GitHub template that helps research groups gather, organise and review evidence for [Green DiSC](https://www.software.ac.uk/GreenDiSC), a Digital Sustainability Certification. It doesn't replace Green DiSC's own submission process; it keeps the evidence that goes into it up to date, and can export it, without locations or names, to attach to your submission.

> **Status:** in development. It covers the Research Group track at Bronze tier. Criteria syncing, records, review cycles, starter guides and the evidence export are ready.

## Get started

For the Green DiSC representative, who sets the repository up:

1. Click **Use this template** to create your own repository (**private** if you will record locations or owners).
2. Follow [Setting up your repository](docs/setup.md): allow the toolkit's actions, choose your track in `config.yml` (this syncs the criteria), add people and name your representative below.
3. Start your first review: **Actions → Start Green DiSC review**, with the date the review should be done by. This creates the group record, a personal record for each member and everyone's check-in, as [GitHub issues](../../issues). See [Running reviews](docs/reviews.md).

## Your Green DiSC representative

> **To fill in:** your representative's name, how to contact them, and a link to their profile or role description. Update it when the representative changes.

- **Name:**
- **Contact:**
- **Profile or role description:**

## Who does what

**The Green DiSC representative** (Maintain role):

- sets up the repository and keeps [Your Green DiSC representative](#your-green-disc-representative) above up to date;
- starts each review and works through the representative's check-in: reviewing and saving the group record, and, occasionally, merging the criteria sync pull request, updating any published copy of the guides, and tidying data rows left by deleted records (see [Running reviews](docs/reviews.md));
- manages who's in the group: gives new members Write access (the next review creates their record), and when someone leaves, hands over their shared items, closes their record (which removes its rows from the data) and removes their access; see [When someone leaves](docs/records.md#when-someone-leaves);
- maintains the repository: merges Dependabot's monthly pull request updating the action pins (see [Updating the toolkit](docs/updating.md));
- when applying, [exports the evidence](docs/evidence.md) and attaches it to the submission, with the representative's profile (`G1-B`) and the onboarding material (`G2-B`).

**Members** (Write role) work through the check-in they get before each review:

- update their personal record (what they use, plus any shared items they look after, and their data cleanups), then comment `/save`;
- add anything new to the group record: computing systems, training, shared material and promotional activities;
- go over the [guides](guides/README.md), opening pull requests for changes and reviewing others' pull requests.

## Documentation

- [Setting up your repository](docs/setup.md)
- [Recording evidence](docs/records.md): the records, which criteria each table is evidence for, and the data files
- [Running reviews](docs/reviews.md)
- [Submitting your evidence](docs/evidence.md): an optional export of the records for Green DiSC's auditors, without locations or names
- [Guides](guides/README.md): starter pages on e-waste and green computing tips, to fill in and publish
- [Keeping criteria in sync with Green DiSC](docs/criteria-sync.md)
- [Updating the toolkit](docs/updating.md): how new versions and template changes reach your repository

## How it works

Inventories and logs (hardware, data, pipelines, training, …) are recorded in GitHub issues and saved to files by a workflow; reference material (e-waste routes, green computing tips) lives in guide pages. Both are brought up to date at every review. Where everything lives:

| Where | What |
|---|---|
| Issues labelled `personal-record` | One per member: the hardware, data resources, data cleanups and pipelines they use or look after (including shared ones). The member edits it and comments `/save` to write the changes to the respective `data/*.csv` files. It stays open while the member is in the group: closing it removes its rows from the files. |
| The issue labelled `group-record` | One for the group: computing infrastructure, training, and resources shared and promotional activities. Any member can edit it; the representative reviews the changes and comments `/save` to write the changes to the respective `data/*.csv` files. It stays open. |
| `data/*.csv` | The saved records, one file per table, usually only written by the bot upon receiving a `/save` comment. |
| Milestones and issues labelled `check-in` | The reviews. A check-in is a short-lived to-do list asking a member to go over their personal record, the group record, and the guides by the review date. Saving the personal record (a successful `/save`) ticks its item; members tick the rest and close the check-in, which is automatically reopened if anything is left unchecked. So each review's milestone tracks each member's progress, and closed milestones show when every past review happened. |
| `guides/` | Reference pages (e-waste, green computing), edited by pull request. |
| `criteria.yml` | The Green DiSC criteria for your track, synced from upstream. |
| `config.yml` | Your track, and which upstream version of the criteria to follow. |
| `.github/ISSUE_TEMPLATE/` | The forms the records are created from. |
| `.github/workflows/` | The automation: saving records on `/save` (and tidying check-ins), starting reviews, syncing the criteria, and exporting the evidence. Each is a thin wrapper around a shared action in [neuroinformatics-unit/actions](https://github.com/neuroinformatics-unit/actions/tree/main/greendisc_toolkit). |
| `.github/dependabot.yml` | Opens one pull request a month updating the pins of GitHub's own actions, to review and merge. The toolkit's own actions have no tagged releases yet, so their pins are updated by hand; see [Updating the toolkit](docs/updating.md). |

## Licence

The toolkit is released under the [BSD 3-Clause License](LICENSE).

The Green DiSC criteria are © Green DiSC, licensed [CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/), and not covered by this toolkit's licence. The toolkit doesn't include them; `criteria.yml` holds only IDs, titles and categories with a link to the [source](https://github.com/Cambridge-Sustainable-Computing-Lab/greenDiSC).
