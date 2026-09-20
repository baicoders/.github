# Contributing to baicoders

## Who can do what

| Team | Repository access | Can merge to `main`? |
| --- | --- | --- |
| `@baicoders/admin` | Admin | Yes — admins are the only mergers |
| `@baicoders/maintainers` | Read | No — contribute via a fork and a pull request |
| `@baicoders/bots` | Write (CI only) | No |

## Workflow for maintainers

Maintainers have read access to the upstream repositories, so all work happens
in a personal fork.

```bash
# once per repository
gh repo fork baicoders/<repo> --clone --remote
cd <repo>

# for every change
git switch main
git pull upstream main
git switch -c feat/short-description

# ... make changes, commit ...

git push origin feat/short-description
gh pr create --repo baicoders/<repo> --base main --fill
```

### Branch naming

| Prefix | Use for |
| --- | --- |
| `feat/` | new functionality |
| `fix/` | bug fixes |
| `chore/` | refactors, dependency bumps, tooling |
| `docs/` | documentation only |
| `hotfix/` | urgent production fix |

### Commits

Use [Conventional Commits](https://www.conventionalcommits.org/): `feat:`,
`fix:`, `chore:`, `docs:`, `refactor:`, `test:`. Keep the subject under 72
characters and write it in the imperative — "add supplier validation", not
"added supplier validation".

## Review rules

1. Every change reaches `main` through a pull request. No direct pushes.
2. A pull request needs approval from **a maintainer who is not the author**.
3. Once approved, a member of `@baicoders/admin` performs the merge.
4. Merges to `main` are **squash merges**, so keep the PR title clean — it
   becomes the commit message.
5. Re-request review after pushing changes that follow an approval.

Do not approve your own work, and do not ask an admin to merge something that
has not been reviewed.

## Before you open a pull request

- [ ] The branch is rebased on the latest `upstream/main`
- [ ] The project builds and its tests pass locally
- [ ] No secrets, tokens, `.env` files or customer data in the diff
- [ ] The PR template is filled in, not deleted
- [ ] Linked to the issue it closes

## Issues

Open issues from the templates — bug report, feature request, or task. Blank
issues are disabled on purpose: the template fields are the minimum a triager
needs. Security problems never go in the issue tracker; see
[SECURITY.md](SECURITY.md).
