# Learn

Self-paced technical tutorials. Each course sits in its own folder and starts from that folder's README.

## Courses

| Course | What you do |
| --- | --- |
| [Infrastructure as Code](iac/) | Build one Terraform configuration up from a single file, then rebuild it with OpenTofu and Terragrunt, all on your own filesystem. |

## This repository is public

Everything you write here, including your branch, your pull request and your commit messages, is readable by anyone.

"Could this be public?" is a stronger test than "is this tidy enough", and it is harder to let slip. This also lets other charities read a real infrastructure repository rather than a sanitised template.

Never commit:

- Secrets of any kind. Keys, tokens, passwords, certificates, connection strings with credentials in them.
- Service-user data. For a mental health organisation this is the absolute line.
- Staff personal-life data. Personal email addresses, home addresses, HR records.
- Internal references. Ticket keys, internal-only URLs, the names of internal tools and chat channels.
- Real production bucket names, host names, and private addresses.

A secret that a running system needs is supplied at the point it runs, from an identity the machine already holds or from a secret store it can read, so that the value never exists in a file at all. [Step 07 of the Infrastructure as Code course](iac/07-mhi-infra.md) shows what that looks like in practice.
