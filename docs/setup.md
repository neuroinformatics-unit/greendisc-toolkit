# Setting up your repository

Everything needed to go from the template to a working repository, in order. Steps 2 and 3 may need an organisation owner.

## 1. Create your repository

Click **Use this template → Create a new repository**. Make it **private** if you will record inventory details such as locations, asset tags or who uses what (see [Privacy](records.md#privacy)).

## 2. Allow the toolkit's actions

The workflows use GitHub's own `actions/checkout` and `actions/setup-python`, and the toolkit's shared actions in `lochhh/actions`.

If your organisation restricts which actions can run (**Organisation settings → Actions → General → Policies**), an organisation owner needs to:

- tick **Allow actions created by GitHub**, and
- add `lochhh/actions@*, lochhh/actions/*` to the allowed actions and reusable workflows (the toolkit's actions are in subfolders of that repository).

If the policy allows all actions, there is nothing to do. The same setting exists per repository under **Settings → Actions → General**, if your organisation lets repositories choose.

## 3. Repository settings

**Settings → Actions → General:**

- **Actions permissions:** actions must be enabled (they are by default).
- **Workflow permissions:** leave the default (read). Each workflow asks for the permissions it needs.
- Tick **Allow GitHub Actions to create and approve pull requests**, so the criteria sync can open its pull request. If it is greyed out, your organisation has disabled it; ask an organisation owner.

## 4. Choose your track and sync the criteria

Edit [`config.yml`](../config.yml) and set `track`:

| `track` | Green DiSC track |
|---|---|
| `RG` | Research Group |
| `CT` | Central Team |
| `RCI` | Research Computing Infrastructure |

Committing the change starts the criteria sync, which opens a pull request creating `criteria.yml`; merge it. If you're keeping the default `RG`, run **Actions → Sync Green DiSC criteria → Run workflow** once instead. See [Keeping criteria in sync](criteria-sync.md) for details on how the sync works.

## 5. Add people

**Settings → Collaborators and teams** (or a team with access to the repository):

| Who | Role | Why |
|---|---|---|
| Members | **Write** | Create their own record and save it with `/save` |
| Green DiSC representative | **Maintain** | Save anyone's record, e.g. to update the record of someone who has left |

People with the **Read** role can see the records but can't save them. See [Who can save](records.md#who-can-save).

A repository owned by a personal account has no Maintain role: every collaborator gets Write, and only the account owner can save other people's records. Use an organisation repository if the representative isn't the owner.

## 6. Create records

Ask each member to create their record: **Issues → New issue → My Green DiSC record**, then comment `/save`. See [Recording evidence](records.md).

## What the workflows can do

For whoever approves the repository. Each workflow asks only for these permissions, using the default `GITHUB_TOKEN`; no secrets or apps are involved.

| Workflow | Permissions | Why |
|---|---|---|
| Save Green DiSC records (`save-record.yml`) | `contents: write`, `issues: write` | Commit `data/*.csv`; label and comment on records, close duplicates |
| Sync Green DiSC criteria (`sync-criteria.yml`) | `contents: write`, `pull-requests: write` | Push the `greendisc/sync-criteria` branch; open its pull request |
