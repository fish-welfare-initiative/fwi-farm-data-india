# FWI Farm Data — India (June 2021 – August 2026)

Public dataset from the **Alliance for Responsible Aquaculture (ARA)** program operated by
[Fish Welfare Initiative](https://www.fishwelfareinitiative.org/) in India.

## About the Program

The ARA program works with fish farmers in India to improve fish welfare through water quality
monitoring and management. Field staff conduct regular visits to measure water quality parameters
and recommend corrective actions when measurements fall outside acceptable ranges.

**Regions covered:** Eluru and Nellore districts, Andhra Pradesh, India

**Program period:** June 2021 – August 2026 (ongoing)

## Datasets

| File | Records | Description |
|------|---------|-------------|
| [`water_quality.csv`](data/water_quality.csv) | 13,567 | Water quality measurements collected during farm visits |
| [`enrolled_ponds.csv`](data/enrolled_ponds.csv) | 324 | Ponds enrolled in the program |
| [`stocking_harvest.csv`](data/stocking_harvest.csv) | 1,699 | Stocking and harvest events |
| [`dropouts.csv`](data/dropouts.csv) | 128 | Ponds that left the program |

Covering 323 ponds — 260 in Eluru, 63 in Nellore.

**Note:** "Enrolled ponds" refers to ponds participating in the ARA program, regardless of whether
they currently have fish stocked. This differs from "active ponds", which would only include ponds
with fish currently in them.

See [`docs/data_dictionary.md`](docs/data_dictionary.md) for column definitions, changes in this
version, and known data issues.

## Privacy

This data has been anonymised to protect farmer privacy:

- **Pond IDs are randomly generated.** They are not derived from any farm attribute, so they cannot
  be reversed. The mapping between published IDs and real ponds exists only in a private key that is
  not part of this repository and is not derivable from anything in it.
- **Excluded:** farmer names, GPS coordinates, village names, and financial figures. Financial
  figures were also recorded in free-text notes; those notes were removed in full. Where this
  removed the only record of a harvest weight, the weight is absent rather than zero — see the
  data dictionary.
- **Fish source generalised** to categories rather than named suppliers, since a specific local
  supplier can act as a fingerprint for an individual farm.
- **Free-text notes reviewed** for names and identifying references.

FWI staff names are retained in `Observer`, `Added by` and `Logged by`.

> **Pond identifiers use the `ara2_` prefix from v3.0.0 onward.** Earlier releases used `pond_`.
> Identifiers are not comparable across releases, and the distinct prefix means a cross-release
> join fails visibly rather than matching partially in silence. Researchers reconciling work built
> on an earlier release should contact us.

## License

Released under [CC-BY-4.0](LICENSE). You are free to share and adapt this data for any purpose,
provided you give appropriate credit.

## Citation

```
Fish Welfare Initiative. (2026). FWI Farm Data — India (June 2021 – August 2026).
https://github.com/fish-welfare-initiative/fwi-farm-data-india
```

## Contact

Questions about this data: [fwi.fish/contact](https://fwi.fish/contact)

## Related Links

- [Fish Welfare Initiative](https://www.fishwelfareinitiative.org/)
- [ARA Program Overview](https://www.fishwelfareinitiative.org/ara)
- [ARA Data Dashboard](https://data.fishwelfareinitiative.org/ara)
