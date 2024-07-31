# GitNav

This script searches GitHub repositories based on a query, then analyzes specific markdown files (`README.md`, `CONTRIBUTING.md`, and `CHANGELOG.md`) in those repositories to find a specific keyword.

## Command-Line Usage

To run the script, provide the following three arguments:

1. **query**: The search query for GitHub repositories.
2. **keyword**: The keyword to search for in markdown files.
3. **token**: Your GitHub personal access token.

### Example Command

```sh
python3 gitnav.py "machine learning language:Python stars:>100" "installation" YOUR_GITHUB_TOKEN
```

## Notes

- **Authentication**: The script requires a GitHub personal access token for authentication. Replace `YOUR_GITHUB_TOKEN` with your own token.
- **Pagination**: The script handles pagination, fetching results page by page until no more repositories are found.
- **Error Handling**: Includes basic error handling for missing files and API request issues.

This script is useful for analyzing multiple repositories to find specific information, such as installation instructions or contribution guidelines, in markdown files.

### This will produce output like:

```plaintext
GitNav
Built by DeadmanXXXII
========================================
Fetching page 1 of search results...
Searching in repository: example-org/example-repo1
Keyword 'installation' found in example-org/example-repo1/README.md
Keyword 'installation' found in example-org/example-repo1/CONTRIBUTING.md

Searching in repository: example-org/example-repo2
README.md not found or error fetching for example-org/example-repo2: 404 Client Error: Not Found for url: https://api.github.com/repos/example-org/example-repo2/contents/README.md

Fetching page 2 of search results...
Searching in repository: example-org/example-repo4
Keyword 'installation' found in example-org/example-repo4/README.md
Keyword 'installation' found in example-org/example-repo4/CHANGELOG.md

No more repositories found.
========================================
```

---
