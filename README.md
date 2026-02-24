# BoulderJS

> For a community overview, see the [BoulderJS organization profile](https://github.com/boulder-js/.github/blob/main/profile/README.md).

Container repository for the BoulderJS community. Each sub-project is an independent git repository that must be cloned separately into this directory.

## Repositories

| Directory | Repository | Description |
| --- | --- | --- |
| `website/` | [boulder-js/website](https://github.com/boulder-js/website) | Astro SSR website deployed to Cloudflare Pages |
| `events/` | [boulder-js/events](https://github.com/boulder-js/events) | Event management via GitHub Issues |
| `talks/` | [boulder-js/talks](https://github.com/boulder-js/talks) | Talk proposals via GitHub Issues |
| `jobs/` | [boulder-js/jobs](https://github.com/boulder-js/jobs) | Job postings via GitHub Issues |

## Setup

Clone this repo, then clone each sub-project into it:

```bash
git clone https://github.com/boulder-js/boulder-js
cd boulder-js
git clone https://github.com/boulder-js/website
git clone https://github.com/boulder-js/events
git clone https://github.com/boulder-js/talks
git clone https://github.com/boulder-js/jobs
```

Everything is gitignored by default — only `README.md` and `.claude/` are tracked in this repo.

## Website Development

See [`website/README.md`](website/README.md) for setup instructions. Requires a GitHub PAT for the `boulder-js` org to fetch event data.

## Community

- Discord: [chat.boulderjs.org](https://chat.boulderjs.org)
- Events: [boulder-js/events](https://github.com/boulder-js/events/issues/new/choose)
- Talk proposals: [boulder-js/talks](https://github.com/boulder-js/talks/issues)
- Jobs: [boulder-js/jobs](https://github.com/boulder-js/jobs/issues)
- [Code of Conduct](https://github.com/boulder-js/.github/blob/main/CODE_OF_CONDUCT.md)
