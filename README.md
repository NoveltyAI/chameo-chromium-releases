# Chameo Chromium downloads

Official Windows x64 kernel packages for Chameo, maintained by NoveltyAI.

Current release: [156.0.8078.79-chameo.2](https://github.com/NoveltyAI/chameo-chromium-releases/releases/tag/156.0.8078.79-chameo.2), **282.2 MB as 7z**, 21.65% smaller than the retained 360.2 MB ZIP. All 357 extracted files are identical across formats. The native kernel passes 42 browser cases and desktop font/location/UI/GPU checks.

Download packages from [Releases](https://github.com/NoveltyAI/chameo-chromium-releases/releases). Updated Chameo clients prefer 7z and extract it internally; no separate 7-Zip installation is required. Older clients can keep using ZIP. Chameo verifies the GitHub asset SHA-256 before extraction. GitHub sign-in is not required.

The original `manifest.json` and `SHA256SUMS` describe the unchanged ZIP. `manifest-7z.json` lists both formats, `SHA256SUMS-7z` checks the 7z, and `packaging-7z.json` records the complete payload comparison. 7z SHA-256: `be5b544180ce837be5e4db8d9c2a1874b85a029b549ca50e3b4262fb510fa73d`.

The updated client passed real anonymous 7z download, SHA-256 verification, installation, fingerprint rotation and desktop/profile relaunch on Azure. Its Rust decoder also independently matched all 357 files against the original ZIP.

The kernel is based on ungoogled-chromium with Chameo's versioned native fingerprint configuration. This repository distributes binaries; the maintained kernel source lives in the separate access-controlled `NoveltyAI/chameo-chromium` repository.

## Portable package

Both formats contain the browser, production runtime dependencies, all supported UI languages, managed fonts and third-party notices. Font resources are compressed losslessly and restored to their original bytes by Chromium. Debug/validation helper binaries, installers and PWA launch helpers are omitted. Browser DevTools and the native fingerprint control protocol remain available. Installed size is unchanged by the switch to 7z.

Extract the complete package together. Chameo's kernel manager handles download, integrity verification, extraction and profile launching. Keep the included license and notice files when redistributing.

## Fingerprint configuration

Supported core settings cover WebRTC, timezone, geolocation, language, UI language, resolution, fonts, device pixel ratio, hardware noise, WebGL metadata, WebGPU, CPU, RAM, device name, MAC metadata, Do Not Track, hardware acceleration, TLS feature suppression and port-scan protection.

Runtime fingerprint changes apply to subsequently created tabs and their frames/workers; existing documents retain their identity. UI language, graphics startup policy, TLS and port policy require a browser restart. Device name and MAC are profile metadata, not changes to host hardware. Battery, keyboard capability emulation and speech playback are outside this release scope.

The attached manifest identifies the Chromium version, private source commit, native schema versions, platform and archive checksum. Release notes describe the validation performed for each package.

## Licenses

Each package includes Chameo's BSD 3-Clause license, the ungoogled-chromium license, Chromium's generated third-party notices, font licenses and applicable dependency notices. Those individual licenses govern the distributed components.
