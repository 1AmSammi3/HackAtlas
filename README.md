# HackAtlas

Discover open-source repositories and find contribution opportunities, powered by live public GitHub data.

## What it does

HackAtlas searches GitHub's REST API directly from the browser. It does not use a database, server, account system, or private GitHub token.

- Search public repositories by name, description, and keywords
- Filter by topic and primary programming language
- Sort by recent activity, stars, or repositories with help-wanted issues
- Filter repositories that report good first issues
- View live stars, forks, open issue counts, topics, license, and last-updated date
- Inspect a repository's open issues for labels such as `good first issue` and `help wanted`
- Responsive layout for desktop and mobile

## Run locally

This is a static site. Open `index.html` in a browser, or use a local static server:

```bash
python -m http.server 8000
```

Then visit http://localhost:8000.

## Data and API behaviour

- Data comes from the GitHub REST API: `GET /search/repositories`.
- Repository issue lists are requested when a user opens a repository card.
- Public unauthenticated API requests are subject to GitHub rate limits. Search requests have a separate, stricter limit. HackAtlas debounces text searches and caches results for the current page session.
- If GitHub rate-limits a request, wait before retrying.
- GitHub search results are not an exhaustive catalogue of every repository.
- GitHub does not provide a universal project difficulty score. HackAtlas does not invent one.
- A repository appearing in HackAtlas does not mean it is participating in Hacktoberfest or that its issues are guaranteed to be beginner-friendly.
- Some repositories may not have a license or contribution labels. Always review a project's README, license, contribution guide, and issue tracker before contributing.

## Deployment

The site can be hosted on GitHub Pages because it is a static HTML, CSS, and JavaScript project. The repository's Pages source should point to the root of the `Sammie` branch.

## Roadmap

- [x] Live public repository search
- [x] Topic, language, keyword, and contribution-opportunity filters
- [x] Repository details and live issue-label lookup
- [x] Mobile-responsive directory
- [ ] Curated project submissions and moderation
- [ ] Scheduled indexing and richer discovery
- [ ] Optional backend or GitHub App for higher authenticated API limits

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Please do not submit fabricated repository metadata, stars, activity, or issue availability.

## License

MIT. See [LICENSE](LICENSE).
