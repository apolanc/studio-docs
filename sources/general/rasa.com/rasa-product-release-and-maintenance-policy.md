# Source: https://rasa.com/rasa-product-release-and-maintenance-policy

# Rasa Product Release and Maintenance Policy

![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68ef7d58530b1791a344b245_general%20header.avif)

## Summary

In order to enable our customers to innovate and to support our continued development and innovation, we have chosen to implement the following Product Release and Software Maintenance Policy. Our End of Life policy defines how long a given release is considered supported, as well as how long a release is considered to be still in active development or maintenance. We provide more information about this in our [support policy](https://rasa.com/agreements/inc/support-services1/) which includes our support SLAs.

## Versioning

Rasa has implemented robust policies governing version naming, as well as release pace for major, minor, and patch releases. Rasa Enterprise, Rasa Pro, and Rasa Open Source adhere to [Semantic Versioning](https://semver.org/), as follows:

The values for a given version number (MAJOR.MINOR.PATCH) are incremented as follows:

- MAJOR version for incompatible API changes or other breaking changes.
- MINOR version for functionality added in a backward compatible manner.
- PATCH version for backward compatible bug fixes.

For example, the Rasa Open Source 3.2.4 release can be read as follows:

- 3 represents the major version. The major release was 3.0.0 but often referred to as 3.0
- 2 represents the minor version. The minor release was 3.2.0 but often referred to as 3.2
- 4 represents the patch number

## Release Frequency

| Version Type | Description | Target Cadence |
| --- | --- | --- |
| Major | For significant changes, or when any backward-incompatible changes are introduced to the API or data model. | Every 1 - 2 yrs |
| Minor | For when new backward-compatible functionality is introduced, a minor feature is introduced, or when a set of smaller features is rolled out. | +/- Quarterly |
| Patch | For backward-compatible bug fixes that fix incorrect behavior. | As needed |

The following table describes the version types and their expected release cadence:

‍

While this table represents our target release frequency, we reserve the right to modify it based on changing market conditions and technical requirements.

## End of Life Process

The End of Life (EoL) process is intended to guide the final business operations associated with a Rasa product, service, or subscription life cycle. The end-of-life process consists of a series of technical and business milestones and activities that, once completed, make a product, service, or subscription obsolete. Once obsolete, the product, service, or subscription is not sold, improved, maintained, or supported.

We have set out below Rasa’s End of Product Lifecycle milestones to help manage the EOL transitions and to explain to customers how, and when to migrate to alternative Rasa products and services. The Rasa platform is an intricate system of multiple products. It also depends on a large set of third-party libraries that are independently maintained and deployed through dependency installation scripts. The End of Life process and policy we established are aligned with the major components’ support policies. It is for this reason that we actively encourage our customers to stay up to date on the Rasa software versions they use in production and have an active migration program that is aligned with this End of Life Process and Maintenance timelines.

## Types of Releases

Major versions, such as 2.0.0 and 3.0.0 provide us with an opportunity to introduce features and break backward compatibility. Minor versions, such as 2.8.0 and 3.2.0, provide us with an opportunity to introduce features. Patch releases, such as 2.8.14 and 3.1.2, fix bugs only. Maintenance activity occurs on all releases that have not reached the end of life, but we focus on the minor release stream (e.g., 3.2.x) to define how long we maintain a particular code line. Active maintenance of a minor release implies that we are fixing bugs and backporting some number of fixes into that code branch.

## Maintenance Policy

### Commercial Support

The following policy applies to all customers with commercial licenses of Rasa products, including Rasa Open Source, Rasa X/Enterprise, Rasa Pro, and associated packages and APIs.

Customers who have purchased a Rasa subscription (regardless of support tier) should expect functional and security bug fixes in the form of a patch release for nine (9) months from the release date of the initial minor version of a given major version. Once Rasa releases the next major release, effectively putting an end to any minor feature releases on the previous major, the last minor release will have an extended support date of twelve (12) months from the initial release date of the last minor. This becomes the Extended Support (ES) release. Technical support is provided for an additional six (6) months from the End of Software maintenance date of every minor release.

More detailed information with actual dates will be maintained in the maintenance table below.

### Community Support

Our goal for community users of Rasa Open Source is to maintain the most recent minor release from the current major release stream. This allows these users to obtain packaged fixes on the latest branch while making only minor changes to their running software.

From time to time we may backport fixes to other minor release streams. For example, a serious security patch might be ported to multiple branches and a release may be packaged to include this patch. We will use our discretion when deciding to do this, but expect it to be very infrequent.

### Definitions

_“End of Software Maintenance_” is the date after which the product is no longer maintained by development engineering. This is also the last date engineering may issue functional or security patches to the product. All upgrades to actively supported versions should be completed by this date.

_“End of Technical Support”_ is the last date to receive applicable service and support as entitled by active service contracts for covered products. This additional support window is a grace period for completing upgrades that weren’t finalized before the end of software maintenance date. After this date, support services are no longer available.

_“Extended Support_” is how Rasa identifies a release that will receive an extended period of support for subscription customers. This will typically be associated with the last minor release of a given major release.

## Upgrade Policy

### Upgrading from a prior Major Version

When upgrading from a previous major, for example, 2.8, the latest minor of a major should be picked as the version to upgrade to, for example, 3.2. All software and security patches will have been applied to that minor.  Please note that upgrades of one product may require an upgrade to another dependent on it. Please refer to the [Compatibility Matrix](https://rasa.com/docs/rasa-enterprise/changelog/compatibility-matrix/) for more details.

### Upgrading multiple Major Versions

Upgrading from older versions, for example, 1.10, to a newer major version, for example, 3.2, always requires an upgrade to any intermediate major version first. For the mentioned example, an upgrade from 1.10 to 2.9 should be performed, and then followed by an upgrade from 2.9 to 3.2. No major version should be skipped.

## Maintenance Tables

The following tables are simplified descriptions of the above policy. There may be occasions where we release a new minor version after a new major version is released. In that case, the tables below will be updated and the above-written policy will take precedence.

#### Rasa Studio

Product Name

Version

Initial Release Date

End of Software Maintenance

End of Technical Support

Rasa Studio

1.17.x

July 6, 2026

April 6, 2027

October 6, 2027

Rasa Studio

1.16.x

April 7, 2026

January 7, 2027

July 7, 2027

Rasa Studio

1.15.x

December 9, 2025

September 9, 2026

March 9, 2027

Rasa Studio

1.14.x

October 21, 2025

July 21, 2026

January 21, 2027

Rasa Studio

1.13.x

July 14, 2025

April 14, 2026

October 14, 2026

Rasa Studio

1.12.x

April 8, 2025

January 8, 2026

July 8, 2026

Rasa Studio

1.11.x

January 15, 2025

October 15, 2025

April 15, 2026

Rasa Studio

1.10.x

December 17, 2024

September 17, 2025

March 17, 2026

Rasa Studio

1.9.x

November 8, 2024

August 8, 2025

February 8, 2026

Rasa Studio

1.8.x

October 23, 2024

July 23, 2025

January 23, 2026

Rasa Studio

1.7.x

September 20, 2024

June 20, 2025

December 20, 2025

Rasa Studio

1.6.x

August 30, 2024

May 30, 2025

November 30, 2025

Rasa Studio

1.5.x

July 19, 2024

April 19, 2025

October 19, 2025

Rasa Studio

1.4.x

June 14, 2024

March 14, 2025

September 14, 2025

Rasa Studio

1.3.x

May 16, 2024

February 16, 2025

August 16, 2025

Rasa Studio

1.3.x

May 16, 2024

February 16, 2025

August 16, 2025

Rasa Studio

1.2.x

April 18, 2024

January 18, 2025

July 18, 2025

Rasa Studio

1.1.x

March 18, 2024

December 18, 2024

June 18, 2025

Rasa Studio

1.0.x

November 29, 2023

August 29, 2024

February 28, 2025

#### Rasa Pro

The table below applies to Rasa Pro (and previous Rasa Plus releases). Go to the next table for Rasa Pro Services.

Product Name

Version

Initial Release Date

End of Software Maintenance

End of Technical Support

Rasa Pro

3.17.x

June 23, 2026

March 23, 2027

September 23, 2027

Rasa Pro

3.16.x

March 26, 2026

December 26, 2026

June 26, 2027

Rasa Pro

3.15.x

November 26, 2025

August 26, 2026

February 26, 2027

Rasa Pro

3.14.x

October 9, 2025

July 9, 2026

January 9, 2027

Rasa Pro

3.13.x

July 7, 2025

April 7, 2026

October 7, 2026

Rasa Pro

3.12.x

March 19, 2025

December 19, 2025

June 19, 2026

Rasa Pro

3.11.x

December 11, 2024

September 11, 2025

March 11, 2026

Rasa Pro

3.10.x

September 4, 2024

June 4, 2025

December 4, 2025

Rasa Pro

3.9.x

July 3, 2024

April 3, 2025

October 3, 2025

Rasa Pro

3.8.x

April 3, 2024

January 3, 2025

July 3, 2025

Rasa Pro

3.7.x

November 22, 2023

August 22, 2024

February 22, 2025

Rasa Pro

3.6.x

July 3, 2023

April 3, 2024

October 3, 2024

Rasa Pro

3.5.x

March 28, 2023

December 28, 2023

June 28, 2024

Rasa Pro

3.4.x

December 21, 2022

September 21, 2023

March 21, 2024

Rasa Pro

3.3.x

October 24, 2022

July 24, 2023

January 24, 2024

#### Rasa Pro Services

The table below applies to Rasa Pro Services. Go to the previous table for Rasa Pro.

Product Name

Version

Initial Release Date

End of Software Maintenance

End of Technical Support

Rasa Pro Services

3.9.x

June 29, 2026

March 29, 2027

September 29, 2027

Rasa Pro Services

3.8.x

March 30, 2026

December 30, 2026

June 30, 2027

Rasa Pro Services

3.7.x

November 27, 2025

August 27, 2026

February 27, 2027

Rasa Pro Services

3.6.x

October 10, 2025

July 10, 2026

January 10, 2027

Rasa Pro Services

3.5.x

March 20, 2025

December 20, 2025

June 20, 2026

Rasa Pro Services

3.4.x

December 12, 2024

September 12, 2025

March 12, 2026

Rasa Pro Services

3.3.x

April 3, 2024

January 3, 2025

July 3, 2025

Rasa Pro Services

3.2.x

November 22, 2023

August 22, 2024

February 22, 2025

Rasa Pro Services

3.1.x

July 3, 2023

April 3, 2024

October 3, 2024

Rasa Pro Services

3.0.x

October 24, 2022

July 24, 2023

January 24, 2024

#### Rasa X/Enterprise

For compatibility of Rasa X/Enterprise with Rasa Pro or Rasa Open Source, please refer to the [Compatibility Matrix](https://rasa.com/docs/rasa-enterprise/changelog/compatibility-matrix/) in the references section below.

Product Name

Version

Initial Release Date

End of Software Maintenance

End of Technical Support

Rasa X/Enterprise

1.4.x

March 15, 2024

December 15, 2024

June 15, 2025

Rasa X/Enterprise

1.3.x

July 31, 2023

April 30, 2024

October 31, 2024

Rasa X/Enterprise

1.2.x

August 12, 2022

May 12, 2023

November 12, 2023

Rasa X/Enterprise

1.1.x

March 29, 2022

December 29, 2022

June 29, 2023

Rasa X/Enterprise

1.0.x

December 2, 2021

September 14, 2022

March 14, 2023

Rasa X/Enterprise

0.42.x

July 27, 2021

January 27, 2022

July 27, 2022

Rasa X/Enterprise

0.19.x

May 21, 2019

February 21, 2020

August 21, 2020

#### Rasa Open Source (Commercial Support)

The following standard and extended End of Software Maintenance dates only apply to commercial subscriptions. Community (Open Source) users should not expect a similar level of support or commitment to receiving software or security patches from Rasa in accordance with these software maintenance support dates.

Product Name

Version

Initial Release Date

End of Software Maintenance

End of Technical Support

Rasa Open Source

3.6.x

July 3, 2023

July 3, 2024

January 3, 2025

Rasa Open Source

3.5.x

March 28, 2023

December 28, 2023

June 28, 2024

Rasa Open Source

3.4.x

December 21, 2022

September 21, 2023

March 21, 2024

Rasa Open Source

3.3.x

October 24, 2022

July 24, 2023

January 24, 2024

Rasa Open Source

3.2.x

June 14, 2022

March 14, 2023

September 14, 2023

Rasa Open Source

3.1.x

March 25, 2022

December 25, 2022

June 25, 2023

Rasa Open Source

3.0.x

November 23, 2021

August 23, 2022

February 23, 2023

Rasa Open Source

2.8.x

July 12, 2021

August 11, 2022

February 11, 2023

Rasa Open Source

2.7.x

June 3, 2021

March 3, 2022

September 3, 2022

Rasa Open Source

2.6.x

May 6, 2021

February 6, 2022

August 6, 2022

Rasa Open Source

2.5.x

April 12, 2021

January 12, 2022

July 12, 2022

Rasa Open Source

2.4.x

March 11, 2021

December 11, 2021

June 11, 2022

Rasa Open Source

2.3.x

February 11, 2021

November 11, 2021

May 11, 2022

Rasa Open Source

2.2.x

December 16, 2020

September 16, 2021

March 16, 2022

Rasa Open Source

2.1.x

December 4, 2020

September 4, 2021

March 4, 2022

Rasa Open Source

2.0.x

October 7, 2020

July 7, 2021

January 7, 2022

## References

Rasa X/Enterprise Compatibility Matrix

[https://rasa.com/docs/rasa-enterprise/changelog/compatibility-matrix](https://rasa.com/docs/rasa-enterprise/changelog/compatibility-matrix/)

Rasa Pro Compatibility Matrix

[https://rasa.com/docs/rasa-pro/compatibility-matrix](https://rasa.com/docs/rasa-pro/compatibility-matrix/)

Rasa X/Enterprise Change Log

[https://rasa.com/docs/rasa-enterprise/changelog/rasa-enterprise-changelog](https://rasa.com/docs/rasa-enterprise/changelog/rasa-enterprise-changelog/)

Rasa Pro Change Log

[https://rasa.com/docs/rasa-pro/rasa-pro-changelog](https://rasa.com/docs/rasa-pro/rasa-pro-changelog/)

Rasa Open Source Change Log

[https://rasa.com/docs/rasa/changelog](https://rasa.com/docs/rasa/changelog/)

Rasa Action Server SDK Change Log

[https://rasa.com/docs/action-server/rasa-sdk-changelog](https://rasa.com/docs/action-server/rasa-sdk-changelog/)

Version Migration Guide

[https://rasa.com/docs/rasa-pro/migration-guide](https://rasa.com/docs/rasa-pro/migration-guide/)

## AI that adapts to your business, not the other way around

## Build your next AI

## agent with Rasa

Power every conversation with enterprise-grade tools that keep your teams in control.

[get a demo](https://rasa.com/connect-with-rasa)

![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68ee4d8c393fe398b80e895c_cta%20card.webp)