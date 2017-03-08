# Contributing
There are a simple base on rules upon we structure all development. This are based in mutual trust
and the respect of each invidual piece of work. The aim of this document is to have an efficient workflow
and an environment we all like to work in. A stable continous flow of changes that are pushed and merged
as fast as possible, keeping the best possible quality.

## The rules
1. All known **bugs** must be **fixed** before writing new code.
1. All reviewed **PRs** must be **merged** before writing new code.
1. All new code needs a specification before it is written.
1. You may not push to master, but merge.
1. You may not merge to master, if not reviewed.
1. Merge commits are forbidden :pray: `git pull --rebase`.
1. You may not commit any code with unsolved warnings.
1. You must follow shared [style and naming conventions](https://github.com/jsdario/netbeast/blob/master/docs/style-guide.md).
1. Bugs will only be marked as solved if there is a test for it.
1. Pull Requests must be of the smallest possible size.
1. You may not start a task without updating trello.
1. Code must be tested in any deployable environment **manually**.

## The hows
* The *spec* must be written from the user point of view.
* The *spec* mut be available from the PR (written or linked to trello or an issue)
* Tag the PRs by topics like `[Alexa][Skill]` if they are dependant one of another.
* Use the branch naming to specify which has to be merged first.
* Do not push without testing at least on Android and iOS.
* Let others know what your PR achieves: update the HISTORY.md. If your PR is trivial
and does not affect the user, please tag it as `[Trivial]`.

## Inspirations
* [The Joel Test](https://www.joelonsoftware.com/2000/08/09/the-joel-test-12-steps-to-better-code/) – J. Spolsky (Stackoverflow CEO) 
* [Escalar equipo técnico en una startup](http://javisantana.com/2017/02/19/escalar-el-equipo-tecnico-en-una-startup.html) – Javi Santana (CARTO CTO)
