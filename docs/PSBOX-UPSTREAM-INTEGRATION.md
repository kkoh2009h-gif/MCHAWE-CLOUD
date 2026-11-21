# PSBox upstream integration record

This file records the reviewed upstream revision for the MCHAWE CLOUD integration.

- Upstream repository: https://github.com/RafaelNGP/psbox-cloud-gaming
- Reviewed upstream commit: `40c61da5fc9720e5078b0d1473931864488aa1b1`
- Reviewed date: 2026-11-22
- Upstream license: GPL-3.0-or-later (retain notices and provide source/derivative compliance as required)
- PS4 platform support is present upstream; the PS4 build uses OpenOrbis.

## PS4 build path documented upstream

```sh
git clone --recursive https://github.com/RafaelNGP/psbox-cloud-gaming.git
cd psbox-cloud-gaming
tools/ps4/fetch-toolchain.sh
cmake -S . -B build-ps4 -G Ninja -DCMAKE_TOOLCHAIN_FILE=cmake/ps4.toolchain.cmake
ninja -C build-ps4
tools/ps4/package.sh build-ps4
```

## Integration state

- The upstream engine is NOT vendored or forked into this repository yet.
- No MCHAWE-branded PKG has been built or tested.
- The web `index.html` remains a UI prototype and is not a cloud-streaming client.
- The next technical step is to import/fork the upstream source with its license notices intact, then make a minimal branding change and run the PS4 packaging workflow.

Do not label the project as installable until a PKG artifact exists and has been verified.


## MCHAWE CI baseline workflow

The repository contains a manually triggered workflow at `.github/workflows/build-psbox-baseline.yml`. It checks out the pinned upstream revision with recursive submodules, installs Linux build packages plus .NET 8, fetches OpenOrbis, configures Release, builds, packages, and uploads the PKG artifact for seven days.


### How to start it

1. Open the repository's **Actions** tab.
2. Select **Build PSBox PS4 baseline**.
3. Press **Run workflow** and confirm the main branch.
4. Wait for the run. If it fails, open the failed step and capture its log; the workflow has not been verified until a successful run and artifact are visible.
5. On success, open the run's **Artifacts** section and download `psbox-ps4-baseline-pkg`.

This workflow builds upstream PSBox unchanged; it does not yet produce a MCHAWE-branded client.
