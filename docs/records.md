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
| Training | `HPC3-B` green computing best practices (sessions and attendance) | `data/training.csv` |
| Sharing and promotion | `G3-B` resources shared (kind `shared resource`); `G4-B` dissemination (kind `promotion`) | `data/sharing.csv` |
| Data cleaning | `DS2-B` cleanups done as a group or with IT | `data/data-cleaning.csv` |

Leave a table empty if it doesn't apply. Reference material, such as e-waste routes, which compute to use, and green computing tips, belongs in the [guides](../guides/README.md) rather than records, so it can be published and read by others.

## Creating your record

1. **Issues → New issue → My Green DiSC record.**
2. Fill in the table: one row per item, copying a row to add more. The **How to update this record** section at the top explains the basics, and the comment above each table (visible when editing) says what each column expects. **Type** is free text; use the suggested names where they fit so items are counted together. Leave a cell blank if you don't know; it is saved as `unknown` so it can be filled in later. Every table also has an optional **Notes** column, which can stay blank.
3. Click **Create**. The bot labels it `unsaved changes` and replies with how to save it.
4. Comment `/save`. The bot checks every row, saves them, replies with a summary (including how many values are still `unknown`) and removes the `unsaved changes` label.

**Keep your record open.** It's yours for as long as you're in the group; it is only closed when you leave (see below).

If something is wrong (e.g. `broken` as a status, or `22` as a year), nothing is saved: the bot replies listing each problem by row and column. Edit the issue, fix them and comment `/save` again.

## Keeping it up to date

Edit your record issue, change the table and comment `/save` again. Your saved rows are replaced by the current table.

Editing the table adds the `unsaved changes` label, and a successful `/save` removes it. Until then your edits are not in the saved data, so the review can find unsaved records with the issue search `is:issue label:"unsaved changes"`.

- **New item:** add a row.
- **Item no longer used:** set its status to `unused` and say in **Action** what will happen to it.
- **Item gone:** set its status to `disposed` and say in **Action** what happened (returned, donated, recycled, …). Keep the row: Green DiSC asks what happened to equipment.
- **Dataset no longer needed:** set its status to `archived` or `deleted`. Keep the row.
- **Pipeline no longer run:** set its status to `retired`. Keep the row.
- **Cleanup done:** add a row to Data cleaning and keep the earlier ones; together they show how often you clean.

Find your record with the issue search `is:issue label:personal-record author:@me`.

Each person has one record. Opening a second one gets it closed with a link to the first.

## The group record

Create it once: **Issues → New issue → Green DiSC group record**, then comment `/save`. After that, anyone in the group can add to it: edit the issue and add a row. A maintainer, such as the Green DiSC representative, checks new rows and comments `/save`; until then the issue is labelled `unsaved changes`. Keep earlier rows; together they are the history Green DiSC asks for.

GitHub doesn't merge edits to an issue: if two people edit it at the same time, the last one to save wins. The issue's edit history (the *edited* link next to it) keeps the earlier version if a row goes missing.

## Who can save

Anyone with **Write** access can save their own personal record and edit the group record. Saving the group record, or someone else's personal record, needs the **Maintain** or **Admin** role, so give the Green DiSC representative Maintain: they check and save the group record, and can update the record of someone who has left. Anyone else who comments `/save` gets a reply explaining that nothing was saved.

## When someone leaves

The representative updates their record (each item's status, with an **Action** saying what happened, e.g. `returned to IT`), comments `/save`, then closes the issue. Closed records stay in the data; `/save` still works on them if something needs correcting later.

## The CSV files

The bot is the only writer of `data/*.csv`. Each row has a `record` column with its issue number, which is how a later `/save` finds the rows to replace, so **don't edit the CSV files directly**: change the issue and `/save` instead, or your edit will be overwritten the next time that record is saved.

## Privacy

**Location** and **Asset tag** are optional, and owner names are implied by who created each record. Keep the repository private if you record them. The public summary only ever contains counts, never rows.
