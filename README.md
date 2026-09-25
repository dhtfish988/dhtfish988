### dhtfish988

Public tools for Mach-O signing inspection, AArch64 dispatch analysis, and a
Chrome DevTools bridge. Each README says what was tested and what was not.

---

#### [MachOInspect](https://github.com/dhtfish988/MachOInspect)

A C++20 library and command-line tool. It reads Mach-O signing metadata, declared
entitlements, hardening settings and resource seals. It does not authenticate CMS
signatures, validate a certificate chain, or decide which permissions the operating
system grants. Use `codesign -v` for signature verification; that result does not
establish which permissions the operating system actually granted. The macOS validation notes are in
[docs/VERIFICATION.md](https://github.com/dhtfish988/MachOInspect/blob/main/docs/VERIFICATION.md).

#### [A64Dispatch](https://github.com/dhtfish988/A64Dispatch)

A C++20 library and command-line tool for AArch64 dispatch analysis and same-size
branch rewriting, with a thin IDA adapter. The baseline is deflat64, which is based
on DumpA1n's unflatten64. Finite examples do not show that a rewrite matches every
input. IDA 9.4 checks on one owned fixture are recorded in the repository. Linux
and Windows have not been run.

#### [ChromeRelay](https://github.com/dhtfish988/ChromeRelay)

A C++20 bridge from MCP to an existing Chrome over the DevTools Protocol. It has
54 canonical actions and 75 legacy names. The recorded browser tests used temporary
profiles on macOS. They do not cover arbitrary pages. The tool does not install a
fingerprint-masking script.

#### [CDTranslator](https://github.com/dhtfish988/CDTranslator)

A small macOS desktop app: translation as you type, and local OCR on a pasted
screenshot through Apple's Vision framework. Text, including OCR results, is sent
to Google for translation. SwiftUI, no API key. The privacy
policy is published at
[dhtfish988.github.io/CDTranslator](https://dhtfish988.github.io/CDTranslator/).

---

Questions and bug reports go through each repository's issues. Upstream authors
and licenses are credited in the repositories.
