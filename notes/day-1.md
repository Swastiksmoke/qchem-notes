# Day 1: First PySCF calculation

I used PySCF in the `qc` environment to run a restricted Hartree–Fock calculation on H₂.

- Geometry: H–H bond length of 0.74 Å
- Basis set: STO-3G
- Result: energy about −1.117 Hartree
- The calculation converged successfully.

This was a setup check. The energy depends on the geometry and basis set, so it is not a highly accurate final result.

## ORCA setup check

ORCA 6.1.1 completed an HF/def2-SVP single-point calculation on H2O.
The output ended with “ORCA TERMINATED NORMALLY”.

## GitHub sign-in setup

Configured Git Credential Manager to use Linux Mint’s Secret Service keyring.
Signed in through the browser and confirmed that `git push` works without
re-entering credentials. The fine-grained token used during setup was revoked;
no token is stored in this repository.