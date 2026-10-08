# NUBARBASE

NUBARBASE is a database of neutron-induced fission data associated with the average number of neutrons emitted per fission (nu-bar, \(\bar{\nu}\)), for use in the [AUTOTALYS](https://github.com/arjankoning1/autotalys) nuclear-data evaluation and processing system.

The repository contains nuclide-specific data and calculation files rather than a standalone executable. Its organization follows the same general pattern as [RESBASE](https://github.com/arjankoning1/resbase).

## Repository structure

The top-level directories are named after nuclides, such as `U235`, `Pu239`, and `Am241`. Isomeric states have a suffix `m` where applicable.

For example, the repository currently contains:

```text
nubarbase/
└── U235/
    ├── input/
    │   ├── tafis.inp
    │   └── tafis.out
    ├── files/
    │   ├── n-U235.mf31
    │   ├── n-U235.mt452
    │   ├── n-U235.mt455
    │   └── n-U235.mt458
    └── random/
        ├── n-U235.mt452.0000
        ├── n-U235.mt452.0001
        └── ...
```

The availability and contents of files may differ between nuclides.

- **`input/`** stores input and output from nuclide-specific calculations, including `tafis.inp` and `tafis.out` in the example.
- **`files/`** stores data components organized by ENDF file and reaction identifiers. In the U-235 example, MT 452 corresponds to total average neutron multiplicity, MT 455 to delayed-neutron multiplicity, MT 458 to fission energy-release information, and MF 31 to neutron-multiplicity covariance information.
- **`random/`** stores numbered sampled or randomized data variants, such as `n-U235.mt452.0000`. Their precise interpretation depends on the generating workflow.

## Obtaining the database

Clone NUBARBASE with Git:

```bash
git clone https://github.com/arjankoning1/nubarbase.git
```

To update an existing clone:

```bash
cd nubarbase
git pull
```

Alternatively, download a source archive from the repository's GitHub page.

## Use with AUTOTALYS

NUBARBASE is intended as a nuclide-specific fission-data resource for the wider AUTOTALYS workflow. Its installation location can be selected to match the organization expected by the AUTOTALYS installation and processing scripts; it does not have to reside in the user's home directory.

The repository contains data, not its own general-purpose installation program. Consult the AUTOTALYS scripts for integration details.

## Data provenance and updates

Evaluated neutron-multiplicity data, fission quantities, and covariance information depend on the underlying evaluation and its version. When modifying or using these data, retain source attribution and record any changes to the evaluation, parameterization, or uncertainty treatment.

## Related repositories

- [AUTOTALYS](https://github.com/arjankoning1/autotalys) — setup and orchestration of the nuclear-data processing system
- [RESBASE](https://github.com/arjankoning1/resbase) — resonance-parameter data
- [TALYS](https://github.com/arjankoning1/talys) — nuclear reaction modelling
- [TEFAL](https://github.com/arjankoning1/tefal) — evaluated nuclear-data file processing
- [TASMAN](https://github.com/arjankoning1/tasman) — sensitivity and covariance analysis

## License

See the repository's `LICENSE` file for its applicable license. If the database is released under CC BY 4.0, users must provide appropriate attribution and indicate changes.

## Author

Arjan Koning
