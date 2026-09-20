### dhtfish988

iOS/macOS binary analysis and ARM64 reverse engineering. I write and maintain my own
tooling for it, and I keep these repositories in the open so the code can be read and
re-run rather than taken on trust.

Each repository below states what it has and has not been verified against —
including the one that is mostly other people's code.

---

#### [SharedSourceKits](https://github.com/dhtfish988/SharedSourceKits)

An iOS kernel research library, and mostly integration work rather than original
research: the exploit implementations come from
[kfd](https://github.com/felix-pb/kfd), and the wrappers and helpers from
[Dopamine](https://github.com/opa334/Dopamine), XPF, Choma and libgrabkernel2, with
their notices kept in
[THIRD_PARTY_NOTICES.md](https://github.com/dhtfish988/SharedSourceKits/blob/main/THIRD_PARTY_NOTICES.md).
Build-verified only — it has never been run on a device here, and the README says so.
For research on hardware you own.

#### [machoaudit](https://github.com/dhtfish988/machoaudit)

Structural auditor for Mach-O code signatures, entitlements and load-command
hardening. It reports what a binary is permitted to do — for the binary, for a bundle
and for the bundle's resource seal — and deliberately does not replace `codesign`,
which is the tool that verifies the cryptography. Parses with the standard library
only; the rule engine is exercised by 123 tests, and the parsers are cross-checked
field by field against `codesign -d -vvv` over a system corpus by
`tools/verify_against_codesign.py`. MIT, Python.

#### [deflat64](https://github.com/dhtfish988/deflat64)

Target-agnostic ARM64 control-flow-flattening and VM-dispatch devirtualizer for IDA
Pro. Continues [unflatten64](https://github.com/DumpA1n/unflatten64) by DumpA1n
(MIT), who handed the project over; the analysis core, the methodology and the safety
model are his work — see [CHANGELOG.md](https://github.com/dhtfish988/deflat64/blob/main/CHANGELOG.md).
The pure-Python layers are tested (84 cases, no IDA needed); the IDA-dependent phase
layer is written but has not been validated against a live IDA, which
[IMPLEMENTATION_STATUS.md](https://github.com/dhtfish988/deflat64/blob/main/IMPLEMENTATION_STATUS.md)
tracks honestly.

#### [UltimateBrowserJS](https://github.com/dhtfish988/UltimateBrowserJS)

MCP server that drives an existing Chrome over the DevTools Protocol, so an assistant
works in your own browser profile instead of a fresh one. 75 tools covering
navigation, forms, frames, tabs, storage, screenshots and assertions. It installs
fingerprint-masking script into pages, which is the part that deserves care, so the
README documents it and states what the tool is for — automating sites you own or are
authorised to automate. MIT, Node.

#### [CDTranslator](https://github.com/dhtfish988/CDTranslator)

A small macOS menu-bar app: translation as you type, and OCR on a pasted screenshot
through Apple's Vision framework. SwiftUI, no API key, no configuration. The privacy
policy is published at
[dhtfish988.github.io/CDTranslator](https://dhtfish988.github.io/CDTranslator/).

---

Four of these are my own tooling; SharedSourceKits is upstream code I integrate, and
it says so above. Questions and bug reports are welcome through each repository's
issues.
