# Infrastructure as Code, from scratch

Build one Terraform configuration up from a single file, then rebuild it with OpenTofu and Terragrunt.

Everything runs on your own filesystem, so there is no cloud account and nothing to pay for. The language, the commands and the state file do not care whether they are creating a text file or a database.

Take the steps in order. Each one edits, extracts or replaces what the last left behind, so a step you skip takes the next one's starting point with it.

You work in `workspaces/your-name/`, on your own branch, and raise a pull request at the end. That is [step 08](08-pull-request.md), and it is as much of the point as the rest. Nobody's directory touches anyone else's, so a dozen pull requests against `main` can all be merged.

This repository is public, so read [what never to commit](../README.md#this-repository-is-public) before you start.

## Start here

Work through [00-setup](00-setup.md) first. It installs the tools and gives you a branch and a directory to work in.

## The steps

| Step | What you build | What it teaches |
| --- | --- | --- |
| [01-local](01-local.md) | A random name and a text file on your disk | `init`, `plan`, `apply`, `destroy`, and what state is |
| [02-variables](02-variables.md) | The same thing, parameterised, three files instead of one | Variables, outputs, locals, `for_each` |
| [03-tofu](03-tofu.md) | Nothing new | Why OpenTofu, and moving a state file across |
| [04-modules](04-modules.md) | The same resources, extracted into a module and called twice | Modules, inputs, outputs, composition |
| [05-environments](05-environments.md) | Dev, staging and prod, by copy and paste | The duplication problem, felt rather than described |
| [06-terragrunt](06-terragrunt.md) | The same three, without the copy and paste | `terragrunt.hcl`, generated blocks, dependencies, `run --all` |
| [07-mhi-infra](07-mhi-infra.md) | Nothing. Read only. | How the real repository is laid out, and what a cloud provider adds |
| [08-pull-request](08-pull-request.md) | A reviewed pull request | Pushing, describing, responding to review, and why merging is the approval |

## Catching up

[reference/](reference/) holds what your workspace should contain at the end of each step. If a step defeats you, drop the finished version over the top of your own and carry on:

```
WORKSPACE=your-name
cp -r ~/learn/iac/reference/04-modules/. ~/learn/iac/workspaces/$WORKSPACE/
```

The trailing `/.` copies the contents rather than the directory. Delete anything the step was supposed to remove, because copying files in cannot take files out. Step 03 has no snapshot, since it changes which binary you run and leaves every file alone.

Come back to the step afterwards.

## How to work through it

- Run `destroy` at the end of any step that created something, so the next step starts from nothing.
- Ask the moment you are stuck. Each step builds on the one before it, so a step you did not finish blocks the rest.
- Read the plan output rather than scrolling past it. Most of this is learning to read a plan.
