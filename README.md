# Privacy Respecting Workflows using GitHub Actions

## CI Go Coverage - ci-go-cover.yml
This workflow checks if Go (golang) code coverage satisfies the minimum specified percent for your project.

* GitHub generates badge.svg you can display in your README.md.
* GitHub will display success or failure in your pull requests and commits.
* Only external script is from GitHub Inc. (actions/checkout@v2)
* __Does not download or upload anything__.
* __Does not ask you to disclose your private email addresses__.
* __Does not ask you to allow reading any private project boards__.
* Does not ask you to grant any permissions on GitHub.
* Does not ask you to sign up to any 3rd-party service.

__Who uses this?__

It's used by [github.com/fxamacker/cbor](https://github.com/fxamacker/cbor).

__Why was this created?__  

This workflow was created because a 3rd-party service wanted (IMHO) too much authorization:
* their "application will be able to read your organization, team membership, and __private project boards__."
* their "application will be able to read and write commit statuses (no direct code access)."
* their "application will be able to read __your private email addresses__."
* their "application will be able to read and modify repository webhooks and services (no direct code access)."
* the right to share data with their unidentified service providers.

__Installation__

0. Copy this file to github.com/OWNER_NAME/REPO_NAME/.github/workflows/ci-go-cover.yml  
1. Change workflow name from "cover 100%" to "cover ≥92.5%". Script will automatically use 92.5%.  
2. Update README.md to use the new path to badge.svg because the path includes the workflow name.  

## License
Copyright (c) 2020-present Montgomery Edwards⁴⁴⁸ (github.com/x448)

x448/workflows is licensed under the MIT License. See [LICENSE](LICENSE) for the full text.
