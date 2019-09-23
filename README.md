# Coding Standards
* [Commit message guidelines](#commit-message-guidelines)
  * [Commit Message Format](#commit-message-format)
  * [Type](#format)
  * [Scope](#scope)
  * [Subject](#subject)
  * [Body](#body)
  * [Footer](#footer)
  * [Examples](#examples)


## Commit message guidelines
These are precise rules about how our git commit messages have to be formatted.
This leads to *more readable messages* that are easy to follow when looking
through *git history*. But also, we can use the git commit messages
to *generate release notes*.

To be able to follow these guidelines, all git commits have to be
**[atomic](https://curiousprogrammer.io/blog/why-i-create-atomic-commits-in-git)**.


### Commit Message Format
Each commit message consists of a **header**, a **body** and optionally a **footer**.
The header has a special format that includes a **type**, optionally a **scope**
and a **subject**:

```
<type> [<scope>: ]<subject>

<body>

[<footer>]
```

The **header** line cannot be longer than *70 characters* and
any line of the commit message cannot be longer *100 characters*!
This allows the message to be easier to read on GitHub as well as
in various git tools.


### Type
This is one of the following emojis:

| Emoji        | Emoji code      | Description                  | Change <br> visible to user | Change <br> to meaning of <br> production code |
| ------------ | --------------- | ---------------------------- | ----------------------- | ------------------------- |
| :star:       | `:star:`        | New / changed feature        | :heavy_check_mark:      | :heavy_check_mark:        |
| :bug:        | `:bug:`         | General bugfix               | :heavy_check_mark:      | :heavy_check_mark:        |
| :lock:       | `:lock:`        | Security feature / bugfix    | :heavy_check_mark:      | :heavy_check_mark:        |
| :recycle:    | `:recycle:`     | General refactoring          | :x:                     | :heavy_check_mark:        |
| :zap:        | `:zap:`         | Performance- / memory-related refactoring | :x:  | :heavy_check_mark:              |
| :art:        | `:art:`         | Formatting, white space, renaming variables etc | :x:  | :x:                       |
| :pencil:     | `:pencil:`      | Documentation, code comments | :x:                     | :x:                       |
| :mag:        | `:mag:`         | Writing, refactoring, fixing automated tests | :x:     | :x:                       |
| :wrench:     | `:wrench:`      | Build scripts, CI, gitignore, other chore       | :x:  | :x:                       |

#### Merges, reverts etc
Commits created by `git merge`, `git revert` etc should begin with
`Merge`, `Revert` etc - just like git automatically creates them.


### Scope
The affected *module* or *component* of the system.
Possible values are specific to each git repository, but typically include:
* `readme`: Changes to `README.md` or sub-pages linked from there
* `drone`: Changes to `.drone.yml` or related configuration
* `docker`: Changes to `Dockerfile` or related configuration
* `terraform`: Changes to terraform configuration files
  * Only in mixed infra / application code repos. In pure infra repos this
    is probably too broad.
* `handler`: Changes to a Lambda's handler function
* No scope: Changes spanning multiple components
  * Double-check whether the commit is
    *[atomic](https://curiousprogrammer.io/blog/why-i-create-atomic-commits-in-git)*

The scope should be specified as perceived *by the person reading* the
release notes generated from commit messages.


### Subject
The subject contains a succinct description of the change:

* Write an English sentence, i.e. including a verb
* Use the imperative, present tense: "change" not "changed" nor "changes"
* Capitalize the first letter
* No dot (.) at the end


### Body
Just as in the **subject**, use the imperative, present tense:
"change" not "changed" nor "changes".
The body should include the motivation for the change and contrast
this with previous behavior.


### Footer
The optional footer contains:
* References to JIRA issues that the commit **Closes** - mostly used in commits merging a PR branch
* References to PR review comments that the commit **Addresses**


### Examples
```
:pencil: changelog: Update changelog to 3.2.1
```
```
:star: drone: Create deploy step

Use the CI pipeline not only to build and test but also to deploy the application
so that deploys are transparent and repeatable and we do not have to do it
manually any more

Closes https://jira.meteogroup.net/browse/NFE-13

Addresses https://github.com/MeteoGroup/lambflow/pull/11#pullrequestreview-289977578
```
