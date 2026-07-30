---
title: Forthcoming changes
type: releaseNotes
date: 2099-01-01
---

# Simplification of UniParc XML Root Tag (Effective Release 2026_04)

We are simplifying the root tag of UniParc XML output by removing the `xmlns:xsi`, `xsi:schemaLocation` and `checkpoint` attributes.

Before:
```xml
<uniparc xmlns="http://uniprot.org/uniparc" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="https://ftp.uniprot.org/pub/databases/uniprot/current_release/uniparc/uniparc.xsd" checkpoint="23739">
```

After:
```xml
<uniparc xmlns="http://uniprot.org/uniparc">
```

**Why:** Newer XML parsers are adopting a stricter "strip mode" that rejects namespaced attribute names like `xmlns:xsi` inside the root tag, throwing `Illegal name character ':'`. These parsers treat the attribute as a plain tag name rather than a namespace declaration, so the colon breaks parsing. Removing the unused namespace declaration and schema location avoids this incompatibility.

**Impact:** Any code that parses the root tag and expects `xsi:schemaLocation` or `checkpoint` to be present should be updated to not rely on them.