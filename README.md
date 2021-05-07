# Secure Workflows using GitHub Actions

## CI Go Coverage - ci-go-cover.yml
This self-contained workflow checks if Go (golang) code coverage satisfies the minimum specified percent for your project.

It doesn't download and execute scripts hosted by 3rd parties because [doing such things leads to bad problems](https://www.securityweek.com/codecov-bash-uploader-dev-tool-compromised-supply-chain-hack).

The code to check coverage is very small, easy to audit, and embedded inside GitHub Actions workflow .yml file.

Example from fxamacker/cbor:  
[![](https://github.com/fxamacker/cbor/workflows/cover%20%E2%89%A598%25/badge.svg)](https://github.com/fxamacker/cbor/actions?query=workflow%3A%22cover+%E2%89%A598%25%22)

Example from x448/float16:  
[![](https://github.com/x448/float16/workflows/cover%20100%25/badge.svg)](https://github.com/x448/float16/actions?query=workflow%3A%22cover+100%25%22)

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

* [github.com/fxamacker/cbor](https://github.com/fxamacker/cbor) - a fuzz-tested CBOR library
* [github.com/veraison](https://github.com/veraison) - This open software initiative is creating software that can be used to build device attestation verification services that can support many architectures. To support the Arm Confidential Compute Architecture, contributions to the Veraison project will develop plug-ins that implement the Arm Confidential Compute Architecture attestation model.
* [github.com/x448/float16](https://github.com/x448/float16)

__Why was this created?__  

This workflow was created because a 3rd-party service wanted (IMHO) too much authorization:
* their "application will be able to read your organization, team membership, and __private project boards__."
* their "application will be able to read __your private email addresses__."
* their privacy policy mentioned IP addresses and the right to share data with their unidentified service providers.

__What's the catch?__

There's less automation and fewer features than services that require you to sacrifice more privacy.

If you modify the GitHub Actions workflow name in ci-go-cover.yml to specify a different required minimum coverage, then you need to update the README.md to update link to badge.svg as well its destination URL.

The destination URL only displays the CI info for builds matching the name specified in ci-go-cover.yml.  So it doesn't list any of the prior builds which kinda makes sense (if you think of this as a query) but isn't obvious.

For example, this is what changed in README.md for [fxamacker/cbor](https://github.com/fxamacker/cbor) when min coverage got bumped up from ≥97% to ≥98%.  You can click on the following two badges to see GitHub displays different results.

From:  
[![](https://github.com/fxamacker/cbor/workflows/cover%20%E2%89%A597%25/badge.svg)](https://github.com/fxamacker/cbor/actions?query=workflow%3A%22cover+%E2%89%A597%25%22)

```
[![](https://github.com/fxamacker/cbor/workflows/cover%20%E2%89%A597%25/badge.svg)](https://github.com/fxamacker/cbor/actions?query=workflow%3A%22cover+%E2%89%A597%25%22)
```

To:  
[![](https://github.com/fxamacker/cbor/workflows/cover%20%E2%89%A598%25/badge.svg)](https://github.com/fxamacker/cbor/actions?query=workflow%3A%22cover+%E2%89%A598%25%22)

```
[![](https://github.com/fxamacker/cbor/workflows/cover%20%E2%89%A598%25/badge.svg)](https://github.com/fxamacker/cbor/actions?query=workflow%3A%22cover+%E2%89%A598%25%22)
```

## Hash
BLAKE2B for ci-go-cover.yml 2020.1.28:  
13ab0715bbae856dfa6e6fac3e785d4e2cf040a9270d7104b4a13041f6d3ba99f7649f820a1d776597afa0b837ee1e711a9469a3bfc75be474c97843b2020f12

SHA384 for ci-go-cover.yml 2020.1.28:  
2fbabc14f7f9dbde8e749109f40239ab3ea7d4b320e532757990cd839cbe3d4ad61611d926d8d0413778859f98028201

## License
Copyright (c) 2020-present Montgomery Edwards⁴⁴⁸ (github.com/x448)

x448/workflows is licensed under the MIT License. See [LICENSE](LICENSE) for the full text.
