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
