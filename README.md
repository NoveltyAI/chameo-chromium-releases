# Chameo Chromium downloads

Official Windows x64 kernel packages for Chameo, maintained by NoveltyAI.

Download ZIP packages from [Releases](https://github.com/NoveltyAI/chameo-chromium-releases/releases). Each release includes `manifest.json` and `SHA256SUMS`. Chameo discovers these releases and verifies the ZIP SHA-256 before installing it. GitHub sign-in is not required to download public assets.

The kernel is based on ungoogled-chromium with Chameo's versioned native fingerprint configuration. This repository distributes binaries; the maintained kernel source lives in the separate access-controlled `NoveltyAI/chameo-chromium` repository.

## Portable package

The ZIP contains the browser, production runtime dependencies, all supported UI languages, managed fonts and third-party notices. Font resources are compressed losslessly and restored to their original bytes by Chromium. Developer tools, installers and PWA launch helpers are omitted.

Extract the complete ZIP together. Chameo's kernel manager handles download, integrity verification, extraction and profile launching. Keep the included license and notice files when redistributing.

## Fingerprint configuration

Supported core settings cover WebRTC, timezone, geolocation, language, UI language, resolution, fonts, device pixel ratio, hardware noise, WebGL metadata, WebGPU, CPU, RAM, device name, MAC metadata, Do Not Track, hardware acceleration, TLS feature suppression and port-scan protection.

Runtime fingerprint changes apply to subsequently created tabs and their frames/workers; existing documents retain their identity. UI language, graphics startup policy, TLS and port policy require a browser restart. Device name and MAC are profile metadata, not changes to host hardware. Battery, keyboard capability emulation and speech playback are outside this release scope.

The attached manifest identifies the Chromium version, private source commit, native schema versions, platform and archive checksum. Release notes describe the validation performed for each package.

## Licenses

Each ZIP includes Chameo's BSD 3-Clause license, the ungoogled-chromium license, Chromium's generated third-party notices, font licenses and applicable dependency notices. Those individual licenses govern the distributed components.
