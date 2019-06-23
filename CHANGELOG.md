# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

### Changed

## [1.1.1] - 2019-06-23

- Added PDF versions of the examples to the CTAN upload.

### Added

## [1.1.0] - 2019-06-23

### Added

- The links to the embedded files (references) are typeset at the bottom of the paper.
- Support for `a4paper` for LNCS papers.

### Changed

- Updated LNCS output to the requirements of [Springer's Consent to Publish v3](http://resource-cms.springer.com/springer-cms/rest/v1/content/731196/data/v3).
- If `nourl` is active, the DOI is used as link for the QR code.
- File embedding is implemented using the [intopdf](https://www.ctan.org/pkg/intopdf) package. Links to the embedded files are shown in the generated PDF.
- ACM format adapted to [acmart](https://github.com/borisveytsman/acmart) v1.50.
- Use [lastpage](https://ctan.org/pkg/lastpage) package instead of custom label.

## 1.0.0 - 2018-02-21

### Added

- Initial version uploaded to CTAN.

[Unreleased]: https://github.com/adbrucker/authorarchive/compare/v1.1.1...HEAD
[1.1.1]: https://github.com/adbrucker/authorarchive/compare/v1.1.0...v1.1.1
[1.1.0]: https://github.com/adbrucker/authorarchive/compare/v1.0.0...v1.1.0
