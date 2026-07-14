# Source: https://rasa.com/docs/rasa-enterprise/changelog/compatibility-matrix

SearchK

When choosing a Rasa Enterprise version to install or update to, refer to the table below to help choose the compatible Rasa Open Source and Rasa SDK versions.

It is recommended to always use the latest `PATCH` version of whatever `MINOR` version you’re on, because it introduces bug fixes without any breaking changes (See [Semantic Versioning](https://legacy-docs-enterprise.rasa.com/docs/rasa-enterprise/changelog/compatibility-matrix/#semantic-versioning)).

| Rasa Enterprise | Rasa Pro | Rasa Open Source & Rasa SDK | Notes |
| --- | --- | --- | --- |
| [1.4.x](https://legacy-docs-enterprise.rasa.com/docs/rasa-enterprise/changelog/rasa-enterprise-changelog) | [3.3.x, 3.4.x, 3.5.x, 3.6.x, 3.7.x](https://rasa.com/docs/rasa/rasa-pro-changelog) | [3.0.x, 3.1.x, 3.2.x, 3.3.x, 3.4.x, 3.5.x, 3.6.x](https://rasa.com/docs/rasa/changelog) | Although Rasa X supports Python 3.7, Rasa Pro 3.6.x and Rasa Open Source 3.6.x [don't support it](https://rasa.com/docs/rasa/rasa-pro-changelog#deprecations-and-removal). |
| [1.3.x](https://legacy-docs-enterprise.rasa.com/docs/rasa-enterprise/changelog/rasa-enterprise-changelog) | [3.3.x, 3.4.x, 3.5.x, 3.6.x](https://rasa.com/docs/rasa/rasa-pro-changelog) | [3.0.x, 3.1.x, 3.2.x, 3.3.x, 3.4.x, 3.5.x, 3.6.x](https://rasa.com/docs/rasa/changelog) | Although Rasa X supports Python 3.7, Rasa Pro 3.6.x and Rasa Open Source 3.6.x [don't support it](https://rasa.com/docs/rasa/rasa-pro-changelog#deprecations-and-removal). |
| [1.2.x](https://legacy-docs-enterprise.rasa.com/docs/rasa-enterprise/changelog/rasa-enterprise-changelog) | [3.3.x, 3.4.x, 3.5.x, 3.6.x](https://rasa.com/docs/rasa/rasa-pro-changelog) | [3.0.x, 3.1.x, 3.2.x, 3.3.x, 3.4.x, 3.5.x, 3.6.x](https://rasa.com/docs/rasa/changelog) | 1.2.x is compatible with Rasa Pro 3.6.x, but it doesn't support the new PII Management functionality introduced with Rasa Pro 3.6. This is supported in 1.3.x. 
Although Rasa Enterprise supports Python 3.7, Rasa Pro 3.6.x and Rasa Open Source 3.6.x [don't support it](https://rasa.com/docs/rasa/rasa-pro-changelog#deprecations-and-removal). |
| 1.1.x | | 3.0.x, 3.1.x | |
| 1.0.1 | | 2.8.x | |

## Pre 1.0 compatibility matrix[#](https://legacy-docs-enterprise.rasa.com/docs/rasa-enterprise/changelog/compatibility-matrix/#pre-10-compatibility-matrix 'Direct link to heading')

| Rasa Enterprise | Rasa Open Source | Rasa SDK |
| --- | --- | --- |
| 0.42.6 | 2.8.14 | 2.8.3 |
| 0.41.2 | 2.7.1 | 2.7.0 |
| 0.40.0 | 2.6.2 | 2.6.0 |
| 0.39.0 | 2.5.0 | 2.5.0 |
| 0.38.0 | 2.4.0 | 2.4.0 |
| 0.37.0 | 2.3.1 | 2.3.1 |
| 0.36.0 | 2.3.1 | 2.3.1 |
| 0.35.0 | 2.2.4 | 2.2.0 |
| 0.34.0 | 2.1.2 | 2.1.2 |
| 0.33.0 | 2.0.2 | 2.0.2 |
| 0.32.2 | 1.10.14 | 1.10.2 |
| 0.31.5 | 1.10.10 | 1.10.2 |
| 0.30.1 | 1.10.8 | 1.10.2 |
| 0.29.3 | 1.10.7 | 1.10.2 |
| 0.28.6 | 1.10.2 | 1.10.1 |
| 0.27.8 | 1.9.7 | 1.9.0 |
| 0.26.4 | 1.8.3 | 1.8.1 |
| 0.25.3 | 1.7.4 | 1.7.0 |
| 0.24.8 | 1.6.2 | 1.6.1 |
| 0.23.6 | 1.5.3 | 1.5.2 |
| 0.22.2 | 1.4.6 | 1.4.0 |
| 0.21.5 | 1.3.10 | 1.3.3 |
| 0.20.5 | 1.2.9 | 1.2.0 |

## Semantic Versioning[#](https://legacy-docs-enterprise.rasa.com/docs/rasa-enterprise/changelog/compatibility-matrix/#semantic-versioning 'Direct link to heading')

`Rasa Enterprise`, `Rasa Open Source` and `Rasa SDK` adhere to [Semantic Versioning](https://semver.org/):

The values for a given a version number `MAJOR.MINOR.PATCH` are incremented as follows:

- `MAJOR` version for incompatible API changes

- `MINOR` version for functionality added in a backwards compatible manner

- `PATCH` version for backwards compatible bug fixes.