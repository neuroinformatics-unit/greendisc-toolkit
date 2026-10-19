# Recording evidence

Each member keeps **one personal record issue** listing the equipment, data and pipelines they use, plus any shared group items they look after (a shared server, meeting-room screen, group dataset or pipeline; each in one person's record only), and the group shares **one group record** for what it does together. The toolkit saves these records to CSV files in `data/`, which become evidence for your Green DiSC submission.

**Personal record:**

| Section | Criteria | Saved to |
|---|---|---|
| Hardware | `01-B` computing hardware inventory; `02-B` unused equipment (items with status `unused`) | `data/hardware.csv` |
| Data resources | `DS1-B` data resource inventory | `data/data-resources.csv` |
| Data cleaning | `DS2-B` data directory cleaning (one row per cleanup) | `data/data-cleaning.csv` |
| Pipelines | `HPC2-B` computing pipeline inventory | `data/pipelines.csv` |

**Group record:**

| Section | Criteria | Saved to |
|---|---|---|
| Compute infrastructure | `HPC1-B` computing infrastructure inventory | `data/compute.csv` |
| Training | `HPC3-B` green computing best practices (sessions and attendance) | `data/training.csv` |
| Sharing and promotion | `G3-B` resources shared (kind `shared resource`); `G4-B` dissemination (kind `promotion`) | `data/sharing.csv` |

Leave a table empty if it doesn't apply. Every table in the issues also opens with the criteria it's evidence for.

The remaining Research Group Bronze criteria aren't records: `G1-B` (representative) is the README's *Your Green DiSC representative* section, and `G2-B` (induction), `03-B` (e-waste) and the materials for `HPC3-B` are [guides](../guides/README.md), kept as pages so they can be published and read by others.

## Your record

Each review creates a personal record for every member who doesn't have one yet (everyone with the **Write**, **Maintain** or **Admin** role), titled `Green DiSC personal record: <username>` and assigned to them. Your review check-in links to it. To start before the next review, use **Issues → New issue → Green DiSC personal record**.

1. Edit the issue and fill in the tables: one row per item. The **How to update this record** section at the top explains the basics, and the comment above each table (visible when editing) says what each column expects. **Type** is free text; use the suggested names where they fit so items are counted together. Leave a cell blank if you don't know: it is saved as `unknown`, so missing data stays visible and can be filled in later. Write `n/a` if a cell doesn't apply, such as **Action** for an item still in use. Every table also has an optional **Notes** column, which can stay blank.
2. Click **Save** on the issue.
3. Comment `/save`. The bot checks every row, saves them, replies with a summary and removes the `unsaved changes` label.

**Keep your record open.** It's yours for as long as you're in the group; it is only closed when you leave (see below).

If something is wrong (e.g. `broken` as a status, or `22` as a year), nothing is saved: the bot replies listing each problem by row and column. Edit the issue, fix them and comment `/save` again.

## Keeping it up to date

Edit your record issue, change the table and comment `/save` again. Your saved rows are replaced by the current table.

Editing the table adds the `unsaved changes` label, and a successful `/save` removes it. Until then your edits are not in the saved data, so the review can find unsaved records with the issue search `is:issue label:"unsaved changes"`.

Before each review you'll get a **check-in** issue asking you to go over your record. Saving your record ticks it off; see [Running reviews](reviews.md).

- **New item:** add a row.
- **Item no longer used:** set its status to `unused` and say in **Action** what will happen to it.
- **Item gone:** set its status to `disposed` and say in **Action** what happened (returned, donated, recycled, …). Keep the row: Green DiSC asks what happened to equipment.
- **Dataset no longer needed:** set its status to `archived` or `deleted`. Keep the row.
- **Pipeline no longer run:** set its status to `retired`. Keep the row.
- **Cleanup done:** add a row to Data cleaning and keep the earlier ones; together they show how often you clean.

Find your record with the issue search `is:issue label:personal-record assignee:@me`.

Each person has one record: the one assigned to them, or that they created. Saving a second one gets a reply with a link to the first. A record that is closed, for someone who left or doesn't need one, is never recreated by a review.

## The group record

The first review creates it, assigned to the representative. After that, anyone in the group can add to it: edit the issue and add a row. The Green DiSC representative reviews members' changes and comments `/save`; until then the issue is labelled `unsaved changes`. Keep earlier rows; together they are the history Green DiSC asks for.

GitHub doesn't merge edits to an issue: if two people edit it at the same time, the last one to save wins. The issue's edit history (the *edited* link next to it) keeps the earlier version if a row goes missing.

## Who can save

Anyone with **Write** access can save their own personal record and edit the group record. Saving the group record, or someone else's personal record, needs the **Maintain** or **Admin** role, so give the Green DiSC representative Maintain: they check and save the group record, and can update the record of someone who has left. Anyone else who comments `/save` gets a reply explaining that nothing was saved.

## When someone leaves

The representative updates their record (each item's status, with an **Action** saying what happened, e.g. `returned to IT`), comments `/save`, then closes the issue. Closed records stay in the data; `/save` still works on them if something needs correcting later.

A closed record isn't recreated by later reviews. If one was closed by mistake, or its owner rejoins the group, **reopen it**: they keep their history, and the next review gives them a check-in again.

## The data files

The bot saves records to CSV files in `data/`, one per table. A file is created the first time a record with that table is saved, and every row has a `record` column with the issue number it came from.

| File | Record | Table |
|---|---|---|
| `hardware.csv` | Personal | Hardware |
| `data-resources.csv` | Personal | Data resources |
| `data-cleaning.csv` | Personal | Data cleaning |
| `pipelines.csv` | Personal | Pipelines |
| `compute.csv` | Group | Compute infrastructure |
| `training.csv` | Group | Training |
| `sharing.csv` | Group | Sharing and promotion |

The bot is the only writer of these files: a `/save` replaces that record's rows with the issue's current tables, so **don't edit the files directly**. Change the issue and `/save` instead, or your edit will be overwritten.

**The one exception:** rows from a record that no longer exists, such as a deleted personal record, are never replaced, because nothing will save that record again. Each review lists them in the representative's check-in. Usually the representative deletes them by editing the CSV files directly. If a record was deleted by mistake, the next review creates a new one for its owner to fill in, and the old rows stay in the git history to copy from; delete them once the owner has re-entered their items.

## Privacy

**Location** and **Asset tag** are optional, and each personal record's title and assignee show whose it is. Keep the repository private if you record them. The public summary only ever contains counts, never rows.
