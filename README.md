# Privacy Respecting Workflows using GitHub Actions

## CI Go Coverage - ci-go-cover.yml
This workflow checks if Go (golang) code coverage satisfies the minimum specified percent for your project.

Example from fxamacker/cbor:  
[![](https://github.com/fxamacker/cbor/workflows/cover%20%E2%89%A597%25/badge.svg)](https://github.com/fxamacker/cbor/blob/master/.github/workflows/ci-go-cover.yml)

Example from x448/float16:  
[![](https://github.com/x448/float16/workflows/cover%20100%25/badge.svg)](https://github.com/x448/float16/blob/master/.github/workflows/cover.yml)

* GitHub generates badge.svg you can display in your README.md.
* GitHub will display success or failure in your pull requests and commits.
* Only external script is from GitHub Inc. (actions/checkout@v2)
* __Does not download or upload anything__.
* __Does not ask you to disclose your private email addresses__.
* __Does not ask you to allow reading any private project boards__.
* Does not ask you to grant any permissions on GitHub.
* Does not ask you to sign up to any 3rd-party service.

If there's enough demand, I can update this to compare coverage with prior commit.

__Installation__

0. Copy this file to github.com/OWNER_NAME/REPO_NAME/.github/workflows/ci-go-cover.yml  
1. Change workflow name from "cover 100%" to "cover ≥92.5%". Script will automatically use 92.5%.  
2. Update README.md to use the new path to badge.svg because the path includes the workflow name.  

__Who uses this?__

* [github.com/fxamacker/cbor](https://github.com/fxamacker/cbor). [Issue 115](https://github.com/fxamacker/cbor/issues/115).
* [github.com/x448/float16](https://github.com/x448/float16)

__Why was this created?__  

This workflow was created because a 3rd-party service wanted (IMHO) too much authorization:
* their "application will be able to read your organization, team membership, and __private project boards__."
* their "application will be able to read __your private email addresses__."
* their privacy policy mentioned IP addresses and the right to share data with their unidentified service providers.

## Hash
BLAKE2B for ci-go-cover.yml 2020.1.28:  
13ab0715bbae856dfa6e6fac3e785d4e2cf040a9270d7104b4a13041f6d3ba99f7649f820a1d776597afa0b837ee1e711a9469a3bfc75be474c97843b2020f12

SHA384 for ci-go-cover.yml 2020.1.28:  
2fbabc14f7f9dbde8e749109f40239ab3ea7d4b320e532757990cd839cbe3d4ad61611d926d8d0413778859f98028201

## License
Copyright (c) 2020-present Montgomery Edwards⁴⁴⁸ (github.com/x448)

x448/workflows is licensed under the MIT License. See [LICENSE](LICENSE) for the full text.
