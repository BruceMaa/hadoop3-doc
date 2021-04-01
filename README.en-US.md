# use mdbook build docs website

[![Github Actions][github-action-image]][github-repo-url]
[![license][license-image]](LICENSE)
[![Github Star][github-repo-star-image]][github-repo-url]
[![standard-readme compliant][standard-readme-image]](standard-readme-url)

[Background](#background) | [Introduction](#introduction) | [Usage](#usage) | [Examples](#examples) | [Related Efforts](#related-efforts) | [Maintainers](#maintainers) | [Contributing](#contributing) | [License](#license) | [中文](README.md)

## Background

use [mdbook](https://rust-lang.github.io/mdBook/index.html) build docs website auto.

## Introduction

```
docs-use-mdbook
├── .github
│   ├── COMMIT_CONVENTION.md
│   ├── ISSUE_TEMPLATE
│   │   ├── bug_report.md
│   │   ├── custom.md
│   │   └── feature_request.md
│   ├── PULL_REQUEST_TEMPLATE.md
│   └── workflows
│       └── main.yml
├── .gitignore
├── CHANGELOG.md
├── CONTRIBUTING.md
├── LICENSE
├── README.md
├── README.en-US.md
```

### 详细介绍

1. [README.md](README.md)

    > A text file containing information about the files in a repository that is typically the first file a visitor to your repository will see. A README file, along with a repository license, contribution guidelines, and a code of conduct, helps you share expectations and manage contributions to your project.

2. [README.en-US.md](README.en-US.md)

    > README use English.

3. [LICENSE](LICENSE)

    > A document that you can include with your project to let people know what they can and can't do with your source code.

4. [.gitignore](.gitignore)

    > A gitignore file specifies intentionally untracked files that Git should ignore. Files already tracked by Git are not affected; see the [NOTES](https://git-scm.com/docs/gitignore).

5. [CHANGELOG.md](CHANGELOG.md)

    > Every time a new version is released, record the changed features of the new version, as well as the modified bug and other information.

6. [CONTRIBUTING.md](CONTRIBUTING.md)

    > Contribution specifications, such as code writing specifications, if you ask questions, raise bugs, raise requirements, how to write documents, etc.

7. [.github/COMMIT_CONVERTION.md](.github/COMMIT_CONVERTION.md)

    > git commit information specification.

8. [.github/PULL_REQUEST_TEMPLATE.md](.github/PULL_REQUEST_TEMPLATE.md)

    > the template of `pull request`.

9. [.github/ISSUE_TEMPLATE/bug_report.md](.github/ISSUE_TEMPLATE/bug_report.md)

    > the template of raise bug in issue.

10. [.github/ISSUE_TEMPLATE/custom.md](.github.com/ISSUE_TEMPLATE/custom.md)

    > custom issue template.

11. [.github/ISSUE_TEMPLATE/feature_request.md](.github/ISSUE_TEMPLATE/feature_request.md)

    > the template of raise requirement in issue.

12. [.github/workflows/main.yml](.github.com/workflows/main.yml)

    > GitHub Action profile.

## Usage

click[![use this template][use-this-template]][generate]button, copy this repository to your GitHub.

or use GitHub cli `gh`

```
gh repo create myRepository -p GitHubTemplates/docs-use-mdbook
```

## Examples

Generally, the open source repository need to have some examples or codes for users' reference.

## Related Efforts

- [mdbook](https://github.com/rust-lang/mdBook) 

## Maintainers

[@BruceMaa](https://github.com/BruceMaa)。

## Contributing

Feel free to dive in![Open an Issue](https://github.com/GitHubTemplates/docs-use-mdbook/issues/new) or submit PRs。

docs-use-mdbook follows the [Contributing](CONTRIBUTING.md) specification。

docs-use-mdbook follows the [Contributor Covenant](http://contributor-covenant.org/version/1/3/0/) Code of Conduct。

## License

[MIT © Bruce Maa.](LICENSE)

[github-action-image]: https://github.com/GitHubTemplates/docs-use-mdbook/actions/workflows/main.yml/badge.svg
[github-repo-url]: https://github.com/GitHubTemplates/docs-use-mdbook/actions/workflows/main.yml
[license-image]: https://img.shields.io/badge/license-MIT-green.svg
[github-repo-star-image]: https://img.shields.io/github/stars/GitHubTemplates/docs-use-mdbook.svg?style=social
[use-this-template]: https://img.shields.io/badge/-use%20this%20template-brightgreen.svg
[generate]: https://github.com/GitHubTemplates/docs-use-mdbook/generate
[standard-readme-image]: https://img.shields.io/badge/readme%20style-standard-brightgreen.svg?style=flat-square
[standard-readme-url]: https://github.com/RichardLitt/standard-readme