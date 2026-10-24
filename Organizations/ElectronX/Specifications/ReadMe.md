# ElectronX FIX Specifications

ElectronX's FIX specification covers both Order Entry and Market Data using FIX 5.0 SP2.

| Document edition | Specification | Source |
| --- | --- | --- |
| October 15, 2026 (`20261015.1`) | [Order Entry and Market Data](Documentation/ElectronX.Fix.v20261015.1.pdf) | [ElectronX release announcement](https://www.electronx.com/platform-updates/fix-updates-oct-15-2026) |
| April 23, 2026 (`20260423.1`) | [Combined archive](Documentation/ElectronX.Fix.v4.0.pdf), [Market Data archive](ElectronX/MarketData/ElectronX.ElectricDerivatives.MarketData.Fix.v4.0.pdf), [Order Entry archive](ElectronX/OrderEntry/ElectronX.ElectricDerivatives.OrderEntry.Fix.v4.0.pdf) | Existing OMI archive |

The October edition is an unmodified copy of the [PDF published by ElectronX](https://cdn.sanity.io/files/bpyvas7v/production/3b666536107711c3837e32c0ffb538c7b676e75f.pdf). It contains 59 pages and has SHA-256:

```text
1ecc0414d905dc58075b46a73335673cb659d69b6e5d5f47998c821ab6aa309a
```

The April files are preserved at their existing paths. Their `v4.0` filenames are OMI archive labels; the protocol described in the documents is FIX 5.0 SP2. Adding the October document does not update the separately maintained FIX dictionaries or XML specifications.
