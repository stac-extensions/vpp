# Vegetation Phenology and Productivity Extension Specification

- **Title:** Vegetation Phenology and Productivity
- **Identifier:** <https://stac-extensions.github.io/vpp/v0.1.0/schema.json>
- **Field Name Prefix:** vpp
- **Scope:** Collection, Item
- **Extension [Maturity Classification](https://github.com/radiantearth/stac-spec/tree/master/extensions/README.md#extension-maturity):** Proposal
- **Owner**: @m-mohr

This document explains the Vegetation Phenology and Productivity Extension to the
[SpatioTemporal Asset Catalog](https://github.com/radiantearth/stac-spec) (STAC) specification.

Vegetation Phenology and Productivity (VPP) parameters describe the seasonal development of vegetation,
such as the start and end of the growing season, and the productivity of the vegetation during a season.
The term is primarily used in the [Copernicus Land Monitoring Service (CLMS)](https://land.copernicus.eu/).
This extension defines the fields used to describe the VPP season and sub-parameter that a STAC object relates to.

- Examples:
  - [Item example](examples/item.json): Shows the basic usage of the extension in a STAC Item
  - [Collection example](examples/collection.json): Shows the basic usage of the extension in a STAC Collection
- [JSON Schema](json-schema/schema.json)
- [Changelog](./CHANGELOG.md)

## Fields

The fields in the table below can be used in these parts of STAC documents:

- [ ] Catalogs
- [x] Collections
- [x] Item Properties (incl. Summaries in Collections)
- [x] Assets (for both Collections and Items, incl. Item Asset Definitions in Collections and Asset Templates)
- [ ] Links (incl. Link Templates)
- [ ] Bands

| Field Name        | Type   | Description                                                              |
| ----------------- | ------ | ------------------------------------------------------------------------ |
| vpp:season        | string | The VPP season number. One of `S1` or `S2`. See below for details.       |
| vpp:sub_parameter | string | The VPP sub-parameter acronym. See below for the list of allowed values. |

### Additional Field Information

#### vpp:season

The Vegetation Phenology and Productivity (VPP) season number. Two seasons can be detected per year.

| Value | Description    |
| ----- | -------------- |
| `S1`  | First season.  |
| `S2`  | Second season. |

#### vpp:sub_parameter

The Vegetation Phenology and Productivity (VPP) sub-parameter acronym.

| Value    | Description                                   |
| -------- | --------------------------------------------- |
| `AMPL`   | Season amplitude                              |
| `EOSD`   | Day of end-of-season                          |
| `EOSV`   | Vegetation index value at end-of-season       |
| `LENGTH` | Length of season                              |
| `LSLOPE` | Slope of the greening up period               |
| `MAXD`   | Day of maximum value in season                |
| `MAXV`   | Maximum value of the season                   |
| `MINV`   | Minimum value of the season                   |
| `QA`     | Quality assurance / quality flag              |
| `RSLOPE` | Slope of the senescent period                 |
| `SOSD`   | Day of start-of-season                        |
| `SOSV`   | Vegetation index value at start-of-season     |
| `SPROD`  | Seasonal productivity                         |
| `TPROD`  | Total productivity                            |

## Contributing

All contributions are subject to the
[STAC Specification Code of Conduct](https://github.com/radiantearth/stac-spec/blob/master/CODE_OF_CONDUCT.md).
For contributions, please follow the
[STAC specification contributing guide](https://github.com/radiantearth/stac-spec/blob/master/CONTRIBUTING.md) Instructions
for running tests are copied here for convenience.

### Running tests

The same checks that run as checks on PRs are part of the repository and can be run locally to verify that changes are valid.
To run tests locally, you'll need `npm`, which is a standard part of any [node.js installation](https://nodejs.org/en/download/).

First you'll need to install everything with npm once. Just navigate to the root of this repository and on
your command line run:

```bash
npm install
```

Then to check markdown formatting and test the examples against the JSON schema, you can run:

```bash
npm test
```

This will spit out the same texts that you see online, and you can then go and fix your markdown or examples.

If the tests reveal formatting problems with the examples, you can fix them with:

```bash
npm run format-examples
```
