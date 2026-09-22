### dhtfish988

iOS/macOS binary analysis and ARM64 reverse engineering. I maintain the projects
below, including original tools, work based on upstream code and integration work.
Their READMEs and verification notes describe the sources, changes and testing.

---

#### [SharedSourceKits](https://github.com/dhtfish988/SharedSourceKits)

An iOS kernel research library. My work here is integration and maintenance of
upstream components: the exploit implementations come from
[kfd](https://github.com/felix-pb/kfd), and the wrappers and helpers from
[Dopamine](https://github.com/opa334/Dopamine), XPF, Choma and libgrabkernel2, with
their notices kept in
[THIRD_PARTY_NOTICES.md](https://github.com/dhtfish988/SharedSourceKits/blob/main/THIRD_PARTY_NOTICES.md).
The repository records build checks, but no on-device validation. Intended for
research on hardware you own or are authorised to test.

#### [machoaudit](https://github.com/dhtfish988/machoaudit)

A Python tool I maintain for inspecting Mach-O signing structures, entitlements,
hardening settings and bundle resource seals. It reports structural findings; it
does not verify the cryptographic signature or replace `codesign`. Unit tests and
comparisons with `codesign` are documented in
[VERIFICATION.md](https://github.com/dhtfish988/machoaudit/blob/main/docs/VERIFICATION.md).

#### [deflat64](https://github.com/dhtfish988/deflat64)

Experimental ARM64 control-flow-flattening and VM-dispatch analysis tooling for
IDA Pro. My maintenance includes CLI restructuring, expanded pure-Python tests,
CI and documentation. Code provenance and changes are recorded in
[CHANGELOG.md](https://github.com/dhtfish988/deflat64/blob/main/CHANGELOG.md).
The pure-Python layers have unit tests; the full IDA pipeline has not been validated
in a live session. See
[VERIFICATION.md](https://github.com/dhtfish988/deflat64/blob/main/docs/VERIFICATION.md).

#### [UltimateBrowserJS](https://github.com/dhtfish988/UltimateBrowserJS)

A Node.js MCP server I maintain for automating an existing Chrome session through
the DevTools Protocol. It supports navigation, forms, frames, tabs, storage,
screenshots and assertions, and includes fingerprint-masking scripts as described
in its README. Intended for sites you own or are authorised to automate.

#### [CDTranslator](https://github.com/dhtfish988/CDTranslator)

A small macOS menu-bar app: translation as you type, and OCR on a pasted screenshot
through Apple's Vision framework. SwiftUI, no API key, no configuration. The privacy
policy is published at
[dhtfish988.github.io/CDTranslator](https://dhtfish988.github.io/CDTranslator/).

---

Questions and bug reports are welcome through each repository's issues. Upstream
authors and licenses are credited in the relevant repositories.
