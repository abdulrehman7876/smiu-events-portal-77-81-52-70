# Team Handoff and Git Workflow

## Recommended four-member split

| Member | Exact files to own | Branch suggestion |
|---|---|---|
| 1 — Team lead | `index.html`, `css/style.css`, `js/main.js`, shared navbar/footer, initial `images/` assets, starter README table | `feature/member-1-home-shared` |
| 2 | `events.html`, `event-details.html` | `feature/member-2-events` |
| 3 | `societies.html`, `register.html` | `feature/member-3-societies-register` |
| 4 | `contact.html`, `README.md`, screenshot folder and final QA report | `feature/member-4-contact-readme` |

For a three-member group, Member 3 also owns `contact.html`, `README.md`, screenshots and final QA.

## Before members begin

1. The team lead creates `smiu-events-portal-<groupname>` on GitHub.
2. Add all group members and teacher `Hassan-Raza0` as collaborators.
3. Use the separate `smiu-events-portal-starter-main.zip` as the first commit to `main`. It contains only the required starter file structure and placeholder pages.
4. Add the original `images/` assets from Member 1's handoff package to the shared starter commit (or let Member 1 add them in the agreed starter setup commit).
5. Each member pulls the latest `main` and creates their own feature branch.
6. Members copy in only their assigned completed page files, make their own commits, open PRs and request reviews. Do not push feature work directly to `main`.
7. Keep the complete `smiu-events-portal-project.zip` as the final reference build. Do **not** upload that complete ZIP to `main` in one commit, because doing so bypasses the required team PR workflow.

## Useful commit sequence examples

These are suggested work steps, not fake commits. Each member should make the changes and commits themselves.

**Member 1**
- `Add responsive shared navigation and footer`
- `Build home hero and featured event carousel`
- `Add upcoming event cards and why-join section`
- `Create portal theme variables and responsive styles`
- `Add shared form feedback and footer year script`

**Member 2**
- `Build responsive events listing grid`
- `Add November schedule table with hover states`
- `Create event details banner and information panel`
- `Add schedule speakers and rules accordion`
- `Add quick registration modal and form labels`

**Member 3**
- `Create responsive student society cards`
- `Add society membership badges and alert`
- `Build registration form identity fields`
- `Add study year and interest controls`
- `Add form validation labels and responsive layout`

**Member 4**
- `Build Student Affairs contact form and details`
- `Add campus map placeholder and team cards`
- `Document project setup and member responsibilities`
- `Add phone and desktop Home screenshots`
- `Test all pages and record final QA fixes`

For three members, Member 3 uses a combined set of society, registration, contact and README tasks and should split those into at least five meaningful commits.

## Git commands for each member

After the team lead has pushed the starter files and Member 1's shared base has been merged, each member should clone the same repository and create a separate branch. Replace `<owner>` and `<groupname>` with the real GitHub values.

```bash
git clone https://github.com/<owner>/smiu-events-portal-<groupname>.git
cd smiu-events-portal-<groupname>
git switch main
git pull origin main
```

Create the branch assigned to you:

```bash
# Member 1
git switch -c feature/member-1-home-shared

# Member 2
git switch -c feature/member-2-events

# Member 3
git switch -c feature/member-3-societies-register

# Member 4
git switch -c feature/member-4-contact-readme
```

Copy only your assigned files into the cloned repository. Commit your real work in separate meaningful steps, then push your branch:

```bash
git add <your-assigned-files>
git commit -m "Describe the actual change"
git push -u origin <your-branch-name>
```

For later commits, repeat `git add`, `git commit` and `git push`. Open a pull request on GitHub with `main` as the base branch. Do not copy all six completed pages directly to `main`; the point is to show each member's own branch, commits, PR and review.

## Pull request process

1. Push the feature branch to GitHub.
2. Open a pull request from the feature branch into `main`.
3. Explain what changed and list the pages / viewport sizes tested.
4. Request a review from a different group member.
5. Reviewer checks file paths, accessibility labels, Bootstrap behavior, responsiveness and the diff. Leave at least one useful review comment where needed.
6. The author fixes review feedback and pushes updates to the same branch.
7. After approval, a different member merges the PR.
8. Everyone pulls the updated `main` before starting their next task.

## Shared CSS and merge conflicts

`css/style.css` is a shared file. Member 1 owns the base theme and shared navbar/footer styles. Other members should request or contribute page-specific CSS in clearly marked sections near the bottom of the file rather than rewriting existing rules. If Git reports a conflict, inspect both versions, preserve valid work from both sides, remove conflict markers, test every page, and describe the real conflict and resolution in `README.md`. Do not delete a teammate's CSS to make the conflict disappear.

## Final test matrix

| Page | 360px | 768px | 1200px | Key interaction |
|---|---:|---:|---:|---|
| Home | [ ] | [ ] | [ ] | Navbar + carousel |
| Events | [ ] | [ ] | [ ] | Responsive cards + table |
| Event details | [ ] | [ ] | [ ] | Accordion + modal |
| Societies | [ ] | [ ] | [ ] | Alert + Join links |
| Register | [ ] | [ ] | [ ] | Form controls + validation |
| Contact | [ ] | [ ] | [ ] | Contact form |
