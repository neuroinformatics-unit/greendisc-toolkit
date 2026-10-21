# Updating the toolkit

Your repository is a copy of the toolkit template, with no link back to it. Most of the toolkit's logic lives in its shared actions, which your workflows use at pinned versions, so most updates are new versions of those actions.

> [!NOTE]
> Most updates arrive by themselves, as Dependabot pull requests to review and merge. Nothing else needs regular attention.

## Action versions

Dependabot (`.github/dependabot.yml`) opens one pull request a month updating the workflows' pinned versions of GitHub's actions. The toolkit's own actions have no tagged releases yet, so Dependabot can't propose their versions: until they do, update their pins by hand, copying them from the [template's workflows](https://github.com/neuroinformatics-unit/greendisc-toolkit/tree/main/.github/workflows).

## Template changes

Occasionally the template changes in a way you may want too, such as a record form if/when Green DiSC updates its criteria, or a workflow after an action's inputs change. Records are read by their column headers, so existing records keep working until you update a form.

The template is versioned: each [release](https://github.com/neuroinformatics-unit/greendisc-toolkit/releases) (`v1.0.0`, `v1.1.0`, …) has notes saying what changed and whether you need to do anything. Note which release your repository was created from or last updated to, so you know which notes are new to you. (There are no releases yet: until the first, merge `template/main`, the latest version, instead of a release tag below.)

In a clone of your repository, add the template as a remote once:

```sh
git remote add template https://github.com/neuroinformatics-unit/greendisc-toolkit.git
```

Then, each time:

```sh
git switch main && git pull                    # start from your latest main
git fetch template --tags                      # get the template's releases
git switch -c update-toolkit-v1.1.0            # a new branch for the update
git merge v1.1.0 --allow-unrelated-histories   # merge in the release (here v1.1.0, or template/main for the latest version)
```

The merge keeps your changes and adds the template's. Resolve any merge conflicts and commit, then push the branch, open a pull request and merge it with **Create a merge commit** (not squash or rebase), so the next update starts from this one.

> [!NOTE]
> **The first time you update**, every file your group has changed, such as `README.md`, `config.yml` and the guides, conflicts, because your repository doesn't share history with the template yet. Resolve them as usual; for those files, that usually means keeping your version. Later updates only conflict where you and the template changed the same lines.
